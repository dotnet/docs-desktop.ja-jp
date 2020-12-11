---
title: LinkLabel コントロールから Web ページを表示する (Visual Basic)
ms.date: 03/30/2017
dev_langs:
- vb
f1_keywords:
- LinkLabel1_LinkClicked
helpviewer_keywords:
- examples [Windows Forms], LinkLabel control
- Web pages [Windows Forms], displaying
- linking [Windows Forms], to Web pages from forms
- Windows Forms, linking to Web pages
- LinkLabel control [Windows Forms], examples
ms.assetid: 477a7398-5971-4de3-b24c-f49f32bdb28a
ms.openlocfilehash: 75373d55b7bc5ef11e39d5b9546996cb1c4f6f7c
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/09/2020
ms.locfileid: "96974160"
---
# <a name="how-to-display-a-web-page-from-a-windows-forms-linklabel-control-visual-basic"></a>方法: Windows フォームの LinkLabel コントロールから Web ページを表示する (Visual Basic)
この例では、ユーザーが Windows フォームコントロールをクリックしたときに、既定のブラウザーに Web ページを表示し <xref:System.Windows.Forms.LinkLabel> ます。  
  
## <a name="example"></a>例  
  
```vb  
Private Sub Form1_Load(ByVal sender As System.Object, ByVal e _  
As System.EventArgs) Handles MyBase.Load  
    LinkLabel1.Text = "Click here to get more info."  
    LinkLabel1.Links.Add(6, 4, "www.microsoft.com")  
End Sub  
Private Sub LinkLabel1_LinkClicked(ByVal sender As System.Object, ByVal _  
e As System.Windows.Forms.LinkLabelLinkClickedEventArgs) Handles _  
LinkLabel1.LinkClicked  
    System.Diagnostics.Process.Start(e.Link.LinkData.ToString())  
End Sub  
```  
  
## <a name="compiling-the-code"></a>コードのコンパイル  
 この例で必要な要素は次のとおりです。  
  
- という名前の Windows フォーム `Form1` 。  
  
- `LinkLabel1` という名前の <xref:System.Windows.Forms.LinkLabel> コントロール。  
  
- アクティブなインターネット接続。  
  
## <a name="net-framework-security"></a>.NET Framework セキュリティ  
 メソッドの呼び出しには、 <xref:System.Diagnostics.Process.Start%2A> 完全な信頼が必要です。 詳細については、「<xref:System.Security.SecurityException>」を参照してください。  
  
## <a name="see-also"></a>関連項目

- <xref:System.Windows.Forms.LinkLabel>
- [LinkLabel コントロール](linklabel-control-windows-forms.md)
