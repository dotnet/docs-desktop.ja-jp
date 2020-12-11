---
title: DataGridView コントロールでのデータの書式設定
ms.date: 03/30/2017
helpviewer_keywords:
- DataGridView control [Windows Forms], formatting data
- data [Windows Forms], formatting in grids
- data grids [Windows Forms], formatting data
ms.assetid: 07bf558d-3748-42ba-8ba0-37fdef924081
ms.openlocfilehash: 3a09acf72841a2135ed2d155f3715ccc30860856
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/09/2020
ms.locfileid: "96974226"
---
# <a name="data-formatting-in-the-windows-forms-datagridview-control"></a>Windows フォーム DataGridView コントロールでのデータの書式設定

コントロールは、 <xref:System.Windows.Forms.DataGridView> セル値と親列に表示されるデータ型の間の自動変換を提供します。 たとえば、テキストボックスの列では、日付、時刻、数値、列挙値の文字列形式を表示し、ユーザーが入力した文字列値をデータストアで必要な型に変換します。  
  
## <a name="formatting-with-the-datagridviewcellstyle-class"></a>DataGridViewCellStyle クラスを使用した書式設定  

 コントロールは、 <xref:System.Windows.Forms.DataGridView> クラスを使用したセル値の基本的なデータ書式設定を提供し <xref:System.Windows.Forms.DataGridViewCellStyle> ます。 プロパティを使用し <xref:System.Windows.Forms.DataGridViewCellStyle.Format%2A> て、現在の既定のカルチャの日付、時刻、数値、および列挙値の書式を設定するには、「 [型の書式設定](/dotnet/standard/base-types/formatting-types)」で説明されている書式指定子を使用します。 また、プロパティを使用して、特定のカルチャに対してこれらの値を書式設定することもでき <xref:System.Windows.Forms.DataGridViewCellStyle.FormatProvider%2A> ます。 指定された形式は、データの表示と、ユーザーが指定した形式で入力したデータの解析の両方に使用されます。  
  
 クラスには、 <xref:System.Windows.Forms.DataGridViewCellStyle> 折り返し、テキストの配置、および null データベース値のカスタム表示に関する追加の書式設定プロパティが用意されています。 詳細については、「[方法 : Windows フォーム DataGridView コントロールのデータの書式を設定する](how-to-format-data-in-the-windows-forms-datagridview-control.md)」を参照してください。  
  
## <a name="formatting-with-the-cellformatting-event"></a>CellFormatting 設定イベントを使用した書式設定  

 基本的な書式設定がニーズに合わない場合は、イベントのハンドラーにカスタムデータ書式を提供でき <xref:System.Windows.Forms.DataGridView.CellFormatting?displayProperty=nameWithType> ます。 <xref:System.Windows.Forms.DataGridViewCellFormattingEventArgs>ハンドラーに渡されるには、 <xref:System.Windows.Forms.ConvertEventArgs.Value%2A> 最初にセル値を格納するプロパティがあります。 通常、この値は自動的に表示の種類に変換されます。 値を自分で変換するには、 <xref:System.Windows.Forms.ConvertEventArgs.Value%2A> プロパティを表示型の値に設定します。  
  
> [!NOTE]
> 書式指定文字列がセルに対して有効になっている場合、 <xref:System.Windows.Forms.ConvertEventArgs.Value%2A> プロパティをに設定しない限り、プロパティ値の変更はオーバーライドされ <xref:System.Windows.Forms.DataGridViewCellFormattingEventArgs.FormattingApplied%2A> `true` ます。  
  
 イベントは、 <xref:System.Windows.Forms.DataGridView.CellFormatting> <xref:System.Windows.Forms.DataGridViewCellStyle> 個々のセルのプロパティを値に基づいて設定する場合にも便利です。 詳細については、「 [方法: Windows フォーム DataGridView コントロールでデータの書式をカスタマイズする](how-to-customize-data-formatting-in-the-windows-forms-datagridview-control.md)」を参照してください。  
  
 ユーザー指定の値の既定の解析がニーズに合わない場合は、コントロールのイベントを処理して <xref:System.Windows.Forms.DataGridView.CellParsing> <xref:System.Windows.Forms.DataGridView> カスタム解析を提供できます。  
  
## <a name="see-also"></a>関連項目

- <xref:System.Windows.Forms.DataGridView>
- <xref:System.Windows.Forms.DataGridViewCellStyle>
- [Windows フォーム DataGridView コントロールでのデータの表示](displaying-data-in-the-windows-forms-datagridview-control.md)
- [Windows フォーム DataGridView コントロールでのセルのスタイル](cell-styles-in-the-windows-forms-datagridview-control.md)
- [方法: Windows フォーム DataGridView コントロールのデータの書式を設定する](how-to-format-data-in-the-windows-forms-datagridview-control.md)
- [方法: Windows フォーム DataGridView コントロールのデータの書式設定をカスタマイズする](how-to-customize-data-formatting-in-the-windows-forms-datagridview-control.md)
