---
title: ComboBox、ListBox、または CheckedListBox コントロールのルックアップテーブルを作成する
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- CheckedListBox control [Windows Forms], creating lookup tables
- lookup tables
- list boxes [Windows Forms], lookup tables
- ListBox control [Windows Forms], lookup tables
- ComboBox control [Windows Forms], lookup table
- lookup tables [Windows Forms], creating for controls
- combo boxes [Windows Forms], lookup tables
- ListBox control [Windows Forms], creating lookup tables
ms.assetid: 4ce35f12-1f4e-4317-92d1-af8686a8cfaa
ms.openlocfilehash: 57dc95fc16d77ee1492f53bf57eac001a343ca8f
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/09/2020
ms.locfileid: "96974264"
---
# <a name="how-to-create-a-lookup-table-for-a-windows-forms-combobox-listbox-or-checkedlistbox-control"></a>方法: Windows フォーム ComboBox、ListBox、または CheckedListBox コントロールのルックアップ テーブルを作成する

Windows フォーム上ではわかりやすい形式でデータを表示し、一方プログラムにはより意味のある形式でデータを格納すると便利な場合があります。 たとえば、食品の注文書の場合、リスト ボックスにメニュー項目が名前で表示されます。 一方、注文を記録するデータ テーブルには、食品を表す一意の ID 番号が含まれることになります。 次の表は、食品の注文書データを格納および表示する方法の例を示しています。  
  
### <a name="orderdetailstable"></a>OrderDetailsTable  
  
|OrderID|ItemID|Quantity|  
|-------------|------------|--------------|  
|4085|12|1|  
|4086|13|3|  
  
### <a name="itemtable"></a>ItemTable  
  
|ID|名前|  
|--------|----------|  
|12|ポテト|  
|13|チキン|  
  
 このシナリオでは、1つのテーブル **OrderDetailsTable** に、表示と保存に関係する実際の情報が格納されます。 しかし、スペースを節約するために、これはかなり謎めいた方法で実行されます。 もう1つの **Itemtable** というテーブルには、どの ID 番号がどの食品名に相当するかに関する外観関連の情報だけが含まれており、実際の食品注文については何もありません。  
  
 **Itemtable** は <xref:System.Windows.Forms.ComboBox> 、3つのプロパティを介して、、またはコントロールに接続され <xref:System.Windows.Forms.ListBox> <xref:System.Windows.Forms.CheckedListBox> ます。 プロパティには `DataSource` 、このテーブルの名前が格納されます。 プロパティには、 `DisplayMember` コントロールに表示する、そのテーブルのデータ列が含まれます (食品名)。 プロパティには、 `ValueMember` 格納されている情報 (ID 番号) を含むテーブルのデータ列が含まれます。  
  
 **OrderDetailsTable** は、プロパティを通じてアクセスされるバインドコレクションによってコントロールに接続され <xref:System.Windows.Forms.Control.DataBindings%2A> ます。 バインドオブジェクトをコレクションに追加する場合は、データソース ( **OrderDetailsTable**) の特定のデータメンバー (ID 番号の列) にコントロールプロパティを接続します。 コントロールで選択がなされる際、このテーブルはフォーム入力が保存される場所です。  
  
### <a name="to-create-a-lookup-table"></a>ルックアップ テーブルを作成するには  
  
1. フォームに <xref:System.Windows.Forms.ComboBox>、<xref:System.Windows.Forms.ListBox>、または <xref:System.Windows.Forms.CheckedListBox> コントロールを追加します。  
  
2. データ ソースに接続します。  
  
3. 2 つのテーブル間のデータ リレーションシップを確立します。 「 [DataRelation オブジェクトの概要」を](/previous-versions/visualstudio/visual-studio-2013/0k21zcyx(v=vs.120))参照してください。  
  
4. 次のプロパティを設定します。 これらはコードまたはデザイナーで設定できます。  
  
    |プロパティ|設定|  
    |--------------|-------------|  
    |<xref:System.Windows.Forms.ListControl.DataSource%2A>|どの ID 番号がどの項目に相当するかについての情報を含むテーブル。 前のシナリオでは、これは `ItemTable` です。|  
    |<xref:System.Windows.Forms.ListControl.DisplayMember%2A>|コントロールに表示するデータ ソース テーブルの列。 前のシナリオでは、これはです `"Name"` (コードで設定するには、引用符を使用します)。|  
    |<xref:System.Windows.Forms.ListControl.ValueMember%2A>|格納された情報を含むデータ ソース テーブルの列。 前のシナリオでは、これはです `"ID"` (コードで設定するには、引用符を使用します)。|  
  
5. プロシージャで <xref:System.Windows.Forms.ControlBindingsCollection> クラスの <xref:System.Windows.Forms.ControlBindingsCollection.Add%2A> メソッドを呼び出して、フォーム入力を記録するテーブルにコントロールの <xref:System.Windows.Forms.ListControl.SelectedValue%2A> プロパティをバインドします。 また <xref:System.Windows.Forms.Control.DataBindings%2A> 、[ **プロパティ** ] ウィンドウでコントロールのプロパティにアクセスすることにより、コードではなくデザイナーでこの操作を行うこともできます。 前のシナリオでは、これはで `OrderDetailsTable` あり、列は `"ItemID"` です。  
  
    ```vb  
    ListBox1.DataBindings.Add("SelectedValue", OrderDetailsTable, "ItemID")  
    ```  
  
    ```csharp  
    listBox1.DataBindings.Add("SelectedValue", OrderDetailsTable, "ItemID");  
    ```  
  
## <a name="see-also"></a>関連項目

- [データ連結と Windows フォーム](../data-binding-and-windows-forms.md)
- [ListBox コントロールの概要](listbox-control-overview-windows-forms.md)
- [ComboBox コントロールの概要](combobox-control-overview-windows-forms.md)
- [CheckedListBox コントロールの概要](checkedlistbox-control-overview-windows-forms.md)
- [オプションのリストを表示するための Windows フォーム コントロール](windows-forms-controls-used-to-list-options.md)
