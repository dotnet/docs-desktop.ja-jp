---
title: Windows フォーム上のコントロールのユーザー補助情報の提供
description: コントロールにアクセシビリティ情報を追加する方法について学習します。 Windows フォームを使用すると、障碍のある方に役立つアクセシビリティの設定をコントロールに追加できます。
ms.date: 10/26/2020
helpviewer_keywords:
- Windows Forms controls, accessibility
- controls [Windows Forms], accessibility
- accessibility [Windows Forms], Windows Forms controls
dev_langs:
- csharp
- vb
ms.openlocfilehash: 27c06a7d01cb98ecb2f7216c09dc292d2fe68a6f
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/09/2020
ms.locfileid: "96942334"
---
# <a name="providing-accessibility-information-for-controls-windows-forms-net"></a><span data-ttu-id="5116d-104">コントロールへのアクセシビリティ情報の提供 (Windows フォーム .NET)</span><span class="sxs-lookup"><span data-stu-id="5116d-104">Providing Accessibility Information for Controls (Windows Forms .NET)</span></span>

<span data-ttu-id="5116d-105">ユーザー補助機能は専用のプログラムおよびデバイスで、障碍を持つユーザーがコンピューターをより効果的に使用するよう助けます。</span><span class="sxs-lookup"><span data-stu-id="5116d-105">Accessibility aids are specialized programs and devices that help people with disabilities use computers more effectively.</span></span> <span data-ttu-id="5116d-106">たとえば、視覚障碍者のためのスクリーン リーダーや、マウスまたはキーボードではなく音声コマンド入力を利用するユーザーのための音声入力ユーティリティがあります。</span><span class="sxs-lookup"><span data-stu-id="5116d-106">Examples include screen readers for people who are blind and voice input utilities for people who provide verbal commands instead of using the mouse or keyboard.</span></span> <span data-ttu-id="5116d-107">これらのユーザー補助機能は、Windows フォーム コントロールによって公開されているアクセシビリティのプロパティと連携します。</span><span class="sxs-lookup"><span data-stu-id="5116d-107">These accessibility aids interact with the accessibility properties exposed by Windows Forms controls.</span></span> <span data-ttu-id="5116d-108">それらのプロパティは以下のとおりです。</span><span class="sxs-lookup"><span data-stu-id="5116d-108">These properties are:</span></span>

- <xref:System.Windows.Forms.AccessibleObject?displayProperty=fullName>
- <xref:System.Windows.Forms.Control.AccessibleDefaultActionDescription?displayProperty=fullName>
- <xref:System.Windows.Forms.Control.AccessibleDescription?displayProperty=fullName>
- <xref:System.Windows.Forms.Control.AccessibleName?displayProperty=fullName>
- <xref:System.Windows.Forms.AccessibleRole?displayProperty=fullName>

[!INCLUDE [desktop guide under construction](../../includes/desktop-guide-preview-note.md)]

## <a name="accessibilityobject-property"></a><span data-ttu-id="5116d-109">AccessibilityObject プロパティ</span><span class="sxs-lookup"><span data-stu-id="5116d-109">AccessibilityObject Property</span></span>

<span data-ttu-id="5116d-110">この読み取り専用プロパティには <xref:System.Windows.Forms.AccessibleObject> インスタンスが含まれます。</span><span class="sxs-lookup"><span data-stu-id="5116d-110">This read-only property contains an <xref:System.Windows.Forms.AccessibleObject> instance.</span></span> <span data-ttu-id="5116d-111">`AccessibleObject` によって、コントロールの説明、画面上の位置、ナビゲーション能力、値に関する情報を提供する <xref:Accessibility.IAccessible> インターフェイスが実装されます。</span><span class="sxs-lookup"><span data-stu-id="5116d-111">The `AccessibleObject` implements the <xref:Accessibility.IAccessible> interface, which provides information about the control's description, screen location, navigational abilities, and value.</span></span> <span data-ttu-id="5116d-112">デザイナーは、コントロールがフォームに追加されたときにこの値を設定します。</span><span class="sxs-lookup"><span data-stu-id="5116d-112">The designer sets this value when the control is added to the form.</span></span>

## <a name="accessibledefaultactiondescription-property"></a><span data-ttu-id="5116d-113">AccessibleDefaultActionDescription プロパティ</span><span class="sxs-lookup"><span data-stu-id="5116d-113">AccessibleDefaultActionDescription Property</span></span>

<span data-ttu-id="5116d-114">この文字列は、コントロールの操作について説明します。</span><span class="sxs-lookup"><span data-stu-id="5116d-114">This string describes the action of the control.</span></span> <span data-ttu-id="5116d-115">[プロパティ] ウィンドウには表示されず、コードでのみ設定できます。</span><span class="sxs-lookup"><span data-stu-id="5116d-115">It does not appear in the Properties window and may only be set in code.</span></span> <span data-ttu-id="5116d-116">次の例では、<xref:System.Windows.Forms.Control.AccessibleDefaultActionDescription> プロパティをボタン コントロールに設定します。</span><span class="sxs-lookup"><span data-stu-id="5116d-116">The following example sets the <xref:System.Windows.Forms.Control.AccessibleDefaultActionDescription> property for a button control:</span></span>

```vb
Button1.AccessibleDefaultActionDescription = "Closes the application."
```

```csharp
button1.AccessibleDefaultActionDescription = "Closes the application.";
```

