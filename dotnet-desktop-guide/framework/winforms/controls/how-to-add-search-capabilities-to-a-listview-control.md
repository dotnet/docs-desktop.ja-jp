---
title: '方法: ListView コントロールに検索機能を追加する'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- lists [Windows Forms], enabling searching
- list views [Windows Forms], enabling searching
- ListView control [Windows Forms], adding search capabilities
- searching [Windows Forms], adding search capabilities to ListView control
ms.assetid: 557782d9-b705-4bab-b496-9938afddac82
ms.openlocfilehash: d5d4dae55fc9f0613ab6535b2fe57e262d0ef141
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/09/2020
ms.locfileid: "96982011"
---
# <a name="how-to-add-search-capabilities-to-a-listview-control"></a>方法: ListView コントロールに検索機能を追加する
多くの場合、コントロール内の項目の大きいリストを操作するときは、 <xref:System.Windows.Forms.ListView> ユーザーに検索機能を提供する必要があります。 コントロールは、 <xref:System.Windows.Forms.ListView> テキスト一致と位置検索という2つの異なる方法でこの機能を提供します。  
  
 メソッドを使用すると、 <xref:System.Windows.Forms.ListView.FindItemWithText%2A> <xref:System.Windows.Forms.ListView> 検索文字列およびオプションの開始インデックスと終了インデックスを指定して、リストまたは詳細ビューでテキスト検索を実行できます。 これに対し、メソッドを使用すると、 <xref:System.Windows.Forms.ListView.FindNearestItem%2A> <xref:System.Windows.Forms.ListView> x 座標と y 座標のセットと検索の方向を指定して、アイコンまたはタイルビュー内の項目を検索できます。  
  
### <a name="to-find-an-item-using-text"></a>テキストを使用して項目を検索するには  
  
1. プロパティを <xref:System.Windows.Forms.ListView> <xref:System.Windows.Forms.ListView.View%2A> またはに設定してを作成 <xref:System.Windows.Forms.View.Details> <xref:System.Windows.Forms.View.List> し、に <xref:System.Windows.Forms.ListView> 項目を設定します。  
  
2. <xref:System.Windows.Forms.ListView.FindItemWithText%2A>検索する項目のテキストを渡して、メソッドを呼び出します。  
  
3. 次のコード例では、基本的なを作成し、 <xref:System.Windows.Forms.ListView> それに項目を設定し、ユーザーからのテキスト入力を使用してリスト内の項目を検索する方法を示します。  
  
 [!code-cpp[System.Windows.Forms.ListViewFindItems#1](~/samples/snippets/cpp/VS_Snippets_Winforms/System.Windows.Forms.ListViewFindItems/cpp/form1.cpp#1)]
 [!code-csharp[System.Windows.Forms.ListViewFindItems#1](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.ListViewFindItems/CS/form1.cs#1)]
 [!code-vb[System.Windows.Forms.ListViewFindItems#1](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.ListViewFindItems/VB/form1.vb#1)]  
  
### <a name="to-find-an-item-using-x--and-y-coordinates"></a>X 座標と y 座標を使用して項目を検索するには  
  
1. プロパティを <xref:System.Windows.Forms.ListView> <xref:System.Windows.Forms.View> またはに設定してを作成 <xref:System.Windows.Forms.View.SmallIcon> <xref:System.Windows.Forms.View.LargeIcon> し、に <xref:System.Windows.Forms.ListView> 項目を設定します。  
  
2. <xref:System.Windows.Forms.ListView.FindNearestItem%2A>必要な x 座標と y 座標、および検索する方向を渡して、メソッドを呼び出します。  
  
3. 次のコード例では、基本的なアイコンを作成し <xref:System.Windows.Forms.ListView> 、それに項目を設定し、イベントをキャプチャして <xref:System.Windows.Forms.Control.MouseDown> 最も近い項目を上方向に検索する方法を示します。  
  
 [!code-cpp[System.Windows.Forms.ListViewFindItems#2](~/samples/snippets/cpp/VS_Snippets_Winforms/System.Windows.Forms.ListViewFindItems/cpp/form1.cpp#2)]
 [!code-csharp[System.Windows.Forms.ListViewFindItems#2](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.ListViewFindItems/CS/form1.cs#2)]
 [!code-vb[System.Windows.Forms.ListViewFindItems#2](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.ListViewFindItems/VB/form1.vb#2)]  
  
## <a name="see-also"></a>関連項目

- <xref:System.Windows.Forms.ListView>
- <xref:System.Windows.Forms.ListView.FindItemWithText%2A>
- <xref:System.Windows.Forms.ListView.FindNearestItem%2A>
- [ListView コントロール](listview-control-windows-forms.md)
- [ListView コントロールの概要](listview-control-overview-windows-forms.md)
- [方法: Windows フォーム ListView コントロールで項目を追加および削除する](how-to-add-and-remove-items-with-the-windows-forms-listview-control.md)
