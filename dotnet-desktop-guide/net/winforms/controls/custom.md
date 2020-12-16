---
title: カスタム コントロールの種類
description: .NET 用の Windows フォームで作成できるさまざまな種類のカスタム コントロールについて説明します。
ms.date: 10/26/2020
ms.topic: overview
f1_keywords:
- UserControl
helpviewer_keywords:
- controls [Windows Forms], user controls
- controls [Windows Forms], types of
- composite controls [Windows Forms]
- extended controls [Windows Forms]
- controls [Windows Forms], extended
- user controls [Windows Forms]
- custom controls [Windows Forms]
- controls [Windows Forms], composite
ms.openlocfilehash: 25430adf6efbb4c1f323496ce46cdea5aa0bb95c
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/09/2020
ms.locfileid: "96942274"
---
# <a name="types-of-custom-controls-windows-forms-net"></a><span data-ttu-id="d0bf8-103">カスタム コントロールの種類 (Windows フォーム .NET)</span><span class="sxs-lookup"><span data-stu-id="d0bf8-103">Types of custom controls (Windows Forms .NET)</span></span>

<span data-ttu-id="d0bf8-104">Windows フォームを使用して、新しいコントロールを開発し、実装できます。</span><span class="sxs-lookup"><span data-stu-id="d0bf8-104">With Windows Forms, you can develop and implement new controls.</span></span> <span data-ttu-id="d0bf8-105">新しいユーザー コントロールを作成し、継承によって既存のコントロールを変更し、独自のペインティングを実行するカスタム コントロールを作成することができます。</span><span class="sxs-lookup"><span data-stu-id="d0bf8-105">You can create a new user control, modify existing controls through inheritance, and write a custom control that does its own painting.</span></span>

[!INCLUDE [desktop guide under construction](../../includes/desktop-guide-preview-note.md)]

<span data-ttu-id="d0bf8-106">作成するコントロールの種類を決めるときに、判断に迷うことがあります。</span><span class="sxs-lookup"><span data-stu-id="d0bf8-106">Deciding which kind of control to create can be confusing.</span></span> <span data-ttu-id="d0bf8-107">この記事では、継承できる各種コントロールの違いを示し、プロジェクトに合わせて特定のタイプのコントロールを選択する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="d0bf8-107">This article highlights the differences among the various kinds of controls from which you can inherit, and provides you with information about how to choose a particular type of control for your project.</span></span>

<table>
<thead>
  <tr>
    <th><span data-ttu-id="d0bf8-108">次の場合</span><span class="sxs-lookup"><span data-stu-id="d0bf8-108">If ...</span></span></th>
    <th><span data-ttu-id="d0bf8-109">作成するもの</span><span class="sxs-lookup"><span data-stu-id="d0bf8-109">Create a ...</span></span></th>
  </tr>
</thead>
<tbody>
  <tr>
    <td>
        <ul>
            <li><span data-ttu-id="d0bf8-110">いくつかの Windows フォーム コントロールの機能を再利用可能な 1 つの単位に結合します。</span><span class="sxs-lookup"><span data-stu-id="d0bf8-110">You want to combine the functionality of several Windows Forms controls into a single reusable unit.</span></span></li>
        </ul>
    </td>
    <td><span data-ttu-id="d0bf8-111"><a href="#composite-controls">複合コントロール</a>。<a href="/dotnet/api/system.windows.forms.usercontrol">System.Windows.Forms.UserControl</a> から継承します。</span><span class="sxs-lookup"><span data-stu-id="d0bf8-111"><a href="#composite-controls">Composite control</a> by inheriting from <a href="/dotnet/api/system.windows.forms.usercontrol">System.Windows.Forms.UserControl</a>.</span></span></td>
  </tr>
  <tr>
    <td>
        <ul>
            <li><span data-ttu-id="d0bf8-112">必要とする機能のほとんどが、既存の Windows フォーム コントロールと同じです。</span><span class="sxs-lookup"><span data-stu-id="d0bf8-112">Most of the functionality you need is already identical to an existing Windows Forms control.</span></span></li>
            <li><span data-ttu-id="d0bf8-113">カスタムのグラフィカル ユーザー インターフェイスが不要な場合、または既存のコントロールの新しいグラフィカル ユーザー インターフェイスをデザインする場合。</span><span class="sxs-lookup"><span data-stu-id="d0bf8-113">You don't need a custom graphical user interface, or you want to design a new graphical user interface for an existing control.</span></span></li>
        </ul>
    </td>
    <td><span data-ttu-id="d0bf8-114"><a href="#extended-controls">拡張コントロール</a>。特定の Windows フォーム コントロールから継承します。</span><span class="sxs-lookup"><span data-stu-id="d0bf8-114"><a href="#extended-controls">Extended control</a> by inheriting from a specific Windows Forms control.</span></span></td>
  </tr>
  <tr>
    <td>
        <ul>
            <li><span data-ttu-id="d0bf8-115">コントロールのカスタムのグラフィカル表現を提供します。</span><span class="sxs-lookup"><span data-stu-id="d0bf8-115">You want to provide a custom graphical representation of your control.</span></span></li>
            <li><span data-ttu-id="d0bf8-116">標準コントロールでは使用できないカスタムの機能を実装する必要があります。</span><span class="sxs-lookup"><span data-stu-id="d0bf8-116">You need to implement custom functionality that isn't available through standard controls.</span></span></li>
        </ul>
    </td>
    <td><span data-ttu-id="d0bf8-117"><a href="#custom-controls">カスタム コントロール</a>。<a href="/dotnet/api/system.windows.forms.control">System.Windows.Forms.Control</a> から継承します。</span><span class="sxs-lookup"><span data-stu-id="d0bf8-117"><a href="#custom-controls">Custom control</a> by inheriting from <a href="/dotnet/api/system.windows.forms.control">System.Windows.Forms.Control</a>.</span></span></td>
  </tr>