## <a name="accessibledescription-property"></a><span data-ttu-id="5116d-117">AccessibleDescription プロパティ</span><span class="sxs-lookup"><span data-stu-id="5116d-117">AccessibleDescription Property</span></span>

<span data-ttu-id="5116d-118">この文字列はコントロールについて説明します。</span><span class="sxs-lookup"><span data-stu-id="5116d-118">This string describes the control.</span></span> <span data-ttu-id="5116d-119"><xref:System.Windows.Forms.Control.AccessibleDescription> プロパティは、プロパティ ウィンドウで、または次のようにコードで設定できます。</span><span class="sxs-lookup"><span data-stu-id="5116d-119">The <xref:System.Windows.Forms.Control.AccessibleDescription> property may be set in the Properties window, or in code as follows:</span></span>

```vb
Button1.AccessibleDescription = "A button with text 'Exit'."
```

```csharp
button1.AccessibleDescription = "A button with text 'Exit'";
```

## <a name="accessiblename-property"></a><span data-ttu-id="5116d-120">AccessibleName プロパティ</span><span class="sxs-lookup"><span data-stu-id="5116d-120">AccessibleName Property</span></span>

<span data-ttu-id="5116d-121">これは、ユーザー補助機能に報告されたコントロールの名前です。</span><span class="sxs-lookup"><span data-stu-id="5116d-121">This is the name of a control reported to accessibility aids.</span></span> <span data-ttu-id="5116d-122"><xref:System.Windows.Forms.Control.AccessibleName> プロパティは、プロパティ ウィンドウで、または次のようにコードで設定できます。</span><span class="sxs-lookup"><span data-stu-id="5116d-122">The <xref:System.Windows.Forms.Control.AccessibleName> property may be set in the Properties window, or in code as follows:</span></span>

```vb
Button1.AccessibleName = "Order"
```

```csharp
button1.AccessibleName = "Order";
```

## <a name="accessiblerole-property"></a><span data-ttu-id="5116d-123">AccessibleRole プロパティ</span><span class="sxs-lookup"><span data-stu-id="5116d-123">AccessibleRole Property</span></span>

<span data-ttu-id="5116d-124">このプロパティには <xref:System.Windows.Forms.AccessibleRole> 列挙型が含まれており、コントロールのユーザー インターフェイスの役割について説明します。</span><span class="sxs-lookup"><span data-stu-id="5116d-124">This property, which contains an <xref:System.Windows.Forms.AccessibleRole> enumeration, describes the user interface role of the control.</span></span> <span data-ttu-id="5116d-125">新しいコントロールは値が `Default` に設定されています。</span><span class="sxs-lookup"><span data-stu-id="5116d-125">A new control has the value set to `Default`.</span></span> <span data-ttu-id="5116d-126">つまり、`Button` コントロールは既定値では `Button` として機能します。</span><span class="sxs-lookup"><span data-stu-id="5116d-126">This would mean that by default, a `Button` control acts as a `Button`.</span></span> <span data-ttu-id="5116d-127">コントロールに別の役割がある場合、このプロパティをリセットできます。</span><span class="sxs-lookup"><span data-stu-id="5116d-127">You may want to reset this property if a control has another role.</span></span> <span data-ttu-id="5116d-128">たとえば、`PictureBox` コントロールを `Chart` として使用する場合、`PictureBox` ではなく `Chart` としてアクセシビリティ製品によって役割を報告するようにできます。</span><span class="sxs-lookup"><span data-stu-id="5116d-128">For example, you may be using a `PictureBox` control as a `Chart`, and you may want accessibility aids to report the role as a `Chart`, not as a `PictureBox`.</span></span> <span data-ttu-id="5116d-129">また、開発したカスタム コントロールにこのプロパティを指定することもできます。</span><span class="sxs-lookup"><span data-stu-id="5116d-129">You may also want to specify this property for custom controls you have developed.</span></span> <span data-ttu-id="5116d-130">このプロパティは、[プロパティ] ウィンドウで、または次のようにコードで設定できます。</span><span class="sxs-lookup"><span data-stu-id="5116d-130">This property may be set in the Properties window, or in code as follows:</span></span>

```vb
PictureBox1.AccessibleRole = AccessibleRole.Chart
```

```csharp
pictureBox1.AccessibleRole = AccessibleRole.Chart;
```

## <a name="see-also"></a><span data-ttu-id="5116d-131">関連項目</span><span class="sxs-lookup"><span data-stu-id="5116d-131">See also</span></span>

- [<span data-ttu-id="5116d-132">Label コントロールの概要 (Windows フォーム .NET)</span><span class="sxs-lookup"><span data-stu-id="5116d-132">Label control overview (Windows Forms .NET)</span></span>](labels.md)
- <xref:System.Windows.Forms.AccessibleObject>
- <xref:System.Windows.Forms.Control.AccessibilityObject?displayProperty=nameWithType>
- <xref:System.Windows.Forms.Control.AccessibleDefaultActionDescription?displayProperty=nameWithType>
- <xref:System.Windows.Forms.Control.AccessibleDescription?displayProperty=nameWithType>
- <xref:System.Windows.Forms.Control.AccessibleName?displayProperty=nameWithType>
- <xref:System.Windows.Forms.Control.AccessibleRole?displayProperty=nameWithType>
- <xref:System.Windows.Forms.AccessibleRole>
