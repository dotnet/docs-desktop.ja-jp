---
title: '方法: データを移動する'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- cursors [Windows Forms], data sources
- data sources [Windows Forms], Windows Forms
- Windows Forms, navigating
- CurrencyManager class [Windows Forms], navigating Windows Forms data
- data [Windows Forms], navigating
ms.assetid: 97360f7b-b181-4084-966a-4c62518f735b
ms.openlocfilehash: 2dd900b652b0ff21ea0eb0dbc5463b22c869ec7c
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/09/2020
ms.locfileid: "96983287"
---
# <a name="how-to-navigate-data-in-windows-forms"></a>方法: Windows フォームでデータ間を移動する
Windows アプリケーションでは、データソース内のレコード間を移動する最も簡単な方法は、 <xref:System.Windows.Forms.BindingSource> コンポーネントをデータソースにバインドしてから、コントロールをにバインドすることです <xref:System.Windows.Forms.BindingSource> 。 その後、、、およびの組み込みナビゲーションメソッドを使用でき <xref:System.Windows.Forms.BindingSource> <xref:System.Windows.Forms.BindingSource.MoveNext%2A> <xref:System.Windows.Forms.BindingSource.MoveLast%2A> <xref:System.Windows.Forms.BindingSource.MovePrevious%2A> <xref:System.Windows.Forms.BindingSource.MoveFirst%2A> ます。 これらのメソッドを使用する <xref:System.Windows.Forms.BindingSource.Position%2A> と <xref:System.Windows.Forms.BindingSource.Current%2A> 、のプロパティとプロパティが適切に調整され <xref:System.Windows.Forms.BindingSource> ます。 また、プロパティを設定して、項目を検索し、現在の項目として設定することもでき <xref:System.Windows.Forms.BindingSource.Position%2A> ます。  
  
### <a name="to-increment-the-position-in-a-data-source"></a>データソース内の位置をインクリメントするには  
  
1. バインドされたデータののプロパティを、移動先の <xref:System.Windows.Forms.BindingSource.Position%2A> <xref:System.Windows.Forms.BindingSource> レコード位置に設定します。 をクリックしたときに、のメソッドを使用してプロパティをインクリメントする例を次に示し <xref:System.Windows.Forms.BindingSource.MoveNext%2A> <xref:System.Windows.Forms.BindingSource> <xref:System.Windows.Forms.BindingSource.Position%2A> `nextButton` ます。 は、 <xref:System.Windows.Forms.BindingSource> `Customers` データセットのテーブルに関連付けられてい `Northwind` ます。  
  
    > [!NOTE]
    > この <xref:System.Windows.Forms.BindingSource.Position%2A> プロパティを最初または最後のレコードを超えた値に設定しても、エラーは発生しません。 .NET Framework では、リストの範囲外の値に位置を設定することができないためです。 最初または最後のレコードがなくなったかどうかを確認するためにアプリケーションで重要な場合は、データ要素数を超えるかどうかをテストするロジックを含めます。  
  
     [!code-csharp[System.Windows.Forms.NavigatingData#4](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.NavigatingData/CS/Form1.cs#4)]
     [!code-vb[System.Windows.Forms.NavigatingData#4](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.NavigatingData/VB/Form1.vb#4)]  
  
### <a name="to-check-whether-you-have-passed-the-end-or-beginning"></a>終了を超えたかどうかを確認するには  
  
1. <xref:System.Windows.Forms.BindingSource.PositionChanged> イベントのイベント ハンドラーを作成します。 ハンドラーでは、提案された位置の値が実際のデータ要素数を超えたかどうかをテストできます。  
  
     次の例は、最後のデータ要素に到達したかどうかをテストする方法を示しています。 この例では、最後の要素にある場合、フォームの [ **次へ** ] ボタンは無効になっています。  
  
    > [!NOTE]
    > コード内で移動するリストを変更する場合は、ユーザーが新しいリストの長さ全体を参照できるように、 **[次へ** ] ボタンを再度有効にする必要があることに注意してください。 また、使用して <xref:System.Windows.Forms.BindingSource.PositionChanged> いる特定ののイベントが <xref:System.Windows.Forms.BindingSource> イベント処理メソッドに関連付けられている必要があることに注意してください。 イベントを処理するメソッドの例を次に示し <xref:System.Windows.Forms.BindingSource.PositionChanged> ます。  
  
     [!code-csharp[System.Windows.Forms.NavigatingData#3](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.NavigatingData/CS/Form1.cs#3)]
     [!code-vb[System.Windows.Forms.NavigatingData#3](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.NavigatingData/VB/Form1.vb#3)]  
  
### <a name="to-find-an-item-and-set-it-as-the-current-item"></a>項目を検索して現在の項目として設定するには  
  
1. 現在のアイテムとして設定するレコードを探します。 <xref:System.Windows.Forms.BindingSource.Find%2A> <xref:System.Windows.Forms.BindingSource> データソースがを実装している場合は、のメソッドを使用してこれを行うことができ <xref:System.ComponentModel.IBindingList> ます。 を実装するデータソースの例 <xref:System.ComponentModel.IBindingList> <xref:System.ComponentModel.BindingList%601> として、とがあり <xref:System.Data.DataView> ます。  
  
     [!code-csharp[System.Windows.Forms.NavigatingData#2](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.NavigatingData/CS/Form1.cs#2)]
     [!code-vb[System.Windows.Forms.NavigatingData#2](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.NavigatingData/VB/Form1.vb#2)]  
  
## <a name="see-also"></a>関連項目

- [Windows フォームがサポートするデータ ソース](data-sources-supported-by-windows-forms.md)
- [Windows フォーム データ バインディングの変更通知](change-notification-in-windows-forms-data-binding.md)
- [データ連結と Windows フォーム](data-binding-and-windows-forms.md)
- [Windows フォームでのデータ バインディング](windows-forms-data-binding.md)
