---
title: ラベル コントロール
description: .NET 用の Windows フォームの Label コントロールについて説明します。 ラベルを使用して、ユーザーがビジュアル要素を識別できるようにします。
ms.date: 10/26/2020
ms.topic: overview
f1_keywords:
- Label
helpviewer_keywords:
- images [Windows Forms], displaying in labels
- labels
- Label control [Windows Forms], about Label control
ms.openlocfilehash: 6f669b7aef1182c35e125ff8dd3ca5ccb299b898
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/09/2020
ms.locfileid: "96942271"
---
# <a name="label-control-overview-windows-forms-net"></a>Label コントロールの概要 (Windows フォーム .NET)

Windows フォームの <xref:System.Windows.Forms.Label> コントロールは、ユーザーが編集できないテキストを表示するために使用されます。 これらは、フォーム上のオブジェクトを識別したり、特定のコントロールが表すものや実行内容を説明したりするために使用されます。 たとえば、ラベルを使用すると、テキスト ボックス、リスト ボックス、コンボ ボックスなどにわかりやすいキャプションを追加できます。 また、実行時にイベントに応答して、ラベルによって表示されるテキストを変更するコードを記述することもできます。

[!INCLUDE [desktop guide under construction](../../includes/desktop-guide-preview-note.md)]

## <a name="working-with-the-label-control"></a>Label コントロールの操作  

<xref:System.Windows.Forms.Label> コントロールはフォーカスを受け取ることができないため、他のコントロールのアクセス キーを作成するために使用できます。 アクセス キーを使用すると、ユーザーは、選択したアクセス キーを使用して <kbd>Alt</kbd> キーを押すことで、タブ オーダーで次のコントロールにフォーカスすることができます。 詳細については、「[ラベルを使用してコントロールにフォーカスを設定する](how-to-create-access-keys.md#use-a-label-to-focus-a-control)」を参照してください。
  
ラベルに表示されるキャプションは、<xref:System.Windows.Forms.Label.Text%2A> プロパティに含まれています。 <xref:System.Windows.Forms.Label.TextAlign%2A> プロパティを使用すると、ラベル内のテキストの配置を設定できます。 詳細については、「[方法:Windows フォーム コントロールによって表示されるテキストを設定する](how-to-set-the-display-text.md)」を参照してください。

## <a name="see-also"></a>関連項目

- [ラベルを使用してコントロールにフォーカスを設定する (Windows フォーム .NET)](how-to-create-access-keys.md#use-a-label-to-focus-a-control)
- [方法: コントロールによって表示されるテキストを設定する (Windows フォーム .NET)](how-to-set-the-display-text.md)
- <xref:System.Windows.Forms.ContainerControl.AutoScaleMode%2A>
- <xref:System.Windows.Forms.Control.Scale%2A>
- <xref:System.Windows.Forms.ContainerControl.PerformAutoScale%2A>
- <xref:System.Windows.Forms.ContainerControl.AutoScaleDimensions%2A>
