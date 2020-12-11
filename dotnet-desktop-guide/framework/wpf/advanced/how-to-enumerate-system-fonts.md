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
# <a name="how-to-enumerate-system-fonts"></a><span data-ttu-id="ebb56-102">方法: システム フォントを列挙する</span><span class="sxs-lookup"><span data-stu-id="ebb56-102">How to: Enumerate System Fonts</span></span>
## <a name="example"></a><span data-ttu-id="ebb56-103">例</span><span class="sxs-lookup"><span data-stu-id="ebb56-103">Example</span></span>  
 <span data-ttu-id="ebb56-104">次の例では、システム フォント コレクション内のフォントを列挙する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="ebb56-104">The following example shows how to enumerate the fonts in the system font collection.</span></span> <span data-ttu-id="ebb56-105"><xref:System.Windows.Media.Fonts.SystemFontFamilies%2A> 内の各 <xref:System.Windows.Media.FontFamily> のフォント ファミリ名が、項目としてコンボ ボックスに追加されます。</span><span class="sxs-lookup"><span data-stu-id="ebb56-105">The font family name of each <xref:System.Windows.Media.FontFamily> within <xref:System.Windows.Media.Fonts.SystemFontFamilies%2A> is added as an item to a combo box.</span></span>  
  
 [!code-csharp[TextOverview#100](~/samples/snippets/csharp/VS_Snippets_Wpf/TextOverview/CSharp/Window1.xaml.cs#100)]
 [!code-vb[TextOverview#100](~/samples/snippets/visualbasic/VS_Snippets_Wpf/TextOverview/visualbasic/window1.xaml.vb#100)]  
  
 <span data-ttu-id="ebb56-106">同じフォント ファミリの複数のバージョンが同じディレクトリ内に存在する場合、[!INCLUDE[TLA#tla_winclient](../../../includes/tlasharptla-winclient-md.md)] フォント列挙体は、フォントの最新バージョンを返します。</span><span class="sxs-lookup"><span data-stu-id="ebb56-106">If multiple versions of the same font family reside in the same directory, the [!INCLUDE[TLA#tla_winclient](../../../includes/tlasharptla-winclient-md.md)] font enumeration returns the most recent version of the font.</span></span> <span data-ttu-id="ebb56-107">バージョン情報に解決策が用意されていない場合は、最新タイムスタンプが含まれるフォントが返されます。</span><span class="sxs-lookup"><span data-stu-id="ebb56-107">If the version information does not provide resolution, the font with latest timestamp is returned.</span></span> <span data-ttu-id="ebb56-108">タイムスタンプ情報が等しい場合は、最初はアルファベット順になっているフォント ファイルが返されます。</span><span class="sxs-lookup"><span data-stu-id="ebb56-108">If the timestamp information is equivalent, the font file that is first in alphabetical order is returned.</span></span>
