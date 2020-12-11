---
title: '方法: グラデーションでシステム カラーを使用する'
ms.date: 03/30/2017
helpviewer_keywords:
- gradients [WPF], system colors in
- system colors in gradients [WPF]
ms.assetid: 11942e7e-6300-4b50-8ed1-f50e8d20e7d2
ms.openlocfilehash: 55c99640907a0c372f8c7bbc50b9b45c9f15ef3c
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/09/2020
ms.locfileid: "96983364"
---
# <a name="how-to-use-system-colors-in-a-gradient"></a>方法: グラデーションでシステム カラーを使用する
グラデーションでシステムカラーを使用するには、 *\<SystemColor>* クラスの color および *\<SystemColor>* colorkey 静的プロパティを使用して、 <xref:System.Windows.SystemColors> 色への参照を取得し *\<SystemColor>* ます。ここで、は目的のシステムカラーの名前です。 *\<SystemColor>* システムテーマの変更に応じて自動的に更新される動的参照を作成する場合は、colorkey プロパティを使用します。 それ以外の場合は、色のプロパティを使用し *\<SystemColor>* ます。  
  
## <a name="example"></a>例  
 次の例では、動的なシステム カラー リソースを使用して、グラデーションを作成します。  
  
 [!code-xaml[brushsamples_snip#GraphicsMMDynamicSystemColorGradientExampleWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/brushsamples_snip/CS/DynamicSystemColorExample.xaml#graphicsmmdynamicsystemcolorgradientexamplewholepage)]  
  
 次の例では、静的なシステム カラー リソースを使用して、グラデーションを作成します。  
  
 [!code-xaml[brushsamples_snip#GraphicsMMStaticSystemColorGradientExampleWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/brushsamples_snip/CS/StaticSystemColorExample.xaml#graphicsmmstaticsystemcolorgradientexamplewholepage)]  
  
## <a name="see-also"></a>関連項目

- <xref:System.Windows.SystemColors>
- [システム ブラシで領域を塗りつぶす](how-to-paint-an-area-with-a-system-brush.md)
- [純色およびグラデーションによる塗りつぶしの概要](painting-with-solid-colors-and-gradients-overview.md)
