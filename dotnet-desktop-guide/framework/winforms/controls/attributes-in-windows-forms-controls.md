---
title: コントロール内の属性
ms.date: 03/30/2017
ms.topic: overview
helpviewer_keywords:
- attributes [Windows Forms]
- attributes [Windows Forms], data binding properties
- attributes [Windows Forms], control properties
- attributes [Windows Forms], classes
ms.assetid: 2c5640e9-6c6c-49d7-a5e4-a768f6be7853
ms.openlocfilehash: 8f60b30021e6418f2ebf53965b62043e46e202b4
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/09/2020
ms.locfileid: "96975150"
---
# <a name="attributes-in-windows-forms-controls"></a>Windows フォーム コントロールの属性

.NET Framework には、カスタム コントロールおよびカスタム コンポーネントのメンバーに適用できるさまざまな属性が用意されています。 これらの属性には、クラスの実行時の動作に影響を及ぼすものもあれば、デザイン時の動作に影響を及ぼすものもあります。  
  
## <a name="attributes-for-control-and-component-properties"></a>コントロールおよびコンポーネントのプロパティの属性  

 次の表には、カスタム コントロールおよびカスタム コンポーネントのプロパティや他のメンバーに適用できる属性が示されています。 これらの属性の多くの使用例については、「[方法: Windows フォーム コントロールに属性を適用する](how-to-apply-attributes-in-windows-forms-controls.md)」を参照してください。  
  
|属性|説明|  
|---------------|-----------------|  
|<xref:System.ComponentModel.AmbientValueAttribute>|プロパティに渡す値を指定し、そのプロパティが別のソースから値を取得するようにします。 これは "*アンビエンス*" と呼ばれています。|  
|<xref:System.ComponentModel.BrowsableAttribute>|プロパティまたはイベントを **プロパティ** ウィンドウに表示するかどうかを指定します。|  
|<xref:System.ComponentModel.CategoryAttribute>|モードに設定されたコントロールに表示されるときに、プロパティまたはイベントをグループ化するカテゴリの名前を指定し <xref:System.Windows.Forms.PropertyGrid> <xref:System.Windows.Forms.PropertySort.Categorized> ます。|  
|<xref:System.ComponentModel.DefaultValueAttribute>|プロパティの既定値を指定します。|  
|<xref:System.ComponentModel.DescriptionAttribute>|プロパティまたはイベントの説明文を指定します。|  
|<xref:System.ComponentModel.DisplayNameAttribute>|引数を受け取らないプロパティ、イベント、または `public void` メソッドの表示名を指定します。|  
|<xref:System.ComponentModel.EditorAttribute>|プロパティの変更に使用するエディターを指定します。|  
|<xref:System.ComponentModel.EditorBrowsableAttribute>|プロパティまたはメソッドをエディターで表示できるかどうかを指定します。|  
|<xref:System.ComponentModel.Design.HelpKeywordAttribute>|クラスまたはメンバーのコンテキスト キーワードを指定します。|  
|<xref:System.ComponentModel.LocalizableAttribute>|プロパティをローカライズする必要があるかどうかを指定します。|  
|<xref:System.ComponentModel.PasswordPropertyTextAttribute>|アスタリスクなどの文字で、オブジェクトのテキスト表記を隠すように指示します。|  
|<xref:System.ComponentModel.ReadOnlyAttribute>|デザイン時に、この属性がバインドされるプロパティが読み取り専用か読み取り/書き込み可能かを指定します。|  
|<xref:System.ComponentModel.RefreshPropertiesAttribute>|関連付けられているプロパティ値が変更されたときに、プロパティ グリッドが更新されるように指定します。|  
|<xref:System.ComponentModel.TypeConverterAttribute>|この属性が関連付けられているオブジェクトのコンバーターとして使用する型を指定します。|  
  
## <a name="attributes-for-data-binding-properties"></a>データ バインディング プロパティの属性  

 次の表には、カスタム コントロールおよびカスタム コンポーネントがデータ バインディングと相互作用する方法を指定するために適用できる属性が示されています。  
  
|属性|説明|  
|---------------|-----------------|  
|<xref:System.ComponentModel.BindableAttribute>|バインディングにプロパティが通常、使用されるかどうかを指定します。|  
|<xref:System.ComponentModel.ComplexBindingPropertiesAttribute>|コンポーネントのデータ ソースおよびデータ メンバーのプロパティを指定します。|  
|<xref:System.ComponentModel.DefaultBindingPropertyAttribute>|コンポーネントの既定のバインディング プロパティを指定します。|  
|<xref:System.ComponentModel.LookupBindingPropertiesAttribute>|コンポーネントのデータ ソースおよびデータ メンバーのプロパティを指定します。|  
|<xref:System.ComponentModel.AttributeProviderAttribute>|属性のリダイレクトを有効にします。|  
  
## <a name="attributes-for-classes"></a>クラスの属性  

 次の表には、デザイン時にカスタム コントロールおよびカスタム コンポーネントの動作を指定するために適用できる属性が示されています。  
  
|属性|説明|  
|---------------|-----------------|  
|<xref:System.ComponentModel.DefaultEventAttribute>|コンポーネントの既定のイベントを指定します。|  
|<xref:System.ComponentModel.DefaultPropertyAttribute>|コンポーネントの既定のプロパティを指定します。|  
|<xref:System.ComponentModel.DesignerAttribute>|コンポーネントのデザイン時サービスを実装するために使用されるクラスを指定します。|  
|<xref:System.ComponentModel.DesignerCategoryAttribute>|クラスのデザイナーが特定のカテゴリに属することを指定します。|  
|<xref:System.ComponentModel.ToolboxItemAttribute>|ツールボックス項目の属性を表します。|  
|<xref:System.ComponentModel.ToolboxItemFilterAttribute>|ツールボックス項目に使用するフィルター文字列とフィルターの種類を指定します。|  
  
## <a name="see-also"></a>関連項目

- <xref:System.Attribute>
- [方法: Windows フォーム コントロールに属性を適用する](how-to-apply-attributes-in-windows-forms-controls.md)
- [デザイン時サポートの拡張](/previous-versions/visualstudio/visual-studio-2013/37899azc(v=vs.120))
- [.NET Framework を使用したカスタム Windows フォーム コントロールの開発](developing-custom-windows-forms-controls.md)
