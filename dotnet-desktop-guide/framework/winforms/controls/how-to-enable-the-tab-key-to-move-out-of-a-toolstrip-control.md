---
title: '方法: Tab キーで ToolStrip コントロールから移動できるようにする'
ms.date: 03/30/2017
helpviewer_keywords:
- controls [Windows Forms], moving between
- TAB key [Windows Forms], enabling
- ToolStrip control [Windows Forms], moving from
ms.assetid: 40f9e88b-09a3-428e-8da8-c00bb65079c6
ms.openlocfilehash: 7fee9f685b9a9b402cbfe9c265669f7905434986
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/09/2020
ms.locfileid: "96980800"
---
# <a name="how-to-enable-the-tab-key-to-move-out-of-a-toolstrip-control"></a>方法: Tab キーで ToolStrip コントロールから移動できるようにする
次の手順を使用して、ユーザーが tab キーを押してからタブオーダーの次のコントロールに移動できるようにし <xref:System.Windows.Forms.ToolStrip> ます。  
  
 は <xref:System.Windows.Forms.ToolStrip> tab キーの最初のキーを受け入れ、方向キーは内の項目を選択し <xref:System.Windows.Forms.ToolStrip> ます。 TAB キーをもう一度押すと、ユーザーがタブオーダーの次のコントロールに移動します。  
  
### <a name="to-enable-the-user-to-press-the-tab-key-to-move-out-of-a-toolstrip-to-the-next-control"></a>ユーザーが TAB キーを押して ToolStrip から次のコントロールに移動できるようにするには  
  
- <xref:System.Windows.Forms.ToolStrip> の  の <xref:System.Windows.Forms.ToolStrip.TabStop%2A> プロパティを `true` に設定します。  
  
## <a name="see-also"></a>関連項目

- <xref:System.Windows.Forms.ToolStrip>
- <xref:System.Windows.Forms.ToolStrip.TabStop%2A>
- [ToolStrip コントロールの概要](toolstrip-control-overview-windows-forms.md)
