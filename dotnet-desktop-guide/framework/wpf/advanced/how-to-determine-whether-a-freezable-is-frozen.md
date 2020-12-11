---
title: '方法: Freezable が固定されているかどうかを判別する'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- Freezable objects [WPF], determining if frozen
ms.assetid: 92e58baa-ee12-4a9e-ac3a-ca458807a8b2
ms.openlocfilehash: 6a63862d35f2c40289ea6445eb3dab8a2abe4a61
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/09/2020
ms.locfileid: "96982883"
---
# <a name="how-to-determine-whether-a-freezable-is-frozen"></a>方法: Freezable が固定されているかどうかを判別する
この例では、<xref:System.Windows.Freezable> オブジェクトが固定されているかどうかを判別する方法を示します。 固定された <xref:System.Windows.Freezable> オブジェクトを変更しようとすると、<xref:System.InvalidOperationException> がスローされます。 この例外がスローされないようにするには、<xref:System.Windows.Freezable> オブジェクトの <xref:System.Windows.Freezable.IsFrozen%2A> プロパティを使用して、固定されているかどうかを判別します。  
  
## <a name="example"></a>例  
 次の例では、<xref:System.Windows.Media.SolidColorBrush> を固定し、<xref:System.Windows.Freezable.IsFrozen%2A> プロパティを使用してテストし、固定されているかどうかを判別します。  
  
 [!code-csharp[freezablesample_procedural#CheckIsFrozenExample](~/samples/snippets/csharp/VS_Snippets_Wpf/freezablesample_procedural/CSharp/freezablesample.cs#checkisfrozenexample)]
 [!code-vb[freezablesample_procedural#CheckIsFrozenExample](~/samples/snippets/visualbasic/VS_Snippets_Wpf/freezablesample_procedural/visualbasic/freezablesample.vb#checkisfrozenexample)]  
  
 <xref:System.Windows.Freezable> オブジェクトの詳細については、「[Freezable オブジェクトの概要](freezable-objects-overview.md)」を参照してください。  
  
## <a name="see-also"></a>関連項目

- <xref:System.Windows.Freezable>
- <xref:System.Windows.Freezable.IsFrozen%2A>
- [Freezable オブジェクトの概要](freezable-objects-overview.md)
- [方法トピック](base-elements-how-to-topics.md)
