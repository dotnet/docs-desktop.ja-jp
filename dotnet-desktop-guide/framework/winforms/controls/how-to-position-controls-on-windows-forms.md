---
title: コントロールを配置する
description: Visual Studio の Windows フォームデザイナー、または Location プロパティを使用してコントロールを配置する方法について説明します。
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
f1_keywords:
- Location
- Location.Y
- Location.X
helpviewer_keywords:
- controls [Windows Forms]
- controls [Windows Forms], moving
- snaplines
- controls [Windows Forms], positioning
ms.assetid: 4693977e-34a4-4f19-8221-68c3120c2b2b
author: jillre
ms.author: jillfra
manager: jillfra
ms.openlocfilehash: e7b26d1741046ea242bd58a9216b8958697e1879
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/09/2020
ms.locfileid: "96974785"
---
# <a name="how-to-position-controls-on-windows-forms"></a><span data-ttu-id="cc9ee-103">方法: Windows フォームにコントロールを配置する</span><span class="sxs-lookup"><span data-stu-id="cc9ee-103">How to: Position controls on Windows Forms</span></span>

<span data-ttu-id="cc9ee-104">コントロールを配置するには、Visual Studio で Windows フォームデザイナーを使用するか、プロパティを指定し <xref:System.Windows.Forms.Control.Location%2A> ます。</span><span class="sxs-lookup"><span data-stu-id="cc9ee-104">To position controls, use the Windows Forms Designer in Visual Studio or specify the <xref:System.Windows.Forms.Control.Location%2A> property.</span></span>

## <a name="position-a-control-on-the-design-surface-of-the-windows-forms-designer"></a><span data-ttu-id="cc9ee-105">Windows フォームデザイナーのデザインサーフェイスにコントロールを配置する</span><span class="sxs-lookup"><span data-stu-id="cc9ee-105">Position a control on the design surface of the Windows Forms Designer</span></span>

<span data-ttu-id="cc9ee-106">Visual Studio で、マウスを使用して適切な位置にコントロールをドラッグします。</span><span class="sxs-lookup"><span data-stu-id="cc9ee-106">In Visual Studio, drag the control to the appropriate location with the mouse.</span></span>

