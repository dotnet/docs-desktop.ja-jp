---
title: 'チュートリアル: ドラッグアンドドロップ操作の実行'
description: Windows フォームでドラッグアンドドロップ操作を実行する方法について説明します。これには、一連のイベント (特に、DragEnter、System.windows.dragdrop.dragleave>、System.windows.dragdrop.drop> イベント) を処理します。
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- Windows Forms, drag and drop operations
- drag and drop [Windows Forms], Windows Forms
ms.assetid: eb66f6bf-4a7d-4c2d-b276-40fefb2d3b6c
ms.openlocfilehash: 83bfda875e2fdec3981bbcb8f8f7be00db342440
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/09/2020
ms.locfileid: "96981156"
---
# <a name="walkthrough-performing-a-drag-and-drop-operation-in-windows-forms"></a><span data-ttu-id="f89e5-103">チュートリアル: Windows フォームにおけるドラッグ アンド ドロップ操作の実行</span><span class="sxs-lookup"><span data-stu-id="f89e5-103">Walkthrough: Performing a Drag-and-Drop Operation in Windows Forms</span></span>
<span data-ttu-id="f89e5-104">Windows ベースのアプリケーション内でドラッグアンドドロップ操作を実行するには、一連のイベント (特に、、、およびイベント) を処理する必要があり <xref:System.Windows.Forms.Control.DragEnter> <xref:System.Windows.Forms.Control.DragLeave> <xref:System.Windows.Forms.Control.DragDrop> ます。</span><span class="sxs-lookup"><span data-stu-id="f89e5-104">To perform drag-and-drop operations within Windows-based applications you must handle a series of events, most notably the <xref:System.Windows.Forms.Control.DragEnter>, <xref:System.Windows.Forms.Control.DragLeave>, and <xref:System.Windows.Forms.Control.DragDrop> events.</span></span> <span data-ttu-id="f89e5-105">これらのイベントのイベント引数で使用できる情報を操作することにより、ドラッグアンドドロップ操作を容易に行うことができます。</span><span class="sxs-lookup"><span data-stu-id="f89e5-105">By working with the information available in the event arguments of these events, you can easily facilitate drag-and-drop operations.</span></span>  
  
## <a name="dragging-data"></a><span data-ttu-id="f89e5-106">データのドラッグ</span><span class="sxs-lookup"><span data-stu-id="f89e5-106">Dragging Data</span></span>  
 <span data-ttu-id="f89e5-107">ドラッグアンドドロップ操作はすべて、ドラッグで開始されます。</span><span class="sxs-lookup"><span data-stu-id="f89e5-107">All drag-and-drop operations begin with dragging.</span></span> <span data-ttu-id="f89e5-108">ドラッグの開始時に収集されるデータを有効にする機能は、メソッドで実装され <xref:System.Windows.Forms.Control.DoDragDrop%2A> ます。</span><span class="sxs-lookup"><span data-stu-id="f89e5-108">The functionality to enable data to be collected when dragging begins is implemented in the <xref:System.Windows.Forms.Control.DoDragDrop%2A> method.</span></span>  
  
 <span data-ttu-id="f89e5-109">次の例では、 <xref:System.Windows.Forms.Control.MouseDown> イベントを使用してドラッグ操作を開始しています。これは最も直観的です (ドラッグアンドドロップ操作のほとんどは、押されているマウスボタンで開始されます)。</span><span class="sxs-lookup"><span data-stu-id="f89e5-109">In the following example, the <xref:System.Windows.Forms.Control.MouseDown> event is used to start the drag operation because it is the most intuitive (most drag-and-drop actions begin with the mouse button being depressed).</span></span> <span data-ttu-id="f89e5-110">ただし、すべてのイベントを使用してドラッグアンドドロッププロシージャを開始できることに注意してください。</span><span class="sxs-lookup"><span data-stu-id="f89e5-110">However, remember that any event could be used to initiate a drag-and-drop procedure.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="f89e5-111">特定のコントロールには、ドラッグ固有のカスタムイベントがあります。</span><span class="sxs-lookup"><span data-stu-id="f89e5-111">Certain controls have custom drag-specific events.</span></span> <span data-ttu-id="f89e5-112"><xref:System.Windows.Forms.ListView> <xref:System.Windows.Forms.TreeView> たとえば、コントロールとコントロールには、イベントがあり <xref:System.Windows.Forms.TreeView.ItemDrag> ます。</span><span class="sxs-lookup"><span data-stu-id="f89e5-112">The <xref:System.Windows.Forms.ListView> and <xref:System.Windows.Forms.TreeView> controls, for example, have an <xref:System.Windows.Forms.TreeView.ItemDrag> event.</span></span>  
  
