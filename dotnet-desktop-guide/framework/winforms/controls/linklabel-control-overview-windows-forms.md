---
title: LinkLabel コントロールの概要
ms.date: 03/30/2017
f1_keywords:
- LinkLabel
helpviewer_keywords:
- links [Windows Forms], LinkLabel control
- Label control [Windows Forms], about Label control
- LinkLabel control [Windows Forms], about LinkLabel control
ms.assetid: 9e248549-10ca-43a3-bb5e-60f583d369f1
ms.openlocfilehash: 3e8607644c858ae804e384c974b5e81c1786c6a1
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/09/2020
ms.locfileid: "96982960"
---
# <a name="linklabel-control-overview-windows-forms"></a>LinkLabel コントロールの概要 (Windows フォーム)
Windows フォーム <xref:System.Windows.Forms.LinkLabel> コントロールを使用すると、Windows フォームアプリケーションに Web スタイルのリンクを追加できます。 コントロールを使用すると、 <xref:System.Windows.Forms.LinkLabel> のコントロールを使用できます <xref:System.Windows.Forms.Label> 。また、テキストの一部を、ファイル、フォルダー、または Web ページへのリンクとして設定することもできます。  
  
## <a name="what-you-can-do-with-the-linklabel-control"></a>LinkLabel コントロールでできること  
 コントロールには、コントロールのすべてのプロパティ、メソッド、およびイベントに加えて、 <xref:System.Windows.Forms.Label> <xref:System.Windows.Forms.LinkLabel> ハイパーリンクおよびリンクの色のプロパティがあります。 プロパティは、 <xref:System.Windows.Forms.LinkLabel.LinkArea%2A> リンクをアクティブにするテキストの領域を設定します。 <xref:System.Windows.Forms.LinkLabel.LinkColor%2A>、、およびの各プロパティは、 <xref:System.Windows.Forms.LinkLabel.VisitedLinkColor%2A> <xref:System.Windows.Forms.LinkLabel.ActiveLinkColor%2A> リンクの色を設定します。 イベントは、 <xref:System.Windows.Forms.LinkLabel.LinkClicked> リンクテキストが選択されたときの動作を決定します。  
  
 コントロールを最も簡単に使用する <xref:System.Windows.Forms.LinkLabel> には、プロパティを使用して1つのリンクを表示し <xref:System.Windows.Forms.LinkLabel.LinkArea%2A> ますが、プロパティを使用して複数のハイパーリンクを表示することもでき <xref:System.Windows.Forms.LinkLabel.Links%2A> ます。 <xref:System.Windows.Forms.LinkLabel.Links%2A>プロパティを使用すると、リンクのコレクションにアクセスできます。 個々のオブジェクトのプロパティでデータを指定することもでき <xref:System.Windows.Forms.LinkLabel.Link.LinkData%2A> <xref:System.Windows.Forms.LinkLabel.Link> ます。 プロパティの値は、 <xref:System.Windows.Forms.LinkLabel.Link.LinkData%2A> 表示するファイルの場所または Web サイトのアドレスを格納するために使用できます。  
  
## <a name="see-also"></a>関連項目

- <xref:System.Windows.Forms.LinkLabel>
- [Label コントロールの概要](label-control-overview-windows-forms.md)
- [方法: Windows フォーム LinkLabel コントロールでオブジェクトまたは Web ページにリンクする](link-to-an-object-or-web-page-with-wf-linklabel-control.md)
- [方法: Windows フォーム LinkLabel コントロールの表示形式を変更する](how-to-change-the-appearance-of-the-windows-forms-linklabel-control.md)
