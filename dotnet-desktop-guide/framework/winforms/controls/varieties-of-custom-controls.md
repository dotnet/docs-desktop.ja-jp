---
title: さまざまなカスタム コントロール
ms.date: 03/30/2017
ms.topic: overview
helpviewer_keywords:
- controls [Windows Forms], user controls
- controls [Windows Forms], types of
- composite controls [Windows Forms]
- extended controls [Windows Forms]
- controls [Windows Forms], extended
- user controls [Windows Forms]
- custom controls [Windows Forms]
- controls [Windows Forms], composite
ms.assetid: 3cea09e5-4344-4ccb-9858-b66ccac210ff
ms.openlocfilehash: e43b9a3fafd52c66681d4d6bbdd0e9bc39c6788a
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/09/2020
ms.locfileid: "96983928"
---
# <a name="varieties-of-custom-controls"></a><span data-ttu-id="83baf-102">さまざまなカスタム コントロール</span><span class="sxs-lookup"><span data-stu-id="83baf-102">Varieties of Custom Controls</span></span>

<span data-ttu-id="83baf-103">.NET Framework を使用して、新しいコントロールを開発し、実装できます。</span><span class="sxs-lookup"><span data-stu-id="83baf-103">With the .NET Framework, you can develop and implement new controls.</span></span> <span data-ttu-id="83baf-104">継承によって、使い慣れたユーザー コントロールや既存のコントロールの機能を拡張できます。</span><span class="sxs-lookup"><span data-stu-id="83baf-104">You can extend the functionality of the familiar user control as well as existing controls through inheritance.</span></span> <span data-ttu-id="83baf-105">また、独自の描画を実行するカスタム コントロールを作成することもできます。</span><span class="sxs-lookup"><span data-stu-id="83baf-105">You can also write custom controls that perform their own painting.</span></span>  
  
 <span data-ttu-id="83baf-106">作成するコントロールの種類を決めるときに、判断に迷うことがあります。</span><span class="sxs-lookup"><span data-stu-id="83baf-106">Deciding which kind of control to create can be confusing.</span></span> <span data-ttu-id="83baf-107">このトピックでは、継承できる各種コントロールの違いを示し、プロジェクトに合わせて特定の種類のコントロールを選択する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="83baf-107">This topic highlights the differences among the various kinds of controls from which you can inherit, and provides you with information about how to choose a particular kind of control for your project.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="83baf-108">Web フォームで使用するコントロールを作成する方法については、「[カスタム ASP.NET サーバー コントロールの開発](/previous-versions/aspnet/zt27tfhy(v=vs.100))」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="83baf-108">For information about authoring a control to use on Web Forms, see [Developing Custom ASP.NET Server Controls](/previous-versions/aspnet/zt27tfhy(v=vs.100)).</span></span>  
  
## <a name="base-control-class"></a><span data-ttu-id="83baf-109">基本コントロール クラス</span><span class="sxs-lookup"><span data-stu-id="83baf-109">Base Control Class</span></span>  

 <span data-ttu-id="83baf-110">クラスは、 <xref:System.Windows.Forms.Control> Windows フォームコントロールの基本クラスです。</span><span class="sxs-lookup"><span data-stu-id="83baf-110">The <xref:System.Windows.Forms.Control> class is the base class for Windows Forms controls.</span></span> <span data-ttu-id="83baf-111">このクラスは、Windows フォーム アプリケーションでのビジュアル表示に必要なインフラストラクチャを提供します。</span><span class="sxs-lookup"><span data-stu-id="83baf-111">It provides the infrastructure required for visual display in Windows Forms applications.</span></span>  
  
 <span data-ttu-id="83baf-112">クラスは、 <xref:System.Windows.Forms.Control> 次のタスクを実行して Windows フォームアプリケーションで視覚的な表示を提供します。</span><span class="sxs-lookup"><span data-stu-id="83baf-112">The <xref:System.Windows.Forms.Control> class performs the following tasks to provide visual display in Windows Forms applications:</span></span>  
  
