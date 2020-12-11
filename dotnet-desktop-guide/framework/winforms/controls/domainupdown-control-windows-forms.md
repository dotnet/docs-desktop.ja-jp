---
title: DomainUpDown コントロール
ms.date: 03/30/2017
helpviewer_keywords:
- DomainUpDown control [Windows Forms]
- spin button control [Windows Forms], up-down controls
- up-down controls
- spin button control
- up-down controls [Windows Forms], spin button controls
ms.assetid: fb7cf017-e931-4a95-9d21-8caee4ee122a
ms.openlocfilehash: b538350a84e341d6b2759a7db28f8799f3777a86
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/09/2020
ms.locfileid: "96981524"
---
# <a name="domainupdown-control-windows-forms"></a>DomainUpDown コントロール (Windows フォーム)
Windows フォームコントロールは、 <xref:System.Windows.Forms.DomainUpDown> テキストボックスと、リストを上または下に移動するためのボタンの組み合わせに似ています。 コントロールは、選択肢の一覧からテキスト文字列を表示して設定します。 ユーザーは上下のボタンをクリックして一覧内を移動し、上下の方向キーを押すか、リスト内の項目に一致する文字列を入力することで、文字列を選択できます。 このコントロールの1つの使用方法は、アルファベット順に並べ替えられた名前のリストから項目を選択することです。 (一覧を並べ替えるには、 <xref:System.Windows.Forms.DomainUpDown.Sorted%2A> プロパティをに設定 `true` します)。このコントロールの機能は、リストボックスまたはコンボボックスとよく似ていますが、スペースが非常に小さくなります。  
  
 コントロールの主要なプロパティは、、、 <xref:System.Windows.Forms.DomainUpDown.Items%2A> <xref:System.Windows.Forms.UpDownBase.ReadOnly%2A> および <xref:System.Windows.Forms.DomainUpDown.Wrap%2A> です。 プロパティは、 <xref:System.Windows.Forms.DomainUpDown.Items%2A> テキスト値がコントロールに表示されるオブジェクトのリストを格納します。 <xref:System.Windows.Forms.UpDownBase.ReadOnly%2A>がに設定されている場合 `false` 、コントロールは、ユーザーが入力してリスト内の値と照合するテキストを自動的に完了します。 <xref:System.Windows.Forms.DomainUpDown.Wrap%2A>がに設定されている場合 `true` 、最後の項目を超えてスクロールすると、リストの最初の項目に移動します。逆の場合も同様です。 コントロールの主要なメソッドは <xref:System.Windows.Forms.DomainUpDown.UpButton%2A> と <xref:System.Windows.Forms.DomainUpDown.DownButton%2A> です。  
  
 このコントロールは、テキスト文字列のみを表示します。 数値を表示するコントロールが必要な場合は、コントロールを使用し <xref:System.Windows.Forms.NumericUpDown> ます。 詳細については、「 [NumericUpDown Control](numericupdown-control-windows-forms.md) 」を参照してください。  
  
## <a name="in-this-section"></a>このセクションの内容  
 [DomainUpDown コントロールの概要](domainupdown-control-overview-windows-forms.md)  
 <xref:System.Windows.Forms.DomainUpDown>ユーザーがテキスト文字列の一覧を参照したり選択したりできるようにする、コントロールの一般的な概念について説明します。  
  
 [方法 : Windows フォーム DomainUpDown コントロールにプログラムで項目を追加する](how-to-add-items-to-windows-forms-domainupdown-controls-programmatically.md)  
 コントロールに表示するテキスト文字列を指定する方法について説明し <xref:System.Windows.Forms.DomainUpDown> ます。  
  
 [方法: Windows フォームの DomainUpDown コントロールから項目を削除する](how-to-remove-items-from-windows-forms-domainupdown-controls.md)  
 コード内のコントロールから項目を削除する方法について説明し <xref:System.Windows.Forms.DomainUpDown> ます。  
  
## <a name="reference"></a>リファレンス  
 <xref:System.Windows.Forms.DomainUpDown>  
 このクラスについて説明し、すべてのメンバーへのリンクの一覧を示します。  
  
 <xref:System.Windows.Forms.NumericUpDown>  
 このクラスについて説明し、すべてのメンバーへのリンクを示します。「」をご紹介します。  
  
## <a name="related-sections"></a>関連項目  
 [Windows フォームで使用するコントロール](controls-to-use-on-windows-forms.md)  
 Windows フォーム コントロールの完全な一覧を、使用に関する情報リンクと共に提供します。
