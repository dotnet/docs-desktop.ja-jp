---
title: PageSetupDialog コンポーネントの概要
ms.date: 03/30/2017
f1_keywords:
- PageSetupDialog
helpviewer_keywords:
- Page Setup dialog box [Windows Forms], displaying
- PageSetupDialog component
ms.assetid: 791caacb-a5ca-4fca-bad9-1a5721ad697c
ms.openlocfilehash: a891cb8cc77007d7591d41461c94f61c077eb300
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/09/2020
ms.locfileid: "96982888"
---
# <a name="pagesetupdialog-component-overview-windows-forms"></a>PageSetupDialog コンポーネントの概要 (Windows フォーム)

Windows フォーム <xref:System.Windows.Forms.PageSetupDialog> コンポーネントは、Windows ベースのアプリケーションで印刷するページの詳細を設定するために使用する、事前に構成されたダイアログボックスです。 ユーザーが独自のダイアログボックスを構成する代わりにページ設定を設定するための簡単なソリューションとして、Windows ベースのアプリケーション内で使用します。 ユーザーが罫線と余白の調整、ヘッダーとフッター、縦または横の向きを設定できるようにすることができます。 Windows の標準のダイアログ ボックスを使用して、ユーザーがすぐに慣れる基本的な機能を持つアプリケーションを作成します。

## <a name="key-properties-and-methods"></a>キーのプロパティとメソッド

実行時 <xref:System.Windows.Forms.CommonDialog.ShowDialog%2A> にダイアログを表示するには、メソッドを使用します。 このコンポーネントには、1つのページ ( <xref:System.Drawing.Printing.PrintDocument> クラス) または任意のドキュメント (クラス) に関連する設定可能なプロパティがあり <xref:System.Drawing.Printing.PageSettings> ます。 また、コンポーネントを使用して、 <xref:System.Windows.Forms.PageSetupDialog> クラスに格納されている特定のプリンター設定を決定することもでき <xref:System.Drawing.Printing.PrinterSettings> ます。

フォームに追加されると、 <xref:System.Windows.Forms.PageSetupDialog> Visual Studio の Windows フォームデザイナーの下部にあるトレイにコンポーネントが表示されます。

## <a name="see-also"></a>関連項目

- <xref:System.Windows.Forms.PageSetupDialog>
- [PageSetupDialog コンポーネント](pagesetupdialog-component-windows-forms.md)
