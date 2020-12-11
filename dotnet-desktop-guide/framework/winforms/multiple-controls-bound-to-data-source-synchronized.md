---
title: '方法: 複数のコントロールを 1 つのデータ ソースにバインドして同期状態を保つ'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- controls [Windows Forms], binding multiple
- controls [Windows Forms], synchronizing with data source
ms.assetid: c2f0ecc6-11e6-4c2c-a1ca-0759630c451e
ms.openlocfilehash: 8a39c50bfc452c807a18a9bf0a65e56cb75d20aa
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/09/2020
ms.locfileid: "96974340"
---
# <a name="how-to-ensure-multiple-controls-bound-to-the-same-data-source-remain-synchronized"></a>方法: 複数のコントロールを 1 つのデータ ソースにバインドして同期状態を保つ
Windows フォームでデータバインディングを使用する場合、複数のコントロールが同じデータソースにバインドされることがよくあります。 場合によっては、コントロールのバインドされたプロパティが相互に同期していることを確認するために、追加の手順を実行する必要があります。 これらの手順は、次の2つの状況で必要になります。  
  
- データソースが <xref:System.ComponentModel.IBindingList> を実装しておらず、 <xref:System.ComponentModel.IBindingList.ListChanged> 型のイベントを生成する場合は <xref:System.ComponentModel.ListChangedType.ItemChanged> 。  
  
- データソースがを実装している場合は <xref:System.ComponentModel.IEditableObject> 。  
  
 前者の場合は、を使用して、 <xref:System.Windows.Forms.BindingSource> データソースをコントロールにバインドできます。 後者の場合、を使用して <xref:System.Windows.Forms.BindingSource> イベントを処理 <xref:System.Windows.Forms.BindingSource.BindingComplete> し、 <xref:System.Windows.Forms.BindingManagerBase.EndCurrentEdit%2A> 関連付けられているでを呼び出し <xref:System.Windows.Forms.BindingManagerBase> ます。  
  
## <a name="example"></a>例  
 次のコード例では、コンポーネントを使用して、3つのコントロール (2 つのテキストボックスコントロールと <xref:System.Windows.Forms.DataGridView> コントロール) を内の同じ列にバインドする方法を示し <xref:System.Data.DataSet> <xref:System.Windows.Forms.BindingSource> ます。 この例では、イベントを処理し、 <xref:System.Windows.Forms.BindingSource.BindingComplete> 1 つのテキストボックスのテキスト値が変更されたときに、追加のテキストボックスと <xref:System.Windows.Forms.DataGridView> コントロールが正しい値で更新されるようにする方法を示します。  
  
 この例では、を使用して、 <xref:System.Windows.Forms.BindingSource> データソースとコントロールをバインドします。 または、コントロールを直接データソースにバインドし、 <xref:System.Windows.Forms.BindingManagerBase> フォームのからバインドのを取得して、のイベントを処理することもでき <xref:System.Windows.Forms.Control.BindingContext%2A> <xref:System.Windows.Forms.BindingManagerBase.BindingComplete> <xref:System.Windows.Forms.BindingManagerBase> ます。 これを行う方法の例については、のイベントに関するヘルプページを参照してください <xref:System.Windows.Forms.BindingManagerBase.BindingComplete> <xref:System.Windows.Forms.BindingManagerBase> 。  
  
 [!code-csharp[System.Windows.Forms.BindingSourceMultipleControls#1](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.BindingSourceMultipleControls/CS/Form1.cs#1)]
 [!code-vb[System.Windows.Forms.BindingSourceMultipleControls#1](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.BindingSourceMultipleControls/VB/Form1.vb#1)]  
  
## <a name="compiling-the-code"></a>コードのコンパイル  
  
- このコード例では、  
  
- <xref:System>、<xref:System.Windows.Forms>、および <xref:System.Drawing> の各アセンブリへの参照。  
  
- イベントが処理されたフォーム <xref:System.Windows.Forms.Form.Load> と、 `InitializeControlsAndDataSource` フォームのイベントハンドラーからの例のメソッドの呼び出し <xref:System.Windows.Forms.Form.Load> 。  
  
## <a name="see-also"></a>関連項目

- [方法: BindingSource コンポーネントを使用してフォーム間でバインド データを共有する](./controls/how-to-share-bound-data-across-forms-using-the-bindingsource-component.md)
- [Windows フォーム データ バインディングの変更通知](change-notification-in-windows-forms-data-binding.md)
- [データ連結に関連するインターフェイス](interfaces-related-to-data-binding.md)
- [Windows フォームでのデータ バインディング](windows-forms-data-binding.md)
