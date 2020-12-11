---
title: '方法: オブジェクトをマウス ポインターに追従させる'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- following the mouse pointer (cursor)
- mouse pointer (cursor), making objects follow
- cursor (mouse pointer), making objects follow
ms.assetid: 50b20415-14bc-405c-baf3-2fb254fffde3
ms.openlocfilehash: f348586341d0fa5b6e1a5fe15ab8c3a75e369e64
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/09/2020
ms.locfileid: "96983272"
---
# <a name="how-to-make-an-object-follow-the-mouse-pointer"></a>方法: オブジェクトをマウス ポインターに追従させる
この例では、マウス ポインターが画面上を移動したときにオブジェクトのディメンションを変更する方法を示します。  
  
 この例には、[!INCLUDE[TLA#tla_ui](../../../includes/tlasharptla-ui-md.md)] を作成する [!INCLUDE[TLA#tla_xaml](../../../includes/tlasharptla-xaml-md.md)] ファイルと、イベント ハンドラーを作成する分離コード ファイルが含まれています。  
  
## <a name="example"></a>例  
 次の XAML では、<xref:System.Windows.Controls.StackPanel> 内の <xref:System.Windows.Shapes.Ellipse> で構成される [!INCLUDE[TLA2#tla_ui](../../../includes/tla2sharptla-ui-md.md)] が作成され、<xref:System.Windows.UIElement.MouseMove> イベントのイベント ハンドラーがアタッチされます。  
  
 [!code-xaml[mouseMoveWithPointer#MouseMoveWithPointerXAML](~/samples/snippets/csharp/VS_Snippets_Wpf/mouseMoveWithPointer/CSharp/Window1.xaml#mousemovewithpointerxaml)]  
  
 次の分離コードでは、<xref:System.Windows.UIElement.MouseMove> イベント ハンドラーが作成されます。  マウス ポインターを動かすと、<xref:System.Windows.Shapes.Ellipse> の高さと幅が増減します。  
  
 [!code-csharp[mouseMoveWithPointer#MouseMovePointerGetPosition](~/samples/snippets/csharp/VS_Snippets_Wpf/mouseMoveWithPointer/CSharp/Window1.xaml.cs#mousemovepointergetposition)]
 [!code-vb[mouseMoveWithPointer#MouseMovePointerGetPosition](~/samples/snippets/visualbasic/VS_Snippets_Wpf/mouseMoveWithPointer/VisualBasic/Window1.xaml.vb#mousemovepointergetposition)]  
  
## <a name="see-also"></a>関連項目

- [入力の概要](input-overview.md)
