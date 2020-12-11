---
title: DataGridView コントロールでのデータの並べ替え
ms.date: 02/13/2018
helpviewer_keywords:
- data [Windows Forms], sorting in grids
- data grids [Windows Forms], sorting data
- DataGridView control [Windows Forms], sorting data
ms.assetid: c1d4f24c-d961-4181-809d-5a5caa6122e4
ms.openlocfilehash: 1fcd5a5f5c6d690c573c4c2c5fa7c32aa0292441
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/09/2020
ms.locfileid: "96983555"
---
# <a name="sorting-data-in-the-windows-forms-datagridview-control"></a>Windows フォーム DataGridView コントロールでのデータの並べ替え

既定では、ユーザーは <xref:System.Windows.Forms.DataGridView> テキストボックスの列のヘッダーをクリックして、コントロール内のデータを並べ替えることができます (または、テキストボックスのセルが .NET Framework 4.7.2 以降のバージョンにフォーカスされている場合は、F3 キーを押します)。 特定の列のプロパティを変更することで、 <xref:System.Windows.Forms.DataGridViewColumn.SortMode> ユーザーが他の列の種類を基準に並べ替えられるようにすることができます。 また、任意の列または複数の列を使用して、データをプログラムによって並べ替えることもできます。

## <a name="in-this-section"></a>このセクションの内容

[Windows フォーム DataGridView コントロール内の列の並べ替えモード](column-sort-modes-in-the-windows-forms-datagridview-control.md)  
コントロール内のデータを並べ替えるためのオプションについて説明します。

[方法: Windows フォーム DataGridView コントロール内の列の並べ替えモードを設定する](set-the-sort-modes-for-columns-wf-datagridview-control.md)  
既定では並べ替えられていない列でユーザーが並べ替えることができるようにする方法について説明します。

[方法 : Windows フォーム DataGridView コントロールの並べ替え機能をカスタマイズする](how-to-customize-sorting-in-the-windows-forms-datagridview-control.md)  
プログラムによってデータを並べ替える方法と、イベントを使用するか、インターフェイスを実装することによって並べ替えをカスタマイズする方法について説明し <xref:System.Windows.Forms.DataGridView.SortCompare?displayProperty=nameWithType> <xref:System.Collections.IComparer> ます。

## <a name="reference"></a>リファレンス

<xref:System.Windows.Forms.DataGridView>  
<xref:System.Windows.Forms.DataGridView> コントロールのリファレンス ドキュメントを提供します。  

<xref:System.Windows.Forms.DataGridView.Sort%2A?displayProperty=nameWithType>  
メソッドのリファレンスドキュメントを提供 <xref:System.Windows.Forms.DataGridView.Sort%2A> します。

<xref:System.Windows.Forms.DataGridViewColumn.SortMode%2A?displayProperty=nameWithType>  
プロパティに関するリファレンスドキュメントを提供 <xref:System.Windows.Forms.DataGridViewColumn.SortMode%2A> します。

<xref:System.Windows.Forms.DataGridViewColumnSortMode>  
列挙体のリファレンスドキュメントを提供 <xref:System.Windows.Forms.DataGridViewColumnSortMode> します。

## <a name="see-also"></a>関連項目

- [DataGridView コントロール](datagridview-control-windows-forms.md)
- [Windows フォーム DataGridView コントロールの列型](column-types-in-the-windows-forms-datagridview-control.md)
