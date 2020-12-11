---
title: HScrollBar コントロールと VScrollBar コントロールの概要
ms.date: 03/30/2017
f1_keywords:
- HScrollBar
- VScrollBar
helpviewer_keywords:
- ScrollBar control [Windows Forms]
- HScrollBar control [Windows Forms], about HScrollBar
- VScrollBar control [Windows Forms], about VScrollBar control
- ScrollBar control [Windows Forms], about ScrollBar control
- scroll bars [Windows Forms], about scroll bars
ms.assetid: 8b307679-1cae-41d8-99aa-3d1efd207cd6
ms.openlocfilehash: abe0c8da9723f17cb80715454f6ab7297724a21f
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/09/2020
ms.locfileid: "96982995"
---
# <a name="hscrollbar-and-vscrollbar-controls-overview-windows-forms"></a>HScrollBar コントロールと VScrollBar コントロールの概要 (Windows フォーム)
Windows フォームコントロールを使用して、 <xref:System.Windows.Forms.ScrollBar> アプリケーションまたはコントロール内で水平方向または垂直方向にスクロールすることにより、項目の長い一覧または大量の情報を簡単に移動できるようにします。 スクロールバーは、Windows インターフェイスの共通要素であるため、 <xref:System.Windows.Forms.ScrollBar> 多くの場合、コントロールはクラスから派生しないコントロールで使用され <xref:System.Windows.Forms.ScrollableControl> ます。 同様に、多くの開発者は、 <xref:System.Windows.Forms.ScrollBar> 独自のユーザーコントロールを作成するときにコントロールを組み込むことを選択します。  
  
 <xref:System.Windows.Forms.HScrollBar>(水平) コントロールと <xref:System.Windows.Forms.VScrollBar> (垂直) コントロールは、他のコントロールとは独立して動作し、独自のイベント、プロパティ、およびメソッドのセットを持ちます。 <xref:System.Windows.Forms.ScrollBar> コントロールは、テキストボックス、リストボックス、コンボボックス、または MDI フォームに関連付けられている組み込みのスクロールバーと同じではありません (コントロールには、 <xref:System.Windows.Forms.TextBox> <xref:System.Windows.Forms.TextBox.ScrollBars%2A> コントロールに関連付けられているスクロールバーを表示または非表示にするプロパティがあります)。  
  
 コントロールは、スクロール <xref:System.Windows.Forms.ScrollBar> <xref:System.Windows.Forms.ScrollBar.Scroll> バーに沿ったスクロールボックス (つまみとも呼ばれます) の動きを監視するために、イベントを使用します。 イベントを使用 <xref:System.Windows.Forms.ScrollBar.Scroll> すると、スクロールバーの値をドラッグしているときの値にアクセスできます。  
  
## <a name="value-property"></a>Value プロパティ  
 <xref:System.Windows.Forms.ScrollBar.Value%2A>プロパティ (既定では 0) は、 `integer` スクロールバーのスクロールボックスの位置に対応する値です。 スクロールボックスの位置が最小値になると、左端 (水平スクロールバーの場合) または一番上の位置 (垂直スクロールバーの場合) に移動します。 スクロールボックスが最大値になると、スクロールボックスが右端または下の位置に移動します。 同様に、範囲の下端と上端の中間にある値によって、スクロールボックスの先頭端がスクロールバーの中央に配置されます。  
  
 ユーザーは、マウスクリックを使用してスクロールバーの値を変更するだけでなく、スクロールボックスをバー上の任意のポイントにドラッグすることもできます。 結果の値は、スクロールボックスの位置によって異なりますが、常に <xref:System.Windows.Forms.ScrollBar.Minimum%2A> ユーザーが設定する to プロパティの範囲内にあり <xref:System.Windows.Forms.ScrollBar.Maximum%2A> ます。  
  
## <a name="largechange-and-smallchange-properties"></a>Largechange] プロパティと Smallchange] プロパティ  
 ユーザーが pageup キーまたは pagedown キーを押すか、スクロールボックスの両側のスクロールバートラックをクリックすると、プロパティ <xref:System.Windows.Forms.ScrollBar.Value%2A> に設定されている値に従ってプロパティが変更され <xref:System.Windows.Forms.ScrollBar.LargeChange%2A> ます。  
  
 ユーザーがいずれかの方向キーを押すか、スクロールバーのボタンのいずれかをクリックすると、プロパティ <xref:System.Windows.Forms.ScrollBar.Value%2A> に設定されている値に従ってプロパティが変更され <xref:System.Windows.Forms.ScrollBar.SmallChange%2A> ます。  
  
## <a name="see-also"></a>関連項目

- <xref:System.Windows.Forms.HScrollBar>
- <xref:System.Windows.Forms.VScrollBar>
- [Windows フォームで使用するコントロール](controls-to-use-on-windows-forms.md)
