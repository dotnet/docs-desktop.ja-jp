---
title: Windows フォームとは
description: この記事では、.NET Core および .NET 5 での Windows フォームの概要について説明します。
ms.date: 10/26/2020
ms.topic: overview
ms.openlocfilehash: a0908891d9391d5820fe75cac69278ddda1b2244
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/09/2020
ms.locfileid: "96992857"
---
# <a name="desktop-guide-windows-forms-net"></a>デスクトップ ガイド (Windows フォーム .NET)

Windows 用の豊富なデスクトップ クライアント アプリを作成する UI フレームワークである、Windows フォームのデスクトップ ガイドへようこそ。 Windows フォームの開発プラットフォームでは、コントロール、グラフィックス、データ バインディング、ユーザー入力など、幅広い一連のアプリ開発機能がサポートされています。 Windows フォームには、Visual Studio のドラッグ アンド ドロップによるビジュアル デザイナーが用意されており、Windows フォーム アプリを簡単に作成できます。

[!INCLUDE [desktop guide under construction](../../includes/desktop-guide-preview-note.md)]

Windows フォームには、次の 2 つの実装があります。

01. [GitHub](https://github.com/dotnet/winforms) 上でホストされる、オープンソース実装。

    このバージョンは、.NET 5 および .NET Core 3.1 で実行されます。 Windows フォームのビジュアル デザイナーには、少なくとも [Visual Studio 2019 バージョン 16.8 Preview](https://visualstudio.microsoft.com/downloads/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=inline+link&utm_content=download+vs2019+desktopguide+winforms) が必要です。

01. Visual Studio 2019 および Visual Studio 2017 でサポートされている、.NET Framework 4 の実装。

    .NET Framework 4 は .NET の Windows のみのバージョンであり、Windows オペレーティング システムのコンポーネントと見なされます。 このバージョンの Windows フォームは .NET Framework と共に配布されます。

このデスクトップ ガイドは、.NET 5 の Windows フォーム向けに書かれています。 .NET Framework バージョンの Windows フォームについて詳しくは、[.NET Framework 用の Windows フォーム](../../../framework/winforms/index.yml?view=netframeworkdesktop-4.8&preserve-view=true)に関するページを参照してください。

## <a name="introduction"></a>はじめに

Windows フォームは、Windows デスクトップ アプリを構築するための UI フレームワークです。 Visual Studio で提供されるビジュアル デザイナーに基づいて、デスクトップ アプリを作成するための最も生産的な方法の 1 つが提供されます。 ビジュアル コントロールのドラッグ アンド ドロップ配置などの機能を使用すると、デスクトップ アプリを簡単に構築できます。

Windows フォームを使用すると、オフラインでもインターネットに接続しているときでも、簡単にデプロイ、更新、および作業を行える視覚的に豊富なアプリを開発できます。 Windows フォーム アプリからは、そのアプリが実行されているコンピューターのローカル ハードウェアとファイル システムにアクセスできます。

Windows フォーム アプリを作成する方法について学習する場合は、「[チュートリアル: 新しい WinForms アプリを作成する (Windows フォーム .NET)](../get-started/create-app-visual-studio.md)」を参照してください。

## <a name="why-migrate-from-net-framework"></a>.NET Framework から移行する理由

.NET 5.0 用の Windows フォームでは、.NET Framework に対する次の機能と拡張機能が提供されます。 詳細については、[.NET 5 用の Windows フォームの新機能](../whats-new/index.md)に関するページを参照してください。 アプリを移行する方法について学習する場合は、「[Windows フォーム デスクトップ アプリを .NET 5 に移行する方法](../migration/index.md)」を参照してください。

## <a name="build-rich-interactive-user-interfaces"></a>リッチで対話型のユーザー インターフェイスを構築する

Windows フォームは、.NET 用の UI テクノロジであり、ファイル システムへの読み書きなど、アプリの一般的なタスクを簡略化するマネージド ライブラリのセットです。 Visual Studio などの開発環境を使用する場合、情報を表示して、ユーザーからの入力を要求し、ネットワーク経由でリモート コンピューターと通信する Windows フォームのスマート クライアント アプリを作成できます。

Windows フォームでは、"*フォーム*" はユーザーに情報を表示するビジュアル サーフェイスです。 通常は、コントロールをフォームに追加して、マウスのクリックやキーの押下などのユーザー アクションへの応答を開発することで、Windows フォーム アプリを構築します。 "*コントロール*" は、データを表示したり、データ入力を受け入れたりする独立した UI 要素です。

ユーザーがフォームまたはそのコントロールのいずれかにアクションを実行すると、そのアクションがイベントを生成します。 アプリではコードを使用してこれらのイベントに反応し、イベントが発生したときにそれらを処理します。<!-- TODO  For more information, see [Creating Event Handlers in Windows Forms](creating-event-handlers-in-windows-forms.md).-->

Windows フォームには、テキスト ボックス、ボタン、ドロップダウン ボックス、ラジオ ボタン、さらには Web ページを表示するコントロールなど、フォームに追加できるさまざまなコントロールが含まれています。<!-- TODO For a list of all the controls you can use on a form, see [Controls to Use on Windows Forms](./controls/controls-to-use-on-windows-forms.md).--> 既存のコントロールがニーズを満たしていない場合、Windows フォームでは <xref:System.Windows.Forms.UserControl> クラスを使用した独自のカスタム コントロールの作成もサポートされます。

Windows フォームには、Microsoft Office のようなハイエンド アプリの機能をエミュレートする豊富な UI コントロールが用意されています。 <xref:System.Windows.Forms.ToolStrip> および <xref:System.Windows.Forms.MenuStrip> コントロールを使用する場合、テキストや画像を含むツールバーとメニューを作成したり、サブメニューを表示したり、テキスト ボックスやコンボ ボックスなど、その他のコントロールをホストしたりできます。

Visual Studio でドラッグ アンド ドロップによる **Windows フォーム デザイナー** を使用すると、Windows フォーム アプリを簡単に作成できます。 コントロールをカーソルで選択して、フォームの任意の場所に配置するだけです。 デザイナーがグリッド線やスナップ線などのツールを提供するので、コントロールの調整が楽になります。 <xref:System.Windows.Forms.FlowLayoutPanel>、<xref:System.Windows.Forms.TableLayoutPanel>、および <xref:System.Windows.Forms.SplitContainer> の各コントロールを使用して、より短い時間で高度なフォーム レイアウトを作成できます。

最後に、独自のカスタム UI 要素を作成する必要がある場合は、<xref:System.Drawing> 名前空間に、線、円、およびその他の図形をフォーム上に直接表示するクラスが多数含まれています。

### <a name="create-forms-and-controls"></a>フォームとコントロールを作成する

これらの機能を使用する方法の手順を追った説明については、次のヘルプ トピックを参照してください。

- [プロジェクトにフォームを追加する方法](../forms/how-to-add.md)
- [フォームにコントロールを追加する方法](../controls/how-to-add-to-a-form.md)

<!-- TODO
| Using the <xref:System.Windows.Forms.ToolStrip> Control | [How to: Create a Basic ToolStrip with Standard Items Using the Designer](./controls/create-a-basic-wf-toolstrip-with-standard-items-using-the-designer.md) |
| Creating graphics with <xref:System.Drawing> | [Getting Started with Graphics Programming](./advanced/getting-started-with-graphics-programming.md)  |
| Creating custom controls                     | [How to: Inherit from the UserControl Class](./controls/how-to-inherit-from-the-usercontrol-class.md) |
-->

## <a name="display-and-manipulate-data"></a>データを表示して操作する

多くのアプリでは、データベース、XML または JSON ファイル、Web サービス、あるいはその他のデータ ソースからデータを表示する必要があります。 Windows フォームは、従来の行と列の形式である、表形式のデータを表示するために、<xref:System.Windows.Forms.DataGridView> コントロールという名前の柔軟なコントロールを提供しているため、すべてのデータが独自のセルを占有します。 <xref:System.Windows.Forms.DataGridView> を使用すると、個別のセルの外観のカスタマイズ、任意の列と行のその場でのロック、セルの内部の複雑なコントロールの表示や、その他の機能が可能になります。

ネットワーク経由のデータ ソースへの接続は、Windows フォームを使用するシンプルなタスクです。 <xref:System.Windows.Forms.BindingSource> コンポーネントは、データ ソースへの接続を表すものであり、データをコントロールにバインドしたり、前と次のレコードに移動したり、レコードを編集したり、変更内容を元のソースに保存したりするためのメソッドが公開されます。 <xref:System.Windows.Forms.BindingNavigator> コントロールは、ユーザーがレコード間を移動する <xref:System.Windows.Forms.BindingSource> コンポーネントに対して、シンプルなインターフェイスを提供します。

Visual Studio の [データ ソース] ウィンドウを使用すると、データバインド コントロールを簡単に作成できます。 このウィンドウには、プロジェクト内のデータベース、Web サービス、オブジェクトなどのデータ ソースが表示されます。 このウィンドウからプロジェクトのフォームに項目をドラッグして、データ バインド コントロールを作成できます。 また、[データ ソース] ウィンドウから既存のコントロールにオブジェクトをドラッグして、データに既存のコントロールをバインドすることもできます。

Windows フォームで管理できる別の種類のデーデータ バインドは "*設定*" です。 ほとんどのアプリでは、フォームの前回のサイズなどの実行時の状態に関する情報を一部保持し、保存されたファイルの既定の場所などのユーザー設定のデータを保持する必要があります。 アプリケーション設定機能は、クライアント コンピューターに両方の種類の設定を保存する簡単な方法を提供することで、こうした要件に対応します。 Visual Studio またはコード エディターを使用してこれらの設定を定義した後、設定は XML として永続化され、実行時に自動的にメモリに読み取られます。

<!-- TODO
### Display and manipulate data

For step-by-step information about how to use these features, see the following Help topics.

| Description                                                   | Help topic                                                                                                                                                        |
|---------------------------------------------------------------|-------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Using the <xref:System.Windows.Forms.BindingSource> component | [How to: Bind Windows Forms Controls with the BindingSource Component Using the Designer](./controls/bind-wf-controls-with-the-bindingsource.md)                  |
| Working with ADO.NET data sources                             | [How to: Sort and Filter ADO.NET Data with the Windows Forms BindingSource Component](./controls/sort-and-filter-ado-net-data-with-wf-bindingsource-component.md) |
| Using the Data Sources window                                 | [Bind Windows Forms controls to data in Visual Studio](/visualstudio/data-tools/bind-windows-forms-controls-to-data-in-visual-studio)                             |
| Using app settings                                            | [How to: Create Application Settings](./advanced/how-to-create-application-settings.md)                                                                           |

-->

## <a name="deploy-apps-to-client-computers"></a>クライアント コンピューターにアプリをデプロイする

アプリを作成した後、ユーザーにそのアプリを送信し、独自のクライアント コンピューターにインストールして実行できるようにする必要があります。 ClickOnce テクノロジを使用する場合、数回クリックするだけで、Visual Studio 内からアプリをデプロイして、Web 上のアプリを指す URL をユーザーに提供することができます。 ClickOnce により、アプリのすべての要素と依存関係が管理され、確実にクライアント コンピューターにアプリが正しくインストールされます。

ClickOnce アプリは、ユーザーがネットワークに接続されている場合にのみ実行するか、オンラインとオフラインの両方で実行するかを構成することができます。 アプリでオフライン操作がサポートされるように指定すると、ClickOnce により、ユーザーの **[スタート]** メニューにアプリへのリンクが追加されます。 その後、ユーザーは、URL を使用せずにそのアプリを開くことができます。

アプリを更新するときに、新しい配置マニフェストとアプリの新しいコピーを Web サーバーに発行します。 ClickOnce により、使用可能な更新プログラムがあることが検出され、ユーザーのインストールがアップグレードされます。 古いアプリを更新するためにカスタム プログラミングは必要ありません。

<!-- TODO

### Deploy ClickOnce apps

For a full introduction to ClickOnce, see [ClickOnce Security and Deployment](/visualstudio/deployment/clickonce-security-and-deployment). For step-by-step information about how to use these features, see the following Help topics,

|Description|Help topic|
|-----------------|----------------|
|Deploying an app by using ClickOnce|[How to: Publish a ClickOnce Application using the Publish Wizard](/visualstudio/deployment/how-to-publish-a-clickonce-application-using-the-publish-wizard)<br /><br /> [Walkthrough: Manually Deploying a ClickOnce Application](/visualstudio/deployment/walkthrough-manually-deploying-a-clickonce-application)|
|Updating a ClickOnce deployment|[How to: Manage Updates for a ClickOnce Application](/visualstudio/deployment/how-to-manage-updates-for-a-clickonce-application)|
|Managing security with ClickOnce|[How to: Enable ClickOnce Security Settings](/visualstudio/deployment/how-to-enable-clickonce-security-settings)|
-->

<!-- TODO
## Other controls and features

There are many other features in Windows Forms that make implementing common tasks fast and easy, such as support for creating dialog boxes, printing, adding help and documentation, and localizing your app to multiple languages.

### Implement other controls and features

For step-by-step information about how to use these features, see the following Help topics.

| Description | Help topic |
|-------------|------------|
|Printing the contents of a form | [How to: Print Graphics in Windows Forms](./advanced/how-to-print-graphics-in-windows-forms.md)<br /><br /> [How to: Print a Multi-Page Text File in Windows Forms](./advanced/how-to-print-a-multi-page-text-file-in-windows-forms.md) |
|Learn more about Windows Forms security | [Security in Windows Forms Overview](security-in-windows-forms-overview.md) |
-->

## <a name="see-also"></a>関連項目

- [チュートリアル: 新しい WinForms アプリを作成する (Windows フォーム .NET)](../get-started/create-app-visual-studio.md)
- [プロジェクトにフォームを追加する方法 (Windows フォーム .NET)](../forms/how-to-add.md)
- [コントロールを追加する (Windows フォーム .NET)](../controls/how-to-add-to-a-form.md)
