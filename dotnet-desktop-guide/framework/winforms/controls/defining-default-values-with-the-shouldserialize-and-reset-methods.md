---
title: ShouldSerialize メソッドと Reset メソッドによる既定値の定義
description: ShouldSerialize および Reset プロパティメソッドを使用して、Windows フォームデザイナーの動作を制御する方法について説明します。
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- custom controls [Windows Forms], property methods
- ShouldPersist method
ms.assetid: 7b6c5e00-3771-46b4-9142-5a80d5864a5e
ms.openlocfilehash: b425b301a1c07030ad4cefa70e41198d08598631
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/09/2020
ms.locfileid: "96974191"
---
# <a name="defining-default-values-with-the-shouldserialize-and-reset-methods"></a>ShouldSerialize メソッドと Reset メソッドによる既定値の定義
`ShouldSerialize` とは、プロパティに `Reset` 単純な既定値がない場合に、プロパティに対して指定できる省略可能なメソッドです。 プロパティに単純な既定値がある場合は、を適用し、 <xref:System.ComponentModel.DefaultValueAttribute> 代わりに属性クラスコンストラクターに既定値を指定する必要があります。 これらのメカニズムのいずれかにより、デザイナーで次の機能が有効になります。

- プロパティは、既定値から変更されている場合、プロパティブラウザーで視覚的に表示されます。

- ユーザーはプロパティを右クリックし、[ **リセット** ] をクリックして、プロパティを既定値に戻すことができます。

- デザイナーでは、より効率的なコードが生成されます。

> [!NOTE]
> を適用するか、 <xref:System.ComponentModel.DefaultValueAttribute> `Reset` *propertyname* メソッドと `ShouldSerialize` *propertyname* メソッドを指定します。 両方を使用しないでください。

メソッドまたはメソッドを宣言する場合は `ShouldSerialize` `Reset` 、アクセス修飾子を使用し `private` ます。 これらのメソッドは通常、ユーザーコードではなく、デザイナーによって呼び出されます。

 `Reset` *PropertyName* メソッドは、次のコードに示すように、プロパティを既定値に設定します。

```vb
Private Sub ResetMyFont()
   MyFont = Nothing
End Sub
```

```csharp
private void ResetMyFont()
{
   MyFont = null;
}
```

> [!NOTE]
> プロパティにメソッドがなく、がでマークされておらず、宣言に既定値が指定されていない場合 `Reset` <xref:System.ComponentModel.DefaultValueAttribute> 、 `Reset` Visual Studio の Windows フォームデザイナーの [ **プロパティ** ] ウィンドウのショートカットメニューで、そのプロパティのオプションは無効になります。

 Visual Studio などのデザイナーでは、PropertyName メソッドを使用して、 `ShouldSerialize` プロパティが既定値から変更されたかどうかを確認し、プロパティが変更された場合にのみコードをフォームに記述します。これにより、コード生成をより効率的に行うことができます。 次に例を示します。

```vb
'Returns true if the font has changed; otherwise, returns false.
' The designer writes code to the form only if true is returned.
Private Function ShouldSerializeMyFont() As Boolean
   Return thefont IsNot Nothing
End Function
```

```csharp
// Returns true if the font has changed; otherwise, returns false.
// The designer writes code to the form only if true is returned.
private bool ShouldSerializeMyFont()
{
   return thefont != null;
}
```

> [!TIP]
> デザイナーによってプロパティがシリアル化されないようにする場合は、の値を使用して [デザイナ Serializationvisibility](xref:System.ComponentModel.DesignerSerializationVisibilityAttribute) 属性を追加し `Hidden` ます。

 完全なコード例を次に示します。

```vb
Option Explicit
Option Strict

Imports System.Drawing
Imports System.Windows.Forms

Public Class MyControl
   Inherits Control

   ' Declare an instance of the Font class
   ' and set its default value to Nothing.
   Private thefont As Font = Nothing

   ' The MyFont property.
   Public Property MyFont() As Font
      ' Note that the Font property never
      ' returns null.
      Get
         If Not (thefont Is Nothing) Then
            Return thefont
         End If
         If Not (Parent Is Nothing) Then
            Return Parent.Font
         End If
         Return Control.DefaultFont
      End Get
      Set
         thefont = value
      End Set
   End Property

   Private Function ShouldSerializeMyFont() As Boolean
      Return thefont IsNot Nothing
   End Function

   Private Sub ResetMyFont()
      MyFont = Nothing
   End Sub
End Class
```

```csharp
using System;
using System.Drawing;
using System.Windows.Forms;

public class MyControl : Control {
   // Declare an instance of the Font class
   // and set its default value to null.
   private Font thefont = null;

   // The MyFont property.
   public Font MyFont {
      // Note that the MyFont property never
      // returns null.
      get {
         if (thefont != null) return thefont;
         if (Parent != null) return Parent.Font;
         return Control.DefaultFont;
      }
      set {
         thefont = value;
      }
   }

   private bool ShouldSerializeMyFont()
   {
      return thefont != null;
   }

   private void ResetMyFont()
   {
      MyFont = null;
   }
}
```

 この場合、プロパティによってアクセスされるプライベート変数の値がであっても `MyFont` `null` 、プロパティブラウザーには表示されず、親のプロパティが表示され `null` <xref:System.Windows.Forms.Control.Font%2A> ます。それ以外の場合 `null` は、で定義されている既定値が表示され <xref:System.Windows.Forms.Control.Font%2A> <xref:System.Windows.Forms.Control> ます。 したがって、の既定値を `MyFont` 単に設定することはできません。また、をこのプロパティに適用することはできませ <xref:System.ComponentModel.DefaultValueAttribute> ん。 代わりに、 `ShouldSerialize` `Reset` プロパティに対してメソッドとメソッドを実装する必要があり `MyFont` ます。

## <a name="see-also"></a>関連項目

- [Windows フォーム コントロールのプロパティ](properties-in-windows-forms-controls.md)
- [プロパティの定義](defining-a-property-in-windows-forms-controls.md)
- [プロパティ変更イベント](property-changed-events.md)
- <xref:System.ComponentModel.DesignerSerializationVisibilityAttribute?displayProperty=fullName>
