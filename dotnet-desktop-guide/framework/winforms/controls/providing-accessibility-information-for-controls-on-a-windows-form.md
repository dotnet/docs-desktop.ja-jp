---
title: Windows フォーム上のコントロールのユーザー補助情報の提供
ms.date: 03/30/2017
helpviewer_keywords:
- Windows Forms controls, accessibility
- controls [Windows Forms], accessibility
- accessibility [Windows Forms], Windows Forms controls
dev_langs:
- csharp
- vb
- cpp
ms.assetid: 887dee6f-5059-4d57-957d-7c6fcd4acb10
ms.openlocfilehash: 672104db94826cfbe113a7ae0ea29546b0c3b9da
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/09/2020
ms.locfileid: "96974387"
---
# <a name="providing-accessibility-information-for-controls-on-a-windows-form"></a><span data-ttu-id="54767-102">Windows フォーム上のコントロールのユーザー補助情報の提供</span><span class="sxs-lookup"><span data-stu-id="54767-102">Providing Accessibility Information for Controls on a Windows Form</span></span>
<span data-ttu-id="54767-103">ユーザー補助機能は専用のプログラムおよびデバイスで、障碍を持つユーザーがコンピューターをより効果的に使用するよう助けます。</span><span class="sxs-lookup"><span data-stu-id="54767-103">Accessibility aids are specialized programs and devices that help people with disabilities use computers more effectively.</span></span> <span data-ttu-id="54767-104">たとえば、視覚障碍者のためのスクリーン リーダーや、マウスまたはキーボードではなく音声コマンド入力を利用するユーザーのための音声入力ユーティリティがあります。</span><span class="sxs-lookup"><span data-stu-id="54767-104">Examples include screen readers for people who are blind and voice input utilities for people who provide verbal commands instead of using the mouse or keyboard.</span></span> <span data-ttu-id="54767-105">これらのユーザー補助機能は、Windows フォーム コントロールによって公開されているアクセシビリティのプロパティと連携します。</span><span class="sxs-lookup"><span data-stu-id="54767-105">These accessibility aids interact with the accessibility properties exposed by Windows Forms controls.</span></span> <span data-ttu-id="54767-106">それらのプロパティは以下のとおりです。</span><span class="sxs-lookup"><span data-stu-id="54767-106">These properties are:</span></span>  
  
- <span data-ttu-id="54767-107">**AccessibilityObject**</span><span class="sxs-lookup"><span data-stu-id="54767-107">**AccessibilityObject**</span></span>  
  
- <span data-ttu-id="54767-108">**AccessibleDefaultActionDescription**</span><span class="sxs-lookup"><span data-stu-id="54767-108">**AccessibleDefaultActionDescription**</span></span>  
  
- <span data-ttu-id="54767-109">**AccessibleDescription**</span><span class="sxs-lookup"><span data-stu-id="54767-109">**AccessibleDescription**</span></span>  
  
- <span data-ttu-id="54767-110">**AccessibleName**</span><span class="sxs-lookup"><span data-stu-id="54767-110">**AccessibleName**</span></span>  
  
- <span data-ttu-id="54767-111">**AccessibleRole**</span><span class="sxs-lookup"><span data-stu-id="54767-111">**AccessibleRole**</span></span>  
  
## <a name="accessibilityobject-property"></a><span data-ttu-id="54767-112">AccessibilityObject プロパティ</span><span class="sxs-lookup"><span data-stu-id="54767-112">AccessibilityObject Property</span></span>  
 <span data-ttu-id="54767-113">この読み取り専用プロパティには <xref:System.Windows.Forms.AccessibleObject> インスタンスが含まれます。</span><span class="sxs-lookup"><span data-stu-id="54767-113">This read-only property contains an <xref:System.Windows.Forms.AccessibleObject> instance.</span></span> <span data-ttu-id="54767-114">**AccessibleObject** は、コントロールの説明、画面上の位置、ナビゲーション能力、および値に関する情報を提供する <xref:Accessibility.IAccessible> インターフェイスを実装します。</span><span class="sxs-lookup"><span data-stu-id="54767-114">The **AccessibleObject** implements the <xref:Accessibility.IAccessible> interface, which provides information about the control's description, screen location, navigational abilities, and value.</span></span> <span data-ttu-id="54767-115">デザイナーは、コントロールがフォームに追加されたときにこの値を設定します。</span><span class="sxs-lookup"><span data-stu-id="54767-115">The designer sets this value when the control is added to the form.</span></span>  
  
## <a name="accessibledefaultactiondescription-property"></a><span data-ttu-id="54767-116">AccessibleDefaultActionDescription プロパティ</span><span class="sxs-lookup"><span data-stu-id="54767-116">AccessibleDefaultActionDescription Property</span></span>  
 <span data-ttu-id="54767-117">この文字列は、コントロールの操作について説明します。</span><span class="sxs-lookup"><span data-stu-id="54767-117">This string describes the action of the control.</span></span> <span data-ttu-id="54767-118">[プロパティ] ウィンドウには表示されず、コードでのみ設定できます。</span><span class="sxs-lookup"><span data-stu-id="54767-118">It does not appear in the Properties window and may only be set in code.</span></span> <span data-ttu-id="54767-119">次の例では、このプロパティをボタン コントロールに設定します。</span><span class="sxs-lookup"><span data-stu-id="54767-119">The following example sets this property for a button control:</span></span>  
  
