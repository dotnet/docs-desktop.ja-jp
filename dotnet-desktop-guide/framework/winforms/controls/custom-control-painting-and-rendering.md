---
title: コントロールのカスタム描画およびレンダリング
ms.date: 03/30/2017
helpviewer_keywords:
- custom controls [Windows Forms], rendering
- custom controls [Windows Forms], painting
- user controls [Windows Forms], painting
ms.assetid: a09dbf76-0966-4cbf-a66a-2083ba98e068
ms.openlocfilehash: 14abac5678bfffa3cdb61307fd3cb54681c82a99
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/09/2020
ms.locfileid: "96974246"
---
# <a name="custom-control-painting-and-rendering"></a><span data-ttu-id="5101b-102">コントロールのカスタム描画およびレンダリング</span><span class="sxs-lookup"><span data-stu-id="5101b-102">Custom Control Painting and Rendering</span></span>
<span data-ttu-id="5101b-103">コントロールのカスタム描画は、.NET Framework によって簡単に実行できる多数の複雑なタスクの1つです。</span><span class="sxs-lookup"><span data-stu-id="5101b-103">Custom painting of controls is one of the many complicated tasks made easy by the .NET Framework.</span></span> <span data-ttu-id="5101b-104">カスタムコントロールを作成する場合は、コントロールのグラフィカルな外観に関する多くのオプションがあります。</span><span class="sxs-lookup"><span data-stu-id="5101b-104">When authoring a custom control, you have many options regarding your control's graphical appearance.</span></span> <span data-ttu-id="5101b-105">から継承されたコントロールを作成する場合は `Control` 、コントロールがグラフィック表示をレンダリングできるようにするコードを用意する必要があります。</span><span class="sxs-lookup"><span data-stu-id="5101b-105">If you are authoring a control that inherits from the `Control`, you must provide code that allows your control to render its graphical representation.</span></span> <span data-ttu-id="5101b-106">を継承してユーザーコントロールを作成する場合、 `UserControl` またはいずれかの Windows フォームコントロールから継承する場合は、標準のグラフィック表示をオーバーライドし、独自のグラフィックスコードを提供することができます。</span><span class="sxs-lookup"><span data-stu-id="5101b-106">If you are creating a user control by inheriting from the `UserControl`, or are inheriting from one of the Windows Forms controls, you may override the standard graphical representation and provide your own graphics code.</span></span> <span data-ttu-id="5101b-107">作成中のの構成コントロールにカスタムレンダリングを提供する場合 `UserControl` 、オプションの方が制限されますが、コントロールとアプリケーションに対してさまざまなグラフィカルな可能性があります。</span><span class="sxs-lookup"><span data-stu-id="5101b-107">If you want to provide custom rendering for the constituent controls of a `UserControl` you are authoring, your options become more limited, but still allow a wide range of graphical possibilities for your controls and applications.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="5101b-108">このセクションの内容</span><span class="sxs-lookup"><span data-stu-id="5101b-108">In This Section</span></span>  
 [<span data-ttu-id="5101b-109">Windows フォーム コントロールのレンダリング</span><span class="sxs-lookup"><span data-stu-id="5101b-109">Rendering a Windows Forms Control</span></span>](rendering-a-windows-forms-control.md)  
 <span data-ttu-id="5101b-110">コントロールを表示するロジックをプログラミングする方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="5101b-110">Shows how to program the logic that displays a control.</span></span>  
  
 [<span data-ttu-id="5101b-111">ユーザー描画コントロール</span><span class="sxs-lookup"><span data-stu-id="5101b-111">User-Drawn Controls</span></span>](user-drawn-controls.md)  
 <span data-ttu-id="5101b-112">コントロールのレンダリングコードを記述およびオーバーライドするために必要な手順の概要を示します。</span><span class="sxs-lookup"><span data-stu-id="5101b-112">Gives an overview of the steps involved in writing and overriding rendering code for your control.</span></span>  
  
 [<span data-ttu-id="5101b-113">内在コントロール</span><span class="sxs-lookup"><span data-stu-id="5101b-113">Constituent Controls</span></span>](constituent-controls.md)  
 <span data-ttu-id="5101b-114">ユーザーコントロールとフォームに内在コントロールのカスタムレンダリングコードを実装する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="5101b-114">Describes how to implement custom rendering code for constituent controls in your user controls and forms.</span></span>  
  
 [<span data-ttu-id="5101b-115">方法: 実行時にコントロールを非表示にする</span><span class="sxs-lookup"><span data-stu-id="5101b-115">How to: Make Your Control Invisible at Run Time</span></span>](how-to-make-your-control-invisible-at-run-time.md)  
 <span data-ttu-id="5101b-116">プロパティを使用し <xref:System.Windows.Forms.Control.Visible%2A> て、コントロールを非表示にしたり表示したりする方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="5101b-116">Shows how to use the <xref:System.Windows.Forms.Control.Visible%2A> property to hide and show a control.</span></span>  
  
 [<span data-ttu-id="5101b-117">方法: コントロールに透明な背景を指定する</span><span class="sxs-lookup"><span data-stu-id="5101b-117">How to: Give Your Control a Transparent Background</span></span>](how-to-give-your-control-a-transparent-background.md)  
 <span data-ttu-id="5101b-118">メソッドを使用し <xref:System.Windows.Forms.Control.SetStyle%2A> て、不透明、透明、または部分的に透明な背景色を作成する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="5101b-118">Shows how to use the <xref:System.Windows.Forms.Control.SetStyle%2A> method to create a background color that is opaque, transparent, or partially transparent.</span></span>  
  
 [<span data-ttu-id="5101b-119">visual スタイルが使用されているコントロールのレンダリング</span><span class="sxs-lookup"><span data-stu-id="5101b-119">Rendering Controls with Visual Styles</span></span>](rendering-controls-with-visual-styles.md)  
 <span data-ttu-id="5101b-120">サポートされているオペレーティングシステムで、visual スタイルを使用してコントロールをレンダリングする方法を示します。</span><span class="sxs-lookup"><span data-stu-id="5101b-120">Shows how to render controls using visual styles in operating systems that support them.</span></span>  
  
