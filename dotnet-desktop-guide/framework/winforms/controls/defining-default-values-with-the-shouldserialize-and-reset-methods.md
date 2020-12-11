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
# <a name="defining-default-values-with-the-shouldserialize-and-reset-methods"></a><span data-ttu-id="41752-103">ShouldSerialize メソッドと Reset メソッドによる既定値の定義</span><span class="sxs-lookup"><span data-stu-id="41752-103">Defining Default Values with the ShouldSerialize and Reset Methods</span></span>
<span data-ttu-id="41752-104">`ShouldSerialize` とは、プロパティに `Reset` 単純な既定値がない場合に、プロパティに対して指定できる省略可能なメソッドです。</span><span class="sxs-lookup"><span data-stu-id="41752-104">`ShouldSerialize` and `Reset` are optional methods that you can provide for a property, if the property does not have a simple default value.</span></span> <span data-ttu-id="41752-105">プロパティに単純な既定値がある場合は、を適用し、 <xref:System.ComponentModel.DefaultValueAttribute> 代わりに属性クラスコンストラクターに既定値を指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="41752-105">If the property has a simple default value, you should apply the <xref:System.ComponentModel.DefaultValueAttribute> and supply the default value to the attribute class constructor instead.</span></span> <span data-ttu-id="41752-106">これらのメカニズムのいずれかにより、デザイナーで次の機能が有効になります。</span><span class="sxs-lookup"><span data-stu-id="41752-106">Either of these mechanisms enables the following features in the designer:</span></span>

- <span data-ttu-id="41752-107">プロパティは、既定値から変更されている場合、プロパティブラウザーで視覚的に表示されます。</span><span class="sxs-lookup"><span data-stu-id="41752-107">The property provides visual indication in the property browser if it has been modified from its default value.</span></span>

- <span data-ttu-id="41752-108">ユーザーはプロパティを右クリックし、[ **リセット** ] をクリックして、プロパティを既定値に戻すことができます。</span><span class="sxs-lookup"><span data-stu-id="41752-108">The user can right-click on the property and choose **Reset** to restore the property to its default value.</span></span>

- <span data-ttu-id="41752-109">デザイナーでは、より効率的なコードが生成されます。</span><span class="sxs-lookup"><span data-stu-id="41752-109">The designer generates more efficient code.</span></span>

> [!NOTE]
> <span data-ttu-id="41752-110">を適用するか、 <xref:System.ComponentModel.DefaultValueAttribute> `Reset` *propertyname* メソッドと `ShouldSerialize` *propertyname* メソッドを指定します。</span><span class="sxs-lookup"><span data-stu-id="41752-110">Either apply the <xref:System.ComponentModel.DefaultValueAttribute> or provide `Reset`*PropertyName* and `ShouldSerialize`*PropertyName* methods.</span></span> <span data-ttu-id="41752-111">両方を使用しないでください。</span><span class="sxs-lookup"><span data-stu-id="41752-111">Do not use both.</span></span>

