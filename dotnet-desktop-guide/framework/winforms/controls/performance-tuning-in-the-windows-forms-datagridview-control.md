---
title: DataGridView コントロールでのパフォーマンスチューニング
ms.date: 03/30/2017
helpviewer_keywords:
- DataGridView control [Windows Forms], performance tuning
- performance [Windows Forms], DataGridView control
- performance tuning [Windows Forms], data grids
ms.assetid: 6ccbff28-a0ff-41e4-b601-61b31b61851d
ms.openlocfilehash: 77ad86c4cd606bcf074473c97371ec27bcc5605b
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/09/2020
ms.locfileid: "96981975"
---
# <a name="performance-tuning-in-the-windows-forms-datagridview-control"></a>Windows フォーム DataGridView コントロールでのパフォーマンス チューニング
大量のデータを処理する場合、コントロールは、 `DataGridView` 十分に使用しない限り、オーバーヘッドの多いメモリを大量に消費する可能性があります。 メモリが制限されているクライアントでは、メモリコストが高い機能を回避することで、このオーバーヘッドの一部を回避できます。 また、シナリオのメモリ使用量をカスタマイズするために、仮想モードを使用して、データのメンテナンスと取得のタスクの一部またはすべてを自分で管理することもできます。  
  
## <a name="in-this-section"></a>このセクションの内容  
 [Windows フォーム DataGridView コントロールを拡張するための推奨される手順](best-practices-for-scaling-the-windows-forms-datagridview-control.md)  
 `DataGridView`大量のデータを処理するときに、不要なメモリ使用やパフォーマンスの低下を回避する方法でコントロールを使用する方法について説明します。  
  
 [Windows フォーム DataGridView コントロールでの仮想モード](virtual-mode-in-the-windows-forms-datagridview-control.md)  
 仮想モードを使用して標準のデータバインディングメカニズムを補完または置き換える方法について説明します。  
  
 [チュートリアル: Windows フォーム DataGridView コントロールでの仮想モードを実装する](implementing-virtual-mode-wf-datagridview-control.md)  
 いくつかの仮想モードイベントのハンドラーを実装する方法について説明します。 また、行レベルのロールバックを実装し、ユーザーが編集するためにコミットする方法も示します。  
  
 [Windows フォーム DataGridView コントロールでの Just-In-Time データ読み込みによる仮想モードの実装](implementing-virtual-mode-jit-data-loading-in-the-datagrid.md)  
 必要に応じてデータを読み込む方法について説明します。これは、使用可能なクライアントメモリが格納できる量よりも多くのデータを表示する場合に便利です。  
  
## <a name="reference"></a>リファレンス  
 <xref:System.Windows.Forms.DataGridView>  
 <xref:System.Windows.Forms.DataGridView> コントロールのリファレンス ドキュメントを提供します。  
  
 <xref:System.Windows.Forms.DataGridView.VirtualMode%2A>  
 プロパティに関するリファレンスドキュメントを提供 <xref:System.Windows.Forms.DataGridView.VirtualMode%2A> します。  
  
## <a name="see-also"></a>関連項目

- [DataGridView コントロール](datagridview-control-windows-forms.md)
- [Windows フォーム DataGridView コントロールでのデータ表示モード](data-display-modes-in-the-windows-forms-datagridview-control.md)
