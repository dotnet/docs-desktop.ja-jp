---
title: DataGridView コントロールでの Just-in-time データ読み込みによる仮想モードの実装
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- examples [Windows Forms], just-in-time data loading
- data [Windows Forms], managing large data sets
- DataGridView control [Windows Forms], virtual mode
- just-in-time data loading
- DataGridView control [Windows Forms], large data sets
- virtual mode [Windows Forms], just-in-time data loading
ms.assetid: 33825f92-7a22-40ee-86d9-9a2ed1ead7b7
ms.openlocfilehash: 7b7990ceacba9e5f479149c934db1914e8dd0bef
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/09/2020
ms.locfileid: "96984027"
---
# <a name="how-to-implement-virtual-mode-with-just-in-time-data-loading-in-the-windows-forms-datagridview-control"></a>方法: Windows フォーム DataGridView コントロールで Just-In-Time データ読み込みを使用して仮想モードを実装する

次のコード例では、必要がある場合にのみ、サーバーからデータを読み込むデータ キャッシュを持つ <xref:System.Windows.Forms.DataGridView> コントロールで仮想モードを使用する方法を示しています。 この例の詳細につい [ては、「Windows フォーム DataGridView コントロールでの Just-in-time データ読み込みによる仮想モードの実装](implementing-virtual-mode-jit-data-loading-in-the-datagrid.md)」を参照してください。  
  
## <a name="example"></a>例  

 [!code-csharp[System.Windows.Forms.DataGridView.Virtual_lazyloading#000](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.Virtual_lazyloading/CS/lazyloading.cs#000)]
 [!code-vb[System.Windows.Forms.DataGridView.Virtual_lazyloading#000](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.Virtual_lazyloading/VB/lazyloading.vb#000)]  
  
## <a name="compiling-the-code"></a>コードのコンパイル  

 この例で必要な要素は次のとおりです。  
  
- System、System.Data、System.Xml、および System.Windows.Forms の各アセンブリへの参照。  
  
- Northwind SQL Server サンプル データベースがインストールされているサーバーへのアクセス。  
  
## <a name="net-framework-security"></a>.NET Framework セキュリティ  

 接続文字列内に機密情報 (パスワードなど) を格納すると、アプリケーションのセキュリティに影響を及ぼすことがあります。 データベースへのアクセスを制御する方法としては、Windows 認証 (統合セキュリティとも呼ばれます) を使用する方が安全です。 詳細については、「[接続情報の保護](/dotnet/framework/data/adonet/protecting-connection-information)」を参照してください。  
  
## <a name="see-also"></a>関連項目

- <xref:System.Windows.Forms.DataGridView>
- <xref:System.Windows.Forms.DataGridView.VirtualMode%2A>
- <xref:System.Windows.Forms.DataGridView.CellValueNeeded>
- [Windows フォーム DataGridView コントロールでの Just-In-Time データ読み込みによる仮想モードの実装](implementing-virtual-mode-jit-data-loading-in-the-datagrid.md)
- [Windows フォーム DataGridView コントロールでのパフォーマンス チューニング](performance-tuning-in-the-windows-forms-datagridview-control.md)
- [Windows フォーム DataGridView コントロールでの仮想モード](virtual-mode-in-the-windows-forms-datagridview-control.md)
