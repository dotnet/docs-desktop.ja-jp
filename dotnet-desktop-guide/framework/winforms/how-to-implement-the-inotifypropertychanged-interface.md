---
title: '方法: INotifyPropertyChanged インターフェイスを実装する'
description: Windows フォームデータバインディングで使用されるビジネスオブジェクトに INotifyPropertyChanged インターフェイスを実装する方法について説明します。
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- INotifyPropertyChanged interface [Windows Forms], implementing
ms.assetid: eac428af-b43b-46ac-80d9-1a5f88658725
ms.openlocfilehash: 83d2ef32787d2dbcd877bc77dcede10111098f8a
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/09/2020
ms.locfileid: "96982403"
---
# <a name="how-to-implement-the-inotifypropertychanged-interface"></a><span data-ttu-id="07001-103">方法: INotifyPropertyChanged インターフェイスを実装する</span><span class="sxs-lookup"><span data-stu-id="07001-103">How to: Implement the INotifyPropertyChanged Interface</span></span>
<span data-ttu-id="07001-104">次のコード例は、インターフェイスを実装する方法を示して <xref:System.ComponentModel.INotifyPropertyChanged> います。</span><span class="sxs-lookup"><span data-stu-id="07001-104">The following code example demonstrates how to implement the <xref:System.ComponentModel.INotifyPropertyChanged> interface.</span></span> <span data-ttu-id="07001-105">Windows フォームデータバインディングで使用されるビジネスオブジェクトにこのインターフェイスを実装します。</span><span class="sxs-lookup"><span data-stu-id="07001-105">Implement this interface on business objects that are used in Windows Forms data binding.</span></span> <span data-ttu-id="07001-106">実装されている場合、インターフェイスは、ビジネスオブジェクトのプロパティの変更をバインドされたコントロールと通信します。</span><span class="sxs-lookup"><span data-stu-id="07001-106">When implemented, the interface  communicates to a bound control the property changes on a business object.</span></span>  
  
## <a name="example"></a><span data-ttu-id="07001-107">例</span><span class="sxs-lookup"><span data-stu-id="07001-107">Example</span></span>  
 [!code-csharp[System.ComponentModel.IPropertyChangeExample#1](~/samples/snippets/csharp/VS_Snippets_Winforms/System.ComponentModel.IPropertyChangeExample/CS/Form1.cs#1)]
 [!code-vb[System.ComponentModel.IPropertyChangeExample#1](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.ComponentModel.IPropertyChangeExample/VB/Form1.vb#1)]  
  
## <a name="see-also"></a><span data-ttu-id="07001-108">関連項目</span><span class="sxs-lookup"><span data-stu-id="07001-108">See also</span></span>

- [<span data-ttu-id="07001-109">方法: PropertyNameChanged パターンを適用する</span><span class="sxs-lookup"><span data-stu-id="07001-109">How to: Apply the PropertyNameChanged Pattern</span></span>](how-to-apply-the-propertynamechanged-pattern.md)
- [<span data-ttu-id="07001-110">Windows フォームでのデータ バインディング</span><span class="sxs-lookup"><span data-stu-id="07001-110">Windows Forms Data Binding</span></span>](windows-forms-data-binding.md)
- [<span data-ttu-id="07001-111">方法: BindingSource と INotifyPropertyChanged の各インターフェイスを使用して変更通知を発生させる</span><span class="sxs-lookup"><span data-stu-id="07001-111">How to: Raise Change Notifications Using a BindingSource and the INotifyPropertyChanged Interface</span></span>](./controls/raise-change-notifications--bindingsource.md)
- [<span data-ttu-id="07001-112">Windows フォーム データ バインディングの変更通知</span><span class="sxs-lookup"><span data-stu-id="07001-112">Change Notification in Windows Forms Data Binding</span></span>](change-notification-in-windows-forms-data-binding.md)
