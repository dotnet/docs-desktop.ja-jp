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
# <a name="how-to-change-the-appearance-of-the-windows-forms-linklabel-control"></a>方法: Windows フォーム LinkLabel コントロールの表示形式を変更する
さまざまな目的に合わせて、コントロールによって表示されるテキストを変更でき <xref:System.Windows.Forms.LinkLabel> ます。 たとえば、テキストを特定の色に下線付きで表示するように設定することによって、テキストをクリックできることをユーザーに示すのが一般的です。 ユーザーがテキストをクリックすると、色が別の色に変わります。 この動作を制御するには、、、、、の各プロパティの5つのプロパティを設定します <xref:System.Windows.Forms.LinkLabel.LinkBehavior%2A> <xref:System.Windows.Forms.LinkLabel.LinkArea%2A> <xref:System.Windows.Forms.LinkLabel.LinkColor%2A> <xref:System.Windows.Forms.LinkLabel.VisitedLinkColor%2A> <xref:System.Windows.Forms.LinkLabel.LinkVisited%2A> 。  
  
### <a name="to-change-the-appearance-of-a-linklabel-control"></a>LinkLabel コントロールの外観を変更するには  
  
1. <xref:System.Windows.Forms.LinkLabel.LinkColor%2A>プロパティとプロパティを、 <xref:System.Windows.Forms.LinkLabel.VisitedLinkColor%2A> 必要な色に設定します。  
  
     これは、プログラムによって、または [ **プロパティ** ] ウィンドウでデザイン時に行うことができます。  
  
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
  
2. プロパティを <xref:System.Windows.Forms.LinkLabel.Text%2A> 適切なキャプションに設定します。  
  
     これは、プログラムによって、または [ **プロパティ** ] ウィンドウでデザイン時に行うことができます。  
  
    ```vb  
    LinkLabel1.Text = "Click here to see more."  
    ```  
  
    ```csharp  
    linkLabel1.Text = "Click here to see more.";  
    ```  
  
    ```cpp  
    linkLabel1->Text = "Click here to see more.";  
    ```  
  
3. プロパティを設定し <xref:System.Windows.Forms.LinkLabel.LinkArea%2A> て、キャプションのどの部分がリンクとして示されるかを決定します。  
  
     <xref:System.Windows.Forms.LinkLabel.LinkArea%2A>値は、 <xref:System.Windows.Forms.LinkArea> 2 つの数値 (開始文字の位置と文字の数) を含むで表されます。 これは、プログラムによって、または [ **プロパティ** ] ウィンドウでデザイン時に行うことができます。  
  
    ```vb  
    LinkLabel1.LinkArea = new LinkArea(6,4)  
    ```  
  
    ```csharp  
    linkLabel1.LinkArea = new LinkArea(6,4);  
    ```  
  
    ```cpp  
    linkLabel1->LinkArea = LinkArea(6,4);  
    ```  
  
4. プロパティを <xref:System.Windows.Forms.LinkLabel.LinkBehavior%2A> 、、 <xref:System.Windows.Forms.LinkBehavior.AlwaysUnderline> <xref:System.Windows.Forms.LinkBehavior.HoverUnderline> またはに設定 <xref:System.Windows.Forms.LinkBehavior.NeverUnderline> します。  
  
     に設定されている場合 <xref:System.Windows.Forms.LinkBehavior.HoverUnderline> 、によって決定されるキャプションの部分に <xref:System.Windows.Forms.LinkLabel.LinkArea%2A> は、ポインターがその上にあるときにのみ下線が引かれます。  
  
5. <xref:System.Windows.Forms.LinkLabel.LinkClicked>イベントハンドラーで、 <xref:System.Windows.Forms.LinkLabel.LinkVisited%2A> プロパティをに設定 `true` します。  
  
     リンクが参照されている場合は、通常は色によって、何らかの形で表示を変更します。 テキストは、プロパティによって指定された色に変更され <xref:System.Windows.Forms.LinkLabel.VisitedLinkColor%2A> ます。  
  
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
  
## <a name="see-also"></a>関連項目

- <xref:System.Windows.Forms.LinkLabel.LinkArea%2A>
- <xref:System.Windows.Forms.LinkLabel.LinkColor%2A>
- <xref:System.Windows.Forms.LinkLabel.VisitedLinkColor%2A>
- <xref:System.Windows.Forms.LinkLabel.LinkVisited%2A>
- [LinkLabel コントロールの概要](linklabel-control-overview-windows-forms.md)
- [方法: Windows フォーム LinkLabel コントロールでオブジェクトまたは Web ページにリンクする](link-to-an-object-or-web-page-with-wf-linklabel-control.md)
- [LinkLabel コントロール](linklabel-control-windows-forms.md)