<span data-ttu-id="41752-112">メソッドまたはメソッドを宣言する場合は `ShouldSerialize` `Reset` 、アクセス修飾子を使用し `private` ます。</span><span class="sxs-lookup"><span data-stu-id="41752-112">When declaring a `ShouldSerialize` or `Reset` method, use the `private` access modifier.</span></span> <span data-ttu-id="41752-113">これらのメソッドは通常、ユーザーコードではなく、デザイナーによって呼び出されます。</span><span class="sxs-lookup"><span data-stu-id="41752-113">These methods are usually invoked by the designer and not by user code.</span></span>

 <span data-ttu-id="41752-114">`Reset` *PropertyName* メソッドは、次のコードに示すように、プロパティを既定値に設定します。</span><span class="sxs-lookup"><span data-stu-id="41752-114">The `Reset`*PropertyName* method sets a property to its default value, as shown in the following code fragment.</span></span>

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
> <span data-ttu-id="41752-115">プロパティにメソッドがなく、がでマークされておらず、宣言に既定値が指定されていない場合 `Reset` <xref:System.ComponentModel.DefaultValueAttribute> 、 `Reset` Visual Studio の Windows フォームデザイナーの [ **プロパティ** ] ウィンドウのショートカットメニューで、そのプロパティのオプションは無効になります。</span><span class="sxs-lookup"><span data-stu-id="41752-115">If a property does not have a `Reset` method, is not marked with a <xref:System.ComponentModel.DefaultValueAttribute>, and does not have a default value supplied in its declaration, the `Reset` option for that property is disabled in the shortcut menu of the **Properties** window of the Windows Forms Designer in Visual Studio.</span></span>

 <span data-ttu-id="41752-116">Visual Studio などのデザイナーでは、PropertyName メソッドを使用して、 `ShouldSerialize` プロパティが既定値から変更されたかどうかを確認し、プロパティが変更された場合にのみコードをフォームに記述します。これにより、コード生成をより効率的に行うことができます。</span><span class="sxs-lookup"><span data-stu-id="41752-116">Designers such as Visual Studio use the `ShouldSerialize`*PropertyName* method to check whether a property has changed from its default value and write code into the form only if a property is changed, thus allowing for more efficient code generation.</span></span> <span data-ttu-id="41752-117">次に例を示します。</span><span class="sxs-lookup"><span data-stu-id="41752-117">For example:</span></span>

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
> <span data-ttu-id="41752-118">デザイナーによってプロパティがシリアル化されないようにする場合は、の値を使用して [デザイナ Serializationvisibility](xref:System.ComponentModel.DesignerSerializationVisibilityAttribute) 属性を追加し `Hidden` ます。</span><span class="sxs-lookup"><span data-stu-id="41752-118">If you want to permanently prevent a property from being serialized by the designer, add the [DesignerSerializationVisibility](xref:System.ComponentModel.DesignerSerializationVisibilityAttribute) attribute with the value of `Hidden`.</span></span>

 <span data-ttu-id="41752-119">完全なコード例を次に示します。</span><span class="sxs-lookup"><span data-stu-id="41752-119">A complete code example follows.</span></span>

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

 <span data-ttu-id="41752-120">この場合、プロパティによってアクセスされるプライベート変数の値がであっても `MyFont` `null` 、プロパティブラウザーには表示されず、親のプロパティが表示され `null` <xref:System.Windows.Forms.Control.Font%2A> ます。それ以外の場合 `null` は、で定義されている既定値が表示され <xref:System.Windows.Forms.Control.Font%2A> <xref:System.Windows.Forms.Control> ます。</span><span class="sxs-lookup"><span data-stu-id="41752-120">In this case, even when the value of the private variable accessed by the `MyFont` property is `null`, the property browser does not display `null`; instead, it displays the <xref:System.Windows.Forms.Control.Font%2A> property of the parent, if it is not `null`, or the default <xref:System.Windows.Forms.Control.Font%2A> value defined in <xref:System.Windows.Forms.Control>.</span></span> <span data-ttu-id="41752-121">したがって、の既定値を `MyFont` 単に設定することはできません。また、をこのプロパティに適用することはできませ <xref:System.ComponentModel.DefaultValueAttribute> ん。</span><span class="sxs-lookup"><span data-stu-id="41752-121">Thus the default value for `MyFont` cannot be simply set, and a <xref:System.ComponentModel.DefaultValueAttribute> cannot be applied to this property.</span></span> <span data-ttu-id="41752-122">代わりに、 `ShouldSerialize` `Reset` プロパティに対してメソッドとメソッドを実装する必要があり `MyFont` ます。</span><span class="sxs-lookup"><span data-stu-id="41752-122">Instead, the `ShouldSerialize` and `Reset` methods must be implemented for the `MyFont` property.</span></span>

## <a name="see-also"></a><span data-ttu-id="41752-123">関連項目</span><span class="sxs-lookup"><span data-stu-id="41752-123">See also</span></span>

- [<span data-ttu-id="41752-124">Windows フォーム コントロールのプロパティ</span><span class="sxs-lookup"><span data-stu-id="41752-124">Properties in Windows Forms Controls</span></span>](properties-in-windows-forms-controls.md)
- [<span data-ttu-id="41752-125">プロパティの定義</span><span class="sxs-lookup"><span data-stu-id="41752-125">Defining a Property</span></span>](defining-a-property-in-windows-forms-controls.md)
- [<span data-ttu-id="41752-126">プロパティ変更イベント</span><span class="sxs-lookup"><span data-stu-id="41752-126">Property-Changed Events</span></span>](property-changed-events.md)
- <xref:System.ComponentModel.DesignerSerializationVisibilityAttribute?displayProperty=fullName>
