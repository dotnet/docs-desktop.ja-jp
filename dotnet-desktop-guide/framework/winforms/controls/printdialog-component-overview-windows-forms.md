---
title: PrintDialog コンポーネントの概要
ms.date: 03/30/2017
f1_keywords:
- PrintDialog
helpviewer_keywords:
- Print dialog box [Windows Forms], displaying
- PrintDialog component [Windows Forms], about PrintDialog component
ms.assetid: 8327b8ac-1017-4b5e-a88b-fea9dd56999c
ms.openlocfilehash: 0ed7f7a1f9770f71b75ae744a056b6943335c852
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/09/2020
ms.locfileid: "96980563"
---
# <a name="printdialog-component-overview-windows-forms"></a>PrintDialog コンポーネントの概要 (Windows フォーム)

Windows フォーム [PrintDialog](printdialog-component-windows-forms.md) コンポーネントは、プリンターの選択、印刷するページの選択、および Windows ベースのアプリケーションでのその他の印刷関連設定の決定に使用される、事前に構成されたダイアログボックスです。 独自のダイアログ ボックスを構成する代わりに、プリンターと印刷関連の設定の選択のための簡単なソリューションとして使用します。 ユーザーがドキュメントのさまざまな部分を印刷できるようにするには、[すべて印刷]、選択したページ範囲を印刷する、または選択内容を印刷します。 Windows の標準のダイアログ ボックスを使用して、ユーザーがすぐに慣れる基本的な機能を持つアプリケーションを作成します。 <xref:System.Windows.Forms.PrintDialog>コンポーネントはクラスから継承され <xref:System.Windows.Forms.CommonDialog> ます。

## <a name="working-with-the-component"></a>コンポーネントの操作

実行時 <xref:System.Windows.Forms.CommonDialog.ShowDialog%2A> にダイアログボックスを表示するには、メソッドを使用します。 このコンポーネントには、1つの印刷ジョブ ( <xref:System.Drawing.Printing.PrintDocument> クラス) または個々のプリンターの設定 (クラス) に関連するプロパティがあり <xref:System.Drawing.Printing.PrinterSettings> ます。 これらはいずれも、複数のプリンターで共有できます。

フォームに追加されると、 <xref:System.Windows.Forms.PrintDialog> Visual Studio の Windows フォームデザイナーの下部にあるトレイにコンポーネントが表示されます。

## <a name="see-also"></a>関連項目

- <xref:System.Windows.Forms.PrintDialog>
- [PrintDialog コンポーネント](printdialog-component-windows-forms.md)
