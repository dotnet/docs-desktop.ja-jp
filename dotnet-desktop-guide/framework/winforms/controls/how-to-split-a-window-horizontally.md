---
title: '方法: ウィンドウを水平方向に分割する'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- SplitContainer control [Windows Forms], horizontal splitter
- splitter windows [Windows Forms], changing splitter orientation
- splitter windows [Windows Forms], horizontal
- windows [Windows Forms], splitting horizontally
ms.assetid: a1f74f29-048c-4723-85fa-b9d375ab8f4b
ms.openlocfilehash: 7ef3fe1210ae42c52a4fd7f23633d6566bc102a5
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/09/2020
ms.locfileid: "96982799"
---
# <a name="how-to-split-a-window-horizontally"></a><span data-ttu-id="d1632-102">方法: ウィンドウを水平方向に分割する</span><span class="sxs-lookup"><span data-stu-id="d1632-102">How to: Split a Window Horizontally</span></span>
<span data-ttu-id="d1632-103">次のコード例では、コントロールを水平方向に分割する分割線を使用し <xref:System.Windows.Forms.SplitContainer> ます。</span><span class="sxs-lookup"><span data-stu-id="d1632-103">The following code example makes the splitter that divides the <xref:System.Windows.Forms.SplitContainer> control horizontal.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="d1632-104">コントロール <xref:System.Windows.Forms.SplitContainer.Orientation%2A> のプロパティは、 <xref:System.Windows.Forms.SplitContainer> コントロール自体ではなく、スプリッターの方向を決定します。</span><span class="sxs-lookup"><span data-stu-id="d1632-104">The <xref:System.Windows.Forms.SplitContainer.Orientation%2A> property of the <xref:System.Windows.Forms.SplitContainer> control determines the direction of the splitter, not of the control itself.</span></span>  
  
### <a name="to-split-a-window-horizontally"></a><span data-ttu-id="d1632-105">ウィンドウを水平方向に分割するには</span><span class="sxs-lookup"><span data-stu-id="d1632-105">To split a window horizontally</span></span>  
  
1. <span data-ttu-id="d1632-106">プロシージャ内で、 <xref:System.Windows.Forms.SplitContainer.Orientation%2A> コントロールのプロパティ <xref:System.Windows.Forms.SplitContainer> をに設定 <xref:System.Windows.Forms.Orientation.Horizontal> します。</span><span class="sxs-lookup"><span data-stu-id="d1632-106">Within a procedure, set the <xref:System.Windows.Forms.SplitContainer.Orientation%2A> property of the <xref:System.Windows.Forms.SplitContainer> control to <xref:System.Windows.Forms.Orientation.Horizontal>.</span></span>  
  
    ```vb  
    Sub ShowSplitContainer()  
        Dim splitContainer1 as new SplitContainer()  
        splitContainer1.BorderStyle = BorderStyle.Fixed3D  
        splitContainer1.Location = New System.Drawing.Point(74, 20)  
        splitContainer1.Name = "DemoSplitContainer"  
        splitContainer1.Size = New System.Drawing.Size(212, 435)  
        splitContainer1.TabIndex = 0  
        splitContainer1.Orientation = Orientation.Horizontal  
        Controls.Add(splitContainer1)  
    End Sub  
    ```  
  
    ```csharp  
    public void showSplitContainer()  
    {  
        SplitContainer splitContainer1 = new SplitContainer ();  
        splitContainer1.BorderStyle = BorderStyle.Fixed3D;  
        splitContainer1.Location = new System.Drawing.Point (74, 20);  
        splitContainer1.Name = "DemoSplitContainer";  
        splitContainer1.Size = new System.Drawing.Size (212, 435);  
        splitContainer1.TabIndex = 0;  
        splitContainer1.Orientation = Orientation.Horizontal;  
        this.Controls.Add (splitContainer1);  
  
    }  
    ```  
  
## <a name="see-also"></a><span data-ttu-id="d1632-107">関連項目</span><span class="sxs-lookup"><span data-stu-id="d1632-107">See also</span></span>

- <xref:System.Windows.Forms.SplitContainer>
- [<span data-ttu-id="d1632-108">SplitContainer コントロール</span><span class="sxs-lookup"><span data-stu-id="d1632-108">SplitContainer Control</span></span>](splitcontainer-control-windows-forms.md)
