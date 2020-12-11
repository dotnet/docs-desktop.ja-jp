---
title: FlowLayoutPanel コントロールの概要
ms.date: 03/30/2017
f1_keywords:
- FlowLayoutPanel
helpviewer_keywords:
- forms [Windows Forms], dynamic layout
- layout [Windows Forms], dynamic
- Windows Forms, dynamic layout
- FlowLayoutPanel control [Windows Forms], about FlowLayoutPanel control
ms.assetid: 3883e024-f5a0-456d-9c27-b4dfa1cc9045
ms.openlocfilehash: 260146cd901fe2b80a73c01060ccd55958cd169e
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/09/2020
ms.locfileid: "96981055"
---
# <a name="flowlayoutpanel-control-overview"></a>FlowLayoutPanel コントロールの概要
<xref:System.Windows.Forms.FlowLayoutPanel> コントロールは、水平または垂直のフローの方向に内容を整列させます。 コントロールの内容をある行から次の行、またはある列から次の列にラップすることができます。 また、内容をラップする代わりにクリップすることができます。  
  
 <xref:System.Windows.Forms.FlowLayoutPanel.FlowDirection%2A> プロパティの値を設定して、フローの方向を指定できます。 <xref:System.Windows.Forms.FlowLayoutPanel> コントロールは、右から左 (RTL) のレイアウトでフローの方向を正しく反転します。 また、<xref:System.Windows.Forms.FlowLayoutPanel.WrapContents%2A> プロパティの値を設定して、<xref:System.Windows.Forms.FlowLayoutPanel> コントロールの内容がラップまたはクリップされるかを指定することもできます。  
  
 <xref:System.Windows.Forms.FlowLayoutPanel> コントロールは、<xref:System.Windows.Forms.Control.AutoSize%2A> プロパティを `true` に設定すると、自動的に内容に合わせたサイズにします。 また、 **Flowbreak** プロパティを子コントロールに提供します。 FlowBreak プロパティの値を `true` に設定することで、 <xref:System.Windows.Forms.FlowLayoutPanel> コントロールを現在のフロー方向のコントロールにレイアウトすること、および次の行または列にラップすることを停止します。  
  
 Windows フォーム コントロールは、<xref:System.Windows.Forms.FlowLayoutPanel> の他のインスタンスを含めて、<xref:System.Windows.Forms.FlowLayoutPanel> コントロールの子にすることができます。 この機能により、実行時にフォームのサイズを調整する高度なレイアウトを構築することができます。  
  
 「 [チュートリアル: FlowLayoutPanel を使用した Windows フォームでのコントロールの配置](walkthrough-arranging-controls-on-windows-forms-using-a-flowlayoutpanel.md)」も参照してください。  
  
## <a name="see-also"></a>関連項目

- <xref:System.Windows.Forms.FlowLayoutPanel.FlowDirection%2A>
- <xref:System.Windows.Forms.TableLayoutPanel>
- [FlowLayoutPanel コントロール](flowlayoutpanel-control-windows-forms.md)
