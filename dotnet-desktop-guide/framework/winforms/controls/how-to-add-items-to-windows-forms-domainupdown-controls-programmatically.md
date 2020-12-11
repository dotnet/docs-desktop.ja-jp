---
title: DomainUpDown コントロールにプログラムで項目を追加する
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- spin button control [Windows Forms], adding items
- DomainUpDown control [Windows Forms], adding items to
ms.assetid: fd31d314-33eb-4181-90f8-d32ed0c4e072
ms.openlocfilehash: 2e9f51fa051bf9b62e95f289db97bffd83450036
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/09/2020
ms.locfileid: "96982019"
---
# <a name="how-to-add-items-to-windows-forms-domainupdown-controls-programmatically"></a>方法 : Windows フォーム DomainUpDown コントロールにプログラムで項目を追加する
コード内の Windows フォームコントロールに項目を追加でき <xref:System.Windows.Forms.DomainUpDown> ます。 <xref:System.Windows.Forms.DomainUpDown.DomainUpDownItemCollection.Add%2A>クラスのメソッドまたはメソッドを呼び出して <xref:System.Windows.Forms.DomainUpDown.DomainUpDownItemCollection.Insert%2A> <xref:System.Windows.Forms.DomainUpDown.DomainUpDownItemCollection> 、コントロールのプロパティに項目を追加し <xref:System.Windows.Forms.DomainUpDown.Items%2A> ます。 メソッドは、 <xref:System.Windows.Forms.DomainUpDown.DomainUpDownItemCollection.Add%2A> コレクションの末尾に項目を追加し <xref:System.Windows.Forms.DomainUpDown.DomainUpDownItemCollection.Insert%2A> ます。メソッドは、指定した位置に項目を追加します。  
  
### <a name="to-add-a-new-item"></a>新しい項目を追加するには  
  
1. 項目 <xref:System.Windows.Forms.DomainUpDown.DomainUpDownItemCollection.Add%2A> の一覧の末尾に項目を追加するには、メソッドを使用します。  
  
    ```vb  
    DomainUpDown1.Items.Add("noodles")  
    ```  
  
    ```csharp  
    domainUpDown1.Items.Add("noodles");  
    ```  
  
    ```cpp  
    domainUpDown1->Items->Add("noodles");  
    ```  
  
     または  
  
2. <xref:System.Windows.Forms.DomainUpDown.DomainUpDownItemCollection.Insert%2A>リスト内の指定した位置に項目を挿入するには、メソッドを使用します。  
  
    ```vb  
    ' Inserts an item at the third position in the list  
    DomainUpDown1.Items.Insert(2, "rice")  
    ```  
  
    ```csharp  
    // Inserts an item at the third position in the list  
    domainUpDown1.Items.Insert(2, "rice");  
    ```  
  
    ```cpp  
    // Inserts an item at the third position in the list  
    domainUpDown1->Items->Insert(2, "rice");  
    ```  
  
## <a name="see-also"></a>関連項目

- <xref:System.Windows.Forms.DomainUpDown>
- <xref:System.Windows.Forms.DomainUpDown.DomainUpDownItemCollection.Add%2A?displayProperty=nameWithType>
- <xref:System.Collections.ArrayList.Insert%2A?displayProperty=nameWithType>
- [DomainUpDown コントロール](domainupdown-control-windows-forms.md)
- [DomainUpDown コントロールの概要](domainupdown-control-overview-windows-forms.md)