```vb  
Button1.AccessibleDefaultActionDescription = _  
   "Closes the application."  
```

```csharp  
Button1.AccessibleDefaultActionDescription =
   "Closes the application.";  
```

```cpp  
button1->AccessibleDefaultActionDescription =  
   "Closes the application.";  
```  
  
## <a name="accessibledescription-property"></a><span data-ttu-id="54767-120">AccessibleDescription プロパティ</span><span class="sxs-lookup"><span data-stu-id="54767-120">AccessibleDescription Property</span></span>  
 <span data-ttu-id="54767-121">この文字列はコントロールについて説明します。</span><span class="sxs-lookup"><span data-stu-id="54767-121">This string describes the control.</span></span> <span data-ttu-id="54767-122">これは、[プロパティ] ウィンドウで、または次のようにコードで設定できます。</span><span class="sxs-lookup"><span data-stu-id="54767-122">It may be set in the Properties window, or in code as follows:</span></span>  
  
```vb  
Button1.AccessibleDescription = "A button with text 'Exit'."  
```

```csharp  
Button1.AccessibleDescription = "A button with text 'Exit'";  
```

```cpp  
button1->AccessibleDescription = "A button with text 'Exit'";  
```  
  
## <a name="accessiblename-property"></a><span data-ttu-id="54767-123">AccessibleName プロパティ</span><span class="sxs-lookup"><span data-stu-id="54767-123">AccessibleName Property</span></span>  
 <span data-ttu-id="54767-124">これは、ユーザー補助機能に報告されたコントロールの名前です。</span><span class="sxs-lookup"><span data-stu-id="54767-124">This is the name of a control reported to accessibility aids.</span></span> <span data-ttu-id="54767-125">これは、[プロパティ] ウィンドウで、または次のようにコードで設定できます。</span><span class="sxs-lookup"><span data-stu-id="54767-125">It may be set in the Properties window, or in code as follows:</span></span>  
  
```vb  
Button1.AccessibleName = "Order"  
```

```csharp  
Button1.AccessibleName = "Order";  
```

```cpp  
button1->AccessibleName = "Order";  
```  
  
## <a name="accessiblerole-property"></a><span data-ttu-id="54767-126">AccessibleRole プロパティ</span><span class="sxs-lookup"><span data-stu-id="54767-126">AccessibleRole Property</span></span>  
 <span data-ttu-id="54767-127">このプロパティには <xref:System.Windows.Forms.AccessibleRole> 列挙型が含まれており、コントロールのユーザー インターフェイスの役割について説明します。</span><span class="sxs-lookup"><span data-stu-id="54767-127">This property, which contains an <xref:System.Windows.Forms.AccessibleRole> enumeration, describes the user interface role of the control.</span></span> <span data-ttu-id="54767-128">新しいコントロールは値が `Default` に設定されています。</span><span class="sxs-lookup"><span data-stu-id="54767-128">A new control has the value set to `Default`.</span></span> <span data-ttu-id="54767-129">つまり、 **ボタン** コントロールは既定値では **ボタン** として機能します。</span><span class="sxs-lookup"><span data-stu-id="54767-129">This would mean that by default, a **Button** control acts as a **Button**.</span></span> <span data-ttu-id="54767-130">コントロールに別の役割がある場合、このプロパティをリセットできます。</span><span class="sxs-lookup"><span data-stu-id="54767-130">You may want to reset this property if a control has another role.</span></span> <span data-ttu-id="54767-131">たとえば、 **PictureBox** コントロールを **Chart** として使用する場合、 **PictureBox** ではなく **Chart** としてユーザー補助機能が役割を報告するようにできます。</span><span class="sxs-lookup"><span data-stu-id="54767-131">For example, you may be using a **PictureBox** control as a **Chart**, and you may want accessibility aids to report the role as a **Chart**, not as a **PictureBox**.</span></span> <span data-ttu-id="54767-132">また、開発したカスタム コントロールにこのプロパティを指定することもできます。</span><span class="sxs-lookup"><span data-stu-id="54767-132">You may also want to specify this property for custom controls you have developed.</span></span> <span data-ttu-id="54767-133">このプロパティは、[プロパティ] ウィンドウで、または次のようにコードで設定できます。</span><span class="sxs-lookup"><span data-stu-id="54767-133">This property may be set in the Properties window, or in code as follows:</span></span>  
  
```vb
PictureBox1.AccessibleRole = AccessibleRole.Chart  
```

```csharp  
PictureBox1.AccessibleRole = AccessibleRole.Chart;  
```

```cpp  
pictureBox1->AccessibleRole = AccessibleRole::Chart;  
```  
  
## <a name="see-also"></a><span data-ttu-id="54767-134">関連項目</span><span class="sxs-lookup"><span data-stu-id="54767-134">See also</span></span>

- <xref:System.Windows.Forms.AccessibleObject>
- <xref:System.Windows.Forms.Control.AccessibilityObject%2A?displayProperty=nameWithType>
- <xref:System.Windows.Forms.Control.AccessibleDefaultActionDescription%2A?displayProperty=nameWithType>
- <xref:System.Windows.Forms.Control.AccessibleDescription%2A?displayProperty=nameWithType>
- <xref:System.Windows.Forms.Control.AccessibleName%2A?displayProperty=nameWithType>
- <xref:System.Windows.Forms.Control.AccessibleRole%2A?displayProperty=nameWithType>
- <xref:System.Windows.Forms.AccessibleRole>
