---
title: OpenFileDialog コンポーネントの概要
ms.date: 03/30/2017
f1_keywords:
- OpenFileDialog
helpviewer_keywords:
- OpenFileDialog component [Windows Forms], about OpenFileDialog
- Open File dialog box [Windows Forms], displaying in Windows Forms
ms.assetid: cd717300-46b6-4f82-8207-b218fa7fa407
ms.openlocfilehash: c519b373150a49ee41dbb0c503f7d5a4862477d5
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/09/2020
ms.locfileid: "96982912"
---
# <a name="openfiledialog-component-overview-windows-forms"></a>OpenFileDialog コンポーネントの概要 (Windows フォーム)

Windows フォームの <xref:System.Windows.Forms.OpenFileDialog> コンポーネントは、事前構成済みのダイアログ ボックスです。 これは、Windows オペレーティングシステムによって公開されているのと同じ **[ファイルを開く** ] ダイアログボックスです。 これは、<xref:System.Windows.Forms.CommonDialog> クラスを継承しています。

## <a name="use-this-component"></a>このコンポーネントを使用する

このコンポーネントは、独自のダイアログボックスを構成する代わりに、ファイルを選択するための簡単なソリューションとして、Windows ベースのアプリケーション内で使用します。 Windows の標準のダイアログ ボックスを使用して、ユーザーがすぐに慣れる基本的な機能を持つアプリケーションを作成します。 ただし、コンポーネントを使用する場合は、 <xref:System.Windows.Forms.OpenFileDialog> 独自のファイルオープンロジックを作成する必要があることに注意してください。

実行時 <xref:System.Windows.Forms.CommonDialog.ShowDialog%2A> にダイアログを表示するには、メソッドを使用します。 ユーザーがプロパティを使用して開くファイルを複数選択できるようにすることができ <xref:System.Windows.Forms.OpenFileDialog.Multiselect%2A> ます。 また、プロパティを使用して、 <xref:System.Windows.Forms.OpenFileDialog.ShowReadOnly%2A> ダイアログボックスに読み取り専用チェックボックスが表示されるかどうかを判断できます。 <xref:System.Windows.Forms.OpenFileDialog.ReadOnlyChecked%2A>プロパティは、読み取り専用チェックボックスがオンになっているかどうかを示します。 最後に、 <xref:System.Windows.Forms.FileDialog.Filter%2A> プロパティは現在のファイル名のフィルター文字列を設定します。これにより、ダイアログボックスの [ファイルの種類] ボックスに表示される選択肢が決まります。

フォームに追加されると、 <xref:System.Windows.Forms.OpenFileDialog> Visual Studio の Windows フォームデザイナーの下部にあるトレイにコンポーネントが表示されます。

## <a name="see-also"></a>関連項目

- <xref:System.Windows.Forms.OpenFileDialog>
- [OpenFileDialog コンポーネント](openfiledialog-component-windows-forms.md)
