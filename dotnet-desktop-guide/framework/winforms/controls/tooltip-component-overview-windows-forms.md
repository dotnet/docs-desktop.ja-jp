---
title: ToolTip コンポーネントの概要
ms.date: 03/30/2017
f1_keywords:
- ToolTip
helpviewer_keywords:
- tooltips [Windows Forms], about tooltips
- ToolTip component [Windows Forms], about ToolTip component
ms.assetid: 3fbc6f08-c882-4acd-a960-a08efe3c7e6e
ms.openlocfilehash: 731f7ad0ce6670000d8c3d3e901e1506f7ef470a
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/09/2020
ms.locfileid: "96983808"
---
# <a name="tooltip-component-overview-windows-forms"></a>ToolTip コンポーネントの概要 (Windows フォーム)
Windows フォーム <xref:System.Windows.Forms.ToolTip> コンポーネントは、ユーザーがコントロールをポイントしたときにテキストを表示します。 ツールヒントは任意のコントロールに関連付けることができます。 このコンポーネントの使用例: フォーム上の領域を節約するには、ボタンに小さいアイコンを表示し、ツールヒントを使用してボタンの機能を説明します。  
  
## <a name="working-with-the-tooltip-component"></a>ツールヒントコンポーネントの操作  
 コンポーネントは、 <xref:System.Windows.Forms.ToolTip> `ToolTip` Windows フォームまたはその他のコンテナー上の複数のコントロールにプロパティを提供します。 たとえば、1つのコンポーネントをフォームに配置した場合は、 <xref:System.Windows.Forms.ToolTip> コントロールの "ここに名前を入力 <xref:System.Windows.Forms.TextBox> してください" を表示し、コントロールの [ここをクリックして変更を保存します] をクリックし <xref:System.Windows.Forms.Button> ます。  
  
 コンポーネントの主要なメソッド <xref:System.Windows.Forms.ToolTip> は、 <xref:System.Windows.Forms.ToolTip.SetToolTip%2A> と <xref:System.Windows.Forms.ToolTip.GetToolTip%2A> です。 メソッドを使用して <xref:System.Windows.Forms.ToolTip.SetToolTip%2A> 、コントロールに表示されるツールヒントを設定できます。 詳細については、「 [方法: デザイン時に Windows フォームのコントロールにツールヒントを設定する](how-to-set-tooltips-for-controls-on-a-windows-form-at-design-time.md)」を参照してください。 キーのプロパティはです <xref:System.Windows.Forms.ToolTip.Active%2A> 。ツールヒントを表示するには、をに設定する必要があります。また、ツールヒント文字列を表示する時間の長さ、ツールヒントを `true` <xref:System.Windows.Forms.ToolTip.AutomaticDelay%2A> 表示するためにユーザーがコントロールをポイントする必要がある期間、およびそれ以降のツールヒントウィンドウが表示されるまでの時間を設定します。 詳細については、「 [方法: Windows フォーム ToolTip コンポーネントの遅延を変更する](how-to-change-the-delay-of-the-windows-forms-tooltip-component.md)」を参照してください。  
  
## <a name="see-also"></a>関連項目

- <xref:System.Windows.Forms.ToolTip>
- [方法: デザイン時に Windows フォームのコントロールにツールヒントを設定する](how-to-set-tooltips-for-controls-on-a-windows-form-at-design-time.md)
- [方法: Windows フォームの ToolTip コンポーネントの遅延時間を変更する](how-to-change-the-delay-of-the-windows-forms-tooltip-component.md)
