---
title: Windows フォーム アプリを .NET 5 に移行する
description: .NET Framework Windows フォーム アプリケーションを .NET 5 に移植する方法について学習します。
ms.date: 11/02/2020
ms.topic: how-to
ms.openlocfilehash: 105c209fc567d2cce70b01267f793152d8140cb8
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/09/2020
ms.locfileid: "96992860"
---
# <a name="how-to-migrate-a-windows-forms-desktop-app-to-net-5"></a>Windows フォーム デスクトップ アプリを .NET 5 に移行する方法

この記事では、Windows Forms デスクトップ アプリを、.NET Framework から .NET 5 以上に移行する方法について説明します。 .NET SDK には、Windows フォーム アプリケーションのサポートが含まれています。 Windows Forms は、まだ Windows 専用のフレームワークであるため、Windows 上でのみ実行されます。

.NET Framework から .NET 5 にアプリを移行するには、通常、新しいプロジェクト ファイルが必要です。 .NET 5 では SDK スタイルのプロジェクト ファイルが使用されますが、.NET Framework では通常、古い Visual Studio プロジェクト ファイルが使用されます。 テキスト エディターで Visual Studio プロジェクト ファイルを開いたことがある場合は、それがどの程度詳細であるかはご存じでしょう。 SDK スタイルのプロジェクトはより小さく、古いプロジェクト ファイル形式の場合と同じ数のエントリは必要ありません。

.NET 5 の詳細については、「[.NET の概要](/dotnet/core/introduction)」を参照してください。

## <a name="prerequisites"></a>前提条件

