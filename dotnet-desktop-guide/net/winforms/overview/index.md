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
# <a name="desktop-guide-windows-forms-net"></a><span data-ttu-id="21b0f-103">デスクトップ ガイド (Windows フォーム .NET)</span><span class="sxs-lookup"><span data-stu-id="21b0f-103">Desktop Guide (Windows Forms .NET)</span></span>

<span data-ttu-id="21b0f-104">Windows 用の豊富なデスクトップ クライアント アプリを作成する UI フレームワークである、Windows フォームのデスクトップ ガイドへようこそ。</span><span class="sxs-lookup"><span data-stu-id="21b0f-104">Welcome to the Desktop Guide for Windows Forms, a UI framework that creates rich desktop client apps for Windows.</span></span> <span data-ttu-id="21b0f-105">Windows フォームの開発プラットフォームでは、コントロール、グラフィックス、データ バインディング、ユーザー入力など、幅広い一連のアプリ開発機能がサポートされています。</span><span class="sxs-lookup"><span data-stu-id="21b0f-105">The Windows Forms development platform supports a broad set of app development features, including controls, graphics, data binding, and user input.</span></span> <span data-ttu-id="21b0f-106">Windows フォームには、Visual Studio のドラッグ アンド ドロップによるビジュアル デザイナーが用意されており、Windows フォーム アプリを簡単に作成できます。</span><span class="sxs-lookup"><span data-stu-id="21b0f-106">Windows Forms features a drag-and-drop visual designer in Visual Studio to easily create Windows Forms apps.</span></span>

[!INCLUDE [desktop guide under construction](../../includes/desktop-guide-preview-note.md)]

<span data-ttu-id="21b0f-107">Windows フォームには、次の 2 つの実装があります。</span><span class="sxs-lookup"><span data-stu-id="21b0f-107">There are two implementations of Windows Forms:</span></span>

