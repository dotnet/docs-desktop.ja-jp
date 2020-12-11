---
title: ListView コントロールのアイコンを表示する
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- ListView control [Windows Forms], displaying icons
- icons [Windows Forms], displaying for ListView controls
- lists [Windows Forms], displaying icons
- ImageList component [Windows Forms], with ListView control
- list views [Windows Forms], displaying icons
ms.assetid: 9d577542-8595-429b-99e5-078770ec9d35
ms.openlocfilehash: 5fc54c448dae95cab50cdafa8403769fb421dffa
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/09/2020
ms.locfileid: "96980839"
---
# <a name="how-to-display-icons-for-the-windows-forms-listview-control"></a>方法: Windows フォーム ListView コントロールのアイコンを表示する
Windows フォームコントロールでは、 <xref:System.Windows.Forms.ListView> 3 つのイメージリストのアイコンを表示できます。 List、Details、および SmallIcon の各ビューには、プロパティで指定したイメージリストのイメージが表示され <xref:System.Windows.Forms.ListView.SmallImageList%2A> ます。 LargeIcon ビューには、プロパティで指定されたイメージリストのイメージが表示され <xref:System.Windows.Forms.ListView.LargeImageList%2A> ます。 リストビューでは、大きいアイコンまたは小さいアイコンの横にある、プロパティに設定された追加のアイコンのセットを表示することもでき <xref:System.Windows.Forms.ListView.StateImageList%2A> ます。 イメージリストの詳細については、「 [Imagelist コンポーネント](imagelist-component-windows-forms.md) 」および「 [方法: Windows フォーム imagelist コンポーネントを使用してイメージを追加または削除する](how-to-add-or-remove-images-with-the-windows-forms-imagelist-component.md)」を参照してください。  
  
### <a name="to-display-images-in-a-list-view"></a>リストビューに画像を表示するには  
  
1. 適切なプロパティ ( <xref:System.Windows.Forms.ListView.SmallImageList%2A> 、 <xref:System.Windows.Forms.ListView.LargeImageList%2A> 、または <xref:System.Windows.Forms.ListView.StateImageList%2A> ) を、使用する既存のコンポーネントに設定し <xref:System.Windows.Forms.ImageList> ます。  
  
     これらのプロパティは、デザイナーでプロパティウィンドウまたはコードで設定できます。  
  
     [!code-csharp[System.Windows.Forms.ListViewLegacyTopics#41](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.ListViewLegacyTopics/CS/Class1.cs#41)]
     [!code-vb[System.Windows.Forms.ListViewLegacyTopics#41](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.ListViewLegacyTopics/VB/Class1.vb#41)]  
  
2. <xref:System.Windows.Forms.ListViewItem.ImageIndex%2A> <xref:System.Windows.Forms.ListViewItem.StateImageIndex%2A> アイコンが関連付けられている各リスト項目のプロパティまたはプロパティを設定します。  
  
     これらのプロパティは、コードで設定することも、 **ListViewItem Collection エディター** 内で設定することもできます。 **ListViewItem Collection エディター** を開くには、[ ![ ](./media/visual-studio-ellipsis-button.png) <xref:System.Windows.Forms.ListView.Items%2A> **プロパティ**] ウィンドウのプロパティの横にある省略記号ボタン ([...] プロパティウィンドウ) をクリックします。  
  
     [!code-csharp[System.Windows.Forms.ListViewLegacyTopics#42](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.ListViewLegacyTopics/CS/Class1.cs#42)]
     [!code-vb[System.Windows.Forms.ListViewLegacyTopics#42](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.ListViewLegacyTopics/VB/Class1.vb#42)]  
  
## <a name="see-also"></a>関連項目

- [ListView コントロールの概要](listview-control-overview-windows-forms.md)
- [方法: Windows フォーム ListView コントロールで項目を追加および削除する](how-to-add-and-remove-items-with-the-windows-forms-listview-control.md)
- [方法: Windows フォーム ListView コントロールに列を追加する](how-to-add-columns-to-the-windows-forms-listview-control.md)
- [方法: TreeView コントロールまたは ListView コントロール (Windows フォーム) にカスタム情報を追加する](add-custom-information-to-a-treeview-or-listview-control-wf.md)
- [ImageList コンポーネント](imagelist-component-windows-forms.md)
