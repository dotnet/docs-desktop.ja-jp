---
title: ColorDialog コンポーネントの概要
ms.date: 03/30/2017
f1_keywords:
- ColorDialog
helpviewer_keywords:
- color dialog box [Windows Forms], about color dialog box
- ColorDialog component [Windows Forms], about ColorDialog
ms.assetid: 6dbdd8f0-f697-4728-bb09-7ea156f6d800
ms.openlocfilehash: 48d9d5072335908f85e65933dadafb1b69f28528
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/09/2020
ms.locfileid: "96974299"
---
# <a name="colordialog-component-overview-windows-forms"></a>ColorDialog コンポーネントの概要 (Windows フォーム)
Windows フォーム <xref:System.Windows.Forms.ColorDialog> コンポーネントは、ユーザーがパレットから色を選択し、そのパレットにカスタムの色を追加できるようにする、事前に構成されたダイアログボックスです。 このダイアログ ボックスは、他の Windows ベースのアプリケーションで表示される色を選択するためのダイアログ ボックスと同じです。 このコントロールは、独自のダイアログ ボックスを使用しない簡易ソリューションとして、Windows ベースのアプリケーションの中で使用します。  
  
 ダイアログボックスで選択した色がプロパティに返され <xref:System.Windows.Forms.ColorDialog.Color%2A> ます。 <xref:System.Windows.Forms.ColorDialog.AllowFullOpen%2A>プロパティがに設定されている場合 `false` 、[カスタム色の定義] ボタンは無効になり、ユーザーはパレットの定義済みの色に制限されます。 <xref:System.Windows.Forms.ColorDialog.SolidColorOnly%2A>プロパティがに設定されている場合 `true` 、ユーザーはディザーカラーを選択できません。 ダイアログボックスを表示するには、メソッドを呼び出す必要があり <xref:System.Windows.Forms.CommonDialog.ShowDialog%2A> ます。  
  
## <a name="see-also"></a>関連項目

- <xref:System.Windows.Forms.ColorDialog>
- [ColorDialog コンポーネント](colordialog-component-windows-forms.md)
- [ダイアログ ボックス コントロールおよびコンポーネント](dialog-box-controls-and-components-windows-forms.md)
- [方法: Windows フォーム ColorDialog コンポーネントの表示形式を変更する](how-to-change-the-appearance-of-the-windows-forms-colordialog-component.md)
