---
title: コントロール内のイベント
ms.date: 03/30/2017
helpviewer_keywords:
- events [Windows Forms], custom controls (using code)
- custom controls [Windows Forms], events overview (using code)
ms.assetid: 7e3d1379-87aa-437c-afce-c99454eff30e
ms.openlocfilehash: 27edaf2d895453d64d35ba6eff724df583a9b7dd
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/09/2020
ms.locfileid: "96981060"
---
# <a name="events-in-windows-forms-controls"></a>Windows フォーム コントロールのイベント

Windows フォームコントロールは、から60を超えるイベントを継承 <xref:System.Windows.Forms.Control?displayProperty=nameWithType> します。 これには、 <xref:System.Windows.Forms.Control.Paint> コントロールを描画するイベント、イベントやイベントなどのウィンドウの表示に関連するイベント、 <xref:System.Windows.Forms.Control.Resize> <xref:System.Windows.Forms.Control.Layout> 低レベルのマウスイベントとキーボードイベントなどがあります。 一部の下位イベントは、によって <xref:System.Windows.Forms.Control> 、やなどのセマンティックイベントに合成され <xref:System.Windows.Forms.Control.Click> <xref:System.Windows.Forms.Control.DoubleClick> ます。 継承されたイベントの詳細については、「」を参照してください <xref:System.Windows.Forms.Control> 。  
  
 継承されたイベントの機能をカスタム コントロールでオーバーライドする必要がある場合、デリゲートを結び付けるのではなく、継承された `On`*EventName* メソッドをオーバーライドします。 .NET Framework でのイベント モデルに詳しくない場合は、「[コンポーネントからのイベントの生成](/previous-versions/visualstudio/visual-studio-2013/sh2e3k5z(v=vs.120))」を参照してください。  
  
## <a name="see-also"></a>関連項目

- [OnPaint メソッドのオーバーライド](overriding-the-onpaint-method.md)
- [ユーザーの入力の処理](handling-user-input.md)
- [イベントの定義](defining-an-event-in-windows-forms-controls.md)
- [イベント](/dotnet/standard/events/index)
