---
title: コントロールの種類に関するアドバイス
ms.date: 03/30/2017
ms.topic: overview
helpviewer_keywords:
- inheritance [Windows Forms], Windows Forms custom controls
- user controls [Windows Forms], when to use
- custom controls [Windows Forms], types
- controls [Windows Forms], creating
ms.assetid: 5235fe9d-c36a-4c08-ae76-6cb90b50085e
ms.openlocfilehash: c26b25fba47c9e63290d64ca3b6cd9a4bfd7c3b1
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/09/2020
ms.locfileid: "96974272"
---
# <a name="control-type-recommendations"></a><span data-ttu-id="99537-102">コントロールの種類に関するアドバイス</span><span class="sxs-lookup"><span data-stu-id="99537-102">Control Type Recommendations</span></span>

<span data-ttu-id="99537-103">.NET Framework は、新しいコントロールを開発して実装する機能を提供します。</span><span class="sxs-lookup"><span data-stu-id="99537-103">The .NET Framework gives you power to develop and implement new controls.</span></span> <span data-ttu-id="99537-104">使い慣れたユーザー コントロールだけでなく、独自の描画を実行するカスタム コントロールを作成することも、継承によって既存のコントロールの機能を拡張することもできるようになりました。</span><span class="sxs-lookup"><span data-stu-id="99537-104">In addition to the familiar user control, you will now find that you are able to write custom controls that perform their own painting, and are even able to extend the functionality of existing controls through inheritance.</span></span> <span data-ttu-id="99537-105">作成するコントロールの種類の決定が、混乱を招く可能性があります。</span><span class="sxs-lookup"><span data-stu-id="99537-105">Deciding which type of control to create can be confusing.</span></span> <span data-ttu-id="99537-106">このセクションでは、継承できるさまざまな種類のコントロールの間の違いについて説明し、プロジェクトに合わせて選択する種類に関する注意点を示しています。</span><span class="sxs-lookup"><span data-stu-id="99537-106">This section highlights the differences between the various types of controls from which you can inherit, and gives considerations regarding the type to choose for your project.</span></span>

> [!NOTE]
> <span data-ttu-id="99537-107">Web フォームで使用するコントロールを作成する場合は、「[カスタム ASP.NET サーバー コントロールの開発](/previous-versions/aspnet/zt27tfhy(v=vs.100))」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="99537-107">If you want to author a control to use on Web Forms, see [Developing Custom ASP.NET Server Controls](/previous-versions/aspnet/zt27tfhy(v=vs.100)).</span></span>

## <a name="inheriting-from-a-windows-forms-control"></a><span data-ttu-id="99537-108">Windows フォーム コントロールからの継承</span><span class="sxs-lookup"><span data-stu-id="99537-108">Inheriting from a Windows Forms Control</span></span>

<span data-ttu-id="99537-109">既存の Windows フォーム コントロールから継承されたコントロールを派生できます。</span><span class="sxs-lookup"><span data-stu-id="99537-109">You can derive an inherited control from any existing Windows Forms control.</span></span> <span data-ttu-id="99537-110">この方法では、すべての Windows フォーム コントロールの本質的な機能をすべて保持して、カスタム プロパティ、メソッド、またはその他の機能を追加することでその機能を拡張することができます。</span><span class="sxs-lookup"><span data-stu-id="99537-110">This approach allows you to retain all of the inherent functionality of a Windows Forms control, and to then extend that functionality by adding custom properties, methods, or other functionality.</span></span> <span data-ttu-id="99537-111">たとえば、数値のみを受け付け、入力を自動的に値に変換できる <xref:System.Windows.Forms.TextBox> から派生したコントロールを作成することができます。</span><span class="sxs-lookup"><span data-stu-id="99537-111">For example, you might create a control derived from <xref:System.Windows.Forms.TextBox> that can accept only numbers and automatically converts input into a value.</span></span> <span data-ttu-id="99537-112">このようなコントロールには、テキスト ボックスのテキストが変更されるたびに呼び出される検証コードが含まれ、値のプロパティを追加で持つことができます。</span><span class="sxs-lookup"><span data-stu-id="99537-112">Such a control might contain validation code that was called whenever the text in the text box changed, and could have an additional property, Value.</span></span> <span data-ttu-id="99537-113">一部のコントロールでは、基本クラスの <xref:System.Windows.Forms.Control.OnPaint%2A> メソッドをオーバーライドすることで、コントロールのグラフィカル インターフェイスにカスタムの外観を追加することができます。</span><span class="sxs-lookup"><span data-stu-id="99537-113">In some controls, you can also add a custom appearance to the graphical interface of your control by overriding the <xref:System.Windows.Forms.Control.OnPaint%2A> method of the base class.</span></span>

 <span data-ttu-id="99537-114">次の場合に、Windows フォーム コントロールから継承します。</span><span class="sxs-lookup"><span data-stu-id="99537-114">Inherit from a Windows Forms control if:</span></span>

