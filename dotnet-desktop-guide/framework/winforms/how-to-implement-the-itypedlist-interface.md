---
title: '方法: ITypedList インターフェイスを実装する'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- ITypedList interface
- BindingList(Of T) class
- data binding [Windows Forms], implementing
- IBindingList interface
ms.assetid: 834cc15c-50bc-4a8b-a610-313d6a217357
ms.openlocfilehash: 3f5a5032166087c7398d310071b3998c845e2780
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/09/2020
ms.locfileid: "96983176"
---
# <a name="how-to-implement-the-itypedlist-interface"></a><span data-ttu-id="5e311-102">方法: ITypedList インターフェイスを実装する</span><span class="sxs-lookup"><span data-stu-id="5e311-102">How to: Implement the ITypedList Interface</span></span>
<span data-ttu-id="5e311-103">インターフェイスを実装して、 <xref:System.ComponentModel.ITypedList> バインド可能なリストのスキーマを検出できるようにします。</span><span class="sxs-lookup"><span data-stu-id="5e311-103">Implement the <xref:System.ComponentModel.ITypedList> interface to enable discovery of the schema for a bindable list.</span></span>  
  
## <a name="example"></a><span data-ttu-id="5e311-104">例</span><span class="sxs-lookup"><span data-stu-id="5e311-104">Example</span></span>  
 <span data-ttu-id="5e311-105">次のコード例は、インターフェイスを実装する方法を示して <xref:System.ComponentModel.ITypedList> います。</span><span class="sxs-lookup"><span data-stu-id="5e311-105">The following code example demonstrates how to implement the <xref:System.ComponentModel.ITypedList> interface.</span></span> <span data-ttu-id="5e311-106">という名前のジェネリック型は、 `SortableBindingList` クラスから派生 <xref:System.ComponentModel.BindingList%601> し、インターフェイスを実装し <xref:System.ComponentModel.ITypedList> ます。</span><span class="sxs-lookup"><span data-stu-id="5e311-106">A generic type named `SortableBindingList` derives from the <xref:System.ComponentModel.BindingList%601> class and implements the <xref:System.ComponentModel.ITypedList> interface.</span></span> <span data-ttu-id="5e311-107">という名前の単純なクラスは、 `Customer` コントロールのヘッダーにバインドされたデータを提供し <xref:System.Windows.Forms.DataGridView> ます。</span><span class="sxs-lookup"><span data-stu-id="5e311-107">A simple class named `Customer` provides data, which is bound to the header of a <xref:System.Windows.Forms.DataGridView> control.</span></span>  
  
 [!code-csharp[System.ComponentModel.ITypedList#1](~/samples/snippets/csharp/VS_Snippets_Winforms/System.ComponentModel.ITypedList/CS/SortableBindingList.cs#1)]
 [!code-vb[System.ComponentModel.ITypedList#1](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.ComponentModel.ITypedList/VB/SortableBindingList.vb#1)]  
  
 [!code-csharp[System.ComponentModel.ITypedList#10](~/samples/snippets/csharp/VS_Snippets_Winforms/System.ComponentModel.ITypedList/CS/Customer.cs#10)]
 [!code-vb[System.ComponentModel.ITypedList#10](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.ComponentModel.ITypedList/VB/Customer.vb#10)]  
  
 [!code-csharp[System.ComponentModel.ITypedList#100](~/samples/snippets/csharp/VS_Snippets_Winforms/System.ComponentModel.ITypedList/CS/Form1.cs#100)]
 [!code-vb[System.ComponentModel.ITypedList#100](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.ComponentModel.ITypedList/VB/Form1.vb#100)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="5e311-108">コードのコンパイル</span><span class="sxs-lookup"><span data-stu-id="5e311-108">Compiling the Code</span></span>  
 <span data-ttu-id="5e311-109">この例で必要な要素は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="5e311-109">This example requires:</span></span>  
  
- <span data-ttu-id="5e311-110">System.Drawing アセンブリおよび System.Windows.Forms アセンブリへの参照。</span><span class="sxs-lookup"><span data-stu-id="5e311-110">References to the System.Drawing and System.Windows.Forms assemblies.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5e311-111">関連項目</span><span class="sxs-lookup"><span data-stu-id="5e311-111">See also</span></span>

- <xref:System.ComponentModel.ITypedList>
- <xref:System.ComponentModel.BindingList%601>
- <xref:System.ComponentModel.IBindingList>
- [<span data-ttu-id="5e311-112">データ連結と Windows フォーム</span><span class="sxs-lookup"><span data-stu-id="5e311-112">Data Binding and Windows Forms</span></span>](data-binding-and-windows-forms.md)
