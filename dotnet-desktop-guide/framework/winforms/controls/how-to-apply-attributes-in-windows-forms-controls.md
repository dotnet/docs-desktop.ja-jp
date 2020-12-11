---
title: コントロールに属性を適用する
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- controls [Windows Forms], applying attributes
- attributes [Windows Forms], applying
- Windows Forms controls, applying attributes
ms.assetid: af0a3f7f-155b-4ba1-83c4-9cf721331a06
ms.openlocfilehash: f12b430d787b4b974e12902b2c17d3a35a09e468
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/09/2020
ms.locfileid: "96980971"
---
# <a name="how-to-apply-attributes-in-windows-forms-controls"></a>方法: Windows フォーム コントロールに属性を適用する

デザイン環境と正しく対話し、実行時に正常に実行されるコンポーネントとコントロールを開発するには、クラスおよびメンバーに属性を正しく適用する必要があります。  
  
## <a name="example"></a>例  

 次のコード例は、カスタムコントロールでいくつかの属性を使用する方法を示しています。 このコントロールは、単純なログ記録機能を示しています。 コントロールがデータソースにバインドされると、コントロールにデータソースから送信された値が表示され <xref:System.Windows.Forms.DataGridView> ます。 値がプロパティで指定された値を超えると `Threshold` 、 `ThresholdExceeded` イベントが発生します。  
  
 は、 `AttributesDemoControl` クラスを使用して値をログに記録し `LogEntry` ます。 クラスはテンプレートクラスであり、これは `LogEntry` ログに記録される型でパラメーター化されることを意味します。 たとえば、 `AttributesDemoControl` が型の値をログに記録している場合、各インスタンスは次のように宣言され、 `float` `LogEntry` 使用されます。  
  
 [!code-csharp[System.ComponentModel.AttributesDemoControl#110](~/samples/snippets/csharp/VS_Snippets_Winforms/System.ComponentModel.AttributesDemoControl/CS/form1.cs#110)]
 [!code-vb[System.ComponentModel.AttributesDemoControl#110](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.ComponentModel.AttributesDemoControl/VB/form1.vb#110)]  
  
> [!NOTE]
> `LogEntry`は任意の型によってパラメーター化されるため、パラメーターの型を操作するにはリフレクションを使用する必要があります。 しきい値機能を機能させるには、パラメーターの型 `T` がインターフェイスを実装する必要があり <xref:System.IComparable> ます。  
  
 をホストするフォームは、 `AttributesDemoControl` パフォーマンスカウンターを定期的に照会します。 各値は、適切な型のにパッケージ化され、 `LogEntry` フォームのに追加され <xref:System.Windows.Forms.BindingSource> ます。 は、 `AttributesDemoControl` データバインディングを通じて値を受け取り、コントロールの値を表示し <xref:System.Windows.Forms.DataGridView> ます。  
  
 [!code-csharp[System.ComponentModel.AttributesDemoControl#1](~/samples/snippets/csharp/VS_Snippets_Winforms/System.ComponentModel.AttributesDemoControl/CS/attributesdemocontrol.cs#1)]
 [!code-vb[System.ComponentModel.AttributesDemoControl#1](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.ComponentModel.AttributesDemoControl/VB/attributesdemocontrol.vb#1)]  
  
 [!code-csharp[System.ComponentModel.AttributesDemoControl#100](~/samples/snippets/csharp/VS_Snippets_Winforms/System.ComponentModel.AttributesDemoControl/CS/form1.cs#100)]
 [!code-vb[System.ComponentModel.AttributesDemoControl#100](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.ComponentModel.AttributesDemoControl/VB/form1.vb#100)]  
  
 最初のコード例は、の `AttributesDemoControl` 実装です。 2番目のコード例は、を使用するフォームを示して `AttributesDemoControl` います。  
  
## <a name="class-level-attributes"></a>クラスレベルの属性  

 一部の属性はクラスレベルで適用されます。 次のコード例は、Windows フォームコントロールに一般的に適用される属性を示しています。  
  
 [!code-csharp[System.ComponentModel.AttributesDemoControl#20](~/samples/snippets/csharp/VS_Snippets_Winforms/System.ComponentModel.AttributesDemoControl/CS/attributesdemocontrol.cs#20)]
 [!code-vb[System.ComponentModel.AttributesDemoControl#20](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.ComponentModel.AttributesDemoControl/VB/attributesdemocontrol.vb#20)]  
  
### <a name="typeconverter-attribute"></a>TypeConverter 属性  

 <xref:System.ComponentModel.TypeConverterAttribute> は、一般的に使用されるもう1つのクラスレベルの属性です。 クラスの使用例を次のコード例に示し `LogEntry` ます。 この例では、という型のの実装も示して <xref:System.ComponentModel.TypeConverter> `LogEntry` `LogEntryTypeConverter` います。  
  
 [!code-csharp[System.ComponentModel.AttributesDemoControl#5](~/samples/snippets/csharp/VS_Snippets_Winforms/System.ComponentModel.AttributesDemoControl/CS/attributesdemocontrol.cs#5)]
 [!code-vb[System.ComponentModel.AttributesDemoControl#5](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.ComponentModel.AttributesDemoControl/VB/attributesdemocontrol.vb#5)]  
  
## <a name="member-level-attributes"></a>メンバーレベルの属性  

 一部の属性は、メンバーレベルで適用されます。 次のコード例は、Windows フォームコントロールのプロパティに一般的に適用されるいくつかの属性を示しています。  
  
 [!code-csharp[System.ComponentModel.AttributesDemoControl#21](~/samples/snippets/csharp/VS_Snippets_Winforms/System.ComponentModel.AttributesDemoControl/CS/attributesdemocontrol.cs#21)]
 [!code-vb[System.ComponentModel.AttributesDemoControl#21](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.ComponentModel.AttributesDemoControl/VB/attributesdemocontrol.vb#21)]  
  
### <a name="ambientvalue-attribute"></a>AmbientValue 属性  

 次の例は、を示し、 <xref:System.ComponentModel.AmbientValueAttribute> デザイン環境との対話をサポートするコードを示しています。 この相互作用は、" *アンビエント*" と呼ばれます。  
  
 [!code-csharp[System.ComponentModel.AttributesDemoControl#23](~/samples/snippets/csharp/VS_Snippets_Winforms/System.ComponentModel.AttributesDemoControl/CS/attributesdemocontrol.cs#23)]
 [!code-vb[System.ComponentModel.AttributesDemoControl#23](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.ComponentModel.AttributesDemoControl/VB/attributesdemocontrol.vb#23)]  
  
### <a name="databinding-attributes"></a>Databinding 属性  

 次の例は、複合データバインディングの実装を示しています。 前に示したクラスレベルでは、 <xref:System.ComponentModel.ComplexBindingPropertiesAttribute> `DataSource` `DataMember` データバインディングに使用するプロパティとプロパティを指定します。 は、 <xref:System.ComponentModel.AttributeProviderAttribute> プロパティがバインドされる型を指定し `DataSource` ます。  
  
 [!code-csharp[System.ComponentModel.AttributesDemoControl#25](~/samples/snippets/csharp/VS_Snippets_Winforms/System.ComponentModel.AttributesDemoControl/CS/attributesdemocontrol.cs#25)]
 [!code-vb[System.ComponentModel.AttributesDemoControl#25](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.ComponentModel.AttributesDemoControl/VB/attributesdemocontrol.vb#25)]  
  
 [!code-csharp[System.ComponentModel.AttributesDemoControl#26](~/samples/snippets/csharp/VS_Snippets_Winforms/System.ComponentModel.AttributesDemoControl/CS/attributesdemocontrol.cs#26)]
 [!code-vb[System.ComponentModel.AttributesDemoControl#26](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.ComponentModel.AttributesDemoControl/VB/attributesdemocontrol.vb#26)]  
  
## <a name="compiling-the-code"></a>コードのコンパイル  
  
- をホストするフォームは、 `AttributesDemoControl` ビルドするためにアセンブリへの参照を必要とし `AttributesDemoControl` ます。  
  
## <a name="see-also"></a>関連項目

- <xref:System.IComparable>
- <xref:System.Windows.Forms.DataGridView>
- [.NET Framework を使用したカスタム Windows フォーム コントロールの開発](developing-custom-windows-forms-controls.md)
- [Windows フォーム コントロールの属性](attributes-in-windows-forms-controls.md)
- [方法 : 標準の型のコレクションを DesignerSerializationVisibilityAttribute でシリアル化する](/previous-versions/visualstudio/visual-studio-2013/ms171833(v=vs.120))