#### <a name="to-start-a-drag-operation"></a><span data-ttu-id="f89e5-113">ドラッグ操作を開始するには</span><span class="sxs-lookup"><span data-stu-id="f89e5-113">To start a drag operation</span></span>  
  
1. <span data-ttu-id="f89e5-114">ドラッグを開始するコントロールのイベントでは、メソッドを使用して、ドラッグする <xref:System.Windows.Forms.Control.MouseDown> `DoDragDrop` データを設定します。ドラッグすると、ドラッグが許可されます。</span><span class="sxs-lookup"><span data-stu-id="f89e5-114">In the <xref:System.Windows.Forms.Control.MouseDown> event for the control where the drag will begin, use the `DoDragDrop` method to set the data to be dragged and the allowed effect dragging will have.</span></span> <span data-ttu-id="f89e5-115">詳細については、次のトピックを参照してください。 <xref:System.Windows.Forms.DragEventArgs.Data%2A> および <xref:System.Windows.Forms.DragEventArgs.AllowedEffect%2A></span><span class="sxs-lookup"><span data-stu-id="f89e5-115">For more information, see <xref:System.Windows.Forms.DragEventArgs.Data%2A> and <xref:System.Windows.Forms.DragEventArgs.AllowedEffect%2A>.</span></span>  
  
     <span data-ttu-id="f89e5-116">次の例は、ドラッグ操作を開始する方法を示しています。</span><span class="sxs-lookup"><span data-stu-id="f89e5-116">The following example shows how to initiate a drag operation.</span></span> <span data-ttu-id="f89e5-117">ドラッグが開始するコントロールはコントロール <xref:System.Windows.Forms.Button> で、ドラッグされるデータはコントロールのプロパティを表す文字列であり、許可されて <xref:System.Windows.Forms.Control.Text%2A> <xref:System.Windows.Forms.Button> いる効果はコピーまたは移動のいずれかになります。</span><span class="sxs-lookup"><span data-stu-id="f89e5-117">The control where the drag begins is a <xref:System.Windows.Forms.Button> control, the data being dragged is the string representing the <xref:System.Windows.Forms.Control.Text%2A> property of the <xref:System.Windows.Forms.Button> control, and the allowed effects are either copying or moving.</span></span>  
  
    ```vb  
    Private Sub Button1_MouseDown(ByVal sender As Object, ByVal e As System.Windows.Forms.MouseEventArgs) Handles Button1.MouseDown  
       Button1.DoDragDrop(Button1.Text, DragDropEffects.Copy Or DragDropEffects.Move)  
    End Sub  
    ```  
  
    ```csharp  
    private void button1_MouseDown(object sender,
    System.Windows.Forms.MouseEventArgs e)  
    {  
       button1.DoDragDrop(button1.Text, DragDropEffects.Copy |
          DragDropEffects.Move);  
    }  
    ```  
  
    > [!NOTE]
    > <span data-ttu-id="f89e5-118">任意のデータをメソッドのパラメーターとして使用でき `DoDragDrop` ます。上記の例では、 <xref:System.Windows.Forms.Control.Text%2A> <xref:System.Windows.Forms.Button> プロパティはドラッグ元 (コントロール) に関連付けられていたため、値をハードコーディングしたり、データセットからデータを取得したりする代わりに、コントロールのプロパティが使用されていました。 <xref:System.Windows.Forms.Button></span><span class="sxs-lookup"><span data-stu-id="f89e5-118">Any data can be used as a parameter in the `DoDragDrop` method; in the example above, the <xref:System.Windows.Forms.Control.Text%2A> property of the <xref:System.Windows.Forms.Button> control was used (rather than hard-coding a value or retrieving data from a dataset) because the property was related to the location being dragged from (the <xref:System.Windows.Forms.Button> control).</span></span> <span data-ttu-id="f89e5-119">ドラッグアンドドロップ操作を Windows ベースのアプリケーションに組み込むときは、この点に注意してください。</span><span class="sxs-lookup"><span data-stu-id="f89e5-119">Keep this in mind as you incorporate drag-and-drop operations into your Windows-based applications.</span></span>  
  
 <span data-ttu-id="f89e5-120">ドラッグ操作が有効になっている間は、イベントを処理して、 <xref:System.Windows.Forms.Control.QueryContinueDrag> ドラッグ操作を続行するためにシステムの "アクセス許可" を要求します。</span><span class="sxs-lookup"><span data-stu-id="f89e5-120">While a drag operation is in effect, you can handle the <xref:System.Windows.Forms.Control.QueryContinueDrag> event, which "asks permission" of the system to continue the drag operation.</span></span> <span data-ttu-id="f89e5-121">このメソッドを処理する場合は、ドラッグ操作に影響を与えるメソッドを呼び出すための適切なポイントでもあります。たとえば、 <xref:System.Windows.Forms.TreeNode> <xref:System.Windows.Forms.TreeView> カーソルがコントロールの上に置かれたときにコントロールのを展開する場合などです。</span><span class="sxs-lookup"><span data-stu-id="f89e5-121">When handling this method, it is also the appropriate point for you to call methods that will have an effect on the drag operation, such as expanding a <xref:System.Windows.Forms.TreeNode> in a <xref:System.Windows.Forms.TreeView> control when the cursor hovers over it.</span></span>  
  
