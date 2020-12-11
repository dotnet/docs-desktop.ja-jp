---
title: アプリケーション設定アーキテクチャ
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- application settings [Windows Forms], architecture
ms.assetid: c8eb2ad0-fac6-4ea2-9140-675a4a44d562
ms.openlocfilehash: 2f4cdbc5b41646e6879be8b36367bfd008e5acde
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/09/2020
ms.locfileid: "96974881"
---
# <a name="application-settings-architecture"></a>アプリケーション設定アーキテクチャ

このトピックでは、アプリケーション設定アーキテクチャのしくみについて説明します。また、グループ化された設定や設定キーなど、アーキテクチャの高度な機能についても説明します。

 アプリケーション設定アーキテクチャでは、アプリケーション スコープまたはユーザー スコープで厳密に型指定された設定の定義と、アプリケーション セッション間での設定の永続化をサポートします。 このアーキテクチャは、ローカル ファイル システムに設定を保存し、ローカル ファイル システムから設定を読み込むための既定の永続化エンジンを提供します。 また、カスタム永続化エンジンを指定するためのインターフェイスも定義します。

 アプリケーションでカスタム コンポーネントがホストされているときに、そのコンポーネントの独自の設定を永続化できるようにするインターフェイスが提供されます。 設定キーを使用することで、各コンポーネントはそのコンポーネントの複数のインスタンスの設定を区別できます。

## <a name="defining-settings"></a>設定の定義

 アプリケーション設定のアーキテクチャは、ASP.NET と Windows フォームの両方で使用されます。また、このアーキテクチャには、両方の環境で共有される複数の基本クラスが含まれています。 最も重要なのは <xref:System.Configuration.SettingsBase> 、コレクションを介して設定へのアクセスを提供し、設定の読み込みと保存のための低レベルの方法を提供するです。 各環境は、から派生した独自のクラスを実装し <xref:System.Configuration.SettingsBase> て、その環境に追加の設定機能を提供します。 Windows フォームベースのアプリケーションでは、すべてのアプリケーション設定をクラスから派生したクラスで定義する必要があり <xref:System.Configuration.ApplicationSettingsBase> ます。これにより、次の機能が基底クラスに追加されます。

- 上位レベルの読み込み操作と保存操作

- ユーザー スコープの設定のサポート

- ユーザーの設定を定義済みの既定値に戻す機能

- 以前のバージョンのアプリケーションの設定のアップグレード

