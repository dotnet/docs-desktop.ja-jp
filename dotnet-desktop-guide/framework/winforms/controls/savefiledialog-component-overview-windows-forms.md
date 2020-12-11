---
title: SaveFileDialog コンポーネントの概要
ms.date: 03/30/2017
f1_keywords:
- SaveFileDialog
helpviewer_keywords:
- Save File dialog box [Windows Forms], displaying
- SaveFileDialog component [Windows Forms], about SaveFileDialog
ms.assetid: be7a625f-46fd-4d06-9985-b613dcbf9bd2
ms.openlocfilehash: 7609c29b7e932ecee7dc8a289617094bd8d480e2
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/09/2020
ms.locfileid: "96974386"
---
# <a name="savefiledialog-component-overview-windows-forms"></a>SaveFileDialog コンポーネントの概要 (Windows フォーム)

Windows フォームの <xref:System.Windows.Forms.SaveFileDialog> コンポーネントは、事前構成済みのダイアログ ボックスです。 これは、Windows によって使用される標準の [ **ファイルの保存** ] ダイアログボックスと同じです。 これは、<xref:System.Windows.Forms.CommonDialog> クラスを継承しています。

## <a name="working-with-the-savefiledialog-component"></a>SaveFileDialog コンポーネントの操作

独自のダイアログボックスを構成する代わりに、ユーザーがファイルを保存できるようにするための簡単なソリューションとして使用します。 標準の Windows ダイアログボックスに依存しているため、ユーザーにとって作成するアプリケーションの基本的な機能はすぐにわかります。 ただし、コンポーネントを使用する場合は、 <xref:System.Windows.Forms.SaveFileDialog> 独自のファイル保存ロジックを作成する必要があることに注意してください。

メソッドを使用し <xref:System.Windows.Forms.CommonDialog.ShowDialog%2A> て、実行時にダイアログボックスを表示できます。 メソッドを使用して、読み取り/書き込みモードでファイルを開くことができ <xref:System.Windows.Forms.SaveFileDialog.OpenFile%2A> ます。

フォームに追加されると、 <xref:System.Windows.Forms.SaveFileDialog> Visual Studio の Windows フォームデザイナーの下部にあるトレイにコンポーネントが表示されます。

## <a name="see-also"></a>関連項目

- <xref:System.Windows.Forms.SaveFileDialog>
- [SaveFileDialog コンポーネント](savefiledialog-component-windows-forms.md)
