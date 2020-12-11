---
title: SplitContainer コントロール
ms.date: 03/30/2017
helpviewer_keywords:
- splitter windows
- SplitContainer control [Windows Forms]
ms.assetid: 2e36f17f-5c39-4fb4-bb09-7ce3ef823402
ms.openlocfilehash: ac04f60847aa6f77c11637f37b5ec94b6f7ef341
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/09/2020
ms.locfileid: "96982436"
---
# <a name="splitcontainer-control-windows-forms"></a><span data-ttu-id="5397a-102">SplitContainer コントロール (Windows フォーム)</span><span class="sxs-lookup"><span data-stu-id="5397a-102">SplitContainer Control (Windows Forms)</span></span>
<span data-ttu-id="5397a-103">Windows フォームの `SplitContainer` コントロールは複合と考えることができ、移動可能なバーで区切られた 2 つのパネルです。</span><span class="sxs-lookup"><span data-stu-id="5397a-103">The Windows Forms `SplitContainer` control can be thought of as a composite; it is two panels separated by a movable bar.</span></span> <span data-ttu-id="5397a-104">マウス ポインターがバーの上に移動すると、ポインターの形が変わり、バーが移動可能であることを示します。</span><span class="sxs-lookup"><span data-stu-id="5397a-104">When the mouse pointer is over the bar, the pointer changes shape to show that the bar is movable.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="5397a-105">**ツールボックス** では、 <xref:System.Windows.Forms.Splitter> 以前のバージョンの Visual Studio にあったコントロールが、このコントロールに置き換えられています。</span><span class="sxs-lookup"><span data-stu-id="5397a-105">In the **Toolbox**, this control replaces the <xref:System.Windows.Forms.Splitter> control that was there in the previous version of Visual Studio.</span></span> <span data-ttu-id="5397a-106">`SplitContainer` コントロールは <xref:System.Windows.Forms.Splitter> コントロールより優先されます。</span><span class="sxs-lookup"><span data-stu-id="5397a-106">The `SplitContainer` control is much preferred over the <xref:System.Windows.Forms.Splitter> control.</span></span> <span data-ttu-id="5397a-107"><xref:System.Windows.Forms.Splitter> クラスは、既存のアプリケーションの互換性のために .NET Framework に含まれていますが、新しいプロジェクトでは `SplitContainer` コントロールを使用することを強くお勧めします。</span><span class="sxs-lookup"><span data-stu-id="5397a-107">The <xref:System.Windows.Forms.Splitter> class is still included in the .NET Framework for compatibility with existing applications, but we strongly encourage you to use the `SplitContainer` control for new projects.</span></span>  
  
 <span data-ttu-id="5397a-108">`SplitContainer` コントロールでは複雑なユーザー インターフェイスを作成できます。多くの場合、1 つのパネルの選択項目が、もう一方のパネルに表示されるオブジェクトを決定します。</span><span class="sxs-lookup"><span data-stu-id="5397a-108">The `SplitContainer` control lets you create complex user interfaces; often, a selection in one panel determines what objects are shown in the other panel.</span></span> <span data-ttu-id="5397a-109">この配置は、情報の表示と参照に対して非常に効果的です。</span><span class="sxs-lookup"><span data-stu-id="5397a-109">This arrangement is very effective for displaying and browsing information.</span></span> <span data-ttu-id="5397a-110">2 つのパネルを使用することで、情報を領域に集約でき、バーまたは「分割」により、ユーザーがパネルを簡単にサイズ変更できます。</span><span class="sxs-lookup"><span data-stu-id="5397a-110">Having two panels allow you to aggregate information in areas, and the bar, or "splitter," makes it easy for users to resize the panels.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="5397a-111">このセクションの内容</span><span class="sxs-lookup"><span data-stu-id="5397a-111">In This Section</span></span>  
 [<span data-ttu-id="5397a-112">SplitContainer コントロールの概要</span><span class="sxs-lookup"><span data-stu-id="5397a-112">SplitContainer Control Overview</span></span>](splitcontainer-control-overview-windows-forms.md)  
 <span data-ttu-id="5397a-113">`SplitContainer` コントロールを導入し、一般的に使用されるプロパティ、メソッド、およびイベントについて説明します。</span><span class="sxs-lookup"><span data-stu-id="5397a-113">Introduces the `SplitContainer` control and describes the commonly used properties, methods, and events.</span></span>  
  
 [<span data-ttu-id="5397a-114">方法: 分割ウィンドウでのサイズ変更および位置指定動作を定義する</span><span class="sxs-lookup"><span data-stu-id="5397a-114">How to: Define Resize and Positioning Behavior in a Split Window</span></span>](how-to-define-resize-and-positioning-behavior-in-a-split-window.md)  
 <span data-ttu-id="5397a-115">`SplitContainer` コントロール内のスプリッターを制御する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="5397a-115">Describes how to control the splitter within the `SplitContainer` control.</span></span>  
  
 [<span data-ttu-id="5397a-116">方法: ウィンドウを水平方向に分割する</span><span class="sxs-lookup"><span data-stu-id="5397a-116">How to: Split a Window Horizontally</span></span>](how-to-split-a-window-horizontally.md)  
 <span data-ttu-id="5397a-117">`SplitContainer` コントロール内のスプリッターの方向を制御する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="5397a-117">Describes how to control the orientation of the splitter within the `SplitContainer` control.</span></span>  
  
 [<span data-ttu-id="5397a-118">方法: Windows フォームでマルチペイン ユーザー インターフェイスを作成する</span><span class="sxs-lookup"><span data-stu-id="5397a-118">How to: Create a Multipane User Interface with Windows Forms</span></span>](how-to-create-a-multipane-user-interface-with-windows-forms.md)  
 <span data-ttu-id="5397a-119">Microsoft Outlook で使用されるような複数ペインのユーザー インターフェイスを作成します。</span><span class="sxs-lookup"><span data-stu-id="5397a-119">Creates a multi-pane user interface that is similar to the one used in Microsoft Outlook.</span></span>  
  
 <span data-ttu-id="5397a-120">「 [方法: デザイナーを使用してウィンドウを水平方向に分割](how-to-split-a-window-horizontally-using-the-designer.md)する」、「 [方法: Windows フォームで windows エクスプローラースタイルのインターフェイスを作成](how-to-create-a-windows-explorer-style-interface-on-a-windows-form.md)する」、「 [方法: デザイナーを使用して Windows フォームでマルチペインユーザーインターフェイスを作成する](create-a-multipane-user-interface-with-wf-using-the-designer.md)」も参照してください。</span><span class="sxs-lookup"><span data-stu-id="5397a-120">Also see [How to: Split a Window Horizontally Using the Designer](how-to-split-a-window-horizontally-using-the-designer.md), [How to: Create a Windows Explorer–Style Interface on a Windows Form](how-to-create-a-windows-explorer-style-interface-on-a-windows-form.md), [How to: Create a Multipane User Interface with Windows Forms Using the Designer](create-a-multipane-user-interface-with-wf-using-the-designer.md).</span></span>  
  
