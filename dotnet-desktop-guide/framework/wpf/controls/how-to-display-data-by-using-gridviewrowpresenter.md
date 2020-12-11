---
title: '方法: GridViewRowPresenter を使用してデータを表示する'
ms.date: 03/30/2017
helpviewer_keywords:
- displaying data with GridViewRowPresenter [WPF]
- GridViewRowPresenter [WPF]
ms.assetid: bdb785a5-a262-44d5-a517-ea14383e5f70
ms.openlocfilehash: 0e471df3ab6fd10417fc58ece4cdb8ff1c457c95
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/09/2020
ms.locfileid: "96985140"
---
# <a name="how-to-display-data-by-using-gridviewrowpresenter"></a>方法: GridViewRowPresenter を使用してデータを表示する
この例では、<xref:System.Windows.Controls.GridViewRowPresenter> オブジェクトと <xref:System.Windows.Controls.GridViewHeaderRowPresenter> オブジェクトを使用し、列にデータを表示する方法を示します。  
  
## <a name="example"></a>例  
 次の例では、<xref:System.Windows.Controls.GridViewRowPresenter> オブジェクトと <xref:System.Windows.Controls.GridViewHeaderRowPresenter> オブジェクトを利用し、<xref:System.DateTime> オブジェクトの <xref:System.DateTime.DayOfWeek%2A> と <xref:System.DateTime.Year%2A> を表示する <xref:System.Windows.Controls.GridViewColumnCollection> を指定する方法を示します。 この例では、<xref:System.Windows.Controls.GridViewColumn> の <xref:System.Windows.Controls.GridViewColumn.Header%2A> に <xref:System.Windows.Style> も定義されます。  
  
 [!code-xaml[GridViewRowPresenterSample#GridViewRowPresenter](~/samples/snippets/csharp/VS_Snippets_Wpf/GridViewRowPresenterSample/CS/Window1.xaml#gridviewrowpresenter)]  
  
## <a name="see-also"></a>関連項目

- <xref:System.Windows.Controls.GridViewHeaderRowPresenter>
- <xref:System.Windows.Controls.GridViewRowPresenter>
- <xref:System.Windows.Controls.GridViewColumnCollection>
- [GridView の概要](gridview-overview.md)