- <span data-ttu-id="99537-115">必要とする機能のほとんどが、既存の Windows フォーム コントロールと同じです。</span><span class="sxs-lookup"><span data-stu-id="99537-115">Most of the functionality you need is already identical to an existing Windows Forms control.</span></span>

- <span data-ttu-id="99537-116">カスタムのグラフィカル インターフェイスが必要ないか、または既存のコントロールに対して新しいグラフィカルのフロント エンドをデザインします。</span><span class="sxs-lookup"><span data-stu-id="99537-116">You do not need a custom graphical interface, or you want to design a new graphical front end for an existing control.</span></span>

## <a name="inheriting-from-the-usercontrol-class"></a><span data-ttu-id="99537-117">UserControl クラスを継承する</span><span class="sxs-lookup"><span data-stu-id="99537-117">Inheriting from the UserControl Class</span></span>

<span data-ttu-id="99537-118">ユーザー コントロールは、共通のコンテナー内にカプセル化された Windows フォーム コントロールのコレクションです。</span><span class="sxs-lookup"><span data-stu-id="99537-118">A user control is a collection of Windows Forms controls encapsulated into a common container.</span></span> <span data-ttu-id="99537-119">コンテナーは、各 Windows フォーム コントロールに関連付けられている固有の機能をすべて保持し、それらのプロパティを選択的に公開してバインドすることができます。</span><span class="sxs-lookup"><span data-stu-id="99537-119">The container holds all of the inherent functionality associated with each of the Windows Forms controls and allows you to selectively expose and bind their properties.</span></span> <span data-ttu-id="99537-120">ユーザー コントロールの例として、データベースから顧客の住所データを表示する貯めに作成されたコントロールがあります。</span><span class="sxs-lookup"><span data-stu-id="99537-120">An example of a user control might be a control built to display customer address data from a database.</span></span> <span data-ttu-id="99537-121">このコントロールには、各フィールドを表示するいくつかのテキスト ボックスと、レコード間を移動するボタン コントロールが含まれます。</span><span class="sxs-lookup"><span data-stu-id="99537-121">This control would include several textboxes to display each field, and button controls to navigate through the records.</span></span> <span data-ttu-id="99537-122">データ バインディングのプロパティは選択的に公開することができ、コントロール全体は、パッケージしてアプリケーション間で再利用できます。</span><span class="sxs-lookup"><span data-stu-id="99537-122">Data-binding properties could be selectively exposed, and the entire control could be packaged and reused from application to application.</span></span>

<span data-ttu-id="99537-123">次の場合に、<xref:System.Windows.Forms.UserControl> クラスから継承します。</span><span class="sxs-lookup"><span data-stu-id="99537-123">Inherit from the <xref:System.Windows.Forms.UserControl> class if:</span></span>

- <span data-ttu-id="99537-124">いくつかの Windows フォーム コントロールの機能を再利用可能な 1 つの単位に結合します。</span><span class="sxs-lookup"><span data-stu-id="99537-124">You want to combine the functionality of several Windows Forms controls into a single reusable unit.</span></span>

## <a name="inheriting-from-the-control-class"></a><span data-ttu-id="99537-125">Control クラスからの継承</span><span class="sxs-lookup"><span data-stu-id="99537-125">Inheriting from the Control Class</span></span>

