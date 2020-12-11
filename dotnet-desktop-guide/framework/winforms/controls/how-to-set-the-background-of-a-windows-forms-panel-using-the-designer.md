---
title: デザイナーを使用してパネルの背景を設定する
ms.date: 03/30/2017
helpviewer_keywords:
- background colors [Windows Forms], Windows Forms Panel controls
- background images [Windows Forms], Windows Forms Panel controls
- Panel control [Windows Forms], background
- colors [Windows Forms], Windows Forms Panel controls
ms.assetid: db83cf54-3c69-4b08-ac6c-25b9b5abb1b0
ms.openlocfilehash: 8bdefba433632f7ba02f549a549c52c7aa56c2d7
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/09/2020
ms.locfileid: "96983047"
---
# <a name="how-to-set-the-background-of-a-windows-forms-panel-using-the-designer"></a>方法: デザイナーを使用して Windows フォームパネルの背景を設定する

Windows フォームコントロールには、 <xref:System.Windows.Forms.Panel> 背景色と背景画像の両方を表示できます。 プロパティは、 <xref:System.Windows.Forms.Control.BackColor%2A> ラベルやラジオボタンなど、パネルに含まれるコントロールの背景色を設定します。 プロパティが設定されていない場合は、 <xref:System.Windows.Forms.Control.BackgroundImage%2A> すべてのパネルが <xref:System.Windows.Forms.Control.BackColor%2A> 選択されます。 プロパティが設定されている場合は、 <xref:System.Windows.Forms.Control.BackgroundImage%2A> パネルに含まれているコントロールの背後に画像が表示されます。

次の手順では、コントロールを含むフォームを含む **Windows アプリケーション** プロジェクトが必要です <xref:System.Windows.Forms.Panel> 。 Visual Studio でこのようなプロジェクトを設定する方法の詳細については、「 [方法: Windows フォームアプリケーションプロジェクトを作成](/visualstudio/ide/step-1-create-a-windows-forms-application-project) する」および「 [方法: Windows フォームにコントロールを追加](how-to-add-controls-to-windows-forms.md)する」を参照してください。

## <a name="set-the-background-in-the-windows-forms-designer"></a>Windows フォームデザイナーの背景を設定する

1. Visual Studio でプロジェクトを開き、コントロールを選択し <xref:System.Windows.Forms.Panel> ます。

2. [ **プロパティ** ] ウィンドウで、プロパティの横にある矢印ボタンをクリックし <xref:System.Windows.Forms.Control.BackColor%2A> て、3つのタブを含むウィンドウを表示します。

3. [ **カスタム** ] タブを選択して、色のパレットを表示します。

4. [ **Web** ] または [ **システム** ] タブを選択して、色の定義済みの名前の一覧を表示し、色を選択します。

5. [ **プロパティ** ] ウィンドウで、プロパティの横にある矢印ボタンをクリックし <xref:System.Windows.Forms.Control.BackgroundImage%2A> ます。

6. [ **開く** ] ダイアログボックスで、表示するファイルを選択します。

## <a name="see-also"></a>関連項目

- <xref:System.Windows.Forms.Control.BackColor%2A>
- <xref:System.Windows.Forms.Control.BackgroundImage%2A>
- [パネル コントロール](panel-control-windows-forms.md)
- [Panel コントロールの概要](panel-control-overview-windows-forms.md)
- [方法: デザイナーを使用して Windows フォーム Panel コントロールでコントロールをグループ化する](group-controls-with-wf-panel-control-using-the-designer.md)