- <span data-ttu-id="83baf-113">ウィンドウ ハンドルを公開する。</span><span class="sxs-lookup"><span data-stu-id="83baf-113">Exposes a window handle.</span></span>  
  
- <span data-ttu-id="83baf-114">メッセージ ルーティングを管理する。</span><span class="sxs-lookup"><span data-stu-id="83baf-114">Manages message routing.</span></span>  
  
- <span data-ttu-id="83baf-115">マウス イベントとキーボード イベント、および他のさまざまなユーザー インターフェイス イベントを提供する。</span><span class="sxs-lookup"><span data-stu-id="83baf-115">Provides mouse and keyboard events, and many other user interface events.</span></span>  
  
- <span data-ttu-id="83baf-116">高度なレイアウト機能を提供する。</span><span class="sxs-lookup"><span data-stu-id="83baf-116">Provides advanced layout features.</span></span>  
  
- <span data-ttu-id="83baf-117">には、、、、など、ビジュアル表示に固有の多くのプロパティが含まれてい <xref:System.Windows.Forms.Control.ForeColor%2A> <xref:System.Windows.Forms.Control.BackColor%2A> <xref:System.Windows.Forms.Control.Height%2A> <xref:System.Windows.Forms.Control.Width%2A> ます。</span><span class="sxs-lookup"><span data-stu-id="83baf-117">Contains many properties specific to visual display, such as <xref:System.Windows.Forms.Control.ForeColor%2A>, <xref:System.Windows.Forms.Control.BackColor%2A>, <xref:System.Windows.Forms.Control.Height%2A>, and <xref:System.Windows.Forms.Control.Width%2A>.</span></span>  
  
- <span data-ttu-id="83baf-118">Windows フォーム コントロールが Microsoft® ActiveX® コントロールとして機能するために必要なセキュリティとスレッドのサポートを提供する。</span><span class="sxs-lookup"><span data-stu-id="83baf-118">Provides the security and threading support necessary for a Windows Forms control to act as a Microsoft® ActiveX® control.</span></span>  
  
 <span data-ttu-id="83baf-119">インフラストラクチャの大部分は基本クラスによって提供されるため、独自の Windows フォーム コントロールを比較的簡単に開発できます。</span><span class="sxs-lookup"><span data-stu-id="83baf-119">Because so much of the infrastructure is provided by the base class, it is relatively easy to develop your own Windows Forms controls.</span></span>  
  
## <a name="kinds-of-controls"></a><span data-ttu-id="83baf-120">コントロールの種類</span><span class="sxs-lookup"><span data-stu-id="83baf-120">Kinds of Controls</span></span>  

 <span data-ttu-id="83baf-121">Windows フォームは、*複合*、*拡張*、*カスタム* の 3 種類のユーザー定義コントロールをサポートします。</span><span class="sxs-lookup"><span data-stu-id="83baf-121">Windows Forms supports three kinds of user-defined controls: *composite*, *extended*, and *custom*.</span></span> <span data-ttu-id="83baf-122">以下のセクションでは、各種コントロールについて説明し、プロジェクトで使用する種類を選択する際の推奨事項を示します。</span><span class="sxs-lookup"><span data-stu-id="83baf-122">The following sections describe each kind of control and give recommendations for choosing the kind to use in your projects.</span></span>  
  
