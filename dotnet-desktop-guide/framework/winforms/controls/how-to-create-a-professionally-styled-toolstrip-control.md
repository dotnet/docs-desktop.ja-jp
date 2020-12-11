---
title: '方法: プロフェッショナル スタイルの ToolStrip コントロールを作成する'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- toolbars [Windows Forms]
- ToolStripProfessionalRenderer class [Windows Forms]
- ToolStripRenderer class [Windows Forms]
- ToolStrip control [Windows Forms]
ms.assetid: c208b2f6-8105-474b-9075-d582e1792870
ms.openlocfilehash: 4e4e899d583eb87b3ced7161f1fd274c0bcc591c
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/09/2020
ms.locfileid: "96982191"
---
# <a name="how-to-create-a-professionally-styled-toolstrip-control"></a>方法: プロフェッショナル スタイルの ToolStrip コントロールを作成する
<xref:System.Windows.Forms.ToolStripProfessionalRenderer> 型から派生する独自のクラスを記述することで、アプリケーションの <xref:System.Windows.Forms.ToolStrip> コントロールにプロフェッショナルな外観と動作 (操作性) を与えることができます。  
  
 この機能は Visual Studio で幅広くサポートされています。  
  
 「[チュートリアル: プロフェッショナル スタイルの ToolStrip コントロールの作成](walkthrough-creating-a-professionally-styled-toolstrip-control.md)」を参照してください。  
  
## <a name="example"></a>例  
 次のコード例は、コントロールを使用して、 <xref:System.Windows.Forms.ToolStrip> Microsoft® Outlook®によって提供される **ナビゲーションウィンドウ** に似た複合コントロールを作成する方法を示しています。  
  
 [!code-csharp[System.Windows.Forms.ToolStrip.StackView#1](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.ToolStrip.StackView/CS/StackView.cs#1)]
 [!code-vb[System.Windows.Forms.ToolStrip.StackView#1](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.ToolStrip.StackView/VB/StackView.vb#1)]  
  
## <a name="compiling-the-code"></a>コードのコンパイル  
 この例で必要な要素は次のとおりです。  
  
- System.Drawing アセンブリおよび System.Windows.Forms アセンブリへの参照。  
  
## <a name="see-also"></a>関連項目

- <xref:System.Windows.Forms.MenuStrip>
- <xref:System.Windows.Forms.ToolStrip>
- <xref:System.Windows.Forms.StatusStrip>
- [ToolStrip コントロール](toolstrip-control-windows-forms.md)
- [方法: フォームに標準メニュー項目を追加する](how-to-provide-standard-menu-items-to-a-form.md)