## <a name="dropping-data"></a><span data-ttu-id="f89e5-122">データの削除</span><span class="sxs-lookup"><span data-stu-id="f89e5-122">Dropping Data</span></span>  
 <span data-ttu-id="f89e5-123">Windows フォームまたはコントロール上の場所からデータのドラッグを開始した後は、どこかにデータをドロップすることをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="f89e5-123">Once you have begun dragging data from a location on a Windows Form or control, you will naturally want to drop it somewhere.</span></span> <span data-ttu-id="f89e5-124">カーソルは、データの削除用に正しく構成されているフォームまたはコントロールの領域と交差すると変更されます。</span><span class="sxs-lookup"><span data-stu-id="f89e5-124">The cursor will change when it crosses an area of a form or control that is correctly configured for dropping data.</span></span> <span data-ttu-id="f89e5-125">Windows フォームまたはコントロール内の領域は、プロパティを設定 <xref:System.Windows.Forms.Control.AllowDrop%2A> し、イベントおよびイベントを処理することによって、削除されたデータを受け入れることができ <xref:System.Windows.Forms.Control.DragEnter> <xref:System.Windows.Forms.Control.DragDrop> ます。</span><span class="sxs-lookup"><span data-stu-id="f89e5-125">Any area within a Windows Form or control can be made to accept dropped data by setting the <xref:System.Windows.Forms.Control.AllowDrop%2A> property and handling the <xref:System.Windows.Forms.Control.DragEnter> and <xref:System.Windows.Forms.Control.DragDrop> events.</span></span>  
  
#### <a name="to-perform-a-drop"></a><span data-ttu-id="f89e5-126">削除を実行するには</span><span class="sxs-lookup"><span data-stu-id="f89e5-126">To perform a drop</span></span>  
  
1. <span data-ttu-id="f89e5-127"><xref:System.Windows.Forms.Control.AllowDrop%2A>プロパティを true に設定します。</span><span class="sxs-lookup"><span data-stu-id="f89e5-127">Set the <xref:System.Windows.Forms.Control.AllowDrop%2A> property to true.</span></span>  
  
2. <span data-ttu-id="f89e5-128">ドロップが `DragEnter` 発生するコントロールのイベントで、ドラッグされるデータが許容される型 (この場合は) であることを確認し <xref:System.Windows.Forms.Control.Text%2A> ます。</span><span class="sxs-lookup"><span data-stu-id="f89e5-128">In the `DragEnter` event for the control where the drop will occur, ensure that the data being dragged is of an acceptable type (in this case, <xref:System.Windows.Forms.Control.Text%2A>).</span></span> <span data-ttu-id="f89e5-129">次に、このコードは、ドロップが列挙体の値に対して発生した場合に発生する効果を設定し <xref:System.Windows.Forms.DragDropEffects> ます。</span><span class="sxs-lookup"><span data-stu-id="f89e5-129">The code then sets the effect that will happen when the drop occurs to a value in the <xref:System.Windows.Forms.DragDropEffects> enumeration.</span></span> <span data-ttu-id="f89e5-130">詳細については、「<xref:System.Windows.Forms.DragEventArgs.Effect%2A>」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="f89e5-130">For more information, see <xref:System.Windows.Forms.DragEventArgs.Effect%2A>.</span></span>  
  
    ```vb  
    Private Sub TextBox1_DragEnter(ByVal sender As Object, ByVal e As System.Windows.Forms.DragEventArgs) Handles TextBox1.DragEnter  
       If (e.Data.GetDataPresent(DataFormats.Text)) Then  
         e.Effect = DragDropEffects.Copy  
       Else  
         e.Effect = DragDropEffects.None  
       End If  
    End Sub  
    ```  
  
    ```csharp  
    private void textBox1_DragEnter(object sender,
    System.Windows.Forms.DragEventArgs e)  
    {  
       if (e.Data.GetDataPresent(DataFormats.Text))
          e.Effect = DragDropEffects.Copy;  
       else  
          e.Effect = DragDropEffects.None;  
    }  
    ```  
  
    > [!NOTE]
    > <span data-ttu-id="f89e5-131">独自の <xref:System.Windows.Forms.DataFormats> オブジェクトをメソッドのパラメーターとして指定することで、独自のを定義でき <xref:System.Object> <xref:System.Windows.Forms.DataObject.SetData%2A> ます。</span><span class="sxs-lookup"><span data-stu-id="f89e5-131">You can define your own <xref:System.Windows.Forms.DataFormats> by specifying your own object as the <xref:System.Object> parameter of the <xref:System.Windows.Forms.DataObject.SetData%2A> method.</span></span> <span data-ttu-id="f89e5-132">これを行うときは、指定されたオブジェクトがシリアル化可能であることを確認してください。</span><span class="sxs-lookup"><span data-stu-id="f89e5-132">Be sure, when doing this, that the object specified is serializable.</span></span> <span data-ttu-id="f89e5-133">詳細については、「<xref:System.Runtime.Serialization.ISerializable>」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="f89e5-133">For more information, see <xref:System.Runtime.Serialization.ISerializable>.</span></span>  
  
