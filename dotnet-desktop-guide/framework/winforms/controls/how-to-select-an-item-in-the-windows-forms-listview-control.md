---
title: ListView コントロール内の項目を選択します
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- lists [Windows Forms], selecting items
- ListView control [Windows Forms], selecting items
- selection [Windows Forms], in list views
- list views [Windows Forms], selecting items
ms.assetid: ddea918e-1ddf-47f4-bd09-1e9b4c9d0c39
ms.openlocfilehash: 57e985af9d0347510d7d7782f68d5b414d36e077
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/09/2020
ms.locfileid: "96974746"
---
# <a name="how-to-select-an-item-in-the-windows-forms-listview-control"></a>方法: Windows フォーム ListView コントロール内の項目を選択する
この例では、Windows フォームコントロール内の項目をプログラムで選択する方法を示し <xref:System.Windows.Forms.ListView> ます。 プログラムによって項目を選択しても、コントロールにフォーカスが自動的に変更されることはありません <xref:System.Windows.Forms.ListView> 。 このため、通常は項目を選択するときに項目をフォーカスとして設定する必要があります。  
  
## <a name="example"></a>例  
 [!code-csharp[System.Windows.Forms.ListView.Misc#1](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.ListView.Misc/CS/form1.cs#1)]
 [!code-vb[System.Windows.Forms.ListView.Misc#1](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.ListView.Misc/VB/form1.vb#1)]  
  
## <a name="compiling-the-code"></a>コードのコンパイル  
 この例で必要な要素は次のとおりです。  
  
- <xref:System.Windows.Forms.ListView>少なくとも1つの項目を含むという名前のコントロール `listView1` 。  
  
- <xref:System?displayProperty=nameWithType> 名前空間と <xref:System.Windows.Forms?displayProperty=nameWithType> 名前空間への参照。  
  
## <a name="see-also"></a>関連項目

- <xref:System.Windows.Forms.ListView>
- <xref:System.Windows.Forms.ListViewItem.Selected%2A?displayProperty=nameWithType>
