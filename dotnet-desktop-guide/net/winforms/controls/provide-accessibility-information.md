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
# <a name="providing-accessibility-information-for-controls-windows-forms-net"></a>コントロールへのアクセシビリティ情報の提供 (Windows フォーム .NET)

ユーザー補助機能は専用のプログラムおよびデバイスで、障碍を持つユーザーがコンピューターをより効果的に使用するよう助けます。 たとえば、視覚障碍者のためのスクリーン リーダーや、マウスまたはキーボードではなく音声コマンド入力を利用するユーザーのための音声入力ユーティリティがあります。 これらのユーザー補助機能は、Windows フォーム コントロールによって公開されているアクセシビリティのプロパティと連携します。 それらのプロパティは以下のとおりです。

- <xref:System.Windows.Forms.AccessibleObject?displayProperty=fullName>
- <xref:System.Windows.Forms.Control.AccessibleDefaultActionDescription?displayProperty=fullName>
- <xref:System.Windows.Forms.Control.AccessibleDescription?displayProperty=fullName>
- <xref:System.Windows.Forms.Control.AccessibleName?displayProperty=fullName>
- <xref:System.Windows.Forms.AccessibleRole?displayProperty=fullName>

[!INCLUDE [desktop guide under construction](../../includes/desktop-guide-preview-note.md)]

## <a name="accessibilityobject-property"></a>AccessibilityObject プロパティ

この読み取り専用プロパティには <xref:System.Windows.Forms.AccessibleObject> インスタンスが含まれます。 `AccessibleObject` によって、コントロールの説明、画面上の位置、ナビゲーション能力、値に関する情報を提供する <xref:Accessibility.IAccessible> インターフェイスが実装されます。 デザイナーは、コントロールがフォームに追加されたときにこの値を設定します。

## <a name="accessibledefaultactiondescription-property"></a>AccessibleDefaultActionDescription プロパティ

この文字列は、コントロールの操作について説明します。 [プロパティ] ウィンドウには表示されず、コードでのみ設定できます。 次の例では、<xref:System.Windows.Forms.Control.AccessibleDefaultActionDescription> プロパティをボタン コントロールに設定します。

```vb
Button1.AccessibleDefaultActionDescription = "Closes the application."
```

```csharp
button1.AccessibleDefaultActionDescription = "Closes the application.";
```

## <a name="accessibledescription-property"></a>AccessibleDescription プロパティ

この文字列はコントロールについて説明します。 <xref:System.Windows.Forms.Control.AccessibleDescription> プロパティは、プロパティ ウィンドウで、または次のようにコードで設定できます。

```vb
Button1.AccessibleDescription = "A button with text 'Exit'."
```

```csharp
button1.AccessibleDescription = "A button with text 'Exit'";
```

## <a name="accessiblename-property"></a>AccessibleName プロパティ

これは、ユーザー補助機能に報告されたコントロールの名前です。 <xref:System.Windows.Forms.Control.AccessibleName> プロパティは、プロパティ ウィンドウで、または次のようにコードで設定できます。

```vb
Button1.AccessibleName = "Order"
```

```csharp
button1.AccessibleName = "Order";
```

## <a name="accessiblerole-property"></a>AccessibleRole プロパティ

このプロパティには <xref:System.Windows.Forms.AccessibleRole> 列挙型が含まれており、コントロールのユーザー インターフェイスの役割について説明します。 新しいコントロールは値が `Default` に設定されています。 つまり、`Button` コントロールは既定値では `Button` として機能します。 コントロールに別の役割がある場合、このプロパティをリセットできます。 たとえば、`PictureBox` コントロールを `Chart` として使用する場合、`PictureBox` ではなく `Chart` としてアクセシビリティ製品によって役割を報告するようにできます。 また、開発したカスタム コントロールにこのプロパティを指定することもできます。 このプロパティは、[プロパティ] ウィンドウで、または次のようにコードで設定できます。

```vb
PictureBox1.AccessibleRole = AccessibleRole.Chart
```

```csharp
pictureBox1.AccessibleRole = AccessibleRole.Chart;
```

## <a name="see-also"></a>関連項目

- [Label コントロールの概要 (Windows フォーム .NET)](labels.md)
- <xref:System.Windows.Forms.AccessibleObject>
- <xref:System.Windows.Forms.Control.AccessibilityObject?displayProperty=nameWithType>
- <xref:System.Windows.Forms.Control.AccessibleDefaultActionDescription?displayProperty=nameWithType>
- <xref:System.Windows.Forms.Control.AccessibleDescription?displayProperty=nameWithType>
- <xref:System.Windows.Forms.Control.AccessibleName?displayProperty=nameWithType>
- <xref:System.Windows.Forms.Control.AccessibleRole?displayProperty=nameWithType>
- <xref:System.Windows.Forms.AccessibleRole>