3. <span data-ttu-id="f89e5-134">ドロップが <xref:System.Windows.Forms.Control.DragDrop> 発生するコントロールのイベントで、メソッドを使用し <xref:System.Windows.Forms.DataObject.GetData%2A> て、ドラッグされているデータを取得します。</span><span class="sxs-lookup"><span data-stu-id="f89e5-134">In the <xref:System.Windows.Forms.Control.DragDrop> event for the control where the drop will occur, use the <xref:System.Windows.Forms.DataObject.GetData%2A> method to retrieve the data being dragged.</span></span> <span data-ttu-id="f89e5-135">詳細については、「<xref:System.Security.Cryptography.Xml.DataObject.Data%2A>」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="f89e5-135">For more information, see <xref:System.Security.Cryptography.Xml.DataObject.Data%2A>.</span></span>  
  
     <span data-ttu-id="f89e5-136">次の例では、 <xref:System.Windows.Forms.TextBox> コントロールはドラッグされているコントロールです (ドロップが発生します)。</span><span class="sxs-lookup"><span data-stu-id="f89e5-136">In the example below, a <xref:System.Windows.Forms.TextBox> control is the control being dragged to (where the drop will occur).</span></span> <span data-ttu-id="f89e5-137">このコードは、 <xref:System.Windows.Forms.Control.Text%2A> <xref:System.Windows.Forms.TextBox> ドラッグされているデータと同じコントロールのプロパティを設定します。</span><span class="sxs-lookup"><span data-stu-id="f89e5-137">The code sets the <xref:System.Windows.Forms.Control.Text%2A> property of the <xref:System.Windows.Forms.TextBox> control equal to the data being dragged.</span></span>  
  
    ```vb  
    Private Sub TextBox1_DragDrop(ByVal sender As Object, ByVal e As System.Windows.Forms.DragEventArgs) Handles TextBox1.DragDrop  
       TextBox1.Text = e.Data.GetData(DataFormats.Text).ToString  
    End Sub  
    ```  
  
    ```csharp  
    private void textBox1_DragDrop(object sender,
    System.Windows.Forms.DragEventArgs e)  
    {  
       textBox1.Text = e.Data.GetData(DataFormats.Text).ToString();  
    }  
    ```  
  
    > [!NOTE]
    > <span data-ttu-id="f89e5-138">また、プロパティを操作することもできます <xref:System.Windows.Forms.DragEventArgs.KeyState%2A> 。これにより、ドラッグアンドドロップ操作中に押されたキーに応じて、特定の効果が発生します (たとえば、CTRL キーが押されたときに、ドラッグしたデータをコピーするのは標準です)。</span><span class="sxs-lookup"><span data-stu-id="f89e5-138">Additionally, you can work with the <xref:System.Windows.Forms.DragEventArgs.KeyState%2A> property, so that, depending on keys depressed during the drag-and-drop operation, certain effects occur (for example, it is standard to copy the dragged data when the CTRL key is pressed).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f89e5-139">関連項目</span><span class="sxs-lookup"><span data-stu-id="f89e5-139">See also</span></span>

- [<span data-ttu-id="f89e5-140">方法: クリップボードにデータを追加する</span><span class="sxs-lookup"><span data-stu-id="f89e5-140">How to: Add Data to the Clipboard</span></span>](how-to-add-data-to-the-clipboard.md)
- [<span data-ttu-id="f89e5-141">方法: クリップボードからデータを取得する</span><span class="sxs-lookup"><span data-stu-id="f89e5-141">How to: Retrieve Data from the Clipboard</span></span>](how-to-retrieve-data-from-the-clipboard.md)
- [<span data-ttu-id="f89e5-142">ドラッグ アンド ドロップ操作とクリップボードのサポート</span><span class="sxs-lookup"><span data-stu-id="f89e5-142">Drag-and-Drop Operations and Clipboard Support</span></span>](drag-and-drop-operations-and-clipboard-support.md)
