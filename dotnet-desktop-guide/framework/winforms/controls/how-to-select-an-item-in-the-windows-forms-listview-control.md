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
# <a name="how-to-select-an-item-in-the-windows-forms-listview-control"></a><span data-ttu-id="f0381-102">方法: Windows フォーム ListView コントロール内の項目を選択する</span><span class="sxs-lookup"><span data-stu-id="f0381-102">How to: Select an Item in the Windows Forms ListView Control</span></span>
<span data-ttu-id="f0381-103">この例では、Windows フォームコントロール内の項目をプログラムで選択する方法を示し <xref:System.Windows.Forms.ListView> ます。</span><span class="sxs-lookup"><span data-stu-id="f0381-103">This example demonstrates how to programmatically select an item in a Windows Forms <xref:System.Windows.Forms.ListView> control.</span></span> <span data-ttu-id="f0381-104">プログラムによって項目を選択しても、コントロールにフォーカスが自動的に変更されることはありません <xref:System.Windows.Forms.ListView> 。</span><span class="sxs-lookup"><span data-stu-id="f0381-104">Selecting an item programmatically does not automatically change the focus to the <xref:System.Windows.Forms.ListView> control.</span></span> <span data-ttu-id="f0381-105">このため、通常は項目を選択するときに項目をフォーカスとして設定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="f0381-105">For this reason, you will typically also want to set the item as focused when selecting an item.</span></span>  
  
## <a name="example"></a><span data-ttu-id="f0381-106">例</span><span class="sxs-lookup"><span data-stu-id="f0381-106">Example</span></span>  
 [!code-csharp[System.Windows.Forms.ListView.Misc#1](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.ListView.Misc/CS/form1.cs#1)]
 [!code-vb[System.Windows.Forms.ListView.Misc#1](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.ListView.Misc/VB/form1.vb#1)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="f0381-107">コードのコンパイル</span><span class="sxs-lookup"><span data-stu-id="f0381-107">Compiling the Code</span></span>  
 <span data-ttu-id="f0381-108">この例で必要な要素は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="f0381-108">This example requires:</span></span>  
  
- <span data-ttu-id="f0381-109"><xref:System.Windows.Forms.ListView>少なくとも1つの項目を含むという名前のコントロール `listView1` 。</span><span class="sxs-lookup"><span data-stu-id="f0381-109">A <xref:System.Windows.Forms.ListView> control named `listView1` that contains at least one item.</span></span>  
  
- <span data-ttu-id="f0381-110"><xref:System?displayProperty=nameWithType> 名前空間と <xref:System.Windows.Forms?displayProperty=nameWithType> 名前空間への参照。</span><span class="sxs-lookup"><span data-stu-id="f0381-110">References to the <xref:System?displayProperty=nameWithType> and <xref:System.Windows.Forms?displayProperty=nameWithType> namespaces.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f0381-111">関連項目</span><span class="sxs-lookup"><span data-stu-id="f0381-111">See also</span></span>

- <xref:System.Windows.Forms.ListView>
- <xref:System.Windows.Forms.ListViewItem.Selected%2A?displayProperty=nameWithType>