01. <span data-ttu-id="21b0f-108">[GitHub](https://github.com/dotnet/winforms) 上でホストされる、オープンソース実装。</span><span class="sxs-lookup"><span data-stu-id="21b0f-108">The open-source implementation hosted on [GitHub](https://github.com/dotnet/winforms).</span></span>

    <span data-ttu-id="21b0f-109">このバージョンは、.NET 5 および .NET Core 3.1 で実行されます。</span><span class="sxs-lookup"><span data-stu-id="21b0f-109">This version runs on .NET 5 and .NET Core 3.1.</span></span> <span data-ttu-id="21b0f-110">Windows フォームのビジュアル デザイナーには、少なくとも [Visual Studio 2019 バージョン 16.8 Preview](https://visualstudio.microsoft.com/downloads/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=inline+link&utm_content=download+vs2019+desktopguide+winforms) が必要です。</span><span class="sxs-lookup"><span data-stu-id="21b0f-110">The Windows Forms Visual Designer requires, at a minimum, [Visual Studio 2019 version 16.8 Preview](https://visualstudio.microsoft.com/downloads/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=inline+link&utm_content=download+vs2019+desktopguide+winforms).</span></span>

01. <span data-ttu-id="21b0f-111">Visual Studio 2019 および Visual Studio 2017 でサポートされている、.NET Framework 4 の実装。</span><span class="sxs-lookup"><span data-stu-id="21b0f-111">The .NET Framework 4 implementation that's supported by Visual Studio 2019 and Visual Studio 2017.</span></span>

    <span data-ttu-id="21b0f-112">.NET Framework 4 は .NET の Windows のみのバージョンであり、Windows オペレーティング システムのコンポーネントと見なされます。</span><span class="sxs-lookup"><span data-stu-id="21b0f-112">.NET Framework 4 is a Windows-only version of .NET and is considered a Windows Operating System component.</span></span> <span data-ttu-id="21b0f-113">このバージョンの Windows フォームは .NET Framework と共に配布されます。</span><span class="sxs-lookup"><span data-stu-id="21b0f-113">This version of Windows Forms is distributed with .NET Framework.</span></span>

<span data-ttu-id="21b0f-114">このデスクトップ ガイドは、.NET 5 の Windows フォーム向けに書かれています。</span><span class="sxs-lookup"><span data-stu-id="21b0f-114">This Desktop Guide is written for Windows Forms on .NET 5.</span></span> <span data-ttu-id="21b0f-115">.NET Framework バージョンの Windows フォームについて詳しくは、[.NET Framework 用の Windows フォーム](../../../framework/winforms/index.yml?view=netframeworkdesktop-4.8&preserve-view=true)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="21b0f-115">For more information about the .NET Framework version of Windows Forms, see [Windows Forms for .NET Framework](../../../framework/winforms/index.yml?view=netframeworkdesktop-4.8&preserve-view=true).</span></span>

## <a name="introduction"></a><span data-ttu-id="21b0f-116">はじめに</span><span class="sxs-lookup"><span data-stu-id="21b0f-116">Introduction</span></span>

<span data-ttu-id="21b0f-117">Windows フォームは、Windows デスクトップ アプリを構築するための UI フレームワークです。</span><span class="sxs-lookup"><span data-stu-id="21b0f-117">Windows Forms is a UI framework for building Windows desktop apps.</span></span> <span data-ttu-id="21b0f-118">Visual Studio で提供されるビジュアル デザイナーに基づいて、デスクトップ アプリを作成するための最も生産的な方法の 1 つが提供されます。</span><span class="sxs-lookup"><span data-stu-id="21b0f-118">It provides one of the most productive ways to create desktop apps based on the visual designer provided in Visual Studio.</span></span> <span data-ttu-id="21b0f-119">ビジュアル コントロールのドラッグ アンド ドロップ配置などの機能を使用すると、デスクトップ アプリを簡単に構築できます。</span><span class="sxs-lookup"><span data-stu-id="21b0f-119">Functionality such as drag-and-drop placement of visual controls makes it easy to build desktop apps.</span></span>

<span data-ttu-id="21b0f-120">Windows フォームを使用すると、オフラインでもインターネットに接続しているときでも、簡単にデプロイ、更新、および作業を行える視覚的に豊富なアプリを開発できます。</span><span class="sxs-lookup"><span data-stu-id="21b0f-120">With Windows Forms, you develop graphically rich apps that are easy to deploy, update, and work while offline or while connected to the internet.</span></span> <span data-ttu-id="21b0f-121">Windows フォーム アプリからは、そのアプリが実行されているコンピューターのローカル ハードウェアとファイル システムにアクセスできます。</span><span class="sxs-lookup"><span data-stu-id="21b0f-121">Windows Forms apps can access the local hardware and file system of the computer where the app is running.</span></span>

<span data-ttu-id="21b0f-122">Windows フォーム アプリを作成する方法について学習する場合は、「[チュートリアル: 新しい WinForms アプリを作成する (Windows フォーム .NET)](../get-started/create-app-visual-studio.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="21b0f-122">To learn how to create a Windows Forms app, see [Tutorial: Create a new WinForms app (Windows Forms .NET)](../get-started/create-app-visual-studio.md).</span></span>

## <a name="why-migrate-from-net-framework"></a><span data-ttu-id="21b0f-123">.NET Framework から移行する理由</span><span class="sxs-lookup"><span data-stu-id="21b0f-123">Why migrate from .NET Framework</span></span>

<span data-ttu-id="21b0f-124">.NET 5.0 用の Windows フォームでは、.NET Framework に対する次の機能と拡張機能が提供されます。</span><span class="sxs-lookup"><span data-stu-id="21b0f-124">Windows Forms for .NET 5.0 provides new features and enhancements over .NET Framework.</span></span> <span data-ttu-id="21b0f-125">詳細については、[.NET 5 用の Windows フォームの新機能](../whats-new/index.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="21b0f-125">For more information, see [What's new in Windows Forms for .NET 5](../whats-new/index.md).</span></span> <span data-ttu-id="21b0f-126">アプリを移行する方法について学習する場合は、「[Windows フォーム デスクトップ アプリを .NET 5 に移行する方法](../migration/index.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="21b0f-126">To learn how to migrate an app, see [How to migrate a Windows Forms desktop app to .NET 5](../migration/index.md).</span></span>

## <a name="build-rich-interactive-user-interfaces"></a><span data-ttu-id="21b0f-127">リッチで対話型のユーザー インターフェイスを構築する</span><span class="sxs-lookup"><span data-stu-id="21b0f-127">Build rich, interactive user interfaces</span></span>

<span data-ttu-id="21b0f-128">Windows フォームは、.NET 用の UI テクノロジであり、ファイル システムへの読み書きなど、アプリの一般的なタスクを簡略化するマネージド ライブラリのセットです。</span><span class="sxs-lookup"><span data-stu-id="21b0f-128">Windows Forms is a UI technology for .NET, a set of managed libraries that simplify common app tasks such as reading and writing to the file system.</span></span> <span data-ttu-id="21b0f-129">Visual Studio などの開発環境を使用する場合、情報を表示して、ユーザーからの入力を要求し、ネットワーク経由でリモート コンピューターと通信する Windows フォームのスマート クライアント アプリを作成できます。</span><span class="sxs-lookup"><span data-stu-id="21b0f-129">When you use a development environment like Visual Studio, you can create Windows Forms smart-client apps that display information, request input from users, and communicate with remote computers over a network.</span></span>

<span data-ttu-id="21b0f-130">Windows フォームでは、"*フォーム*" はユーザーに情報を表示するビジュアル サーフェイスです。</span><span class="sxs-lookup"><span data-stu-id="21b0f-130">In Windows Forms, a *form* is a visual surface on which you display information to the user.</span></span> <span data-ttu-id="21b0f-131">通常は、コントロールをフォームに追加して、マウスのクリックやキーの押下などのユーザー アクションへの応答を開発することで、Windows フォーム アプリを構築します。</span><span class="sxs-lookup"><span data-stu-id="21b0f-131">You ordinarily build Windows Forms apps by adding controls to forms and developing responses to user actions, such as mouse clicks or key presses.</span></span> <span data-ttu-id="21b0f-132">"*コントロール*" は、データを表示したり、データ入力を受け入れたりする独立した UI 要素です。</span><span class="sxs-lookup"><span data-stu-id="21b0f-132">A *control* is a discrete UI element that displays data or accepts data input.</span></span>

<span data-ttu-id="21b0f-133">ユーザーがフォームまたはそのコントロールのいずれかにアクションを実行すると、そのアクションがイベントを生成します。</span><span class="sxs-lookup"><span data-stu-id="21b0f-133">When a user does something to your form or one of its controls, the action generates an event.</span></span> <span data-ttu-id="21b0f-134">アプリではコードを使用してこれらのイベントに反応し、イベントが発生したときにそれらを処理します。</span><span class="sxs-lookup"><span data-stu-id="21b0f-134">Your app reacts to these events with code, and processes the events when they occur.</span></span><!-- TODO  For more information, see [Creating Event Handlers in Windows Forms](creating-event-handlers-in-windows-forms.md).-->

<span data-ttu-id="21b0f-135">Windows フォームには、テキスト ボックス、ボタン、ドロップダウン ボックス、ラジオ ボタン、さらには Web ページを表示するコントロールなど、フォームに追加できるさまざまなコントロールが含まれています。</span><span class="sxs-lookup"><span data-stu-id="21b0f-135">Windows Forms contains a variety of controls that you can add to forms: controls that display text boxes, buttons, drop-down boxes, radio buttons, and even webpages.</span></span><!-- TODO For a list of all the controls you can use on a form, see [Controls to Use on Windows Forms](./controls/controls-to-use-on-windows-forms.md).--> <span data-ttu-id="21b0f-136">既存のコントロールがニーズを満たしていない場合、Windows フォームでは <xref:System.Windows.Forms.UserControl> クラスを使用した独自のカスタム コントロールの作成もサポートされます。</span><span class="sxs-lookup"><span data-stu-id="21b0f-136">If an existing control doesn't meet your needs, Windows Forms also supports creating your own custom controls using the <xref:System.Windows.Forms.UserControl> class.</span></span>

<span data-ttu-id="21b0f-137">Windows フォームには、Microsoft Office のようなハイエンド アプリの機能をエミュレートする豊富な UI コントロールが用意されています。</span><span class="sxs-lookup"><span data-stu-id="21b0f-137">Windows Forms has rich UI controls that emulate features in high-end apps like Microsoft Office.</span></span> <span data-ttu-id="21b0f-138"><xref:System.Windows.Forms.ToolStrip> および <xref:System.Windows.Forms.MenuStrip> コントロールを使用する場合、テキストや画像を含むツールバーとメニューを作成したり、サブメニューを表示したり、テキスト ボックスやコンボ ボックスなど、その他のコントロールをホストしたりできます。</span><span class="sxs-lookup"><span data-stu-id="21b0f-138">When you use the <xref:System.Windows.Forms.ToolStrip> and <xref:System.Windows.Forms.MenuStrip> controls, you can create toolbars and menus that contain text and images, display submenus, and host other controls such as text boxes and combo boxes.</span></span>

<span data-ttu-id="21b0f-139">Visual Studio でドラッグ アンド ドロップによる **Windows フォーム デザイナー** を使用すると、Windows フォーム アプリを簡単に作成できます。</span><span class="sxs-lookup"><span data-stu-id="21b0f-139">With the drag-and-drop **Windows Forms Designer** in Visual Studio, you can easily create Windows Forms apps.</span></span> <span data-ttu-id="21b0f-140">コントロールをカーソルで選択して、フォームの任意の場所に配置するだけです。</span><span class="sxs-lookup"><span data-stu-id="21b0f-140">Just select the controls with your cursor and place them where you want on the form.</span></span> <span data-ttu-id="21b0f-141">デザイナーがグリッド線やスナップ線などのツールを提供するので、コントロールの調整が楽になります。</span><span class="sxs-lookup"><span data-stu-id="21b0f-141">The designer provides tools such as gridlines and snap lines to take the hassle out of aligning controls.</span></span> <span data-ttu-id="21b0f-142"><xref:System.Windows.Forms.FlowLayoutPanel>、<xref:System.Windows.Forms.TableLayoutPanel>、および <xref:System.Windows.Forms.SplitContainer> の各コントロールを使用して、より短い時間で高度なフォーム レイアウトを作成できます。</span><span class="sxs-lookup"><span data-stu-id="21b0f-142">You can use the <xref:System.Windows.Forms.FlowLayoutPanel>, <xref:System.Windows.Forms.TableLayoutPanel>, and <xref:System.Windows.Forms.SplitContainer> controls to create advanced form layouts in less time.</span></span>

<span data-ttu-id="21b0f-143">最後に、独自のカスタム UI 要素を作成する必要がある場合は、<xref:System.Drawing> 名前空間に、線、円、およびその他の図形をフォーム上に直接表示するクラスが多数含まれています。</span><span class="sxs-lookup"><span data-stu-id="21b0f-143">Finally, if you must create your own custom UI elements, the <xref:System.Drawing> namespace contains a large selection of classes to render lines, circles, and other shapes directly on a form.</span></span>

### <a name="create-forms-and-controls"></a><span data-ttu-id="21b0f-144">フォームとコントロールを作成する</span><span class="sxs-lookup"><span data-stu-id="21b0f-144">Create forms and controls</span></span>

<span data-ttu-id="21b0f-145">これらの機能を使用する方法の手順を追った説明については、次のヘルプ トピックを参照してください。</span><span class="sxs-lookup"><span data-stu-id="21b0f-145">For step-by-step information about how to use these features, see the following Help topics.</span></span>

- [<span data-ttu-id="21b0f-146">プロジェクトにフォームを追加する方法</span><span class="sxs-lookup"><span data-stu-id="21b0f-146">How to add a form to a project</span></span>](../forms/how-to-add.md)
- [<span data-ttu-id="21b0f-147">フォームにコントロールを追加する方法</span><span class="sxs-lookup"><span data-stu-id="21b0f-147">How to add Controls to to a form</span></span>](../controls/how-to-add-to-a-form.md)

<!-- TODO
| Using the <xref:System.Windows.Forms.ToolStrip> Control | [How to: Create a Basic ToolStrip with Standard Items Using the Designer](./controls/create-a-basic-wf-toolstrip-with-standard-items-using-the-designer.md) |
| Creating graphics with <xref:System.Drawing> | [Getting Started with Graphics Programming](./advanced/getting-started-with-graphics-programming.md)  |
| Creating custom controls                     | [How to: Inherit from the UserControl Class](./controls/how-to-inherit-from-the-usercontrol-class.md) |
-->

## <a name="display-and-manipulate-data"></a><span data-ttu-id="21b0f-148">データを表示して操作する</span><span class="sxs-lookup"><span data-stu-id="21b0f-148">Display and manipulate data</span></span>

<span data-ttu-id="21b0f-149">多くのアプリでは、データベース、XML または JSON ファイル、Web サービス、あるいはその他のデータ ソースからデータを表示する必要があります。</span><span class="sxs-lookup"><span data-stu-id="21b0f-149">Many apps must display data from a database, XML or JSON file, web service, or other data source.</span></span> <span data-ttu-id="21b0f-150">Windows フォームは、従来の行と列の形式である、表形式のデータを表示するために、<xref:System.Windows.Forms.DataGridView> コントロールという名前の柔軟なコントロールを提供しているため、すべてのデータが独自のセルを占有します。</span><span class="sxs-lookup"><span data-stu-id="21b0f-150">Windows Forms provides a flexible control that is named the <xref:System.Windows.Forms.DataGridView> control for displaying such tabular data in a traditional row and column format, so that every piece of data occupies its own cell.</span></span> <span data-ttu-id="21b0f-151"><xref:System.Windows.Forms.DataGridView> を使用すると、個別のセルの外観のカスタマイズ、任意の列と行のその場でのロック、セルの内部の複雑なコントロールの表示や、その他の機能が可能になります。</span><span class="sxs-lookup"><span data-stu-id="21b0f-151">When you use <xref:System.Windows.Forms.DataGridView>, you can customize the appearance of individual cells, lock arbitrary rows and columns in place, and display complex controls inside cells, among other features.</span></span>

<span data-ttu-id="21b0f-152">ネットワーク経由のデータ ソースへの接続は、Windows フォームを使用するシンプルなタスクです。</span><span class="sxs-lookup"><span data-stu-id="21b0f-152">Connecting to data sources over a network is a simple task with Windows Forms.</span></span> <span data-ttu-id="21b0f-153"><xref:System.Windows.Forms.BindingSource> コンポーネントは、データ ソースへの接続を表すものであり、データをコントロールにバインドしたり、前と次のレコードに移動したり、レコードを編集したり、変更内容を元のソースに保存したりするためのメソッドが公開されます。</span><span class="sxs-lookup"><span data-stu-id="21b0f-153">The <xref:System.Windows.Forms.BindingSource> component represents a connection to a data source, and exposes methods for binding data to controls, navigating to the previous and next records, editing records, and saving changes back to the original source.</span></span> <span data-ttu-id="21b0f-154"><xref:System.Windows.Forms.BindingNavigator> コントロールは、ユーザーがレコード間を移動する <xref:System.Windows.Forms.BindingSource> コンポーネントに対して、シンプルなインターフェイスを提供します。</span><span class="sxs-lookup"><span data-stu-id="21b0f-154">The <xref:System.Windows.Forms.BindingNavigator> control provides a simple interface over the <xref:System.Windows.Forms.BindingSource> component for users to navigate between records.</span></span>

<span data-ttu-id="21b0f-155">Visual Studio の [データ ソース] ウィンドウを使用すると、データバインド コントロールを簡単に作成できます。</span><span class="sxs-lookup"><span data-stu-id="21b0f-155">You can create data-bound controls easily by using the Data Sources window in Visual Studio.</span></span> <span data-ttu-id="21b0f-156">このウィンドウには、プロジェクト内のデータベース、Web サービス、オブジェクトなどのデータ ソースが表示されます。</span><span class="sxs-lookup"><span data-stu-id="21b0f-156">The window displays data sources such as databases, web services, and objects in your project.</span></span> <span data-ttu-id="21b0f-157">このウィンドウからプロジェクトのフォームに項目をドラッグして、データ バインド コントロールを作成できます。</span><span class="sxs-lookup"><span data-stu-id="21b0f-157">You can create data-bound controls by dragging items from this window onto forms in your project.</span></span> <span data-ttu-id="21b0f-158">また、[データ ソース] ウィンドウから既存のコントロールにオブジェクトをドラッグして、データに既存のコントロールをバインドすることもできます。</span><span class="sxs-lookup"><span data-stu-id="21b0f-158">You can also data-bind existing controls to data by dragging objects from the Data Sources window onto existing controls.</span></span>

<span data-ttu-id="21b0f-159">Windows フォームで管理できる別の種類のデーデータ バインドは "*設定*" です。</span><span class="sxs-lookup"><span data-stu-id="21b0f-159">Another type of data binding you can manage in Windows Forms is *settings*.</span></span> <span data-ttu-id="21b0f-160">ほとんどのアプリでは、フォームの前回のサイズなどの実行時の状態に関する情報を一部保持し、保存されたファイルの既定の場所などのユーザー設定のデータを保持する必要があります。</span><span class="sxs-lookup"><span data-stu-id="21b0f-160">Most apps must retain some information about their run-time state, such as the last-known size of forms, and retain user preference data, such as default locations for saved files.</span></span> <span data-ttu-id="21b0f-161">アプリケーション設定機能は、クライアント コンピューターに両方の種類の設定を保存する簡単な方法を提供することで、こうした要件に対応します。</span><span class="sxs-lookup"><span data-stu-id="21b0f-161">The Application Settings feature addresses these requirements by providing an easy way to store both types of settings on the client computer.</span></span> <span data-ttu-id="21b0f-162">Visual Studio またはコード エディターを使用してこれらの設定を定義した後、設定は XML として永続化され、実行時に自動的にメモリに読み取られます。</span><span class="sxs-lookup"><span data-stu-id="21b0f-162">After you define these settings by using either Visual Studio or a code editor, the settings are persisted as XML and automatically read back into memory at run time.</span></span>

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

## <a name="deploy-apps-to-client-computers"></a><span data-ttu-id="21b0f-163">クライアント コンピューターにアプリをデプロイする</span><span class="sxs-lookup"><span data-stu-id="21b0f-163">Deploy apps to client computers</span></span>

<span data-ttu-id="21b0f-164">アプリを作成した後、ユーザーにそのアプリを送信し、独自のクライアント コンピューターにインストールして実行できるようにする必要があります。</span><span class="sxs-lookup"><span data-stu-id="21b0f-164">After you have written your app, you must send the app to your users so that they can install and run it on their own client computers.</span></span> <span data-ttu-id="21b0f-165">ClickOnce テクノロジを使用する場合、数回クリックするだけで、Visual Studio 内からアプリをデプロイして、Web 上のアプリを指す URL をユーザーに提供することができます。</span><span class="sxs-lookup"><span data-stu-id="21b0f-165">When you use the ClickOnce technology, you can deploy your apps from within Visual Studio by using just a few clicks, and provide your users with a URL pointing to your app on the web.</span></span> <span data-ttu-id="21b0f-166">ClickOnce により、アプリのすべての要素と依存関係が管理され、確実にクライアント コンピューターにアプリが正しくインストールされます。</span><span class="sxs-lookup"><span data-stu-id="21b0f-166">ClickOnce manages all the elements and dependencies in your app, and ensures that the app is correctly installed on the client computer.</span></span>

<span data-ttu-id="21b0f-167">ClickOnce アプリは、ユーザーがネットワークに接続されている場合にのみ実行するか、オンラインとオフラインの両方で実行するかを構成することができます。</span><span class="sxs-lookup"><span data-stu-id="21b0f-167">ClickOnce apps can be configured to run only when the user is connected to the network, or to run both online and offline.</span></span> <span data-ttu-id="21b0f-168">アプリでオフライン操作がサポートされるように指定すると、ClickOnce により、ユーザーの **[スタート]** メニューにアプリへのリンクが追加されます。</span><span class="sxs-lookup"><span data-stu-id="21b0f-168">When you specify that an app should support offline operation, ClickOnce adds a link to your app in the user's **Start** menu.</span></span> <span data-ttu-id="21b0f-169">その後、ユーザーは、URL を使用せずにそのアプリを開くことができます。</span><span class="sxs-lookup"><span data-stu-id="21b0f-169">The user can then open the app without using the URL.</span></span>

<span data-ttu-id="21b0f-170">アプリを更新するときに、新しい配置マニフェストとアプリの新しいコピーを Web サーバーに発行します。</span><span class="sxs-lookup"><span data-stu-id="21b0f-170">When you update your app, you publish a new deployment manifest and a new copy of your app to your web server.</span></span> <span data-ttu-id="21b0f-171">ClickOnce により、使用可能な更新プログラムがあることが検出され、ユーザーのインストールがアップグレードされます。</span><span class="sxs-lookup"><span data-stu-id="21b0f-171">ClickOnce will detect that there is an update available and upgrade the user's installation.</span></span> <span data-ttu-id="21b0f-172">古いアプリを更新するためにカスタム プログラミングは必要ありません。</span><span class="sxs-lookup"><span data-stu-id="21b0f-172">No custom programming is required to update old apps.</span></span>

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

## <a name="see-also"></a><span data-ttu-id="21b0f-173">関連項目</span><span class="sxs-lookup"><span data-stu-id="21b0f-173">See also</span></span>

- [<span data-ttu-id="21b0f-174">チュートリアル: 新しい WinForms アプリを作成する (Windows フォーム .NET)</span><span class="sxs-lookup"><span data-stu-id="21b0f-174">Tutorial: Create a new WinForms app (Windows Forms .NET)</span></span>](../get-started/create-app-visual-studio.md)
- [<span data-ttu-id="21b0f-175">プロジェクトにフォームを追加する方法 (Windows フォーム .NET)</span><span class="sxs-lookup"><span data-stu-id="21b0f-175">How to add a form to a project (Windows Forms .NET)</span></span>](../forms/how-to-add.md)
- [<span data-ttu-id="21b0f-176">コントロールを追加する (Windows フォーム .NET)</span><span class="sxs-lookup"><span data-stu-id="21b0f-176">Add a control (Windows Forms .NET)</span></span>](../controls/how-to-add-to-a-form.md)