</tbody>
</table>

## <a name="base-control-class"></a><span data-ttu-id="d0bf8-118">基本コントロール クラス</span><span class="sxs-lookup"><span data-stu-id="d0bf8-118">Base Control Class</span></span>

<span data-ttu-id="d0bf8-119"><xref:System.Windows.Forms.Control> クラスは、Windows フォーム コントロールの基底クラスです。</span><span class="sxs-lookup"><span data-stu-id="d0bf8-119">The <xref:System.Windows.Forms.Control> class is the base class for Windows Forms controls.</span></span> <span data-ttu-id="d0bf8-120">Windows フォーム アプリケーションでのビジュアル表示に必要なインフラストラクチャが提供され、さらに以下の機能が提供されます。</span><span class="sxs-lookup"><span data-stu-id="d0bf8-120">It provides the infrastructure required for visual display in Windows Forms applications and provides the following capabilities:</span></span>

- <span data-ttu-id="d0bf8-121">ウィンドウ ハンドルを公開する。</span><span class="sxs-lookup"><span data-stu-id="d0bf8-121">Exposes a window handle.</span></span>
- <span data-ttu-id="d0bf8-122">メッセージ ルーティングを管理する。</span><span class="sxs-lookup"><span data-stu-id="d0bf8-122">Manages message routing.</span></span>
- <span data-ttu-id="d0bf8-123">マウス イベントとキーボード イベント、および他のさまざまなユーザー インターフェイス イベントを提供する。</span><span class="sxs-lookup"><span data-stu-id="d0bf8-123">Provides mouse and keyboard events, and many other user interface events.</span></span>
- <span data-ttu-id="d0bf8-124">高度なレイアウト機能を提供する。</span><span class="sxs-lookup"><span data-stu-id="d0bf8-124">Provides advanced layout features.</span></span>
- <span data-ttu-id="d0bf8-125"><xref:System.Windows.Forms.Control.ForeColor%2A>、<xref:System.Windows.Forms.Control.BackColor%2A>、<xref:System.Windows.Forms.Control.Height%2A>、<xref:System.Windows.Forms.Control.Width%2A> など、ビジュアル表示に固有の多くのプロパティを含む。</span><span class="sxs-lookup"><span data-stu-id="d0bf8-125">Contains many properties specific to visual display, such as <xref:System.Windows.Forms.Control.ForeColor%2A>, <xref:System.Windows.Forms.Control.BackColor%2A>, <xref:System.Windows.Forms.Control.Height%2A>, and <xref:System.Windows.Forms.Control.Width%2A>.</span></span>
- <span data-ttu-id="d0bf8-126">Windows フォーム コントロールが Microsoft® ActiveX® コントロールとして機能するために必要なセキュリティとスレッドのサポートを提供する。</span><span class="sxs-lookup"><span data-stu-id="d0bf8-126">Provides the security and threading support necessary for a Windows Forms control to act as a Microsoft® ActiveX® control.</span></span>

