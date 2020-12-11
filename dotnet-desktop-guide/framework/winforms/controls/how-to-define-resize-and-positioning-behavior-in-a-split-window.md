---
title: '方法: 分割ウィンドウでのサイズ変更および位置指定動作を定義する'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- split windows [Windows Forms], resizing
- splitter windows [Windows Forms], resizing
- SplitContainer control [Windows Forms], resizing
ms.assetid: 9bf73f36-ed2d-4a02-b15a-0770eff4fdfa
ms.openlocfilehash: 8cdcfdfaa135a92ed6a6e96d4a72de2c97f2493d
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/09/2020
ms.locfileid: "96980875"
---
# <a name="how-to-define-resize-and-positioning-behavior-in-a-split-window"></a><span data-ttu-id="394cc-102">方法: 分割ウィンドウでのサイズ変更および位置指定動作を定義する</span><span class="sxs-lookup"><span data-stu-id="394cc-102">How to: Define Resize and Positioning Behavior in a Split Window</span></span>
<span data-ttu-id="394cc-103">コントロールのパネルは、 <xref:System.Windows.Forms.SplitContainer> ユーザーがサイズを変更して操作するのに適しています。</span><span class="sxs-lookup"><span data-stu-id="394cc-103">The panels of the <xref:System.Windows.Forms.SplitContainer> control lend themselves well to being resized and manipulated by users.</span></span> <span data-ttu-id="394cc-104">ただし、スプリッターがどこに配置され、どこに移動できるのかをプログラムで制御する必要がある場合もあります。</span><span class="sxs-lookup"><span data-stu-id="394cc-104">However, there will be times when you will want to programmatically control the splitter—where it is positioned and to what degree it can be moved.</span></span>  
  
 <span data-ttu-id="394cc-105"><xref:System.Windows.Forms.SplitContainer.SplitterIncrement%2A>コントロールのプロパティとその他のプロパティを使用すると、 <xref:System.Windows.Forms.SplitContainer> ユーザーインターフェイスの動作をニーズに合わせて細かく制御できます。</span><span class="sxs-lookup"><span data-stu-id="394cc-105">The <xref:System.Windows.Forms.SplitContainer.SplitterIncrement%2A> property and the other properties on the <xref:System.Windows.Forms.SplitContainer> control give you precise control over the behavior of your user interface to suit your needs.</span></span> <span data-ttu-id="394cc-106">次の表はそのようなプロパティです。</span><span class="sxs-lookup"><span data-stu-id="394cc-106">These properties are listed in the following table.</span></span>  
  
|<span data-ttu-id="394cc-107">名前</span><span class="sxs-lookup"><span data-stu-id="394cc-107">Name</span></span>|<span data-ttu-id="394cc-108">説明</span><span class="sxs-lookup"><span data-stu-id="394cc-108">Description</span></span>|  
|----------|-----------------|  
|<span data-ttu-id="394cc-109"><xref:System.Windows.Forms.SplitContainer.IsSplitterFixed%2A> プロパティ</span><span class="sxs-lookup"><span data-stu-id="394cc-109"><xref:System.Windows.Forms.SplitContainer.IsSplitterFixed%2A> property</span></span>|<span data-ttu-id="394cc-110">キーボードまたはマウスを使ってスプリッターを移動可能にするかどうかを決定します。</span><span class="sxs-lookup"><span data-stu-id="394cc-110">Determines if the splitter is movable by means of the keyboard or mouse.</span></span>|  
|<span data-ttu-id="394cc-111"><xref:System.Windows.Forms.SplitContainer.SplitterDistance%2A> プロパティ</span><span class="sxs-lookup"><span data-stu-id="394cc-111"><xref:System.Windows.Forms.SplitContainer.SplitterDistance%2A> property</span></span>|<span data-ttu-id="394cc-112">左端または上端から移動可能スプリッターバーまでの距離をピクセル単位で決定します。</span><span class="sxs-lookup"><span data-stu-id="394cc-112">Determines the distance in pixels from the left or upper edge to the movable splitter bar.</span></span>|  
|<span data-ttu-id="394cc-113"><xref:System.Windows.Forms.SplitContainer.SplitterIncrement%2A> プロパティ</span><span class="sxs-lookup"><span data-stu-id="394cc-113"><xref:System.Windows.Forms.SplitContainer.SplitterIncrement%2A> property</span></span>|<span data-ttu-id="394cc-114">ユーザーがスプリッターを移動できる最小距離をピクセル単位で指定します。</span><span class="sxs-lookup"><span data-stu-id="394cc-114">Determines the minimum distance, in pixels, that the splitter can be moved by the user.</span></span>|  
  
 <span data-ttu-id="394cc-115">次の例では、 <xref:System.Windows.Forms.SplitContainer.SplitterIncrement%2A> "スナップスプリッター" 効果を作成するようにプロパティを変更しています。ユーザーがスプリッターをドラッグすると、既定の1ではなく、10ピクセル単位で増加します。</span><span class="sxs-lookup"><span data-stu-id="394cc-115">The example below modifies the <xref:System.Windows.Forms.SplitContainer.SplitterIncrement%2A> property to create a "snapping splitter" effect; when the user drags the splitter, it increments in units of 10 pixels rather than the default 1.</span></span>  
  