- 設定の変更前または保存前の検証

 設定は、名前空間内で定義されているいくつかの属性を使用して記述できます。これらの設定に <xref:System.Configuration> ついては、「 [アプリケーション設定の属性](application-settings-attributes.md)」を参照してください。 設定を定義する場合は、またはのいずれかを使用して適用する必要があります <xref:System.Configuration.ApplicationScopedSettingAttribute> <xref:System.Configuration.UserScopedSettingAttribute> 。これは、設定がアプリケーション全体に適用されるか、現在のユーザーにのみ適用されるかを示します。

 次のコード例では、`BackgroundColor` という 1 つの設定を指定してカスタム設定クラスを定義しています。

 [!code-csharp[ApplicationSettings.Create#1](~/samples/snippets/csharp/VS_Snippets_Winforms/ApplicationSettings.Create/CS/MyAppSettings.cs#1)]
 [!code-vb[ApplicationSettings.Create#1](~/samples/snippets/visualbasic/VS_Snippets_Winforms/ApplicationSettings.Create/VB/MyAppSettings.vb#1)]

## <a name="settings-persistence"></a>設定の永続化

 <xref:System.Configuration.ApplicationSettingsBase>クラスはそれ自体を保持したり設定を読み込んだりしません。このジョブは、から派生するクラスである設定プロバイダーに分類されます <xref:System.Configuration.SettingsProvider> 。 の派生クラスがを通じて設定プロバイダーを指定していない場合は、既定のプロバイダーである <xref:System.Configuration.ApplicationSettingsBase> <xref:System.Configuration.SettingsProviderAttribute> <xref:System.Configuration.LocalFileSettingsProvider> が使用されます。

 最初に .NET Framework と共にリリースされた構成システムでは、ローカルコンピューターの machine.config ファイル、または `app.` アプリケーションと共に配置するexe.config ファイルのいずれかを使用して、静的なアプリケーション構成データを提供できます。 クラスは、 <xref:System.Configuration.LocalFileSettingsProvider> 次の方法でこのネイティブサポートを拡張します。

- アプリケーション スコープの設定は、machine.config ファイルまたは `app.`exe.config ファイルに保存できます。 machine.config は常に読み取り専用です。`app`.exe.config は、セキュリティを考慮して、ほとんどのアプリケーションで読み取り専用に制限されています。

- ユーザー スコープの設定は、`app`.exe.config ファイルに保存できます。この場合、設定は静的な既定値として扱われます。

- 既定値以外のユーザー スコープの設定は、*user*.config という新しいファイルに保存されます。*user* は、アプリケーションを現在実行しているユーザーのユーザー名です。 ユーザースコープ設定の既定値は、を使用して指定でき <xref:System.Configuration.DefaultSettingValueAttribute> ます。 ユーザー スコープの設定はアプリケーションの実行時に変更されることが多いため、`user`.config は常に読み取り/書き込みになります。

 この 3 つの構成ファイルはいずれも XML 形式で設定を保存します。 アプリケーション スコープの設定の最上位の XML 要素は `<appSettings>` であり、ユーザー スコープの設定には `<userSettings>` が使用されます。 アプリケーション スコープの設定と、ユーザー スコープの設定の既定値が含まれた `app`.exe.config ファイルは、次のようになります。

```xml
<?xml version="1.0" encoding="utf-8" ?>
<configuration>
    <configSections>
        <sectionGroup name="applicationSettings" type="System.Configuration.ApplicationSettingsGroup, System, Version=2.0.0.0, Culture=neutral, PublicKeyToken=b77a5c561934e089" >
            <section name="WindowsApplication1.Properties.Settings" type="System.Configuration.ClientSettingsSection, System, Version=2.0.0.0, Culture=neutral, PublicKeyToken=b77a5c561934e089" />
        </sectionGroup>
        <sectionGroup name="userSettings" type="System.Configuration.UserSettingsGroup, System, Version=2.0.0.0, Culture=neutral, PublicKeyToken=b77a5c561934e089" >
            <section name="WindowsApplication1.Properties.Settings" type="System.Configuration.ClientSettingsSection, System, Version=2.0.0.0, Culture=neutral, PublicKeyToken=b77a5c561934e089" allowExeDefinition="MachineToLocalUser" />
        </sectionGroup>
    </configSections>
    <applicationSettings>
        <WindowsApplication1.Properties.Settings>
            <setting name="Cursor" serializeAs="String">
                <value>Default</value>
            </setting>
            <setting name="DoubleBuffering" serializeAs="String">
                <value>False</value>
            </setting>
        </WindowsApplication1.Properties.Settings>
    </applicationSettings>
    <userSettings>
        <WindowsApplication1.Properties.Settings>
            <setting name="FormTitle" serializeAs="String">
                <value>Form1</value>
            </setting>
            <setting name="FormSize" serializeAs="String">
                <value>595, 536</value>
            </setting>
        </WindowsApplication1.Properties.Settings>
    </userSettings>
</configuration>
```

 構成ファイルのアプリケーション設定セクション内の要素の定義については、「[アプリケーション設定のスキーマ](/dotnet/framework/configure-apps/file-schema/application-settings-schema)」を参照してください。

### <a name="settings-bindings"></a>設定のバインド

 アプリケーション設定では、Windows フォーム データ バインド アーキテクチャを使用して、設定オブジェクトとコンポーネント間で設定の更新の双方向通信を行います。 Visual Studio を使用してアプリケーション設定を作成し、設定をコンポーネントのプロパティに割り当てると、これらのバインドが自動的に生成されます。

 アプリケーション設定は、インターフェイスをサポートするコンポーネントにのみバインドでき <xref:System.Windows.Forms.IBindableComponent> ます。 また、コンポーネントは、特定のバインドされたプロパティの変更イベントを実装するか、インターフェイスによってプロパティが変更されたことをアプリケーション設定に通知する必要があり <xref:System.ComponentModel.INotifyPropertyChanged> ます。 コンポーネントがを実装せず、 <xref:System.Windows.Forms.IBindableComponent> Visual Studio を介してバインドする場合、バインドされたプロパティは初めて設定されますが、更新されません。 コンポーネントがを実装し <xref:System.Windows.Forms.IBindableComponent> ていても、プロパティの変更通知をサポートしていない場合、プロパティが変更されても、バインドは設定ファイル内で更新されません。

 などの一部の Windows フォームコンポーネントで <xref:System.Windows.Forms.ToolStripItem> は、設定のバインドがサポートされていません。

### <a name="settings-serialization"></a>設定のシリアル化

 <xref:System.Configuration.LocalFileSettingsProvider>が設定をディスクに保存する必要がある場合、次の操作が実行されます。

1. リフレクションを使用して、派生クラスで定義されているすべてのプロパティ <xref:System.Configuration.ApplicationSettingsBase> を調べ、またはのいずれかで適用されるすべてのプロパティを検索し <xref:System.Configuration.ApplicationScopedSettingAttribute> <xref:System.Configuration.UserScopedSettingAttribute> ます。

2. プロパティをディスクにシリアル化します。 最初に、 <xref:System.ComponentModel.TypeConverter.ConvertToString%2A> <xref:System.ComponentModel.TypeConverter.ConvertFromString%2A> 関連付けられている型のまたはの呼び出しを試み <xref:System.ComponentModel.TypeConverter> ます。 この呼び出しが失敗すると、代わりに XML シリアル化を使用します。

3. 設定の属性に基づいて、どの設定がどのファイルに指定されているかを判断します。

 独自の設定クラスを実装する場合は、を使用し <xref:System.Configuration.SettingsSerializeAsAttribute> て、列挙体を使用してバイナリまたはカスタムのシリアル化の設定をマークでき <xref:System.Configuration.SettingsSerializeAs> ます。 コードで独自の設定クラスを作成する方法の詳細については、「[方法 : アプリケーション設定を作成する](how-to-create-application-settings.md)」を参照してください。

### <a name="settings-file-locations"></a>設定ファイルの場所

 `app`.exe.config ファイルと *user*.config ファイルの場所は、アプリケーションのインストール方法によって異なります。 Windows フォームベースのアプリケーションをローカルコンピューターにコピーする場合、 `app`.exe.config はアプリケーションのメインの実行可能ファイルのベースディレクトリと同じディレクトリに配置され、 *ユーザー*.config はプロパティで指定された場所に格納されます <xref:System.Windows.Forms.Application.LocalUserAppDataPath%2A?displayProperty=nameWithType> 。 ClickOnce を使用してインストールされたアプリケーションの場合、これらのファイルは両方とも、%InstallRoot%\Documents と設定の \\ *ユーザー名*\Local 設定の下にある clickonce データディレクトリに格納されます。

 ユーザーが移動プロファイルを有効にしている場合、これらのファイルの格納場所は少し異なります。移動プロファイルを使用すると、ドメイン内の他のコンピューターを使用しているときに、ユーザーはさまざまなウィンドウとアプリケーション設定を定義できます。 その場合は、ClickOnce アプリケーションと ClickOnce 以外のアプリケーションの両方で、 `app` %InstallRoot%\Documents とSettings \\ *username*\Application Data の下に格納されている.exe.config とユーザー .config ファイルが格納されます。

 アプリケーション設定機能と新しい配置テクノロジの連携の詳細については、「[ClickOnce とアプリケーション設定](/visualstudio/deployment/clickonce-and-application-settings)」を参照してください。 ClickOnce データディレクトリの詳細については、「 [Clickonce アプリケーションにおけるローカルデータおよびリモートデータへのアクセス](/visualstudio/deployment/accessing-local-and-remote-data-in-clickonce-applications)」を参照してください。

## <a name="application-settings-and-security"></a>アプリケーション設定とセキュリティ

 アプリケーション設定は部分信頼で機能するように設計されています。部分信頼は、インターネットまたはイントラネット上でホストされる Windows フォーム アプリケーションの既定の制限された環境です。 既定の設定プロバイダーでアプリケーション設定を使用する場合、部分信頼以外の特別なアクセス許可は不要です。

 ClickOnce アプリケーションでアプリケーション設定を使用する場合、 `user` .config ファイルは clickonce データディレクトリに格納されます。 アプリケーションの .config ファイルのサイズは、 `user` ClickOnce によって設定されたデータディレクトリクォータを超えることはできません。 詳細については、「[ClickOnce とアプリケーション設定](/visualstudio/deployment/clickonce-and-application-settings)」を参照してください。

## <a name="custom-settings-providers"></a>カスタム設定プロバイダー

 アプリケーション設定アーキテクチャでは、から派生したアプリケーション設定ラッパークラス <xref:System.Configuration.ApplicationSettingsBase> と、から派生した関連設定プロバイダーの間に疎結合があり <xref:System.Configuration.SettingsProvider> ます。 この関連付けは、 <xref:System.Configuration.SettingsProviderAttribute> ラッパークラスまたはその個々のプロパティに適用されたによってのみ定義されます。 設定プロバイダーが明示的に指定されていない場合は、既定のプロバイダーである <xref:System.Configuration.LocalFileSettingsProvider> が使用されます。 そのため、このアーキテクチャではカスタム設定プロバイダーの作成と使用がサポートされています。

 たとえば、すべての設定データを Microsoft SQL Server データベースに格納するプロバイダーである `SqlSettingsProvider` を開発して使用するとします。 <xref:System.Configuration.SettingsProvider>派生クラスは、メソッド内のこの情報を `Initialize` 型のパラメーターとして受け取り <xref:System.Collections.Specialized.NameValueCollection?displayProperty=nameWithType> ます。 次に、メソッドを実装して、 <xref:System.Configuration.SettingsProvider.GetPropertyValues%2A> データストアから設定を取得して <xref:System.Configuration.SettingsProvider.SetPropertyValues%2A> 保存します。 プロバイダーは、提供されたを使用して、 <xref:System.Configuration.SettingsPropertyCollection> <xref:System.Configuration.SettingsProvider.GetPropertyValues%2A> プロパティの名前、型、スコープ、およびそのプロパティに対して定義されているその他の設定属性を特定できます。

 カスタム プロバイダーでは、1 つのプロパティと 1 つのメソッドを実装する必要がありますが、この実装はわかりにくいことがあります。 <xref:System.Configuration.SettingsProvider.ApplicationName%2A>プロパティはの抽象プロパティです <xref:System.Configuration.SettingsProvider> 。これをプログラミングして、次の値を返す必要があります。

 [!code-csharp[ApplicationSettings.Architecture#2](~/samples/snippets/csharp/VS_Snippets_Winforms/ApplicationSettings.Architecture/CS/DummyClass.cs#2)]
 [!code-vb[ApplicationSettings.Architecture#2](~/samples/snippets/visualbasic/VS_Snippets_Winforms/ApplicationSettings.Architecture/VB/DummyProviderClass.vb#2)]

 派生クラスでは、引数を受け取らず値を返さない `Initialize` メソッドも実装する必要があります。 このメソッドは、で定義されていません <xref:System.Configuration.SettingsProvider> 。

 最後に、をプロバイダーに実装して、設定 <xref:System.Configuration.IApplicationSettingsProvider> の更新、既定値への設定の戻し、およびアプリケーションのバージョン間での設定のアップグレードをサポートします。

 カスタム プロバイダーを実装してコンパイルしたら、既定のプロバイダーではなく、このプロバイダーを使用するよう設定クラスに指示する必要があります。 これを行うには、を使用し <xref:System.Configuration.SettingsProviderAttribute> ます。 設定クラス全体に適用された場合、プロバイダーは、クラスが定義する各設定に使用されます。個々の設定に適用された場合、アプリケーション設定のアーキテクチャは、そのプロバイダーをその設定にのみ使用し、rest に対してを使用し <xref:System.Configuration.LocalFileSettingsProvider> ます。 次のコード例は、カスタム プロバイダーを使用するよう設定クラスに指示する方法を示しています。

 [!code-csharp[ApplicationSettings.Architecture#1](~/samples/snippets/csharp/VS_Snippets_Winforms/ApplicationSettings.Architecture/CS/DummyClass.cs#1)]
 [!code-vb[ApplicationSettings.Architecture#1](~/samples/snippets/visualbasic/VS_Snippets_Winforms/ApplicationSettings.Architecture/VB/DummyProviderClass.vb#1)]

 プロバイダーを複数のスレッドから同時に呼び出すことができますが、プロバイダーは常に同じ格納場所に書き込みを行います。したがって、アプリケーション設定アーキテクチャによってインスタンス化されるカスタム プロバイダー クラスのインスタンスは 1 つに限られます。

> [!IMPORTANT]
> カスタム プロバイダーがスレッドセーフであり、構成ファイルへの書き込みを実行できるスレッドが一度に 1 つだけであることを確認する必要があります。

 プロバイダーは、名前空間で定義されているすべての設定属性をサポートする必要はありませんが、最小のサポートとでもサポートする必要が <xref:System.Configuration?displayProperty=nameWithType> あり <xref:System.Configuration.ApplicationScopedSettingAttribute> <xref:System.Configuration.UserScopedSettingAttribute> <xref:System.Configuration.DefaultSettingValueAttribute> ます。 サポートされていない属性がある場合、カスタム プロバイダーは通知なしに失敗します。例外をスローする必要はありません。 ただし、設定クラスで属性の無効な組み合わせが使用されている場合 (およびを同じ設定に適用する場合など)、 <xref:System.Configuration.ApplicationScopedSettingAttribute> <xref:System.Configuration.UserScopedSettingAttribute> プロバイダーは例外をスローして操作を中止する必要があります。

## <a name="see-also"></a>関連項目

- <xref:System.Configuration.ApplicationSettingsBase>
- <xref:System.Configuration.SettingsProvider>
- <xref:System.Configuration.LocalFileSettingsProvider>
- [アプリケーション設定の概要](application-settings-overview.md)
- [カスタム コントロールのアプリケーション設定](application-settings-for-custom-controls.md)
- [ClickOnce とアプリケーションの設定](/visualstudio/deployment/clickonce-and-application-settings)
- [アプリケーション設定スキーマ](/dotnet/framework/configure-apps/file-schema/application-settings-schema)
