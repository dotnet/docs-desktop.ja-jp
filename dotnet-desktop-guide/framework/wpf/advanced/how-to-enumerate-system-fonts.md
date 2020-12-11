---
title: '方法: システム フォントを列挙する'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- typography [WPF], enumerating system fonts
- fonts [WPF], enumerating
- system fonts [WPF], enumerating
- enumerating [WPF], system fonts
ms.assetid: 36e37791-55b9-4f01-a496-5cc10335e6a6
ms.openlocfilehash: 7ea16afa12233ad5f8268ec048bed187f6081299
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/09/2020
ms.locfileid: "96983791"
---
# <a name="how-to-enumerate-system-fonts"></a>方法: システム フォントを列挙する
## <a name="example"></a>例  
 次の例では、システム フォント コレクション内のフォントを列挙する方法を示します。 <xref:System.Windows.Media.Fonts.SystemFontFamilies%2A> 内の各 <xref:System.Windows.Media.FontFamily> のフォント ファミリ名が、項目としてコンボ ボックスに追加されます。  
  
 [!code-csharp[TextOverview#100](~/samples/snippets/csharp/VS_Snippets_Wpf/TextOverview/CSharp/Window1.xaml.cs#100)]
 [!code-vb[TextOverview#100](~/samples/snippets/visualbasic/VS_Snippets_Wpf/TextOverview/visualbasic/window1.xaml.vb#100)]  
  
 同じフォント ファミリの複数のバージョンが同じディレクトリ内に存在する場合、[!INCLUDE[TLA#tla_winclient](../../../includes/tlasharptla-winclient-md.md)] フォント列挙体は、フォントの最新バージョンを返します。 バージョン情報に解決策が用意されていない場合は、最新タイムスタンプが含まれるフォントが返されます。 タイムスタンプ情報が等しい場合は、最初はアルファベット順になっているフォント ファイルが返されます。
