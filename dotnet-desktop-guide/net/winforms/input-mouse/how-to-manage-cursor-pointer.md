---
title: マウス ポインターを管理する方法
description: .NET 用の Windows フォームで、マウス ポインターにアクセス、制御、および変更する方法について説明します。
ms.date: 10/26/2020
dev_langs:
- csharp
- vb
helpviewer_keywords:
- pointers [Windows Forms], setting
- mouse pointers
- mouse cursors
- mouse pointers [Windows Forms], setting
- cursors [Windows Forms], setting
- mouse [Windows Forms], cursors
ms.openlocfilehash: b4439c34bf7a7f41a94ce5ec5971520d9c82e469
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/09/2020
ms.locfileid: "96942298"
---
# <a name="manage-mouse-pointers-windows-forms-net"></a>マウス ポインターを管理する (Windows フォーム .NET)

マウス *ポインター* (カーソルと呼ばれることもあります) は、マウスで行われたユーザー入力に対し、画面上のフォーカス ポイントを指定するビットマップです。 このトピックでは、Windows フォームにおけるマウス ポインターの概要および、マウス ポインターを変更および制御する方法について説明します。

[!INCLUDE [desktop guide under construction](../../includes/desktop-guide-preview-note.md)]

## <a name="accessing-the-mouse-pointer"></a>マウス ポインターにアクセスする

マウス ポインターは <xref:System.Windows.Forms.Cursor> クラスによって表され、各 <xref:System.Windows.Forms.Control> には、そのコントロールのポインターを指定する <xref:System.Windows.Forms.Control.Cursor%2A?displayProperty=nameWithType> プロパティがあります。 <xref:System.Windows.Forms.Cursor> クラスには、<xref:System.Windows.Forms.Cursor.Position%2A> や <xref:System.Windows.Forms.Cursor.HotSpot%2A> プロパティなどのポインターを表すプロパティや、<xref:System.Windows.Forms.Cursor.Show%2A>、<xref:System.Windows.Forms.Cursor.Hide%2A>、<xref:System.Windows.Forms.Cursor.DrawStretched%2A> メソッドなどのポインターの外観を変更するメソッドがあります。

次の例では、カーソルがボタン上にあると、カーソルが非表示になります。

:::code language="csharp" source="snippets/how-to-manage-cursor-pointer/csharp/Form1.cs" id="ShowHideCursor":::
:::code language="vb" source="snippets/how-to-manage-cursor-pointer/vb/Form1.vb" id="ShowHideCursor":::

## <a name="controlling-the-mouse-pointer"></a>マウス ポインターを制御する

マウス ポインターを使用できる領域を制限したり、マウスの位置を変更したい場合があります。 <xref:System.Windows.Forms.Cursor> の <xref:System.Windows.Forms.Cursor.Position%2A> プロパティを使用すると、マウスの現在の位置を取得または設定できます。 また、<xref:System.Windows.Forms.Cursor.Clip%2A> プロパティを設定して、マウス ポインターを使用できる領域を制限することができます。 クリップ領域は、既定で画面全体です。

次の例では、クリック時にマウス ポインターが 2 つのボタン間に配置されます。

:::code language="csharp" source="snippets/how-to-manage-cursor-pointer/csharp/Form1.cs" id="MoveCursor":::
:::code language="vb" source="snippets/how-to-manage-cursor-pointer/vb/Form1.vb" id="MoveCursor":::

## <a name="changing-the-mouse-pointer"></a>マウス ポインターを変更する

ユーザーにフィードバックを提供する重要な方法として、マウス ポインターを変更する方法があります。 たとえば、<xref:System.Windows.Forms.Control.MouseEnter> および <xref:System.Windows.Forms.Control.MouseLeave> イベントのハンドラーでマウス ポインターを変更し、計算が行われていることをユーザーに通知して、コントロールでのユーザー操作を制限できます。 アプリケーションでドラッグアンドドロップ操作が行われている場合などのシステム イベントのために、マウス ポインターが変わることもあります。

マウス ポインターを変更する第一の方法は、コントロールの <xref:System.Windows.Forms.Control.Cursor%2A?displayProperty=nameWithType> または <xref:System.Windows.Forms.Control.DefaultCursor%2A> プロパティを新しい <xref:System.Windows.Forms.Cursor> に設定することです。 マウス ポインターの変更例については、<xref:System.Windows.Forms.Cursor> クラスのコード例を参照してください。 <xref:System.Windows.Forms.Cursors> クラスでは、これ以外に手のようなポインターなど、さまざまな種類のポインターに対する <xref:System.Windows.Forms.Cursor> オブジェクトのセットを公開しています。

次の例では、ボタンのマウス ポインターのカーソルが手の形に変更されます。

:::code language="csharp" source="snippets/how-to-manage-cursor-pointer/csharp/Form1.cs" id="SetControlCursor":::
:::code language="vb" source="snippets/how-to-manage-cursor-pointer/vb/Form1.vb" id="SetControlCursor":::

マウス ポインターがコントロール上にあるときに常に砂時計のような待機ポインターを表示するには、<xref:System.Windows.Forms.Control> クラスの <xref:System.Windows.Forms.Control.UseWaitCursor%2A> プロパティを使用します。

## <a name="see-also"></a>関連項目

- [マウスの使用の概要 (Windows フォーム .NET)](overview.md)
- [マウス イベントの使用 (Windows フォーム .NET)](events.md)
- [クリックとダブルクリックを区別する方法 (Windows フォーム .NET)](how-to-distinguish-between-clicks-and-double-clicks.md)
- [マウス イベントをシミュレートする方法 (Windows フォーム .NET)](how-to-simulate-events.md)
- <xref:System.Windows.Forms.Cursor?displayProperty=nameWithType>
- <xref:System.Windows.Forms.Cursor.Position%2A?displayProperty=nameWithType>
