---
title: ProgressBar コントロールの概要
ms.date: 03/30/2017
f1_keywords:
- ProgressBar
helpviewer_keywords:
- ProgressBar control [Windows Forms], about ProgressBar control
- progress controls [Windows Forms], about progress controls
ms.assetid: a05d9cba-3a6a-4f8f-94b8-8ec12799fb80
ms.openlocfilehash: a0c4a0401d06614ab3ad148b932ebc64080c592c
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/09/2020
ms.locfileid: "96974392"
---
# <a name="progressbar-control-overview-windows-forms"></a>ProgressBar コントロールの概要 (Windows フォーム)
> [!IMPORTANT]
> <xref:System.Windows.Forms.ToolStripProgressBar> コントロールは、<xref:System.Windows.Forms.ProgressBar> コントロールに代わると共に追加の機能を提供します。ただし、<xref:System.Windows.Forms.ProgressBar> コントロールは、下位互換性を保つ目的および将来使用する目的で保持されます。  
  
 Windows フォームコントロールは、 <xref:System.Windows.Forms.ProgressBar> 水平バーに配置された適切な数の四角形を表示することによって、プロセスの進行状況を示します。 プロセスが完了すると、バーは塗りつぶされます。 一般的に、進行状況バーは、プロセスが完了するまでの待機時間をユーザーに示すために使用されます。たとえば、大きなファイルが読み込まれている場合です。  
  
> [!NOTE]
> コントロールは、 <xref:System.Windows.Forms.ProgressBar> フォーム上で水平方向にのみ配置できます。  
  
## <a name="key-properties-and-methods"></a>キーのプロパティとメソッド  
 コントロールの主要なプロパティ <xref:System.Windows.Forms.ProgressBar> は、、、 <xref:System.Windows.Forms.ProgressBar.Value%2A> <xref:System.Windows.Forms.ProgressBar.Minimum%2A> および <xref:System.Windows.Forms.ProgressBar.Maximum%2A> です。 <xref:System.Windows.Forms.ProgressBar.Minimum%2A>プロパティと <xref:System.Windows.Forms.ProgressBar.Maximum%2A> プロパティは、進行状況バーに表示できる最大値と最小値を設定します。 プロパティは、 <xref:System.Windows.Forms.ProgressBar.Value%2A> 操作の完了に向けた進行状況を表します。 コントロールに表示されるバーはブロックで構成されているため、コントロールによって表示される値は、 <xref:System.Windows.Forms.ProgressBar> プロパティの現在の値のみを概算し <xref:System.Windows.Forms.ProgressBar.Value%2A> ます。 プロパティは、コントロールのサイズに基づいて、 <xref:System.Windows.Forms.ProgressBar> <xref:System.Windows.Forms.ProgressBar.Value%2A> 次のブロックを表示するタイミングを決定します。  
  
 現在の進行状況の値を更新する最も一般的な方法は、プロパティを設定するコードを記述することです <xref:System.Windows.Forms.ProgressBar.Value%2A> 。 大きなファイルを読み込む例では、ファイルの最大サイズをキロバイト単位で設定できます。 たとえば、プロパティが100に設定されている場合、プロパティは10に設定され、 <xref:System.Windows.Forms.ProgressBar.Maximum%2A> <xref:System.Windows.Forms.ProgressBar.Minimum%2A> <xref:System.Windows.Forms.ProgressBar.Value%2A> プロパティは50に設定され、5つの四角形が表示されます。 これは、表示できる数の半分です。  
  
 ただし、プロパティを直接設定する以外に、コントロールによって表示される値を変更する方法は他にもあり <xref:System.Windows.Forms.ProgressBar> <xref:System.Windows.Forms.ProgressBar.Value%2A> ます。 <xref:System.Windows.Forms.ProgressBar.Step%2A>プロパティを使用して、プロパティをインクリメントする値を指定でき <xref:System.Windows.Forms.ProgressBar.Value%2A> ます。 次に、メソッドを呼び出すと、 <xref:System.Windows.Forms.ProgressBar.PerformStep%2A> 値がインクリメントされます。 インクリメント値を変更するには、メソッドを使用して、 <xref:System.Windows.Forms.ProgressBar.Increment%2A> プロパティをインクリメントする値を指定し <xref:System.Windows.Forms.ProgressBar.Value%2A> ます。  
  
 現在のアクションについてグラフィカルにユーザーに通知する別のコントロールが <xref:System.Windows.Forms.StatusBar> コントロールです。  
  
> [!IMPORTANT]
> コントロールとコントロールは、およびコントロール <xref:System.Windows.Forms.StatusStrip> <xref:System.Windows.Forms.ToolStripStatusLabel> に対して、機能の置き換えと追加を行います。ただし、コントロール <xref:System.Windows.Forms.StatusBar> とコントロールは、 <xref:System.Windows.Forms.StatusBarPanel> <xref:System.Windows.Forms.StatusBar> <xref:System.Windows.Forms.StatusBarPanel> 下位互換性と将来の使用の両方について、選択した場合に保持されます。  
  
## <a name="see-also"></a>関連項目

- <xref:System.Windows.Forms.ProgressBar>
- [ProgressBar コントロール](progressbar-control-windows-forms.md)
