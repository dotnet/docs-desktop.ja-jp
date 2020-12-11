---
title: '方法: XAML を使用してテーブルを定義する'
ms.date: 03/30/2017
helpviewer_keywords:
- XAML [WPF], defining tables
- documents [WPF], defining tables with XAML
- tables [WPF], defining with XAML
ms.assetid: 83f2dc58-437e-4cdc-b5dd-0019810c7a85
ms.openlocfilehash: 709e977670b867f6513bf166918d3bcba0a8c62c
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/09/2020
ms.locfileid: "96982648"
---
# <a name="how-to-define-a-table-with-xaml"></a>方法: XAML を使用してテーブルを定義する
次の例では、[!INCLUDE[TLA#tla_xaml](../../../includes/tlasharptla-xaml-md.md)] を使用して、<xref:System.Windows.Documents.Table> を定義する方法を示しています。  このテーブル例には、(<xref:System.Windows.Documents.TableColumn> によって表される) 4 つの列と (<xref:System.Windows.Documents.TableRow> によって表される) いくつかの行があります。それらには、データの他にタイトル、ヘッダー、およびフッター情報が含まれています。  行は <xref:System.Windows.Documents.TableRowGroup> 要素に含まれている必要があります。  テーブルの各行は、(<xref:System.Windows.Documents.TableCell> 要素によって表される) 1 つ以上のセルで構成されています。  テーブルのセルのコンテンツは、この場合は <xref:System.Windows.Documents.Paragraph> 要素である <xref:System.Windows.Documents.Block> 要素に含まれている必要があります。  このテーブルには、(<xref:System.Windows.Documents.Hyperlink> 要素によって表される) ハイパーリンクもフッター行にあります。  
  
## <a name="example"></a>例  
 [!code-xaml[TableSnippetsXAML#_TableXAML](~/samples/snippets/csharp/VS_Snippets_Wpf/TableSnippetsXAML/CS/Window1.xaml#_tablexaml)]  
  
 この例で定義したテーブルのレンダリング結果は、次の図のとおりです。  
  
 ![XAML で定義したテーブルのスクリーンショット。](./media/how-to-define-a-table-with-xaml/planetary-information-xaml-table.png)
