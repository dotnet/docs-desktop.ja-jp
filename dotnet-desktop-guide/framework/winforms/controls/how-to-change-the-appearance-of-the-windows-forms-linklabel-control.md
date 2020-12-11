---
title: LinkLabel コントロールの外観を変更する
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- LinkLabel properties
- LinkLabel control [Windows Forms], changing appearance of links
- links [Windows Forms], changing appearance
- examples [Windows Forms], LinkLabel control
- LinkLabel control [Windows Forms], examples
ms.assetid: fdc5854f-5162-4457-8cbe-1042feb2d132
ms.openlocfilehash: df66991289373a05fc7c27b7768a96643e3bbae0
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/09/2020
ms.locfileid: "96980923"
---
# <a name="how-to-change-the-appearance-of-the-windows-forms-linklabel-control"></a><span data-ttu-id="9648f-102">方法: Windows フォーム LinkLabel コントロールの表示形式を変更する</span><span class="sxs-lookup"><span data-stu-id="9648f-102">How to: Change the Appearance of the Windows Forms LinkLabel Control</span></span>
<span data-ttu-id="9648f-103">さまざまな目的に合わせて、コントロールによって表示されるテキストを変更でき <xref:System.Windows.Forms.LinkLabel> ます。</span><span class="sxs-lookup"><span data-stu-id="9648f-103">You can change the text displayed by the <xref:System.Windows.Forms.LinkLabel> control to suit a variety of purposes.</span></span> <span data-ttu-id="9648f-104">たとえば、テキストを特定の色に下線付きで表示するように設定することによって、テキストをクリックできることをユーザーに示すのが一般的です。</span><span class="sxs-lookup"><span data-stu-id="9648f-104">For example, it is common practice to indicate to the user that text can be clicked by setting the text to appear in a specific color with an underline.</span></span> <span data-ttu-id="9648f-105">ユーザーがテキストをクリックすると、色が別の色に変わります。</span><span class="sxs-lookup"><span data-stu-id="9648f-105">After the user clicks the text, the color changes to a different color.</span></span> <span data-ttu-id="9648f-106">この動作を制御するには、、、、、の各プロパティの5つのプロパティを設定します <xref:System.Windows.Forms.LinkLabel.LinkBehavior%2A> <xref:System.Windows.Forms.LinkLabel.LinkArea%2A> <xref:System.Windows.Forms.LinkLabel.LinkColor%2A> <xref:System.Windows.Forms.LinkLabel.VisitedLinkColor%2A> <xref:System.Windows.Forms.LinkLabel.LinkVisited%2A> 。</span><span class="sxs-lookup"><span data-stu-id="9648f-106">To control this behavior, you can set five different properties: the <xref:System.Windows.Forms.LinkLabel.LinkBehavior%2A>, <xref:System.Windows.Forms.LinkLabel.LinkArea%2A>, <xref:System.Windows.Forms.LinkLabel.LinkColor%2A>, <xref:System.Windows.Forms.LinkLabel.VisitedLinkColor%2A>, and <xref:System.Windows.Forms.LinkLabel.LinkVisited%2A> properties.</span></span>  
  
### <a name="to-change-the-appearance-of-a-linklabel-control"></a><span data-ttu-id="9648f-107">LinkLabel コントロールの外観を変更するには</span><span class="sxs-lookup"><span data-stu-id="9648f-107">To change the appearance of a LinkLabel control</span></span>  
  