<span data-ttu-id="d0bf8-127">インフラストラクチャの大部分は基底クラスによって提供されるため、独自の Windows フォーム コントロールを比較的簡単に開発できます。</span><span class="sxs-lookup"><span data-stu-id="d0bf8-127">Because so much of the infrastructure is provided by the base class, it's relatively easy to develop your own Windows Forms controls.</span></span>

## <a name="composite-controls"></a><span data-ttu-id="d0bf8-128">複合コントロール</span><span class="sxs-lookup"><span data-stu-id="d0bf8-128">Composite Controls</span></span>

<span data-ttu-id="d0bf8-129">複合コントロールは、共通のコンテナーにカプセル化された Windows フォーム コントロールのコレクションです。</span><span class="sxs-lookup"><span data-stu-id="d0bf8-129">A composite control is a collection of Windows Forms controls encapsulated in a common container.</span></span> <span data-ttu-id="d0bf8-130">この種のコントロールは、*ユーザー コントロール* とも呼ばれます。</span><span class="sxs-lookup"><span data-stu-id="d0bf8-130">This kind of control is sometimes called a *user control*.</span></span> <span data-ttu-id="d0bf8-131">含まれているコントロールは、*内在コントロール* と呼ばれます。</span><span class="sxs-lookup"><span data-stu-id="d0bf8-131">The contained controls are called *constituent controls*.</span></span>

<span data-ttu-id="d0bf8-132">複合コントロールは、含まれている各 Windows フォーム コントロールに関連する固有の機能をすべて保持し、それらのプロパティを選択的に公開してバインドできます。</span><span class="sxs-lookup"><span data-stu-id="d0bf8-132">A composite control holds all of the inherent functionality associated with each of the contained Windows Forms controls and enables you to selectively expose and bind their properties.</span></span> <span data-ttu-id="d0bf8-133">また、開発者側での追加作業を必要としない多数の既定のキーボード処理機能も提供します。</span><span class="sxs-lookup"><span data-stu-id="d0bf8-133">A composite control also provides a great deal of default keyboard handling functionality with no extra development effort on your part.</span></span>

<span data-ttu-id="d0bf8-134">たとえば、データベースの顧客の住所データを表示する複合コントロールを作成できます。</span><span class="sxs-lookup"><span data-stu-id="d0bf8-134">For example, a composite control could be built to display customer address data from a database.</span></span> <span data-ttu-id="d0bf8-135">このコントロールには、データベース フィールドを表示するための <xref:System.Windows.Forms.DataGridView> コントロール、データ ソースへのバインドを処理するための <xref:System.Windows.Forms.BindingSource>、およびレコード間を移動するための <xref:System.Windows.Forms.BindingNavigator> コントロールが含まれます。</span><span class="sxs-lookup"><span data-stu-id="d0bf8-135">This control would include a <xref:System.Windows.Forms.DataGridView> control to display the database fields, a <xref:System.Windows.Forms.BindingSource> to handle binding to a data source, and a <xref:System.Windows.Forms.BindingNavigator> control to move through the records.</span></span> <span data-ttu-id="d0bf8-136">データ バインディング プロパティを選択的に公開したり、コントロール全体をパッケージ化してアプリケーション間で再利用したりできます。</span><span class="sxs-lookup"><span data-stu-id="d0bf8-136">You could selectively expose data binding properties, and you could package and reuse the entire control from application to application.</span></span><!-- TODO For an example of this kind of composite control, see [How to: Apply Attributes in Windows Forms Controls](how-to-apply-attributes-in-windows-forms-controls.md).-->

<span data-ttu-id="d0bf8-137">複合コントロールを作成するには、<xref:System.Windows.Forms.UserControl> クラスから派生させます。</span><span class="sxs-lookup"><span data-stu-id="d0bf8-137">To author a composite control, derive from the <xref:System.Windows.Forms.UserControl> class.</span></span> <span data-ttu-id="d0bf8-138"><xref:System.Windows.Forms.UserControl> 基底クラスは、子コントロールに対してキーボード ルーティングを提供し、複数の子コントロールを 1 つのグループとして機能させることができます。</span><span class="sxs-lookup"><span data-stu-id="d0bf8-138">The <xref:System.Windows.Forms.UserControl> base class provides keyboard routing for child controls and enables child controls to work as a group.</span></span><!-- TODO For more information, see [Developing a Composite Windows Forms Control](developing-a-composite-windows-forms-control.md).-->

