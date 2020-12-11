---
title: DataGridView コントロールの既定の機能
ms.date: 03/30/2017
helpviewer_keywords:
- data grids [Windows Forms], default functionality in DataGridView control
- DataGridView control [Windows Forms], default functionality
ms.assetid: 4405f697-cad1-4839-9bcd-8ddb09d9f00e
ms.openlocfilehash: b695883ac7ec3fb0c459adb66214b0eceab3a128
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/09/2020
ms.locfileid: "96974204"
---
# <a name="default-functionality-in-the-windows-forms-datagridview-control"></a>Windows フォーム DataGridView コントロールの既定の機能
Windows フォームコントロールでは、 <xref:System.Windows.Forms.DataGridView> ユーザーは大量の既定機能を使用できます。  
  
## <a name="default-functionality"></a>既定の機能  
 既定では、 <xref:System.Windows.Forms.DataGridView> コントロールは次のようになります。  
  
- テーブルが垂直方向にスクロールしても表示されたままの列ヘッダーと行ヘッダーを自動的に表示します。  
  
- には、現在の行の選択インジケーターを含む行ヘッダーがあります。  
  
- 最初のセルに選択範囲の四角形があります。  
  
- ユーザーが列の区切り線をダブルクリックすると、自動的にサイズを変更できる列があります。  
  
- は、 <xref:System.Windows.Forms.Application.EnableVisualStyles%2A> アプリケーションのメソッドからメソッドが呼び出されたときに、WINDOWS XP と Windows Server 2003 ファミリの visual スタイルを自動的にサポートし `Main` ます。  
  
 また、既定では、コントロールの内容を <xref:System.Windows.Forms.DataGridView> 編集できます。  
  
- ユーザーがセル内で F2 キーをダブルクリックまたは押すと、コントロールはセルを自動的に編集モードにし、ユーザーの入力に応じてセルの内容を更新します。  
  
- ユーザーがグリッドの最後までスクロールすると、新しいレコードを追加するための行が存在することがわかります。 ユーザーがこの行をクリックすると、コントロールに新しい行が追加され、 <xref:System.Windows.Forms.DataGridView> 既定値が使用されます。 ユーザーが ESC キーを押すと、この新しい行は消えます。  
  
- ユーザーが行ヘッダーをクリックすると、行全体が選択されます。  
  
 コントロールをデータソースにバインドするときに、 <xref:System.Windows.Forms.DataGridView> そのプロパティを設定して、 <xref:System.Windows.Forms.DataGridView.DataSource%2A> コントロールを次のようにします。  
  
- では、データソースの列の名前が列ヘッダーのテキストとして自動的に使用されます。  
  
- には、データソースの内容が設定されます。 <xref:System.Windows.Forms.DataGridView> 列は、データソースの各列に対して自動的に作成されます。  
  
- テーブル内の表示されている各行に対して行を作成します。  
  
- は、ユーザーが列ヘッダーをクリックしたときに、基になるデータに基づいて行を自動的に並べ替えます。  
  
## <a name="see-also"></a>関連項目

- <xref:System.Windows.Forms.DataGridView>
- [DataGridView コントロール](datagridview-control-windows-forms.md)