- [Visual Studio 2019 バージョン 16.8 Preview](https://visualstudio.microsoft.com/downloads/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=inline+link&utm_content=download+vs2019+desktopguide+winforms)

  - [Visual Studio デスクトップ ワークロード](/visualstudio/install/modify-visual-studio?view=vs-2019&preserve-view=true#modify-workloads)を選択します。

  - [.NET 5 の個別のコンポーネント](/visualstudio/install/modify-visual-studio?view=vs-2019&preserve-view=true#modify-individual-components)を選択します。

- Visual Studio のプレビュー版 WinForms デザイナー。

  デザイナーを有効にするには、 **[ツール]**  >  **[オプション]**  >  **[環境]**  >  **[プレビュー機能]** に移動し、 **[Use the preview Windows Forms designer for .NET Core apps]\(プレビュー版 Windows フォーム デザイナー (.NET Core アプリ) を使用する\)** オプションを選択します。

- この記事では、[絵合わせゲーム](https://github.com/dotnet/samples/tree/master/windowsforms/matching-game/net45/)のサンプル アプリを使用します。 これに従う場合は、アプリケーションをダウンロードして Visual Studio で開きます。 それ以外の場合は、独自のアプリを使用します。

### <a name="consider"></a>次の例を考えてみましょう

.NET Framework Windows フォーム アプリケーションを移行するときに、考慮する必要がある点がいくつかあります。

01. アプリケーションが移行に適した候補であることを確認する。

    [.NET Portability Analyzer](/dotnet/standard/analyzers/portability-analyzer) を使用して、プロジェクトで .NET 5 に移行するかどうかを判断します。 プロジェクトに .NET 5 に関する問題がある場合は、これらの問題を特定するのにアナライザーが役立ちます。 .NET Portability Analyzer ツールは、Visual Studio の拡張機能としてインストールすることも、コマンド ラインから使用することもできます。 詳細については、[.NET Portability Analyzer](/dotnet/standard/analyzers/portability-analyzer) に関するページをご覧ください。

01. Windows Forms の別のバージョンを使用している。

    .NET Core 3.0 がリリースされたときに、Windows フォームは [GitHub でオープン ソース](https://github.com/dotnet/winforms)になりました。 .NET 5 用の Windows フォームのコードは、.NET Framework Windows フォーム コード ベースからの 1 つの分岐です。 いくつか違いがあるため、アプリの移行が困難になる可能性があります。

01. [Windows 互換機能パック][compat-pack]が移行に役立つ可能性がある。

    .NET Framework で利用できる一部の API は、.NET 5 では利用できません。 [Windows 互換機能パック][compat-pack]を使用すると、これらの API の多くが追加され、Windows Forms アプリに .NET 5 との互換性を持たせるのに役立つ場合があります。

01. 自分のプロジェクトで使用されている NuGet パッケージを更新する。

    移行する前に、常に NuGet パッケージの最新バージョンを使用することをお勧めします。 アプリケーションで NuGet パッケージを参照している場合は、最新バージョンに更新してください。 アプリケーションが正常にビルドされることを確認します。 アップグレード後にパッケージ エラーが発生した場合は、コードを壊さない最新のバージョンにパッケージをダウングレードします。

## <a name="back-up-your-projects"></a>プロジェクトをバックアップする

プロジェクトを移行するための最初の手順は、プロジェクトをバックアップすることです。 問題が発生した場合は、バックアップを復元することでコードを元の状態に復元できます。 プロジェクトをバックアップする際に、.NET Portability Analyzer などのツールには頼らないでください (そうするように思われても)。 元のプロジェクトのコピーを個人的に作成することをお勧めします。

## <a name="nuget-packages"></a>NuGet パッケージ

プロジェクトで NuGet パッケージが参照されている場合、プロジェクト フォルダー内に **packages.config** ファイルがある可能性があります。 SDK スタイルのプロジェクトの場合、NuGet パッケージ参照はプロジェクト ファイルで構成されます。 Visual Studio プロジェクト ファイルでは、必要に応じて、そのプロジェクト ファイルで NuGet パッケージを定義することもできます。 .NET 5 では、NuGet パッケージに対して **packages.config** は使用されません。 移行の前に、NuGet パッケージ参照をプロジェクト ファイルに移行する必要があります。

**packages.config** ファイルを移行するには、次の手順を行います。

01. **ソリューション エクスプローラー** で、移行するプロジェクトを見つけます。
02. 右クリックで **[packages.config]**  >  **[packages.config を PackageReference に移行する]** の順に進みます。
03. 最上位のパッケージをすべて選択します。

ビルド レポートは、NuGet パッケージの移行に関する問題を通知するために生成されます。

## <a name="project-file"></a>プロジェクト ファイル

アプリを移行する次の手順では、プロジェクト ファイルを変換します。 前述のように、.NET 5 では SDK スタイルのプロジェクト ファイルが使用され、.NET Framework で使用される Visual Studio プロジェクト ファイルは読み込まれません。 しかし、SDK スタイルのプロジェクトを既に使用している可能性があります。 Visual Studio でその違いを簡単に見つけることができます。 **ソリューション エクスプローラー** でプロジェクト ファイルを右クリックし、 **[プロジェクト ファイルの編集]** メニューオプションを探します。 このメニュー項目が欠落している場合は、古い Visual Studio プロジェクト形式を使用しているため、アップグレードする必要があります。

ソリューション内の各プロジェクトを変換します。 以前に参照されたサンプル アプリを使用する場合、**MatchingGame** と **MatchingGame.Logic** プロジェクトの両方が変換されます。

プロジェクトを変換するには、次の手順を行います。

01. **ソリューション エクスプローラー** で、移行するプロジェクトを見つけます。
01. プロジェクトを右クリックし、 **[プロジェクトのアンロード]** を選択します。
01. プロジェクトを右クリックし、 **[プロジェクト ファイルの編集]** を選択します。
01. プロジェクトの XML をコピーし、テキスト エディターに貼り付けます。 新しいプロジェクトに内容を簡単に移動できるようにコピーが必要になります。
01. ファイルの内容を消去し、次の XML を貼り付けます。

    ```xml
    <Project Sdk="Microsoft.NET.Sdk">

      <PropertyGroup>
        <OutputType>WinExe</OutputType>
        <TargetFramework>net5.0-windows</TargetFramework>
        <UseWindowsForms>true</UseWindowsForms>
        <GenerateAssemblyInfo>false</GenerateAssemblyInfo>
      </PropertyGroup>

    </Project>
    ```

    > [!IMPORTANT]
    > ライブラリで `<OutputType>` 設定を定義する必要はありません。 ライブラリ プロジェクトをアップグレードする場合は、そのエントリを削除します。

この XML により、プロジェクトの基本構造が提供されます。 しかし、古いプロジェクト ファイルのどの設定も含まれていません。 以前にテキスト エディターにコピーした古いプロジェクト情報を使用して、次の手順を行います。

01. 古いプロジェクト ファイルの次の要素を、新しいプロジェクト ファイルの `<PropertyGroup>` 要素にコピーします。

    - `<RootNamespace>`
    - `<AssemblyName>`

    プロジェクト ファイルは次の XML のようになるはずです。

    ```xml
    <Project Sdk="Microsoft.NET.Sdk">

      <PropertyGroup>
        <OutputType>WinExe</OutputType>
        <TargetFramework>net5.0-windows</TargetFramework>
        <UseWindowsForms>true</UseWindowsForms>
        <GenerateAssemblyInfo>false</GenerateAssemblyInfo>

        <RootNamespace>MatchingGame</RootNamespace>
        <AssemblyName>MatchingGame</AssemblyName>
      </PropertyGroup>

    </Project>
    ```

01. `<ProjectReference>` または `<PackageReference>` を含む古いプロジェクト ファイルの `<ItemGroup>` 要素を、`</PropertyGroup>` 終了タグの後の新しいファイルにコピーします。

    プロジェクト ファイルは次の XML のようになるはずです。

    ```xml
    <Project Sdk="Microsoft.NET.Sdk">

      <PropertyGroup>
        (contains settings previously described)
      </PropertyGroup>

      <ItemGroup>
        <ProjectReference Include="..\MatchingGame.Logic\MatchingGame.Logic.csproj">
          <Project>{36b3e6e2-a9ae-4924-89ae-7f0120ce08bd}</Project>
          <Name>MatchingGame.Logic</Name>
        </ProjectReference>
      </ItemGroup>
      <ItemGroup>
        <PackageReference Include="MetroFramework">
          <Version>1.2.0.3</Version>
        </PackageReference>
      </ItemGroup>

    </Project>
    ```

    `<ProjectReference>` 要素には子の `<Project>` と `<Name>` は必要でないため、これらの設定は削除できます。

    ```xml
    <ItemGroup>
      <ProjectReference Include="..\MatchingGame.Logic\MatchingGame.Logic.csproj" />
    </ItemGroup>
    ```

### <a name="resources-and-settings"></a>リソースと設定

.NET Framework 用の Windows フォーム プロジェクトには通常、*Properties/Settings.settings* や *Properties/Resources.resx* などの他のファイルが含まれています。 これらのファイルと、*resx* 形式のファイル以外のアプリ用に作成されたすべての *resx* ファイルは、移行する必要があります。

これらのエントリを古いプロジェクト ファイルから、新しいプロジェクトの `<ItemGroup>` 要素にコピーします。 エントリをコピーした後、`<Compile Include="value">` または `<EmbeddedResource Include="value">` 要素は、`Include` ではなく代わりに `Update` を使用するように変更します。

- *Settings.settings* ファイルの構成をインポートします。 `Include` が `<Compile>` 要素で `Update` に変更されたことに注目してください。

  ```xml
  <ItemGroup>
    <None Include="Properties\Settings.settings">
      <Generator>SettingsSingleFileGenerator</Generator>
      <LastGenOutput>Settings.Designer.cs</LastGenOutput>
    </None>
    <Compile Update="Properties\Settings.Designer.cs">
      <AutoGen>True</AutoGen>
      <DependentUpon>Settings.settings</DependentUpon>
      <DesignTimeSharedInput>True</DesignTimeSharedInput>
    </Compile>
  </ItemGroup>
  ```

  > [!IMPORTANT]
  > **Visual Basic** プロジェクトの場合、通常は *My Project* フォルダーが使用されますが、C# プロジェクトの場合は通常、既定のプロジェクト設定ファイルには *Properties* フォルダーが使用されます。
  
- *properties/Resources.resx* ファイルなど、*resx* ファイルの構成をインポートします。 `Include` が `<Compile>` と `<EmbeddedResource>` の両方の要素で `Update` に変更され、`<SubType>` が `<EmbeddedResource>` から削除されたことに注目してください。

  ```xml
  <ItemGroup>
    <EmbeddedResource Update="Properties\Resources.resx">
      <Generator>ResXFileCodeGenerator</Generator>
      <LastGenOutput>Resources.Designer.cs</LastGenOutput>
    </EmbeddedResource>
    <Compile Update="Properties\Resources.Designer.cs">
      <AutoGen>True</AutoGen>
      <DependentUpon>Resources.resx</DependentUpon>
      <DesignTime>True</DesignTime>
    </Compile>
  </ItemGroup>
  ```

  > [!IMPORTANT]
  > **Visual Basic** プロジェクトの場合、通常は *My Project* フォルダーが使用されますが、C# プロジェクトの場合は通常、既定のプロジェクト リソース ファイルには *Properties* フォルダーが使用されます。

### <a name="visual-basic"></a>Visual Basic

Visual Basic 言語プロジェクトには追加の構成が必要です。

01. 構成ファイルの *My Project\Application.myapp* 設定をインポートします。 `<None>` および `<Compile>` 要素で、`Include` 属性ではなく `Update` 属性が使用されていることに注目してください。

    ```xml
    <ItemGroup>
      <None Update="My Project\Application.myapp">
        <Generator>MyApplicationCodeGenerator</Generator>
        <LastGenOutput>Application.Designer.vb</LastGenOutput>
      </None>
      <Compile Update="My Project\Application.Designer.vb">
        <AutoGen>True</AutoGen>
        <DependentUpon>Application.myapp</DependentUpon>
        <DesignTime>True</DesignTime>
      </Compile>
    </ItemGroup>
    ```

01. `<PropertyGroup>` 要素に `<MyType>WindowsForms</MyType>` 設定を追加します。

    ```xml
    <PropertyGroup>
      (contains settings previously described)

      <MyType>WindowsForms</MyType>
    </PropertyGroup>
    ```

    この設定により、Visual Basic プログラマーが使い慣れている `My` 名前空間メンバーがインポートされます。

01. プロジェクトで定義されている名前空間をインポートします。

    Visual Basic プロジェクトでは、すべてのコード ファイルに名前空間を自動的にインポートできます。 `<Import>` を含む古いプロジェクト ファイルの `<ItemGroup>` 要素を、`</PropertyGroup>` 終了タグの後の新しいファイルにコピーします。

    ```xml
    <ItemGroup>
      <Import Include="Microsoft.VisualBasic" />
      <Import Include="System" />
      <Import Include="System.Collections" />
      <Import Include="System.Collections.Generic" />
      <Import Include="System.Data" />
      <Import Include="System.Drawing" />
      <Import Include="System.Diagnostics" />
      <Import Include="System.Windows.Forms" />
      <Import Include="System.Linq" />
      <Import Include="System.Xml.Linq" />
      <Import Include="System.Threading.Tasks" />
    </ItemGroup>
    ```

    `<Import>` ステートメントが見つからない場合、またはプロジェクトのコンパイルに失敗した場合は、少なくともプロジェクトで次の `<Import>` ステートメントが定義されていることを確認してください。

    ```xml
    <ItemGroup>
      <Import Include="System.Data" />
      <Import Include="System.Drawing" />
      <Import Include="System.Windows.Forms" />
    </ItemGroup>
    ```

01. 元のプロジェクトから、`<Option*>` と `<StartupObject>` の設定を `<PropertyGroup>` 要素にコピーします。

    ```xml
    <PropertyGroup>
      (contains settings previously described)

      <OptionExplicit>On</OptionExplicit>
      <OptionCompare>Binary</OptionCompare>
      <OptionStrict>Off</OptionStrict>
      <OptionInfer>On</OptionInfer>
      <StartupObject>MatchingGame.My.MyApplication</StartupObject>
    </PropertyGroup>
    ```

### <a name="reload-the-project"></a>プロジェクトを再度読み込む

プロジェクトを新しい SDK スタイルの形式に変換した後、Visual Studio でそのプロジェクトを再度読み込みます。

01. **ソリューション エクスプローラー** で、変換したプロジェクトを見つけます。
01. プロジェクトを右クリックし、 **[プロジェクトの再読み込み]** を選択します。

    プロジェクトの読み込みに失敗した場合は、そのプロジェクトの XML が間違っている可能性があります。 編集のためにプロジェクト ファイルを開き、間違いを特定して修正します。 間違いが見つからない場合は、やり直してみてください。

## <a name="edit-appconfig"></a>App.config を編集する

アプリに *App.config* ファイルがある場合は、`<supportedRuntime>` 要素を削除します。

```xml
<supportedRuntime version="v4.0" sku=".NETFramework,Version=v4.5" />
```

*App.config* ファイルで考慮する必要がある点がいくつかあります。 .NET Framework の *App.config* ファイルは、アプリを構成するだけでなく、ログ記録などのランタイム設定と動作を構成するためにも使用されていました。 .NET 5 以降 (および .NET Core) の *App.config* ファイルは、ランタイム構成に使用されなくなりました。 *App.config* ファイルにこれらのセクションが含まれている場合、それらは考慮されません。

## <a name="add-the-compatibility-package"></a>互換性パッケージを追加する

プロジェクト ファイルが正しく読み込まれていても、プロジェクトのコンパイルに失敗すると、次のようなエラーが表示されます。

- **型または名前空間 \<some name> が見つかりませんでした**
- **名前 \<some name> は現在のコンテキスト内に存在しません**

[`Microsoft.Windows.Compatibility`](https://www.nuget.org/packages/Microsoft.Windows.Compatibility/) パッケージをアプリに追加することが必要になる場合があります。 このパッケージでは、Windows レジストリとやり取りするための `System.Configuration.ConfigurationManager` クラスや API など、.NET Framework から 21,000 個までの .NET API を追加します。 `Microsoft.Windows.Compatibility` パッケージを追加します。

プロジェクト ファイルを編集し、次の `<ItemGroup>` 要素を追加します。

```xml
<ItemGroup>
  <PackageReference Include="Microsoft.Windows.Compatibility" Version="5.0.0" />
</ItemGroup>
```

## <a name="test-your-app"></a>アプリをテストする

アプリの移行が完了した後、それをテストします。

## <a name="next-steps"></a>次のステップ

- [Windows フォームでの破壊的変更](/dotnet/core/compatibility/winforms)について学習する。
- [Windows 互換機能パック][compat-pack]の詳細を確認する。

[compat-pack]: /dotnet/core/porting/windows-compat-pack
