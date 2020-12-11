---
title: FolderBrowserDialog コンポーネントの概要
ms.date: 03/30/2017
f1_keywords:
- FolderBrowserDialog
helpviewer_keywords:
- FolderBrowserDialog component [Windows Forms], about FolderBrowserDialog
- directories [Windows Forms], enabling browsing in applications
- folders [Windows Forms], enabling browsing in applications
ms.assetid: 796b622c-3ba9-4356-93bb-e217fc52f2c7
ms.openlocfilehash: 8b017ba08ae4205e930ac00177c89a89fde17d3b
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/09/2020
ms.locfileid: "96981519"
---
# <a name="folderbrowserdialog-component-overview-windows-forms"></a>FolderBrowserDialog コンポーネントの概要 (Windows フォーム)

Windows フォーム <xref:System.Windows.Forms.FolderBrowserDialog> コンポーネントは、フォルダーの参照および選択に使用されるモーダルダイアログボックスです。 コンポーネント内から新しいフォルダーを作成することもでき <xref:System.Windows.Forms.FolderBrowserDialog> ます。

> [!NOTE]
> フォルダーではなくファイルを選択するには、 [OpenFileDialog](openfiledialog-component-windows-forms.md) コンポーネントを使用します。

コンポーネントは、 <xref:System.Windows.Forms.FolderBrowserDialog> メソッドを使用して実行時に表示され <xref:System.Windows.Forms.CommonDialog.ShowDialog%2A> ます。 プロパティを設定して、 <xref:System.Windows.Forms.FolderBrowserDialog.RootFolder%2A> ダイアログボックスのツリービュー内に表示される最上位のフォルダーとサブフォルダーを決定します。 ダイアログボックスが表示されたら、プロパティを使用して、選択された <xref:System.Windows.Forms.FolderBrowserDialog.SelectedPath%2A> フォルダーのパスを取得できます。

フォームに追加されると、 <xref:System.Windows.Forms.FolderBrowserDialog> Visual Studio の Windows フォームデザイナーの下部にあるトレイにコンポーネントが表示されます。

## <a name="see-also"></a>関連項目

- <xref:System.Windows.Forms.FolderBrowserDialog>
- [方法: Windows フォーム FolderBrowserDialog コンポーネントを使用してフォルダーを選択する](how-to-choose-folders-with-the-windows-forms-folderbrowserdialog-component.md)
- [FolderBrowserDialog コンポーネント](folderbrowserdialog-component-windows-forms.md)
