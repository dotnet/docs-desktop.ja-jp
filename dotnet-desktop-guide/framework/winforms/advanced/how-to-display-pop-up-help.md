---
title: '方法: ポップアップ ヘルプを表示する'
ms.date: 03/30/2017
helpviewer_keywords:
- pop-up Help
- Help [Windows Forms], pop-up Help
- Windows Forms, displaying Help
- forms [Windows Forms], displaying Help
- modal dialog boxes [Windows Forms], pop-up Help
- F1 Help [Windows Forms], in dialog boxes
- HelpProvider component [Windows Forms]
- Help [Windows Forms], adding to dialog boxes
ms.assetid: 218aa81e-e87e-4d67-af05-11627bbdce3b
ms.openlocfilehash: a3b40f49119fcf7900f1f0c8b77c5d83fe81144c
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/09/2020
ms.locfileid: "96974406"
---
# <a name="how-to-display-pop-up-help"></a>方法: ポップアップヘルプを表示する

Windows フォームに関するヘルプを表示する方法の1つは、プロパティを使用してアクセスできる、タイトルバーの右側にある [ **ヘルプ** ] ボタンを使用する方法です <xref:System.Windows.Forms.Form.HelpButton%2A> 。 この種類のヘルプの表示は、ダイアログ ボックスでの使用に適しています。 モーダル形式で表示されるダイアログ ボックス (<xref:System.Windows.Forms.Form.ShowDialog%2A> メソッドを使用) は、別のウィンドウにフォーカスを移動するときはモーダル ダイアログ ボックスを閉じる必要があるため、外部のヘルプ システムを起動する場合は問題が発生します。 また、[ **ヘルプ** ] ボタンを使用するには、タイトルバーに [ **最小化** ] ボタンまたは [ **最大化** ] ボタンが表示されないようにする必要があります。 これは標準のダイアログボックスの規則であり、通常、フォームには [ **最小化** ] ボタンと [ **最大化** ] ボタンがあります。

また、 <xref:System.Windows.Forms.HelpProvider> ポップアップヘルプを実装している場合でも、コンポーネントを使用して、ヘルプシステム内のファイルにコントロールをリンクすることもできます。 詳細については、「 [Windows アプリケーションでのヘルプの提供](how-to-provide-help-in-a-windows-application.md)」を参照してください。

## <a name="display-pop-up-help"></a>ポップアップヘルプを表示する

1. Visual Studio で、[ツールボックス] から [HelpProvider](../controls/helpprovider-component-windows-forms.md) コンポーネントをフォームにドラッグします。

   これは、Windows フォーム デザイナーの下部にあるトレイ内に配置されます。

2. [プロパティ] ウィンドウで、<xref:System.Windows.Forms.Form.HelpButton%2A> プロパティを `true` に設定します。 これで、フォームのタイトル バーの右側に疑問符の付いたボタンが表示されます。

3. <xref:System.Windows.Forms.Form.HelpButton%2A> が表示されるには、フォームの <xref:System.Windows.Forms.Form.MinimizeBox%2A> プロパティと <xref:System.Windows.Forms.Form.MaximizeBox%2A> プロパティを `false` に設定し、<xref:System.Windows.Forms.Form.ControlBox%2A> プロパティを `true` に設定し、<xref:System.Windows.Forms.Form.FormBorderStyle%2A> プロパティを<xref:System.Windows.Forms.FormBorderStyle.FixedSingle>、<xref:System.Windows.Forms.FormBorderStyle.Fixed3D>、<xref:System.Windows.Forms.FormBorderStyle.FixedDialog>、または <xref:System.Windows.Forms.FormBorderStyle.Sizable> のいずれかの値に設定する必要があります。

4. フォーム上のヘルプを表示し、[プロパティ] ウィンドウのヘルプの文字列を設定するコントロールを選択します。 これは、 [ツールヒント](../controls/tooltip-component-windows-forms.md)のようなウィンドウに表示されるテキストの文字列です。

5. **F5** キーを押します。

6. タイトルバーの [ **ヘルプ** ] ボタンをクリックし、ヘルプ文字列を設定したコントロールをクリックします。

## <a name="see-also"></a>関連項目

- [ツールヒントを使用したコントロールのヘルプ](control-help-using-tooltips.md)
- [Windows フォームでのヘルプの統合](integrating-user-help-in-windows-forms.md)
- [Windows フォーム](../index.yml)