### <a name="composite-controls"></a><span data-ttu-id="83baf-123">複合コントロール</span><span class="sxs-lookup"><span data-stu-id="83baf-123">Composite Controls</span></span>  

 <span data-ttu-id="83baf-124">複合コントロールは、共通のコンテナーにカプセル化された Windows フォーム コントロールのコレクションです。</span><span class="sxs-lookup"><span data-stu-id="83baf-124">A composite control is a collection of Windows Forms controls encapsulated in a common container.</span></span> <span data-ttu-id="83baf-125">この種のコントロールは、*ユーザー コントロール* とも呼ばれます。</span><span class="sxs-lookup"><span data-stu-id="83baf-125">This kind of control is sometimes called a *user control*.</span></span> <span data-ttu-id="83baf-126">含まれているコントロールは、*内在コントロール* と呼ばれます。</span><span class="sxs-lookup"><span data-stu-id="83baf-126">The contained controls are called *constituent controls*.</span></span>  
  
 <span data-ttu-id="83baf-127">複合コントロールは、含まれている各 Windows フォーム コントロールに関連する固有の機能をすべて保持し、それらのプロパティを選択的に公開してバインドできます。</span><span class="sxs-lookup"><span data-stu-id="83baf-127">A composite control holds all of the inherent functionality associated with each of the contained Windows Forms controls and enables you to selectively expose and bind their properties.</span></span> <span data-ttu-id="83baf-128">また、開発者側での追加作業を必要としない多数の既定のキーボード処理機能も提供します。</span><span class="sxs-lookup"><span data-stu-id="83baf-128">A composite control also provides a great deal of default keyboard handling functionality with no extra development effort on your part.</span></span>  
  
 <span data-ttu-id="83baf-129">たとえば、データベースの顧客の住所データを表示する複合コントロールを作成できます。</span><span class="sxs-lookup"><span data-stu-id="83baf-129">For example, a composite control could be built to display customer address data from a database.</span></span> <span data-ttu-id="83baf-130">このコントロールには、 <xref:System.Windows.Forms.DataGridView> データベースフィールドを表示するコントロール、 <xref:System.Windows.Forms.BindingSource> データソースへのバインドを処理するためのコントロール、およびレコード間を移動するコントロールを含めることができ <xref:System.Windows.Forms.BindingNavigator> ます。</span><span class="sxs-lookup"><span data-stu-id="83baf-130">This control could include a <xref:System.Windows.Forms.DataGridView> control to display the database fields, a <xref:System.Windows.Forms.BindingSource> to handle binding to a data source, and a <xref:System.Windows.Forms.BindingNavigator> control to move through the records.</span></span> <span data-ttu-id="83baf-131">データ バインディング プロパティを選択的に公開したり、コントロール全体をパッケージ化してアプリケーション間で再利用したりできます。</span><span class="sxs-lookup"><span data-stu-id="83baf-131">You could selectively expose data binding properties, and you could package and reuse the entire control from application to application.</span></span> <span data-ttu-id="83baf-132">この種の複合コントロールの例については、「[方法 : Windows フォーム コントロールに属性を適用する](how-to-apply-attributes-in-windows-forms-controls.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="83baf-132">For an example of this kind of composite control, see [How to: Apply Attributes in Windows Forms Controls](how-to-apply-attributes-in-windows-forms-controls.md).</span></span>  
  
 <span data-ttu-id="83baf-133">複合コントロールを作成するには、クラスから派生させ <xref:System.Windows.Forms.UserControl> ます。</span><span class="sxs-lookup"><span data-stu-id="83baf-133">To author a composite control, derive from the <xref:System.Windows.Forms.UserControl> class.</span></span> <span data-ttu-id="83baf-134"><xref:System.Windows.Forms.UserControl>基本クラスは、子コントロールのキーボードルーティングを提供し、子コントロールがグループとして機能できるようにします。</span><span class="sxs-lookup"><span data-stu-id="83baf-134">The <xref:System.Windows.Forms.UserControl> base class provides keyboard routing for child controls and enables child controls to work as a group.</span></span> <span data-ttu-id="83baf-135">詳細については、「[複合 Windows フォーム コントロールの開発](developing-a-composite-windows-forms-control.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="83baf-135">For more information, see [Developing a Composite Windows Forms Control](developing-a-composite-windows-forms-control.md).</span></span>  
  
 <span data-ttu-id="83baf-136">**推奨**</span><span class="sxs-lookup"><span data-stu-id="83baf-136">**Recommendation**</span></span>  
  
 <span data-ttu-id="83baf-137">次の場合に、<xref:System.Windows.Forms.UserControl> クラスから継承します。</span><span class="sxs-lookup"><span data-stu-id="83baf-137">Inherit from the <xref:System.Windows.Forms.UserControl> class if:</span></span>  
  
- <span data-ttu-id="83baf-138">いくつかの Windows フォーム コントロールの機能を再利用可能な 1 つの単位に結合します。</span><span class="sxs-lookup"><span data-stu-id="83baf-138">You want to combine the functionality of several Windows Forms controls into a single reusable unit.</span></span>  
  
### <a name="extended-controls"></a><span data-ttu-id="83baf-139">拡張コントロール</span><span class="sxs-lookup"><span data-stu-id="83baf-139">Extended Controls</span></span>  

 <span data-ttu-id="83baf-140">既存の Windows フォーム コントロールから継承されたコントロールを派生できます。</span><span class="sxs-lookup"><span data-stu-id="83baf-140">You can derive an inherited control from any existing Windows Forms control.</span></span> <span data-ttu-id="83baf-141">この方法では、Windows フォーム コントロールの固有の機能をすべて保持し、カスタム プロパティやカスタム メソッドなどの機能を追加してその機能を拡張できます。</span><span class="sxs-lookup"><span data-stu-id="83baf-141">With this approach, you can retain all of the inherent functionality of a Windows Forms control, and then extend that functionality by adding custom properties, methods, or other features.</span></span> <span data-ttu-id="83baf-142">この方法を使用して、基本コントロールの描画ロジックをオーバーライドし、そのユーザー インターフェイスの外観を変更して拡張できます。</span><span class="sxs-lookup"><span data-stu-id="83baf-142">With this option, you can override the base control's paint logic, and then extend its user interface by changing its appearance.</span></span>  
  
 <span data-ttu-id="83baf-143">たとえば、 <xref:System.Windows.Forms.Button> ユーザーがクリックした回数を追跡するコントロールから派生したコントロールを作成できます。</span><span class="sxs-lookup"><span data-stu-id="83baf-143">For example, you can create a control derived from the <xref:System.Windows.Forms.Button> control that tracks how many times a user has clicked it.</span></span>  
  
 <span data-ttu-id="83baf-144">コントロールによっては、基本クラスのメソッドをオーバーライドすることによって、コントロールのグラフィカルユーザーインターフェイスにカスタムの外観を追加することもでき <xref:System.Windows.Forms.Control.OnPaint%2A> ます。</span><span class="sxs-lookup"><span data-stu-id="83baf-144">In some controls, you can also add a custom appearance to the graphical user interface of your control by overriding the <xref:System.Windows.Forms.Control.OnPaint%2A> method of the base class.</span></span> <span data-ttu-id="83baf-145">クリックを追跡する拡張ボタンでは、メソッドをオーバーライドして <xref:System.Windows.Forms.Control.OnPaint%2A> の基本実装を呼び出し <xref:System.Windows.Forms.Control.OnPaint%2A> てから、 <xref:System.Windows.Forms.Button> コントロールのクライアント領域の1つの隅にクリック数を描画できます。</span><span class="sxs-lookup"><span data-stu-id="83baf-145">For an extended button that tracks clicks, you can override the <xref:System.Windows.Forms.Control.OnPaint%2A> method to call the base implementation of <xref:System.Windows.Forms.Control.OnPaint%2A>, and then draw the click count in one corner of the <xref:System.Windows.Forms.Button> control's client area.</span></span>  
  
 <span data-ttu-id="83baf-146">**推奨**</span><span class="sxs-lookup"><span data-stu-id="83baf-146">**Recommendation**</span></span>  
  
 <span data-ttu-id="83baf-147">次の場合に、Windows フォーム コントロールから継承します。</span><span class="sxs-lookup"><span data-stu-id="83baf-147">Inherit from a Windows Forms control if:</span></span>  
  
- <span data-ttu-id="83baf-148">必要とする機能のほとんどが、既存の Windows フォーム コントロールと同じです。</span><span class="sxs-lookup"><span data-stu-id="83baf-148">Most of the functionality you need is already identical to an existing Windows Forms control.</span></span>  
  
- <span data-ttu-id="83baf-149">カスタムのグラフィカル ユーザー インターフェイスが不要な場合、または既存のコントロールの新しいグラフィカル ユーザー インターフェイスをデザインする場合。</span><span class="sxs-lookup"><span data-stu-id="83baf-149">You do not need a custom graphical user interface, or you want to design a new graphical user interface for an existing control.</span></span>  
  
### <a name="custom-controls"></a><span data-ttu-id="83baf-150">カスタム コントロール</span><span class="sxs-lookup"><span data-stu-id="83baf-150">Custom Controls</span></span>  

 <span data-ttu-id="83baf-151">コントロールを作成するもう1つの方法は、から継承することによって最初から作成することです <xref:System.Windows.Forms.Control> 。</span><span class="sxs-lookup"><span data-stu-id="83baf-151">Another way to create a control is to create one substantially from the beginning by inheriting from <xref:System.Windows.Forms.Control>.</span></span> <span data-ttu-id="83baf-152">クラスは、 <xref:System.Windows.Forms.Control> マウスやキーボードの処理イベントなど、コントロールに必要なすべての基本機能を提供しますが、コントロール固有の機能やグラフィカルインターフェイスは提供しません。</span><span class="sxs-lookup"><span data-stu-id="83baf-152">The <xref:System.Windows.Forms.Control> class provides all of the basic functionality required by controls, including mouse and keyboard handling events, but no control-specific functionality or graphical interface.</span></span>  
  
 <span data-ttu-id="83baf-153">クラスから継承することによってコントロールを作成する <xref:System.Windows.Forms.Control> 場合 <xref:System.Windows.Forms.UserControl> は、または既存の Windows フォームコントロールから継承するよりもはるかに多くの思考と労力が必要です。</span><span class="sxs-lookup"><span data-stu-id="83baf-153">Creating a control by inheriting from the <xref:System.Windows.Forms.Control> class requires much more thought and effort than inheriting from <xref:System.Windows.Forms.UserControl> or an existing Windows Forms control.</span></span> <span data-ttu-id="83baf-154">多くの実装が開発者に委ねられるため、作成されるコントロールは、複合コントロールや拡張コントロールよりも柔軟性に優れ、ニーズに合わせてコントロールを調整できます。</span><span class="sxs-lookup"><span data-stu-id="83baf-154">Because a great deal of implementation is left for you, your control can have greater flexibility than a composite or extended control, and you can tailor your control to suit your exact needs.</span></span>  
  
 <span data-ttu-id="83baf-155">カスタムコントロールを実装するには、 <xref:System.Windows.Forms.Control.OnPaint%2A> 必要な機能固有のコードだけでなく、コントロールのイベントのコードも記述する必要があります。</span><span class="sxs-lookup"><span data-stu-id="83baf-155">To implement a custom control, you must write code for the <xref:System.Windows.Forms.Control.OnPaint%2A> event of the control, as well as any feature-specific code you need.</span></span> <span data-ttu-id="83baf-156">また、 <xref:System.Windows.Forms.Control.WndProc%2A> メソッドをオーバーライドして、windows メッセージを直接処理することもできます。</span><span class="sxs-lookup"><span data-stu-id="83baf-156">You can also override the <xref:System.Windows.Forms.Control.WndProc%2A> method and handle windows messages directly.</span></span> <span data-ttu-id="83baf-157">これはコントロールを作成する最も強力な方法ですが、この手法を効果的に使用するには、Microsoft Win32® API を十分に理解している必要があります。</span><span class="sxs-lookup"><span data-stu-id="83baf-157">This is the most powerful way to create a control, but to use this technique effectively, you need to be familiar with the Microsoft Win32® API.</span></span>  
  
 <span data-ttu-id="83baf-158">カスタム コントロールの例として、アナログ時計の外観と動作を複製した時計コントロールがあります。</span><span class="sxs-lookup"><span data-stu-id="83baf-158">An example of a custom control is a clock control that duplicates the appearance and behavior of an analog clock.</span></span> <span data-ttu-id="83baf-159">カスタム描画が呼び出され、内部コンポーネントからのイベントに応答して、時計の針が移動し <xref:System.Windows.Forms.Timer.Tick> <xref:System.Windows.Forms.Timer> ます。</span><span class="sxs-lookup"><span data-stu-id="83baf-159">Custom painting is invoked to cause the hands of the clock to move in response to <xref:System.Windows.Forms.Timer.Tick> events from an internal <xref:System.Windows.Forms.Timer> component.</span></span> <span data-ttu-id="83baf-160">詳細については、「[方法 : シンプルな Windows フォーム コントロールを開発する](how-to-develop-a-simple-windows-forms-control.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="83baf-160">For more information, see [How to: Develop a Simple Windows Forms Control](how-to-develop-a-simple-windows-forms-control.md).</span></span>  
  
 <span data-ttu-id="83baf-161">**推奨**</span><span class="sxs-lookup"><span data-stu-id="83baf-161">**Recommendation**</span></span>  
  
 <span data-ttu-id="83baf-162">次の場合に、<xref:System.Windows.Forms.Control> クラスから継承します。</span><span class="sxs-lookup"><span data-stu-id="83baf-162">Inherit from the <xref:System.Windows.Forms.Control> class if:</span></span>  
  
- <span data-ttu-id="83baf-163">コントロールのカスタムのグラフィカル表現を提供します。</span><span class="sxs-lookup"><span data-stu-id="83baf-163">You want to provide a custom graphical representation of your control.</span></span>  
  
- <span data-ttu-id="83baf-164">標準コントロールでは使用できないカスタムの機能を実装する必要があります。</span><span class="sxs-lookup"><span data-stu-id="83baf-164">You need to implement custom functionality that is not available through standard controls.</span></span>  
  
### <a name="activex-controls"></a><span data-ttu-id="83baf-165">ActiveX コントロール</span><span class="sxs-lookup"><span data-stu-id="83baf-165">ActiveX Controls</span></span>  

 <span data-ttu-id="83baf-166">Windows フォーム インストラクチャは、Windows フォーム コントロールをホストするために最適化されていますが、ActiveX コントロールを使用することもできます。</span><span class="sxs-lookup"><span data-stu-id="83baf-166">Although the Windows Forms infrastructure has been optimized to host Windows Forms controls, you can still use ActiveX controls.</span></span> <span data-ttu-id="83baf-167">Visual Studio では、このタスクに対するサポートが用意されています。</span><span class="sxs-lookup"><span data-stu-id="83baf-167">There is support for this task in Visual Studio.</span></span> <span data-ttu-id="83baf-168">詳細については、「[方法 : Windows フォームに ActiveX コントロールを追加する](how-to-add-activex-controls-to-windows-forms.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="83baf-168">For more information, see [How to: Add ActiveX Controls to Windows Forms](how-to-add-activex-controls-to-windows-forms.md).</span></span>  
  
### <a name="windowless-controls"></a><span data-ttu-id="83baf-169">ウィンドウなしのコントロール</span><span class="sxs-lookup"><span data-stu-id="83baf-169">Windowless Controls</span></span>  

 <span data-ttu-id="83baf-170">Microsoft Visual Basic® 6.0 と ActiveX テクノロジは、"*ウィンドウなし*" のコントロールをサポートします。</span><span class="sxs-lookup"><span data-stu-id="83baf-170">The Microsoft Visual Basic® 6.0and ActiveX technologies support *windowless* controls.</span></span> <span data-ttu-id="83baf-171">ウィンドウなしのコントロールは、Windows フォームではサポートされていません。</span><span class="sxs-lookup"><span data-stu-id="83baf-171">Windowless controls are not supported in Windows Forms.</span></span>  
  
## <a name="custom-design-experience"></a><span data-ttu-id="83baf-172">カスタム デザイン エクスペリエンス</span><span class="sxs-lookup"><span data-stu-id="83baf-172">Custom Design Experience</span></span>  

 <span data-ttu-id="83baf-173">カスタムのデザイン時エクスペリエンスを実装する必要がある場合は、独自のデザイナーを作成できます。</span><span class="sxs-lookup"><span data-stu-id="83baf-173">If you need to implement a custom design-time experience, you can author your own designer.</span></span> <span data-ttu-id="83baf-174">複合コントロールの場合 <xref:System.Windows.Forms.Design.ParentControlDesigner> は、クラスまたはクラスからカスタムデザイナークラスを派生させ <xref:System.Windows.Forms.Design.DocumentDesigner> ます。</span><span class="sxs-lookup"><span data-stu-id="83baf-174">For composite controls, derive your custom designer class from the <xref:System.Windows.Forms.Design.ParentControlDesigner> or the <xref:System.Windows.Forms.Design.DocumentDesigner> classes.</span></span> <span data-ttu-id="83baf-175">拡張コントロールとカスタムコントロールの場合は、クラスからカスタムデザイナークラスを派生させ <xref:System.Windows.Forms.Design.ControlDesigner> ます。</span><span class="sxs-lookup"><span data-stu-id="83baf-175">For extended and custom controls, derive your custom designer class from the <xref:System.Windows.Forms.Design.ControlDesigner> class.</span></span>  
  
 <span data-ttu-id="83baf-176">コントロールをデザイナーに関連付けるには、を使用し <xref:System.ComponentModel.DesignerAttribute> ます。</span><span class="sxs-lookup"><span data-stu-id="83baf-176">Use the <xref:System.ComponentModel.DesignerAttribute> to associate your control with your designer.</span></span> <span data-ttu-id="83baf-177">詳細については、「[デザイン時サポートの拡張](/previous-versions/visualstudio/visual-studio-2013/37899azc(v=vs.120))」および「[方法 : デザイン時機能を活用した Windows フォーム コントロールを作成する](/previous-versions/visualstudio/visual-studio-2013/307hck25(v=vs.120))」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="83baf-177">For more information, see [Extending Design-Time Support](/previous-versions/visualstudio/visual-studio-2013/37899azc(v=vs.120)) and [How to: Create a Windows Forms Control That Takes Advantage of Design-Time Features](/previous-versions/visualstudio/visual-studio-2013/307hck25(v=vs.120)).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="83baf-178">関連項目</span><span class="sxs-lookup"><span data-stu-id="83baf-178">See also</span></span>

- [<span data-ttu-id="83baf-179">.NET Framework を使用したカスタム Windows フォーム コントロールの開発</span><span class="sxs-lookup"><span data-stu-id="83baf-179">Developing Custom Windows Forms Controls with the .NET Framework</span></span>](developing-custom-windows-forms-controls.md)
- [<span data-ttu-id="83baf-180">方法: シンプルな Windows フォーム コントロールを開発する</span><span class="sxs-lookup"><span data-stu-id="83baf-180">How to: Develop a Simple Windows Forms Control</span></span>](how-to-develop-a-simple-windows-forms-control.md)
- [<span data-ttu-id="83baf-181">複合 Windows フォーム コントロールの開発</span><span class="sxs-lookup"><span data-stu-id="83baf-181">Developing a Composite Windows Forms Control</span></span>](developing-a-composite-windows-forms-control.md)
- <span data-ttu-id="83baf-182">[デザイン時サポートの拡張](/previous-versions/visualstudio/visual-studio-2013/37899azc(v=vs.120))</span><span class="sxs-lookup"><span data-stu-id="83baf-182">[Extending Design-Time Support](/previous-versions/visualstudio/visual-studio-2013/37899azc(v=vs.120))</span></span>
- <span data-ttu-id="83baf-183">[方法 : デザイン時機能を活用した Windows フォーム コントロールを作成する](/previous-versions/visualstudio/visual-studio-2013/307hck25(v=vs.120))</span><span class="sxs-lookup"><span data-stu-id="83baf-183">[How to: Create a Windows Forms Control That Takes Advantage of Design-Time Features](/previous-versions/visualstudio/visual-studio-2013/307hck25(v=vs.120))</span></span>
