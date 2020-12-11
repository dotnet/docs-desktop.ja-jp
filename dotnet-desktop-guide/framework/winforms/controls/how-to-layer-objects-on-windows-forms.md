---
title: オブジェクトを階層化する
description: Windows フォームコントロールと子フォームにオブジェクトをレイヤー化して、より複雑なユーザーインターフェイスを作成する方法について説明します。
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- Windows Forms controls, layering
- controls [Windows Forms], layering
- z order
- controls [Windows Forms], positioning
- z-order
ms.assetid: 1acc4281-2976-4715-86f4-bda68134baaf
author: jillre
ms.author: jillfra
manager: jillfra
ms.openlocfilehash: 6269b09c56963fefd500b9e1e6c9d7f51f9619cf
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/09/2020
ms.locfileid: "96982731"
---
# <a name="how-to-layer-objects-on-windows-forms"></a><span data-ttu-id="57f0d-103">方法: Windows フォーム上のオブジェクトをレイヤー化する</span><span class="sxs-lookup"><span data-stu-id="57f0d-103">How to: Layer objects on Windows Forms</span></span>

<span data-ttu-id="57f0d-104">複雑なユーザーインターフェイスを作成する場合や、マルチドキュメントインターフェイス (MDI) フォームを使用する場合は、多くの場合、コントロールと子フォームの両方をレイヤー化することで、より複雑なユーザーインターフェイス (UI) を作成できます。</span><span class="sxs-lookup"><span data-stu-id="57f0d-104">When you create a complex user interface, or work with a multiple document interface (MDI) form, you will often want to layer both controls and child forms to create more complex user interfaces (UI).</span></span> <span data-ttu-id="57f0d-105">グループのコンテキスト内でコントロールとウィンドウを移動して追跡するには、 *z オーダー* を操作します。</span><span class="sxs-lookup"><span data-stu-id="57f0d-105">To move and keep track of controls and windows within the context of a group, you manipulate their *z-order*.</span></span> <span data-ttu-id="57f0d-106">Z オーダーは、フォームの z 軸 (深度) に沿ってフォーム上のコントロールを視覚的に重ねたものです。</span><span class="sxs-lookup"><span data-stu-id="57f0d-106">Z-order is the visual layering of controls on a form along the form's z-axis (depth).</span></span> <span data-ttu-id="57f0d-107">Z オーダーの最上部にあるウィンドウは、他のすべてのウィンドウと重なっています。</span><span class="sxs-lookup"><span data-stu-id="57f0d-107">The window at the top of the z-order overlaps all other windows.</span></span> <span data-ttu-id="57f0d-108">他のすべてのウィンドウは、z オーダーの下部にあるウィンドウと重なっています。</span><span class="sxs-lookup"><span data-stu-id="57f0d-108">All other windows overlap the window at the bottom of the z-order.</span></span>

## <a name="to-layer-controls-at-design-time"></a><span data-ttu-id="57f0d-109">デザイン時にコントロールをレイヤー化するには</span><span class="sxs-lookup"><span data-stu-id="57f0d-109">To layer controls at design time</span></span>

1. <span data-ttu-id="57f0d-110">Visual Studio で、レイヤー化するコントロールを選択します。</span><span class="sxs-lookup"><span data-stu-id="57f0d-110">In Visual Studio, select a control that you want to layer.</span></span>

2. <span data-ttu-id="57f0d-111">[ **書式** ] メニューの [ **順序**] をクリックし、[ **前面へ移動** ] または [ **背面へ** 移動] を選択します。</span><span class="sxs-lookup"><span data-stu-id="57f0d-111">On the **Format** menu, select **Order**, and then select **Bring To Front** or **Send To Back**.</span></span>

## <a name="to-layer-controls-programmatically"></a><span data-ttu-id="57f0d-112">プログラムによってコントロールをレイヤー化するには</span><span class="sxs-lookup"><span data-stu-id="57f0d-112">To layer controls programmatically</span></span>

<span data-ttu-id="57f0d-113"><xref:System.Windows.Forms.Control.BringToFront%2A> <xref:System.Windows.Forms.Control.SendToBack%2A> コントロールの z オーダーを操作するには、メソッドとメソッドを使用します。</span><span class="sxs-lookup"><span data-stu-id="57f0d-113">Use the <xref:System.Windows.Forms.Control.BringToFront%2A> and <xref:System.Windows.Forms.Control.SendToBack%2A> methods to manipulate the z-order of the controls.</span></span>

<span data-ttu-id="57f0d-114">たとえば、コントロールが別のコントロールの下にあり、そのコントロールを上に表示する場合は、 <xref:System.Windows.Forms.TextBox> `txtFirstName` 次のコードを使用します。</span><span class="sxs-lookup"><span data-stu-id="57f0d-114">For example, if a <xref:System.Windows.Forms.TextBox> control, `txtFirstName`, is underneath another control and you want to have it on top, use the following code:</span></span>

```vb
txtFirstName.BringToFront()
```

```csharp
txtFirstName.BringToFront();
```

```cpp
txtFirstName->BringToFront();
```

> [!NOTE]
> <span data-ttu-id="57f0d-115">Windows フォームは *コントロールの含有* をサポートします。</span><span class="sxs-lookup"><span data-stu-id="57f0d-115">Windows Forms supports *control containment*.</span></span> <span data-ttu-id="57f0d-116">コントロールのコンテインメントでは、コントロール内のコントロールの数など、コントロールを含むコントロール内に多数のコントロールを配置する必要が <xref:System.Windows.Forms.RadioButton> <xref:System.Windows.Forms.GroupBox> あります。</span><span class="sxs-lookup"><span data-stu-id="57f0d-116">Control containment involves placing a number of controls within a containing control, such as a number of <xref:System.Windows.Forms.RadioButton> controls within a <xref:System.Windows.Forms.GroupBox> control.</span></span> <span data-ttu-id="57f0d-117">次に、それを含んでいるコントロール内のコントロールをレイヤー化できます。</span><span class="sxs-lookup"><span data-stu-id="57f0d-117">You can then layer the controls within the containing control.</span></span> <span data-ttu-id="57f0d-118">グループボックスを移動すると、コントロールがその中に含まれているため、コントロールも移動します。</span><span class="sxs-lookup"><span data-stu-id="57f0d-118">Moving the group box moves the controls as well, because they are contained inside it.</span></span>

## <a name="see-also"></a><span data-ttu-id="57f0d-119">関連項目</span><span class="sxs-lookup"><span data-stu-id="57f0d-119">See also</span></span>

- [<span data-ttu-id="57f0d-120">Windows フォームコントロール</span><span class="sxs-lookup"><span data-stu-id="57f0d-120">Windows Forms Controls</span></span>](index.md)
- [<span data-ttu-id="57f0d-121">各 Windows フォーム コントロールのラベル設定とショートカットの作成</span><span class="sxs-lookup"><span data-stu-id="57f0d-121">Labeling Individual Windows Forms Controls and Providing Shortcuts to Them</span></span>](labeling-individual-windows-forms-controls-and-providing-shortcuts-to-them.md)
- [<span data-ttu-id="57f0d-122">Windows フォームで使用するコントロール</span><span class="sxs-lookup"><span data-stu-id="57f0d-122">Controls to Use on Windows Forms</span></span>](controls-to-use-on-windows-forms.md)
- [<span data-ttu-id="57f0d-123">Windows フォーム コントロールの機能別一覧</span><span class="sxs-lookup"><span data-stu-id="57f0d-123">Windows Forms Controls by Function</span></span>](windows-forms-controls-by-function.md)