### <a name="to-define-splitcontainer-resize-behavior"></a><span data-ttu-id="394cc-116">SplitContainer のサイズ変更動作を定義するには</span><span class="sxs-lookup"><span data-stu-id="394cc-116">To define SplitContainer resize behavior</span></span>  
  
1. <span data-ttu-id="394cc-117">プロシージャでは、プロパティを目的のサイズに設定して、 <xref:System.Windows.Forms.SplitContainer.SplitterIncrement%2A> スプリッターの "スナップ" 動作が実現されるようにします。</span><span class="sxs-lookup"><span data-stu-id="394cc-117">In a procedure, set the <xref:System.Windows.Forms.SplitContainer.SplitterIncrement%2A> property to the desired size, so that the 'snapping' behavior of the splitter is achieved.</span></span>  
  
     <span data-ttu-id="394cc-118">次のコード例では、フォームのイベント内で、 <xref:System.Windows.Forms.Form.Load> コントロール内のスプリッター <xref:System.Windows.Forms.SplitContainer> が、ドラッグ時に10ピクセルジャンプするように設定されています。</span><span class="sxs-lookup"><span data-stu-id="394cc-118">In the following code example, within the form's <xref:System.Windows.Forms.Form.Load> event, the splitter within the <xref:System.Windows.Forms.SplitContainer> control is set to jump 10 pixels when dragged.</span></span>  
  
    ```vb  
    Private Sub Form1_Load(ByVal sender As System.Object, _  
        ByVal e As System.EventArgs) Handles MyBase.Load  
        Dim splitSnapper as new SplitContainer()  
        splitSnapper.SplitterIncrement = 10  
        splitSnapper.Dock = DockStyle.Fill  
        splitSnapper.Parent = me  
    End Sub  
    ```  
  
    ```csharp  
    private void Form1_Load(System.Object sender, System.EventArgs e)  
    {  
        SplitContainer splitSnapper = new SplitContainer();  
        splitSnapper.SplitterIncrement = 10;  
        splitSnapper.Dock = DockStyle.Fill;  
        splitSnapper.Parent = this;  
    }  
    ```  
  
     <span data-ttu-id="394cc-119">(Visual C#)フォームのコンストラクターに次のコードを配置して、イベントハンドラーを登録します。</span><span class="sxs-lookup"><span data-stu-id="394cc-119">(Visual C#) Place the following code in the form's constructor to register the event handler.</span></span>  
  
    ```csharp  
    this.Load += new System.EventHandler(this.Form1_Load);  
    ```  
  
     <span data-ttu-id="394cc-120">分割線を左または右に少し移動すると、認識効果は得られません。ただし、いずれかの方向でマウスポインターが10ピクセルになると、スプリッターは新しい位置にスナップされます。</span><span class="sxs-lookup"><span data-stu-id="394cc-120">Moving the splitter slightly to the left or right will have no discernible effect; however, when the mouse pointer goes 10 pixels in either direction, the splitter will snap to the new position.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="394cc-121">関連項目</span><span class="sxs-lookup"><span data-stu-id="394cc-121">See also</span></span>

- <xref:System.Windows.Forms.SplitContainer>
- <xref:System.Windows.Forms.SplitContainer.SplitterIncrement%2A>