1. <span data-ttu-id="9648f-108"><xref:System.Windows.Forms.LinkLabel.LinkColor%2A>プロパティとプロパティを、 <xref:System.Windows.Forms.LinkLabel.VisitedLinkColor%2A> 必要な色に設定します。</span><span class="sxs-lookup"><span data-stu-id="9648f-108">Set the <xref:System.Windows.Forms.LinkLabel.LinkColor%2A> and <xref:System.Windows.Forms.LinkLabel.VisitedLinkColor%2A> properties to the colors you want.</span></span>  
  
     <span data-ttu-id="9648f-109">これは、プログラムによって、または [ **プロパティ** ] ウィンドウでデザイン時に行うことができます。</span><span class="sxs-lookup"><span data-stu-id="9648f-109">This can be done either programmatically or at design time in the **Properties** window.</span></span>  
  
    ```vb  
    ' You can set the color using decimal values for red, green, and blue  
    LinkLabel1.LinkColor = Color.FromArgb(0, 0, 255)  
    ' Or you can set the color using defined constants  
    LinkLabel1.VisitedLinkColor = Color.Purple  
    ```  
  
    ```csharp  
    // You can set the color using decimal values for red, green, and blue  
    linkLabel1.LinkColor = Color.FromArgb(0, 0, 255);  
    // Or you can set the color using defined constants  
    linkLabel1.VisitedLinkColor = Color.Purple;  
    ```  
  
    ```cpp  
    // You can set the color using decimal values for red, green, and blue  
    linkLabel1->LinkColor = Color::FromArgb(0, 0, 255);  
    // Or you can set the color using defined constants  
    linkLabel1->VisitedLinkColor = Color::Purple;  
    ```  
  
2. <span data-ttu-id="9648f-110">プロパティを <xref:System.Windows.Forms.LinkLabel.Text%2A> 適切なキャプションに設定します。</span><span class="sxs-lookup"><span data-stu-id="9648f-110">Set the <xref:System.Windows.Forms.LinkLabel.Text%2A> property to an appropriate caption.</span></span>  
  
     <span data-ttu-id="9648f-111">これは、プログラムによって、または [ **プロパティ** ] ウィンドウでデザイン時に行うことができます。</span><span class="sxs-lookup"><span data-stu-id="9648f-111">This can be done either programmatically or at design time in the **Properties** window.</span></span>  
  
    ```vb  
    LinkLabel1.Text = "Click here to see more."  
    ```  
  
    ```csharp  
    linkLabel1.Text = "Click here to see more.";  
    ```  
  
    ```cpp  
    linkLabel1->Text = "Click here to see more.";  
    ```  
  
3. <span data-ttu-id="9648f-112">プロパティを設定し <xref:System.Windows.Forms.LinkLabel.LinkArea%2A> て、キャプションのどの部分がリンクとして示されるかを決定します。</span><span class="sxs-lookup"><span data-stu-id="9648f-112">Set the <xref:System.Windows.Forms.LinkLabel.LinkArea%2A> property to determine which part of the caption will be indicated as a link.</span></span>  
  
     <span data-ttu-id="9648f-113"><xref:System.Windows.Forms.LinkLabel.LinkArea%2A>値は、 <xref:System.Windows.Forms.LinkArea> 2 つの数値 (開始文字の位置と文字の数) を含むで表されます。</span><span class="sxs-lookup"><span data-stu-id="9648f-113">The <xref:System.Windows.Forms.LinkLabel.LinkArea%2A> value is represented with a <xref:System.Windows.Forms.LinkArea> containing two numbers, the starting character position and the number of characters.</span></span> <span data-ttu-id="9648f-114">これは、プログラムによって、または [ **プロパティ** ] ウィンドウでデザイン時に行うことができます。</span><span class="sxs-lookup"><span data-stu-id="9648f-114">This can be done either programmatically or at design time in the **Properties** window.</span></span>  
  
    ```vb  
    LinkLabel1.LinkArea = new LinkArea(6,4)  
    ```  
  
    ```csharp  
    linkLabel1.LinkArea = new LinkArea(6,4);  
    ```  
  
    ```cpp  
    linkLabel1->LinkArea = LinkArea(6,4);  
    ```  
  
4. <span data-ttu-id="9648f-115">プロパティを <xref:System.Windows.Forms.LinkLabel.LinkBehavior%2A> 、、 <xref:System.Windows.Forms.LinkBehavior.AlwaysUnderline> <xref:System.Windows.Forms.LinkBehavior.HoverUnderline> またはに設定 <xref:System.Windows.Forms.LinkBehavior.NeverUnderline> します。</span><span class="sxs-lookup"><span data-stu-id="9648f-115">Set the <xref:System.Windows.Forms.LinkLabel.LinkBehavior%2A> property to <xref:System.Windows.Forms.LinkBehavior.AlwaysUnderline>, <xref:System.Windows.Forms.LinkBehavior.HoverUnderline>, or <xref:System.Windows.Forms.LinkBehavior.NeverUnderline>.</span></span>  
  
     <span data-ttu-id="9648f-116">に設定されている場合 <xref:System.Windows.Forms.LinkBehavior.HoverUnderline> 、によって決定されるキャプションの部分に <xref:System.Windows.Forms.LinkLabel.LinkArea%2A> は、ポインターがその上にあるときにのみ下線が引かれます。</span><span class="sxs-lookup"><span data-stu-id="9648f-116">If it is set to <xref:System.Windows.Forms.LinkBehavior.HoverUnderline>, the part of the caption determined by <xref:System.Windows.Forms.LinkLabel.LinkArea%2A> will only be underlined when the pointer rests on it.</span></span>  
  