## <a name="extended-controls"></a><span data-ttu-id="d0bf8-139">拡張コントロール</span><span class="sxs-lookup"><span data-stu-id="d0bf8-139">Extended Controls</span></span>

<span data-ttu-id="d0bf8-140">既存の Windows フォーム コントロールから継承されたコントロールを派生できます。</span><span class="sxs-lookup"><span data-stu-id="d0bf8-140">You can derive an inherited control from any existing Windows Forms control.</span></span> <span data-ttu-id="d0bf8-141">この方法では、Windows フォーム コントロールの固有の機能をすべて保持し、カスタム プロパティ、メソッドなどの機能を追加してその機能を拡張できます。</span><span class="sxs-lookup"><span data-stu-id="d0bf8-141">With this approach, you can keep all of the inherent functionality of a Windows Forms control, and then extend that functionality by adding custom properties, methods, or other features.</span></span> <span data-ttu-id="d0bf8-142">この方法を使用して、基本コントロールの描画ロジックをオーバーライドし、そのユーザー インターフェイスの外観を変更して拡張できます。</span><span class="sxs-lookup"><span data-stu-id="d0bf8-142">With this option, you can override the base control's paint logic, and then extend its user interface by changing its appearance.</span></span>

<span data-ttu-id="d0bf8-143">たとえば、ユーザーがクリックした回数を追跡する、<xref:System.Windows.Forms.Button> コントロールから派生したコントロールを作成できます。</span><span class="sxs-lookup"><span data-stu-id="d0bf8-143">For example, you can create a control derived from the <xref:System.Windows.Forms.Button> control that tracks how many times a user has clicked it.</span></span>

<span data-ttu-id="d0bf8-144">一部のコントロールでは、基底クラスの <xref:System.Windows.Forms.Control.OnPaint%2A> メソッドをオーバーライドすることで、コントロールのグラフィカル ユーザー インターフェイスにカスタムの外観を追加することもできます。</span><span class="sxs-lookup"><span data-stu-id="d0bf8-144">In some controls, you can also add a custom appearance to the graphical user interface of your control by overriding the <xref:System.Windows.Forms.Control.OnPaint%2A> method of the base class.</span></span> <span data-ttu-id="d0bf8-145">クリックを追跡する拡張ボタンの場合は、<xref:System.Windows.Forms.Control.OnPaint%2A> メソッドをオーバーライドして <xref:System.Windows.Forms.Control.OnPaint%2A> の基本実装を呼び出し、<xref:System.Windows.Forms.Button> コントロールのクライアント領域の 1 つの隅にクリック数を描画します。</span><span class="sxs-lookup"><span data-stu-id="d0bf8-145">For an extended button that tracks clicks, you can override the <xref:System.Windows.Forms.Control.OnPaint%2A> method to call the base implementation of <xref:System.Windows.Forms.Control.OnPaint%2A>, and then draw the click count in one corner of the <xref:System.Windows.Forms.Button> control's client area.</span></span>

## <a name="custom-controls"></a><span data-ttu-id="d0bf8-146">カスタム コントロール</span><span class="sxs-lookup"><span data-stu-id="d0bf8-146">Custom Controls</span></span>

<span data-ttu-id="d0bf8-147">コントロールを作成する別の方法は、<xref:System.Windows.Forms.Control> から継承することで、実質的に一から作成する方法です。</span><span class="sxs-lookup"><span data-stu-id="d0bf8-147">Another way to create a control is to create one substantially from the beginning by inheriting from <xref:System.Windows.Forms.Control>.</span></span> <span data-ttu-id="d0bf8-148"><xref:System.Windows.Forms.Control> クラスは、コントロールで必要とされるすべての基本的な機能 (マウスやキーボードの処理イベントなど) を提供しますが、コントロール固有の機能やグラフィカル インターフェイスは提供しません。</span><span class="sxs-lookup"><span data-stu-id="d0bf8-148">The <xref:System.Windows.Forms.Control> class provides all of the basic functionality required by controls, including mouse and keyboard handling events, but no control-specific functionality or graphical interface.</span></span>

