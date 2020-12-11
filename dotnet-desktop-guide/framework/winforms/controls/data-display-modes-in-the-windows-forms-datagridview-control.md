---
title: DataGridView コントロールのデータ表示モード
ms.date: 03/30/2017
helpviewer_keywords:
- data [Windows Forms], display modes
- data grids [Windows Forms], display modes
- DataGridView control [Windows Forms], display modes
ms.assetid: 9755a030-3f3f-4705-a661-ba5a48a81875
ms.openlocfilehash: ad6be647e3a36904b055fd6771f539df28938fab
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/09/2020
ms.locfileid: "96974234"
---
# <a name="data-display-modes-in-the-windows-forms-datagridview-control"></a>Windows フォーム DataGridView コントロールでのデータ表示モード
コントロールは、 <xref:System.Windows.Forms.DataGridView> バインド、バインド解除、および仮想の3つの異なるモードでデータを表示できます。 要件に基づいて最適なモードを選択します。  
  
## <a name="unbound"></a>非バインド  
 非バインドモードは、プログラムで管理する比較的少量のデータを表示する場合に適しています。 <xref:System.Windows.Forms.DataGridView>バインドモードとしてデータソースに直接コントロールをアタッチすることはありません。 代わりに、メソッドを使用して、通常はコントロールにデータを設定する必要があり <xref:System.Windows.Forms.DataGridViewRowCollection.Add%2A?displayProperty=nameWithType> ます。  
  
 非バインドモードは、静的な読み取り専用のデータの場合や、外部データストアと対話する独自のコードを提供する場合に特に便利です。 ただし、ユーザーが外部データソースと対話できるようにする場合は、通常、バインドモードを使用します。  
  
 読み取り専用のバインドされていないを使用する例につい <xref:System.Windows.Forms.DataGridView> ては、「方法: バインドされていない [Windows フォーム DataGridView コントロールを作成](how-to-create-an-unbound-windows-forms-datagridview-control.md)する」を参照してください。  
  
## <a name="bound"></a>Bound  
 バインドモードは、データストアとの自動操作を使用したデータの管理に適しています。 <xref:System.Windows.Forms.DataGridView>コントロールをデータソースに直接アタッチするには、プロパティを設定し <xref:System.Windows.Forms.DataGridView.DataSource%2A> ます。 コントロールがデータにバインドされると、データ行がプッシュされ、その部分を明示的に管理する必要がなくプルされます。 <xref:System.Windows.Forms.DataGridView.AutoGenerateColumns%2A>プロパティがの場合 `true` 、データソース内の各列によって、対応する列がコントロールに作成されます。 独自の列を作成する場合は、このプロパティをに設定 `false` し、プロパティを使用して、 <xref:System.Windows.Forms.DataGridViewColumn.DataPropertyName%2A> 構成時に各列をバインドすることができます。 これは、既定で生成される型以外の列の型を使用する場合に便利です。 詳細については、「 [Windows フォーム DataGridView コントロールの列の型](column-types-in-the-windows-forms-datagridview-control.md)」を参照してください。  
  
 バインドされたコントロールを使用する例につい <xref:System.Windows.Forms.DataGridView> ては、「 [チュートリアル: Windows フォーム DataGridView コントロールでのデータの検証](walkthrough-validating-data-in-the-windows-forms-datagridview-control.md)」を参照してください。  
  
 バインドモードのコントロールに非バインド列を追加することもでき <xref:System.Windows.Forms.DataGridView> ます。 これは、ユーザーが特定の行に対して操作を実行できるようにするボタンまたはリンクの列を表示する場合に便利です。 また、バインドされた列から計算された値を含む列を表示する場合にも便利です。 イベントのハンドラーで、計算列のセル値を設定でき <xref:System.Windows.Forms.DataGridView.CellFormatting> ます。 ただし、データソースとしてまたはを使用している場合は、 <xref:System.Data.DataSet> <xref:System.Data.DataTable> 代わりにプロパティを使用して計算列を作成することをお勧めし <xref:System.Data.DataColumn.Expression%2A?displayProperty=nameWithType> ます。 この場合、コントロールは <xref:System.Windows.Forms.DataGridView> 計算列を、データソース内の他の列と同様に扱います。  
  
 バインドモードでの非バインド列による並べ替えはサポートされていません。 バインドモードでユーザー編集可能な値を含む非バインド列を作成する場合は、バインドされた列によってコントロールが並べ替えられるときに、仮想モードを実装してこれらの値を維持する必要があります。  
  
## <a name="virtual"></a>仮想  
 仮想モードを使用すると、独自のデータ管理操作を実装できます。 バインドされた列によってコントロールが並べ替えられている場合は、バインドモードのバインドされていない列の値を維持するために必要です。 ただし、仮想モードの主な用途は、大量のデータを操作するときのパフォーマンスを最適化することです。  
  
 <xref:System.Windows.Forms.DataGridView>管理するキャッシュにコントロールをアタッチすると、データ行をプッシュおよびプルするタイミングがコードによって制御されます。 メモリフットプリントを小さくするために、キャッシュのサイズは現在表示されている行の数と同じにする必要があります。 ユーザーが新しい行をスクロールして表示すると、コードはキャッシュから新しいデータを要求し、必要に応じて、メモリから古いデータをフラッシュします。  
  
 仮想モードを実装する場合は、データモデルで新しい行が必要になったタイミングと、新しい行の追加をロールバックするタイミングを追跡する必要があります。 この機能の正確な実装は、データモデルの実装とデータモデルのトランザクションセマンティクスによって異なります。コミットスコープがセルレベルまたは行レベルのどちらであるかを示します。  
  
 仮想モードの詳細については、「 [Windows フォーム DataGridView コントロールでの仮想モード](virtual-mode-in-the-windows-forms-datagridview-control.md)」を参照してください。 仮想モードイベントの使用方法を示す例については、「 [チュートリアル: Windows フォーム DataGridView コントロールでの仮想モードの実装](implementing-virtual-mode-wf-datagridview-control.md)」を参照してください。  
  
## <a name="see-also"></a>関連項目

- <xref:System.Windows.Forms.DataGridView>
- <xref:System.Windows.Forms.DataGridView.DataSource%2A?displayProperty=nameWithType>
- <xref:System.Windows.Forms.DataGridView.VirtualMode%2A?displayProperty=nameWithType>
- <xref:System.Windows.Forms.BindingSource>
- <xref:System.Windows.Forms.DataGridViewColumn.DataPropertyName%2A?displayProperty=nameWithType>
- [Windows フォーム DataGridView コントロールでのデータの表示](displaying-data-in-the-windows-forms-datagridview-control.md)
- [Windows フォーム DataGridView コントロールの列型](column-types-in-the-windows-forms-datagridview-control.md)
- [チュートリアル: バインドされていない Windows フォーム DataGridView コントロールを作成する](walkthrough-creating-an-unbound-windows-forms-datagridview-control.md)
- [方法: データを Windows フォーム DataGridView コントロールにバインドする](how-to-bind-data-to-the-windows-forms-datagridview-control.md)
- [Windows フォーム DataGridView コントロールでの仮想モード](virtual-mode-in-the-windows-forms-datagridview-control.md)
- [チュートリアル: Windows フォーム DataGridView コントロールでの仮想モードを実装する](implementing-virtual-mode-wf-datagridview-control.md)