5. <span data-ttu-id="9648f-117"><xref:System.Windows.Forms.LinkLabel.LinkClicked>イベントハンドラーで、 <xref:System.Windows.Forms.LinkLabel.LinkVisited%2A> プロパティをに設定 `true` します。</span><span class="sxs-lookup"><span data-stu-id="9648f-117">In the <xref:System.Windows.Forms.LinkLabel.LinkClicked> event handler, set the <xref:System.Windows.Forms.LinkLabel.LinkVisited%2A> property to `true`.</span></span>  
  
     <span data-ttu-id="9648f-118">リンクが参照されている場合は、通常は色によって、何らかの形で表示を変更します。</span><span class="sxs-lookup"><span data-stu-id="9648f-118">When a link has been visited, it is common practice to change its appearance in some way, usually by color.</span></span> <span data-ttu-id="9648f-119">テキストは、プロパティによって指定された色に変更され <xref:System.Windows.Forms.LinkLabel.VisitedLinkColor%2A> ます。</span><span class="sxs-lookup"><span data-stu-id="9648f-119">The text will change to the color specified by the <xref:System.Windows.Forms.LinkLabel.VisitedLinkColor%2A> property.</span></span>  
  
    ```vb  
    Protected Sub LinkLabel1_LinkClicked (ByVal sender As Object, _  
       ByVal e As EventArgs) Handles LinkLabel1.LinkClicked  
       ' Change the color of the link text  
       ' by setting LinkVisited to True.  
       LinkLabel1.LinkVisited = True  
       ' Then do whatever other action is appropriate  
    End Sub  
    ```  
  
    ```csharp  
    protected void LinkLabel1_LinkClicked(object sender, System.EventArgs e)  
    {  
       // Change the color of the link text by setting LinkVisited
       // to True.  
       linkLabel1.LinkVisited = true;  
       // Then do whatever other action is appropriate  
    }  
    ```  
  
    ```cpp  
    private:  
       System::Void linkLabel1_LinkClicked(System::Object ^  sender,  
          System::Windows::Forms::LinkLabelLinkClickedEventArgs ^  e)  
       {  
          // Change the color of the link text by setting LinkVisited
          // to True.  
          linkLabel1->LinkVisited = true;  
          // Then do whatever other action is appropriate  
       }  
    ```  
  
## <a name="see-also"></a><span data-ttu-id="9648f-120">関連項目</span><span class="sxs-lookup"><span data-stu-id="9648f-120">See also</span></span>

- <xref:System.Windows.Forms.LinkLabel.LinkArea%2A>
- <xref:System.Windows.Forms.LinkLabel.LinkColor%2A>
- <xref:System.Windows.Forms.LinkLabel.VisitedLinkColor%2A>
- <xref:System.Windows.Forms.LinkLabel.LinkVisited%2A>
- [<span data-ttu-id="9648f-121">LinkLabel コントロールの概要</span><span class="sxs-lookup"><span data-stu-id="9648f-121">LinkLabel Control Overview</span></span>](linklabel-control-overview-windows-forms.md)
- [<span data-ttu-id="9648f-122">方法: Windows フォーム LinkLabel コントロールでオブジェクトまたは Web ページにリンクする</span><span class="sxs-lookup"><span data-stu-id="9648f-122">How to: Link to an Object or Web Page with the Windows Forms LinkLabel Control</span></span>](link-to-an-object-or-web-page-with-wf-linklabel-control.md)
- [<span data-ttu-id="9648f-123">LinkLabel コントロール</span><span class="sxs-lookup"><span data-stu-id="9648f-123">LinkLabel Control</span></span>](linklabel-control-windows-forms.md)