<span data-ttu-id="d0bf8-149"><xref:System.Windows.Forms.Control> クラスから継承することでコントロールを作成する場合は、<xref:System.Windows.Forms.UserControl> や既存の Windows フォーム コントロールから継承する場合よりも、はるかに多くの配慮と労力が必要です。</span><span class="sxs-lookup"><span data-stu-id="d0bf8-149">Creating a control by inheriting from the <xref:System.Windows.Forms.Control> class requires much more thought and effort than inheriting from <xref:System.Windows.Forms.UserControl> or an existing Windows Forms control.</span></span> <span data-ttu-id="d0bf8-150">多くの実装が開発者に委ねられるため、作成されるコントロールは、複合コントロールや拡張コントロールよりも柔軟性に優れ、ニーズに合わせてコントロールを調整できます。</span><span class="sxs-lookup"><span data-stu-id="d0bf8-150">Because a great deal of implementation is left for you, your control can have greater flexibility than a composite or extended control, and you can tailor your control to suit your exact needs.</span></span>

<span data-ttu-id="d0bf8-151">カスタム コントロールを実装するには、コントロールの <xref:System.Windows.Forms.Control.OnPaint%2A> イベントのコードと、必要な機能固有のコードを作成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="d0bf8-151">To implement a custom control, you must write code for the <xref:System.Windows.Forms.Control.OnPaint%2A> event of the control, as well as any feature-specific code you need.</span></span> <span data-ttu-id="d0bf8-152">また、<xref:System.Windows.Forms.Control.WndProc%2A> メソッドをオーバーライドして、Windows メッセージを直接処理することもできます。</span><span class="sxs-lookup"><span data-stu-id="d0bf8-152">You can also override the <xref:System.Windows.Forms.Control.WndProc%2A> method and handle windows messages directly.</span></span> <span data-ttu-id="d0bf8-153">これはコントロールを作成する最も強力な方法ですが、この手法を効果的に使用するには、Microsoft Win32® API を十分に理解している必要があります。</span><span class="sxs-lookup"><span data-stu-id="d0bf8-153">This is the most powerful way to create a control, but to use this technique effectively, you need to be familiar with the Microsoft Win32® API.</span></span>

<span data-ttu-id="d0bf8-154">カスタム コントロールの例として、アナログ時計の外観と動作を複製した時計コントロールがあります。</span><span class="sxs-lookup"><span data-stu-id="d0bf8-154">An example of a custom control is a clock control that duplicates the appearance and behavior of an analog clock.</span></span> <span data-ttu-id="d0bf8-155">内部 <xref:System.Windows.Forms.Timer> コンポーネントからの <xref:System.Windows.Forms.Timer.Tick> イベントに応答してカスタム ペインティングが呼び出されて、時計の針が移動します。</span><span class="sxs-lookup"><span data-stu-id="d0bf8-155">Custom painting is invoked to cause the hands of the clock to move in response to <xref:System.Windows.Forms.Timer.Tick> events from an internal <xref:System.Windows.Forms.Timer> component.</span></span><!-- TODO For more information, see [How to: Develop a Simple Windows Forms Control](how-to-develop-a-simple-windows-forms-control.md).-->

## <a name="activex-controls"></a><span data-ttu-id="d0bf8-156">ActiveX コントロール</span><span class="sxs-lookup"><span data-stu-id="d0bf8-156">ActiveX Controls</span></span>

<span data-ttu-id="d0bf8-157">Windows フォーム インストラクチャは、Windows フォーム コントロールをホストするために最適化されていますが、ActiveX コントロールを使用することもできます。</span><span class="sxs-lookup"><span data-stu-id="d0bf8-157">Although the Windows Forms infrastructure has been optimized to host Windows Forms controls, you can still use ActiveX controls.</span></span> <span data-ttu-id="d0bf8-158">Visual Studio では、このタスクに対するサポートが用意されています。</span><span class="sxs-lookup"><span data-stu-id="d0bf8-158">There's support for this task in Visual Studio.</span></span><!-- TODO For more information, see [How to: Add ActiveX Controls to Windows Forms](how-to-add-activex-controls-to-windows-forms.md).-->

## <a name="windowless-controls"></a><span data-ttu-id="d0bf8-159">ウィンドウなしのコントロール</span><span class="sxs-lookup"><span data-stu-id="d0bf8-159">Windowless Controls</span></span>

