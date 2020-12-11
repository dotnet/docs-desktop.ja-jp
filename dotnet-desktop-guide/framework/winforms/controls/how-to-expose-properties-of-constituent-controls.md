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
# <a name="how-to-expose-properties-of-constituent-controls"></a><span data-ttu-id="52720-102">方法: 内在コントロールのプロパティを公開する</span><span class="sxs-lookup"><span data-stu-id="52720-102">How to: Expose Properties of Constituent Controls</span></span>
<span data-ttu-id="52720-103">複合コントロールを構成するコントロールは、 *内在コントロール* と呼ばれます。</span><span class="sxs-lookup"><span data-stu-id="52720-103">The controls that make up a composite control are called *constituent controls*.</span></span> <span data-ttu-id="52720-104">これらのコントロールは通常、プライベートとして宣言されるため、開発者がアクセスすることはできません。</span><span class="sxs-lookup"><span data-stu-id="52720-104">These controls are normally declared private, and thus cannot be accessed by the developer.</span></span> <span data-ttu-id="52720-105">これらのコントロールのプロパティを今後のユーザーが使用できるようにするには、それらをユーザーに公開する必要があります。</span><span class="sxs-lookup"><span data-stu-id="52720-105">If you want to make properties of these controls available to future users, you must expose them to the user.</span></span> <span data-ttu-id="52720-106">内在コントロールのプロパティは、ユーザーコントロールにプロパティを作成し、 `get` そのプロパティのアクセサーとアクセサーを使用して、 `set` 内在コントロールのプライベートプロパティの変更を反映することによって公開されます。</span><span class="sxs-lookup"><span data-stu-id="52720-106">A property of a constituent control is exposed by creating a property in the user control, and using the `get` and `set` accessors of that property to effect the change in the private property of the constituent control.</span></span>

 <span data-ttu-id="52720-107">という名前の構成ボタンを持つ仮想的なユーザーコントロールを考えてみましょう `MyButton` 。</span><span class="sxs-lookup"><span data-stu-id="52720-107">Consider a hypothetical user control with a constituent button named `MyButton`.</span></span> <span data-ttu-id="52720-108">この例では、ユーザーがプロパティを要求すると、 `ConstituentButtonBackColor` のプロパティに格納されている値 <xref:System.Windows.Forms.Control.BackColor%2A> `MyButton` が配信されます。</span><span class="sxs-lookup"><span data-stu-id="52720-108">In this example, when the user requests the `ConstituentButtonBackColor` property, the value stored in the <xref:System.Windows.Forms.Control.BackColor%2A> property of `MyButton` is delivered.</span></span> <span data-ttu-id="52720-109">ユーザーがこのプロパティに値を割り当てた場合、その値はのプロパティに自動的に渡され、 <xref:System.Windows.Forms.Control.BackColor%2A> `MyButton` コードが `set` 実行され、の色が変更され `MyButton` ます。</span><span class="sxs-lookup"><span data-stu-id="52720-109">When the user assigns a value to this property, that value is automatically passed to the <xref:System.Windows.Forms.Control.BackColor%2A> property of `MyButton` and the `set` code will execute, changing the color of `MyButton`.</span></span>

 <span data-ttu-id="52720-110">次の例は、構成ボタンのプロパティを公開する方法を示してい <xref:System.Windows.Forms.Control.BackColor%2A> ます。</span><span class="sxs-lookup"><span data-stu-id="52720-110">The following example shows how to expose the <xref:System.Windows.Forms.Control.BackColor%2A> property of the constituent button:</span></span>

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

### <a name="to-expose-a-property-of-a-constituent-control"></a><span data-ttu-id="52720-111">内在コントロールのプロパティを公開するには</span><span class="sxs-lookup"><span data-stu-id="52720-111">To expose a property of a constituent control</span></span>

1. <span data-ttu-id="52720-112">ユーザーコントロールのパブリックプロパティを作成します。</span><span class="sxs-lookup"><span data-stu-id="52720-112">Create a public property for your user control.</span></span>

2. <span data-ttu-id="52720-113">`get`プロパティのセクションで、公開するプロパティの値を取得するコードを記述します。</span><span class="sxs-lookup"><span data-stu-id="52720-113">In the `get` section of the property, write code that retrieves the value of the property you want to expose.</span></span>

3. <span data-ttu-id="52720-114">プロパティの `set` セクションに、プロパティの値を、構成対象のコントロールの公開されたプロパティに渡すコードを記述します。</span><span class="sxs-lookup"><span data-stu-id="52720-114">In the `set` section of the property, write code that passes the value of the property to the exposed property of the constituent control.</span></span>

## <a name="see-also"></a><span data-ttu-id="52720-115">関連項目</span><span class="sxs-lookup"><span data-stu-id="52720-115">See also</span></span>

- <xref:System.Windows.Forms.UserControl>
- [<span data-ttu-id="52720-116">Windows フォーム コントロールのプロパティ</span><span class="sxs-lookup"><span data-stu-id="52720-116">Properties in Windows Forms Controls</span></span>](properties-in-windows-forms-controls.md)
- [<span data-ttu-id="52720-117">さまざまなカスタム コントロール</span><span class="sxs-lookup"><span data-stu-id="52720-117">Varieties of Custom Controls</span></span>](varieties-of-custom-controls.md)