> [!NOTE]
> <span data-ttu-id="cc9ee-107">コントロールを選択し、方向キーを使用して移動し、より正確に配置します。</span><span class="sxs-lookup"><span data-stu-id="cc9ee-107">Select the control and move it with the ARROW keys to position it more precisely.</span></span> <span data-ttu-id="cc9ee-108">また、 *スナップ線* を使用すると、フォームにコントロールを正確に配置できます。</span><span class="sxs-lookup"><span data-stu-id="cc9ee-108">Also, *snaplines* assist you in placing controls precisely on your form.</span></span> <span data-ttu-id="cc9ee-109">詳細については、「 [チュートリアル: スナップ線を使用した Windows フォームでのコントロールの配置](walkthrough-arranging-controls-on-windows-forms-using-snaplines.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="cc9ee-109">For more information, see [Walkthrough: Arranging Controls on Windows Forms Using Snaplines](walkthrough-arranging-controls-on-windows-forms-using-snaplines.md).</span></span>

## <a name="position-a-control-using-the-properties-window"></a><span data-ttu-id="cc9ee-110">プロパティウィンドウを使用してコントロールを配置する</span><span class="sxs-lookup"><span data-stu-id="cc9ee-110">Position a control using the Properties window</span></span>

1. <span data-ttu-id="cc9ee-111">Visual Studio で、配置するコントロールを選択します。</span><span class="sxs-lookup"><span data-stu-id="cc9ee-111">In Visual Studio, select the control you want to position.</span></span>

2. <span data-ttu-id="cc9ee-112">[ **プロパティ** ] ウィンドウで、プロパティの値をコンマで区切って入力し、 <xref:System.Windows.Forms.Control.Location%2A> コンテナー内にコントロールを配置します。</span><span class="sxs-lookup"><span data-stu-id="cc9ee-112">In the **Properties** window, enter values for the <xref:System.Windows.Forms.Control.Location%2A> property, separated by a comma, to position the control within its container.</span></span>

   <span data-ttu-id="cc9ee-113">最初の数値 (X) は、コンテナーの左境界線からの距離です。2番目の数値 (Y) は、コンテナー領域の上境界からの距離をピクセル単位で表したものです。</span><span class="sxs-lookup"><span data-stu-id="cc9ee-113">The first number (X) is the distance from the left border of the container; the second number (Y) is the distance from the upper border of the container area, measured in pixels.</span></span>

   > [!NOTE]
   > <span data-ttu-id="cc9ee-114">プロパティを展開して、 <xref:System.Windows.Forms.Control.Location%2A> **X** 値と **Y** 値を個別に入力できます。</span><span class="sxs-lookup"><span data-stu-id="cc9ee-114">You can expand the <xref:System.Windows.Forms.Control.Location%2A> property to type the **X** and **Y** values individually.</span></span>

## <a name="position-a-control-programmatically"></a><span data-ttu-id="cc9ee-115">プログラムによるコントロールの配置</span><span class="sxs-lookup"><span data-stu-id="cc9ee-115">Position a control programmatically</span></span>

1. <span data-ttu-id="cc9ee-116"><xref:System.Windows.Forms.Control.Location%2A>コントロールのプロパティをに設定 <xref:System.Drawing.Point> します。</span><span class="sxs-lookup"><span data-stu-id="cc9ee-116">Set the <xref:System.Windows.Forms.Control.Location%2A> property of the control to a <xref:System.Drawing.Point>.</span></span>

    ```vb
    Button1.Location = New Point(100, 100)
    ```

    ```csharp
    button1.Location = new Point(100, 100);
    ```

    ```cpp
    button1->Location = Point(100, 100);
    ```

2. <span data-ttu-id="cc9ee-117">サブプロパティを使用して、コントロールの位置の X 座標を変更 <xref:System.Windows.Forms.Control.Left%2A> します。</span><span class="sxs-lookup"><span data-stu-id="cc9ee-117">Change the X coordinate of the control's location using the <xref:System.Windows.Forms.Control.Left%2A> subproperty.</span></span>

    ```vb
    Button1.Left = 300
    ```

    ```csharp
    button1.Left = 300;
    ```

    ```cpp
    button1->Left = 300;
    ```

## <a name="increment-a-controls-location-programmatically"></a><span data-ttu-id="cc9ee-118">プログラムによってコントロールの位置をインクリメントする</span><span class="sxs-lookup"><span data-stu-id="cc9ee-118">Increment a control's location programmatically</span></span>

<span data-ttu-id="cc9ee-119">サブプロパティを設定して、 <xref:System.Windows.Forms.Control.Left%2A> コントロールの X 座標をインクリメントします。</span><span class="sxs-lookup"><span data-stu-id="cc9ee-119">Set the <xref:System.Windows.Forms.Control.Left%2A> subproperty to increment the X coordinate of the control.</span></span>

```vb
Button1.Left += 200
```

```csharp
button1.Left += 200;
```

```cpp
button1->Left += 200;
```

> [!NOTE]
> <span data-ttu-id="cc9ee-120"><xref:System.Windows.Forms.Control.Location%2A>コントロールの X 位置と Y 位置を同時に設定するには、プロパティを使用します。</span><span class="sxs-lookup"><span data-stu-id="cc9ee-120">Use the <xref:System.Windows.Forms.Control.Location%2A> property to set a control's X and Y positions simultaneously.</span></span> <span data-ttu-id="cc9ee-121">位置を個別に設定するには、コントロールの <xref:System.Windows.Forms.Control.Left%2A> (**X**) サブプロパティまたは <xref:System.Windows.Forms.Control.Top%2A> (**Y**) サブプロパティを使用します。</span><span class="sxs-lookup"><span data-stu-id="cc9ee-121">To set a position individually, use the control's <xref:System.Windows.Forms.Control.Left%2A> (**X**) or <xref:System.Windows.Forms.Control.Top%2A> (**Y**) subproperty.</span></span> <span data-ttu-id="cc9ee-122"><xref:System.Drawing.Point>この構造体にはボタンの座標のコピーが含まれているため、ボタンの位置を表す構造体の X 座標と Y 座標は暗黙的に設定しないようにしてください。</span><span class="sxs-lookup"><span data-stu-id="cc9ee-122">Do not try to implicitly set the X and Y coordinates of the <xref:System.Drawing.Point> structure that represents the button's location, because this structure contains a copy of the button's coordinates.</span></span>

## <a name="see-also"></a><span data-ttu-id="cc9ee-123">関連項目</span><span class="sxs-lookup"><span data-stu-id="cc9ee-123">See also</span></span>

- [<span data-ttu-id="cc9ee-124">Windows フォームコントロール</span><span class="sxs-lookup"><span data-stu-id="cc9ee-124">Windows Forms Controls</span></span>](index.md)
- [<span data-ttu-id="cc9ee-125">チュートリアル : スナップ線を使用した Windows フォーム上のコントロールの配置</span><span class="sxs-lookup"><span data-stu-id="cc9ee-125">Walkthrough: Arranging Controls on Windows Forms Using Snaplines</span></span>](walkthrough-arranging-controls-on-windows-forms-using-snaplines.md)
- [<span data-ttu-id="cc9ee-126">チュートリアル: TableLayoutPanel を使用した Windows フォーム上のコントロールの配置</span><span class="sxs-lookup"><span data-stu-id="cc9ee-126">Walkthrough: Arranging Controls on Windows Forms Using a TableLayoutPanel</span></span>](walkthrough-arranging-controls-on-windows-forms-using-a-tablelayoutpanel.md)
- [<span data-ttu-id="cc9ee-127">チュートリアル: FlowLayoutPanel を使用した Windows フォーム上のコントロールの配置</span><span class="sxs-lookup"><span data-stu-id="cc9ee-127">Walkthrough: Arranging Controls on Windows Forms Using a FlowLayoutPanel</span></span>](walkthrough-arranging-controls-on-windows-forms-using-a-flowlayoutpanel.md)
- [<span data-ttu-id="cc9ee-128">各 Windows フォーム コントロールのラベル設定とショートカットの作成</span><span class="sxs-lookup"><span data-stu-id="cc9ee-128">Labeling Individual Windows Forms Controls and Providing Shortcuts to Them</span></span>](labeling-individual-windows-forms-controls-and-providing-shortcuts-to-them.md)
- [<span data-ttu-id="cc9ee-129">Windows フォームで使用するコントロール</span><span class="sxs-lookup"><span data-stu-id="cc9ee-129">Controls to Use on Windows Forms</span></span>](controls-to-use-on-windows-forms.md)
- [<span data-ttu-id="cc9ee-130">Windows フォーム コントロールの機能別一覧</span><span class="sxs-lookup"><span data-stu-id="cc9ee-130">Windows Forms Controls by Function</span></span>](windows-forms-controls-by-function.md)
- <span data-ttu-id="cc9ee-131">[方法: Windows フォームの画面位置を設定する](/previous-versions/visualstudio/visual-studio-2010/52aha046(v=vs.100))</span><span class="sxs-lookup"><span data-stu-id="cc9ee-131">[How to: Set the Screen Location of Windows Forms](/previous-versions/visualstudio/visual-studio-2010/52aha046(v=vs.100))</span></span>
