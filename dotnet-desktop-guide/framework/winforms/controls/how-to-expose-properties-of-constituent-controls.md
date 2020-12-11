---
title: '方法: 内在コントロールのプロパティを公開する'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- user controls [Windows Forms], exposing constituent controls
- controls [Windows Forms], constituent
- custom controls [Windows Forms], exposing properties
- constituent controls
ms.assetid: 5c1ec98b-aa48-4823-986e-4712551cfdf1
ms.openlocfilehash: f006e42771a5ecc71f6a508fd78d0e2dd8f2d2f2
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/09/2020
ms.locfileid: "96980799"
---
# <a name="how-to-expose-properties-of-constituent-controls"></a>方法: 内在コントロールのプロパティを公開する
複合コントロールを構成するコントロールは、 *内在コントロール* と呼ばれます。 これらのコントロールは通常、プライベートとして宣言されるため、開発者がアクセスすることはできません。 これらのコントロールのプロパティを今後のユーザーが使用できるようにするには、それらをユーザーに公開する必要があります。 内在コントロールのプロパティは、ユーザーコントロールにプロパティを作成し、 `get` そのプロパティのアクセサーとアクセサーを使用して、 `set` 内在コントロールのプライベートプロパティの変更を反映することによって公開されます。

 という名前の構成ボタンを持つ仮想的なユーザーコントロールを考えてみましょう `MyButton` 。 この例では、ユーザーがプロパティを要求すると、 `ConstituentButtonBackColor` のプロパティに格納されている値 <xref:System.Windows.Forms.Control.BackColor%2A> `MyButton` が配信されます。 ユーザーがこのプロパティに値を割り当てた場合、その値はのプロパティに自動的に渡され、 <xref:System.Windows.Forms.Control.BackColor%2A> `MyButton` コードが `set` 実行され、の色が変更され `MyButton` ます。

 次の例は、構成ボタンのプロパティを公開する方法を示してい <xref:System.Windows.Forms.Control.BackColor%2A> ます。

```vb
Public Property ButtonColor() as System.Drawing.Color
   Get
      Return MyButton.BackColor
   End Get
   Set(Value as System.Drawing.Color)
      MyButton.BackColor = Value
   End Set
End Property
```

```csharp
public Color ButtonColor
{
   get
   {
      return(myButton.BackColor);
   }
   set
   {
      myButton.BackColor = value;
   }
}
```

### <a name="to-expose-a-property-of-a-constituent-control"></a>内在コントロールのプロパティを公開するには

1. ユーザーコントロールのパブリックプロパティを作成します。

2. `get`プロパティのセクションで、公開するプロパティの値を取得するコードを記述します。

3. プロパティの `set` セクションに、プロパティの値を、構成対象のコントロールの公開されたプロパティに渡すコードを記述します。

## <a name="see-also"></a>関連項目

- <xref:System.Windows.Forms.UserControl>
- [Windows フォーム コントロールのプロパティ](properties-in-windows-forms-controls.md)
- [さまざまなカスタム コントロール](varieties-of-custom-controls.md)
