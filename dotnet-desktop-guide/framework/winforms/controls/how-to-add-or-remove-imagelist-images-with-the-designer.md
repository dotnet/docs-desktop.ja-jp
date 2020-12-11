---
title: '方法: デザイナーを使って ImageList イメージを追加または削除する'
ms.date: 03/30/2017
helpviewer_keywords:
- ImageList component [Windows Forms], adding images
- ImageList component [Windows Forms], removing images
- images [Windows Forms], adding to ImageList component
ms.assetid: 5699b244-e37c-4d20-bc35-7441e55c1e3a
ms.openlocfilehash: cdc7b563a0ee4f8779b99b4e9a6786e78f8d500f
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/09/2020
ms.locfileid: "96982264"
---
# <a name="how-to-add-or-remove-imagelist-images-with-the-designer"></a>方法: デザイナーを使って ImageList イメージを追加または削除する

コンポーネントにイメージを追加するには、 <xref:System.Windows.Forms.ImageList> さまざまな方法があります。 に関連付けられたスマートタグを使用すると、イメージをすばやく追加できます <xref:System.Windows.Forms.ImageList> 。また、で他のプロパティをいくつか設定する場合は、 <xref:System.Windows.Forms.ImageList> プロパティウィンドウで画像を追加する方が便利な場合があります。 コードを使用してイメージを追加することもできます。 コードを使用してイメージを追加する方法の詳細については、「 [方法: Windows フォーム ImageList コンポーネントを使用してイメージを追加または削除](how-to-add-or-remove-images-with-the-windows-forms-imagelist-component.md)する」を参照してください。 通常は、 <xref:System.Windows.Forms.ImageList> コントロールに関連付けられる前にコンポーネントにイメージを設定しますが、これは必須ではありません。

### <a name="to-add-or-remove-images-by-using-the-properties-window"></a>プロパティウィンドウを使用してイメージを追加または削除するには

1. コンポーネントを選択 <xref:System.Windows.Forms.ImageList> するか、フォームに追加します。

2. プロパティウィンドウで、プロパティの横にある省略記号ボタン ( ![ Visual Studio のプロパティウィンドウの省略記号ボタン (...)) をクリックし ](./media/visual-studio-ellipsis-button.png) <xref:System.Windows.Forms.ImageList.Images%2A> ます。

3. **イメージコレクションエディター** で、[**追加**] または [**削除**] をクリックして、一覧からイメージを追加または削除します。

### <a name="to-add-or-remove-images-using-the-smart-tag"></a>スマートタグを使用してイメージを追加または削除するには

1. コンポーネントを選択 <xref:System.Windows.Forms.ImageList> するか、フォームに追加します。

2. デザイナーアクショングリフをクリックします (![小さい黒い矢印](./media/designer-actions-glyph.gif))

3. [ **ImageList Tasks** ] ダイアログボックスで、[ **Images の選択**] を選択します。

4. **イメージコレクションエディター** で、[**追加**] または [**削除**] をクリックして、一覧からイメージを追加または削除します。

## <a name="see-also"></a>関連項目

- [イメージ、ビットマップ、およびメタファイル](../advanced/images-bitmaps-and-metafiles.md)
- [チュートリアル: デザイン アクションを使って一般的なタスクを実行する](perform-common-tasks-design-actions.md)
- [ImageList コンポーネント](imagelist-component-windows-forms.md)