## <a name="reference"></a><span data-ttu-id="5397a-121">リファレンス</span><span class="sxs-lookup"><span data-stu-id="5397a-121">Reference</span></span>  
 <span data-ttu-id="5397a-122"><xref:System.Windows.Forms.SplitContainer> クラス</span><span class="sxs-lookup"><span data-stu-id="5397a-122"><xref:System.Windows.Forms.SplitContainer> class</span></span>  
 <span data-ttu-id="5397a-123">このクラスについて説明し、すべてのメンバーへのリンクの一覧を示します。</span><span class="sxs-lookup"><span data-stu-id="5397a-123">Describes this class and has links to all its members.</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="5397a-124">関連項目</span><span class="sxs-lookup"><span data-stu-id="5397a-124">Related Sections</span></span>  
 [<span data-ttu-id="5397a-125">Windows フォームコントロール</span><span class="sxs-lookup"><span data-stu-id="5397a-125">Windows Forms Controls</span></span>](index.md)  
 <span data-ttu-id="5397a-126">Windows フォームでの操作専用に設計されているコントロールについてのトピックへのリンクを提供します。</span><span class="sxs-lookup"><span data-stu-id="5397a-126">Provides links to topics about the controls designed specifically to work with Windows Forms.</span></span>  
  
 [<span data-ttu-id="5397a-127">Windows フォームで使用するコントロール</span><span class="sxs-lookup"><span data-stu-id="5397a-127">Controls to Use on Windows Forms</span></span>](controls-to-use-on-windows-forms.md)  
 <span data-ttu-id="5397a-128">Windows フォーム コントロールの完全な一覧を、使用に関する情報リンクと共に提供します。</span><span class="sxs-lookup"><span data-stu-id="5397a-128">Provides a complete list of Windows Forms controls, with links to information on their use.</span></span>
