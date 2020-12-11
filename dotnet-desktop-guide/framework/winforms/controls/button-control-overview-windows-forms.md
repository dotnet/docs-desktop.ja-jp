---
title: Button コントロールの概要
ms.date: 03/30/2017
f1_keywords:
- Button
helpviewer_keywords:
- Button control [Windows Forms], about Button control
- buttons [Windows Forms], about buttons
ms.assetid: 255b291b-51a9-4a92-a1a4-2400cd82443f
ms.openlocfilehash: 4ba7b333e5414efb4814d64ce50c55e08b27f859
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/09/2020
ms.locfileid: "96981556"
---
# <a name="button-control-overview-windows-forms"></a>Button コントロールの概要 (Windows フォーム)
Windows フォームの <xref:System.Windows.Forms.Button> コントロールを使用すると、ユーザーはそれをクリックしてアクションを実行できます。 ボタンをクリックすると、ボタンを実際に押して離したかのように表示されます。 ユーザーがボタンをクリックするたびに、 <xref:System.Windows.Forms.Control.Click> イベントハンドラーが呼び出されます。 イベントハンドラーにコードを配置して、 <xref:System.Windows.Forms.Control.Click> 選択した任意のアクションを実行します。  
  
 ボタンに表示されるテキストは、プロパティに含まれてい <xref:System.Windows.Forms.Control.Text%2A> ます。 テキストがボタンの幅を超えている場合は、次の行に折り返されます。 ただし、コントロールが全体的な高さに対応できない場合はクリップされます。 詳細については、「 [方法: Windows フォームコントロールによって表示されるテキストを設定する](how-to-set-the-text-displayed-by-a-windows-forms-control.md)」を参照してください。 プロパティには <xref:System.Windows.Forms.Control.Text%2A> アクセスキーを含めることができます。これにより、ユーザーは ALT キーを押しながらアクセスキーを押してコントロールを "クリック" できます。 詳細については、「 [方法: Windows フォームコントロールのアクセスキーを作成する](how-to-create-access-keys-for-windows-forms-controls.md)」を参照してください。 テキストの外観は、プロパティとプロパティによって制御され <xref:System.Windows.Forms.Control.Font%2A> <xref:System.Windows.Forms.ButtonBase.TextAlign%2A> ます。  
  
 コントロールでは、 <xref:System.Windows.Forms.Button> プロパティとプロパティを使用してイメージを表示することもでき <xref:System.Windows.Forms.ButtonBase.Image%2A> <xref:System.Windows.Forms.ButtonBase.ImageList%2A> ます。 詳細については、「 [方法: Windows フォームコントロールによって表示されるイメージを設定する](how-to-set-the-image-displayed-by-a-windows-forms-control.md)」を参照してください。  
  
## <a name="see-also"></a>関連項目

- <xref:System.Windows.Forms.Button>
- [方法 : Windows フォームのボタンのクリックに応答する](how-to-respond-to-windows-forms-button-clicks.md)
- [Windows フォームの Button コントロールを選択する方法](ways-to-select-a-windows-forms-button-control.md)
- [方法: デザイナーを使用して Windows フォームの Button コントロールを承認ボタンとして指定する](designate-a-wf-button-as-the-accept-button-using-the-designer.md)
- [方法: デザイナーを使用して Windows フォームの Button コントロールをキャンセル ボタンとして指定する](designate-a-wf-button-as-the-cancel-button-using-the-designer.md)
- [Button コントロール](button-control-windows-forms.md)
