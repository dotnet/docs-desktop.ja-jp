---
title: Panel コントロールの概要
ms.date: 03/30/2017
f1_keywords:
- Panel
helpviewer_keywords:
- grouping controls [Windows Forms], Panel control
- Panel control [Windows Forms], about Panel control
ms.assetid: b6b83636-2c39-4dad-89d6-f0fa41049a74
ms.openlocfilehash: 3ea86e898e8a3e1ca90ba8e0a6240414702a1a73
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/09/2020
ms.locfileid: "96981983"
---
# <a name="panel-control-overview-windows-forms"></a>Panel コントロールの概要 (Windows フォーム)
Windows フォーム <xref:System.Windows.Forms.Panel> コントロールは、他のコントロールの識別可能なグループ化を提供するために使用されます。 通常、パネルを使用して、関数によってフォームを分割します。 たとえば、使用する夜間配送業者などのメーリングオプションを指定する注文フォームがあるとします。 パネル内のすべてのオプションをグループ化すると、ユーザーは論理的な視覚的な手掛かりを得ることができます。 デザイン時には、すべてのコントロールを簡単に移動できます。コントロールを移動すると、 <xref:System.Windows.Forms.Panel> それに含まれるすべてのコントロールも移動します。 パネルにグループ化されたコントロールには、そのプロパティを使用してアクセスできます <xref:System.Windows.Forms.Control.Controls%2A> 。 このプロパティは、インスタンスのコレクションを返し <xref:System.Windows.Forms.Control> ます。そのため、通常は、この方法で取得したコントロールを特定の型にキャストする必要があります。  
  
## <a name="panel-versus-groupbox"></a>パネルと GroupBox  
 コントロール <xref:System.Windows.Forms.Panel> はコントロールに似ていますが、 <xref:System.Windows.Forms.GroupBox> スクロールバーを持つことができるのはコントロールだけで、 <xref:System.Windows.Forms.Panel> キャプションはコントロールのみに <xref:System.Windows.Forms.GroupBox> 表示されます。  
  
## <a name="key-properties"></a>キー プロパティ  
 スクロールバーを表示するには、 <xref:System.Windows.Forms.ScrollableControl.AutoScroll%2A> プロパティをに設定し `true` ます。 また、、、およびの各プロパティを設定して、パネルの外観をカスタマイズすることもでき <xref:System.Windows.Forms.Control.BackColor%2A> <xref:System.Windows.Forms.Control.BackgroundImage%2A> <xref:System.Windows.Forms.Panel.BorderStyle%2A> ます。 およびプロパティの詳細に <xref:System.Windows.Forms.Control.BackColor%2A> つい <xref:System.Windows.Forms.Control.BackgroundImage%2A> ては、「 [方法: パネルの背景を設定する](how-to-set-the-background-of-a-windows-forms-panel.md)」を参照してください。 プロパティは、 <xref:System.Windows.Forms.Panel.BorderStyle%2A> 表示されている境界線 ( <xref:System.Windows.Forms.BorderStyle.None> )、線 ( <xref:System.Windows.Forms.BorderStyle.FixedSingle> )、または影付きの線 () がないパネルを表示するかどうかを決定し <xref:System.Windows.Forms.BorderStyle.Fixed3D> ます。  
  
## <a name="see-also"></a>関連項目

- <xref:System.Windows.Forms.Panel>
- [GroupBox コントロール](groupbox-control-windows-forms.md)
- [方法: デザイナーを使用して Windows フォーム Panel コントロールでコントロールをグループ化する](group-controls-with-wf-panel-control-using-the-designer.md)
- [方法: デザイナーを使って Windows フォーム パネルの背景を設定する](how-to-set-the-background-of-a-windows-forms-panel-using-the-designer.md)
