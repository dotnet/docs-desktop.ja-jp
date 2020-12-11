---
title: コンテンツに合わせてラベルコントロールのサイズを変更する
ms.date: 03/30/2017
helpviewer_keywords:
- captions [Windows Forms], sizing
- sizing controls
- size [Windows Forms], controls
- labels [Windows Forms], sizing to fit contents
- Label control [Windows Forms], sizing to fit contents
ms.assetid: 99648964-63b2-438c-980e-d24103ad602b
ms.openlocfilehash: 6a563693feaa5074f5d13f0b82cc4d0305a79c23
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/09/2020
ms.locfileid: "96982804"
---
# <a name="how-to-size-a-windows-forms-label-control-to-fit-its-contents"></a>方法: Windows フォーム Label コントロールのサイズを内容に合わせて変更する
Windows フォーム <xref:System.Windows.Forms.Label> コントロールは単一行または複数行にすることができ、サイズを固定するか、キャプションに合わせて自動的にサイズを変更することができます。 <xref:System.Windows.Forms.Label.AutoSize%2A>プロパティを使用すると、コントロールのサイズを大きくしたり小さくしたりすることができます。これは、実行時にキャプションが変化する場合に特に便利です。  
  
### <a name="to-make-a-label-control-resize-dynamically-to-fit-its-contents"></a>コンテンツに合わせてラベルコントロールのサイズを動的に変更するには  
  
1. <xref:System.Windows.Forms.Label.AutoSize%2A>プロパティをに設定 `true` します。  
  
 がに設定されている場合、可能であれ <xref:System.Windows.Forms.Label.AutoSize%2A> `false` ば、プロパティで指定された単語 <xref:System.Windows.Forms.Label.Text%2A> は次の行に折り返されますが、コントロールは拡張されません。  
  
## <a name="see-also"></a>関連項目

- [方法: Windows フォームの Label コントロールでアクセス キーを作成する](how-to-create-access-keys-with-windows-forms-label-controls.md)
- [Label コントロールの概要](label-control-overview-windows-forms.md)
- [Label コントロール](label-control-windows-forms.md)
