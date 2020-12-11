---
title: RichTextBox コントロールにスクロールバーを表示する
ms.date: 03/30/2017
helpviewer_keywords:
- text boxes [Windows Forms], displaying scroll bars
- scroll bars [Windows Forms], displaying in controls
- RichTextBox control [Windows Forms], displaying scroll bars
ms.assetid: cdeb42e1-86e8-410c-ba46-18aec264ef5f
ms.openlocfilehash: 2185b572ef20765043d3df3dbfd8bf5b21cfac28
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/09/2020
ms.locfileid: "96982551"
---
# <a name="how-to-display-scroll-bars-in-the-windows-forms-richtextbox-control"></a>方法: Windows フォームの RichTextBox コントロールにスクロール バーを表示する
既定では、Windows フォームコントロールには、 <xref:System.Windows.Forms.RichTextBox> 必要に応じて水平スクロールバーと垂直スクロールバーが表示されます。 次の表に示すように、コントロールのプロパティに使用できる値は7つあり <xref:System.Windows.Forms.RichTextBox.ScrollBars%2A> <xref:System.Windows.Forms.RichTextBox> ます。  
  
### <a name="to-display-scroll-bars-in-a-richtextbox-control"></a>RichTextBox コントロールにスクロールバーを表示するには  
  
1. <xref:System.Windows.Forms.RichTextBox.Multiline%2A> プロパティを `true`に設定します。 <xref:System.Windows.Forms.RichTextBox.Multiline%2A>プロパティがに設定されている場合、水平を含むスクロールバーの種類は表示されません `false` 。  
  
2. プロパティを <xref:System.Windows.Forms.RichTextBox.ScrollBars%2A> 列挙体の適切な値に設定し <xref:System.Windows.Forms.RichTextBoxScrollBars> ます。  
  
    |値|説明|  
    |-----------|-----------------|  
    |<xref:System.Windows.Forms.RichTextBoxScrollBars.Both> (既定値)|テキストがコントロールの幅または長さを超えた場合にのみ、水平または垂直のスクロールバー、またはその両方を表示します。|  
    |<xref:System.Windows.Forms.RichTextBoxScrollBars.None>|どの種類のスクロールバーも表示されません。|  
    |<xref:System.Windows.Forms.RichTextBoxScrollBars.Horizontal>|テキストがコントロールの幅を超えた場合にのみ、水平スクロールバーを表示します。 (これを行うには、 <xref:System.Windows.Forms.TextBoxBase.WordWrap%2A> プロパティをに設定する必要があり `false` ます)。|  
    |<xref:System.Windows.Forms.RichTextBoxScrollBars.Vertical>|テキストがコントロールの高さを超えた場合にのみ、垂直スクロールバーを表示します。|  
    |<xref:System.Windows.Forms.RichTextBoxScrollBars.ForcedHorizontal>|プロパティがに設定されている場合、水平スクロールバーを表示 <xref:System.Windows.Forms.TextBoxBase.WordWrap%2A> `false` します。 テキストがコントロールの幅を超えていない場合、スクロールバーは淡色表示されます。|  
    |<xref:System.Windows.Forms.RichTextBoxScrollBars.ForcedVertical>|常に垂直スクロールバーを表示します。 テキストがコントロールの長さを超えていない場合、スクロールバーは淡色表示されます。|  
    |<xref:System.Windows.Forms.RichTextBoxScrollBars.ForcedBoth>|常に垂直スクロールバーを表示します。 プロパティがに設定されている場合、水平スクロールバーを表示 <xref:System.Windows.Forms.TextBoxBase.WordWrap%2A> `false` します。 テキストがコントロールの幅または長さを超えていない場合、スクロールバーはグレー表示されます。|  
  
3. <xref:System.Windows.Forms.TextBoxBase.WordWrap%2A> プロパティに適切な値を設定します。  
  
    |値|説明|  
    |-----------|-----------------|  
    |`false`|コントロール内のテキストは、コントロールの幅に合わせて自動的に調整されないので、改行に達するまで右にスクロールします。 上にある水平スクロールバーまたは両方を選択した場合は、この値を使用します。|  
    |`true` (既定)|コントロール内のテキストは、コントロールの幅に合わせて自動的に調整されます。 水平スクロールバーは表示されません。 1つ以上の段落を表示する場合は、この値を使用します。|  
  
## <a name="see-also"></a>関連項目

- <xref:System.Windows.Forms.RichTextBoxScrollBars>
- <xref:System.Windows.Forms.RichTextBox>
- [RichTextBox コントロール](richtextbox-control-windows-forms.md)
- [Windows フォームで使用するコントロール](controls-to-use-on-windows-forms.md)