## <a name="reference"></a><span data-ttu-id="5101b-121">リファレンス</span><span class="sxs-lookup"><span data-stu-id="5101b-121">Reference</span></span>  
 <xref:System.Windows.Forms.Control>  
 <span data-ttu-id="5101b-122">このクラスについて説明し、すべてのメンバーへのリンクの一覧を示します。</span><span class="sxs-lookup"><span data-stu-id="5101b-122">Describes this class and has links to all of its members.</span></span>  
  
 <xref:System.Windows.Forms.UserControl>  
 <span data-ttu-id="5101b-123">このクラスについて説明し、すべてのメンバーへのリンクの一覧を示します。</span><span class="sxs-lookup"><span data-stu-id="5101b-123">Describes this class and has links to all of its members.</span></span>  
  
 <xref:System.Windows.Forms.Control.OnPaint%2A>  
 <span data-ttu-id="5101b-124">このメソッドについて説明します。</span><span class="sxs-lookup"><span data-stu-id="5101b-124">Describes this method.</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="5101b-125">関連項目</span><span class="sxs-lookup"><span data-stu-id="5101b-125">Related Sections</span></span>  
 [<span data-ttu-id="5101b-126">方法: 描画する Graphics オブジェクトを作成する</span><span class="sxs-lookup"><span data-stu-id="5101b-126">How to: Create Graphics Objects for Drawing</span></span>](../advanced/how-to-create-graphics-objects-for-drawing.md)  
 <span data-ttu-id="5101b-127">Visual Studio の観点から GDI + グラフィックス機能を紹介し、詳細情報へのリンクを示します。</span><span class="sxs-lookup"><span data-stu-id="5101b-127">Introduces GDI+ graphics functionality from a Visual Studio perspective and gives links to more information.</span></span>  
  
 [<span data-ttu-id="5101b-128">さまざまなカスタム コントロール</span><span class="sxs-lookup"><span data-stu-id="5101b-128">Varieties of Custom Controls</span></span>](varieties-of-custom-controls.md)  
 <span data-ttu-id="5101b-129">作成できるカスタムコントロールの種類について説明します。</span><span class="sxs-lookup"><span data-stu-id="5101b-129">Describes the kinds of custom controls you can author.</span></span>