<span data-ttu-id="99537-126">コントロールを作成する別の方法は、<xref:System.Windows.Forms.Control> から継承することで、実質的に一から作成する方法です。</span><span class="sxs-lookup"><span data-stu-id="99537-126">Another way to create a control is to create one substantially from scratch by inheriting from <xref:System.Windows.Forms.Control>.</span></span> <span data-ttu-id="99537-127"><xref:System.Windows.Forms.Control> クラスは、コントロール (イベントなど) によって必要とされる基本的な機能をすべて提供しますが、コントロール固有の機能やグラフィカル インターフェイスは提供しません。</span><span class="sxs-lookup"><span data-stu-id="99537-127">The <xref:System.Windows.Forms.Control> class provides all of the basic functionality required by controls (for example, events), but no control-specific functionality or graphical interface.</span></span> <span data-ttu-id="99537-128"><xref:System.Windows.Forms.Control> クラスから継承することでコントロールを作成する場合は、ユーザー コントロールや既存の Windows フォーム コントロールから継承する場合よりも、はるかに多くの配慮と労力が必要です。</span><span class="sxs-lookup"><span data-stu-id="99537-128">Creating a control by inheriting from the <xref:System.Windows.Forms.Control> class requires a lot more thought and effort than inheriting from user control or an existing Windows Forms control.</span></span> <span data-ttu-id="99537-129">作成者は、コントロールの <xref:System.Windows.Forms.Control.OnPaint%2A> イベントのコード、および必要とされる機能固有のコードを作成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="99537-129">The author must write code for the <xref:System.Windows.Forms.Control.OnPaint%2A> event of the control, as well as any functionality specific code that is needed.</span></span> <span data-ttu-id="99537-130">ただし、より大きな柔軟性が可能になり、正確なニーズに合わせてコントロールをカスタムに調整することができます。</span><span class="sxs-lookup"><span data-stu-id="99537-130">Greater flexibility is allowed, however, and you can custom tailor a control to suit your exact needs.</span></span> <span data-ttu-id="99537-131">カスタム コントロールの例は、アナログ時計の外観や動作を複製する時計コントロールです。</span><span class="sxs-lookup"><span data-stu-id="99537-131">An example of a custom control is a clock control that duplicates the look and action of an analog clock.</span></span> <span data-ttu-id="99537-132">内部タイマー コンポーネントからの <xref:System.Windows.Forms.Timer.Tick> イベントに応答してカスタム描画が呼び出されて、時計の針が移動します。</span><span class="sxs-lookup"><span data-stu-id="99537-132">Custom painting would be invoked to cause the hands of the clock to move in response to <xref:System.Windows.Forms.Timer.Tick> events from an internal timer component.</span></span>

<span data-ttu-id="99537-133">次の場合に、<xref:System.Windows.Forms.Control> クラスから継承します。</span><span class="sxs-lookup"><span data-stu-id="99537-133">Inherit from the <xref:System.Windows.Forms.Control> class if:</span></span>

- <span data-ttu-id="99537-134">コントロールのカスタムのグラフィカル表現を提供します。</span><span class="sxs-lookup"><span data-stu-id="99537-134">You want to provide a custom graphical representation of your control.</span></span>

- <span data-ttu-id="99537-135">標準コントロールでは使用できないカスタムの機能を実装する必要があります。</span><span class="sxs-lookup"><span data-stu-id="99537-135">You need to implement custom functionality that is not available through standard controls.</span></span>

## <a name="related-articles"></a><span data-ttu-id="99537-136">関連記事</span><span class="sxs-lookup"><span data-stu-id="99537-136">Related articles</span></span>

- <span data-ttu-id="99537-137">[方法: [ツールボックス アイテムの選択] ダイアログ ボックスにコントロールを表示する](how-to-display-a-control-in-the-choose-toolbox-items-dialog-box.md)</span><span class="sxs-lookup"><span data-stu-id="99537-137">[How to: Display a Control in the Choose Toolbox Items Dialog Box](how-to-display-a-control-in-the-choose-toolbox-items-dialog-box.md)</span></span>

- [<span data-ttu-id="99537-138">チュートリアル: DesignerSerializationVisibilityAttribute を使用した、標準データ型のコレクションのシリアル化</span><span class="sxs-lookup"><span data-stu-id="99537-138">Walkthrough: Serializing Collections of Standard Types with the DesignerSerializationVisibilityAttribute</span></span>](serializing-collections-designerserializationvisibilityattribute.md)

- [<span data-ttu-id="99537-139">チュートリアル: Windows フォームコントロールからの継承</span><span class="sxs-lookup"><span data-stu-id="99537-139">Walkthrough: Inheriting from a Windows Forms Control</span></span>](walkthrough-inheriting-from-a-windows-forms-control-with-visual-csharp.md)