<span data-ttu-id="d0bf8-160">Microsoft Visual Basic® 6.0 と ActiveX テクノロジは、"*ウィンドウなし*" のコントロールをサポートします。</span><span class="sxs-lookup"><span data-stu-id="d0bf8-160">The Microsoft Visual Basic® 6.0 and ActiveX technologies support *windowless* controls.</span></span> <span data-ttu-id="d0bf8-161">ウィンドウなしのコントロールは、Windows フォームではサポートされていません。</span><span class="sxs-lookup"><span data-stu-id="d0bf8-161">Windowless controls aren't supported in Windows Forms.</span></span>

## <a name="custom-design-experience"></a><span data-ttu-id="d0bf8-162">カスタム デザイン エクスペリエンス</span><span class="sxs-lookup"><span data-stu-id="d0bf8-162">Custom Design Experience</span></span>

<span data-ttu-id="d0bf8-163">カスタムのデザイン時エクスペリエンスを実装する必要がある場合は、独自のデザイナーを作成できます。</span><span class="sxs-lookup"><span data-stu-id="d0bf8-163">If you need to implement a custom design-time experience, you can author your own designer.</span></span> <span data-ttu-id="d0bf8-164">複合コントロールの場合は、<xref:System.Windows.Forms.Design.ParentControlDesigner> または <xref:System.Windows.Forms.Design.DocumentDesigner> クラスからカスタム デザイナー クラスを派生させます。</span><span class="sxs-lookup"><span data-stu-id="d0bf8-164">For composite controls, derive your custom designer class from the <xref:System.Windows.Forms.Design.ParentControlDesigner> or the <xref:System.Windows.Forms.Design.DocumentDesigner> classes.</span></span> <span data-ttu-id="d0bf8-165">拡張およびカスタム コントロールの場合は、<xref:System.Windows.Forms.Design.ControlDesigner> クラスからカスタム デザイナー クラスを派生させます。</span><span class="sxs-lookup"><span data-stu-id="d0bf8-165">For extended and custom controls, derive your custom designer class from the <xref:System.Windows.Forms.Design.ControlDesigner> class.</span></span>

<span data-ttu-id="d0bf8-166">コントロールをデザイナーに関連付けるには、<xref:System.ComponentModel.DesignerAttribute> を使用します。</span><span class="sxs-lookup"><span data-stu-id="d0bf8-166">Use the <xref:System.ComponentModel.DesignerAttribute> to associate your control with your designer.</span></span>

<span data-ttu-id="d0bf8-167">次の情報は最新ではありませんが、役に立ちます。</span><span class="sxs-lookup"><span data-stu-id="d0bf8-167">The following information is out of date but may help you.</span></span>

- <span data-ttu-id="d0bf8-168">[(Visual Studio 2013) デザイン時サポートの拡張](/previous-versions/visualstudio/visual-studio-2013/37899azc(v=vs.120)).</span><span class="sxs-lookup"><span data-stu-id="d0bf8-168">[(Visual Studio 2013) Extending Design-Time Support](/previous-versions/visualstudio/visual-studio-2013/37899azc(v=vs.120)).</span></span>
- <span data-ttu-id="d0bf8-169">[(Visual Studio 2013) 方法: デザイン時機能を活用した Windows フォーム コントロールを作成する](/previous-versions/visualstudio/visual-studio-2013/307hck25(v=vs.120))</span><span class="sxs-lookup"><span data-stu-id="d0bf8-169">[(Visual Studio 2013) How to: Create a Windows Forms Control That Takes Advantage of Design-Time Features](/previous-versions/visualstudio/visual-studio-2013/307hck25(v=vs.120)).</span></span>

## <a name="see-also"></a><span data-ttu-id="d0bf8-170">関連項目</span><span class="sxs-lookup"><span data-stu-id="d0bf8-170">See also</span></span>

- [<span data-ttu-id="d0bf8-171">コントロールの使用の概要 (Windows フォーム .NET)</span><span class="sxs-lookup"><span data-stu-id="d0bf8-171">Overview of Using Controls (Windows Forms .NET)</span></span>](overview.md)

<!-- TODO: link to the ..\custom-controls\ content 

- [Developing Custom Windows Forms Controls](developing-custom-windows-forms-controls.md)
- [How to: Develop a Simple Windows Forms Control](how-to-develop-a-simple-windows-forms-control.md)
- [Developing a Composite Windows Forms Control](developing-a-composite-windows-forms-control.md)
-->