- [<span data-ttu-id="99537-140">方法: コントロールにツールボックス ビットマップを指定する</span><span class="sxs-lookup"><span data-stu-id="99537-140">How to: Provide a Toolbox Bitmap for a Control</span></span>](how-to-provide-a-toolbox-bitmap-for-a-control.md)

- [<span data-ttu-id="99537-141">方法: 既存の Windows フォーム コントロールから継承する</span><span class="sxs-lookup"><span data-stu-id="99537-141">How to: Inherit from Existing Windows Forms Controls</span></span>](how-to-inherit-from-existing-windows-forms-controls.md)

- [<span data-ttu-id="99537-142">チュートリアル : カスタム Windows フォーム コントロールのデザイン時のデバッグ</span><span class="sxs-lookup"><span data-stu-id="99537-142">Walkthrough: Debugging Custom Windows Forms Controls at Design Time</span></span>](walkthrough-debugging-custom-windows-forms-controls-at-design-time.md)

- [<span data-ttu-id="99537-143">方法: コントロール クラスを継承する</span><span class="sxs-lookup"><span data-stu-id="99537-143">How to: Inherit from the Control Class</span></span>](how-to-inherit-from-the-control-class.md)

- [<span data-ttu-id="99537-144">方法: UserControl の実行時の動作をテストする</span><span class="sxs-lookup"><span data-stu-id="99537-144">How to: Test the Run-Time Behavior of a UserControl</span></span>](how-to-test-the-run-time-behavior-of-a-usercontrol.md)

- [<span data-ttu-id="99537-145">方法 : デザイン時にフォームの端に合わせてコントロールを配置する</span><span class="sxs-lookup"><span data-stu-id="99537-145">How to: Align a Control to the Edges of Forms at Design Time</span></span>](how-to-align-a-control-to-the-edges-of-forms-at-design-time.md)

- [<span data-ttu-id="99537-146">方法: UserControl クラスを継承する</span><span class="sxs-lookup"><span data-stu-id="99537-146">How to: Inherit from the UserControl Class</span></span>](how-to-inherit-from-the-usercontrol-class.md)

- [<span data-ttu-id="99537-147">方法: Windows フォームのコントロールを作成する</span><span class="sxs-lookup"><span data-stu-id="99537-147">How to: Author Controls for Windows Forms</span></span>](how-to-author-controls-for-windows-forms.md)

- [<span data-ttu-id="99537-148">方法: 複合コントロールを作成する</span><span class="sxs-lookup"><span data-stu-id="99537-148">How to: Author Composite Controls</span></span>](how-to-author-composite-controls.md)

- [<span data-ttu-id="99537-149">チュートリアル: 複合コントロールの作成</span><span class="sxs-lookup"><span data-stu-id="99537-149">Walkthrough: Authoring a Composite Control</span></span>](walkthrough-authoring-a-composite-control-with-visual-csharp.md)

- [<span data-ttu-id="99537-150">チュートリアル: Visual Studio の Design-Time 機能を利用する Windows フォームコントロールの作成</span><span class="sxs-lookup"><span data-stu-id="99537-150">Walkthrough: Creating a Windows Forms Control That Takes Advantage of Visual Studio Design-Time Features</span></span>](creating-a-wf-control-design-time-features.md)

- <span data-ttu-id="99537-151">[方法 : デザイン時機能を活用した Windows フォーム コントロールを作成する](/previous-versions/visualstudio/visual-studio-2013/307hck25(v=vs.120))</span><span class="sxs-lookup"><span data-stu-id="99537-151">[How to: Create a Windows Forms Control That Takes Advantage of Design-Time Features](/previous-versions/visualstudio/visual-studio-2013/307hck25(v=vs.120))</span></span>

## <a name="see-also"></a><span data-ttu-id="99537-152">関連項目</span><span class="sxs-lookup"><span data-stu-id="99537-152">See also</span></span>

- [<span data-ttu-id="99537-153">方法: シンプルな Windows フォーム コントロールを開発する</span><span class="sxs-lookup"><span data-stu-id="99537-153">How to: Develop a Simple Windows Forms Control</span></span>](how-to-develop-a-simple-windows-forms-control.md)
- [<span data-ttu-id="99537-154">さまざまなカスタム コントロール</span><span class="sxs-lookup"><span data-stu-id="99537-154">Varieties of Custom Controls</span></span>](varieties-of-custom-controls.md)
