---
title: マウスポインター
ms.date: 03/30/2017
helpviewer_keywords:
- pointers [Windows Forms], setting
- mouse pointers
- mouse cursors
- mouse pointers [Windows Forms], setting
- cursors [Windows Forms], setting
- mouse [Windows Forms], cursors
ms.assetid: c3400d85-de5b-42e8-abc3-d6088d69ee53
ms.openlocfilehash: 4e8349effcd9b59045e39b763b4cb8b7d2fceb91
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/09/2020
ms.locfileid: "96983415"
---
# <a name="mouse-pointers-in-windows-forms"></a>Windows フォームにおけるマウス ポインター
マウス *ポインター* はカーソルとも呼ばれ、マウスを使用してユーザーが入力する画面上のフォーカスポイントを指定するビットマップです。 このトピックでは Windows フォームのマウスポインターの概要について説明し、マウスポインターを変更および制御する方法について説明します。  
  
## <a name="accessing-the-mouse-pointer"></a>マウスポインターへのアクセス  
 マウスポインターはクラスによって表され、各には、 <xref:System.Windows.Forms.Cursor> <xref:System.Windows.Forms.Control> <xref:System.Windows.Forms.Control.Cursor%2A?displayProperty=nameWithType> そのコントロールのポインターを指定するプロパティがあります。 クラスには、 <xref:System.Windows.Forms.Cursor> プロパティやプロパティなど、ポインターを記述するプロパティ、、、 <xref:System.Windows.Forms.Cursor.Position%2A> およびメソッドなど、 <xref:System.Windows.Forms.Cursor.HotSpot%2A> ポインターの外観を変更できるメソッドが含まれてい <xref:System.Windows.Forms.Cursor.Show%2A> <xref:System.Windows.Forms.Cursor.Hide%2A> <xref:System.Windows.Forms.Cursor.DrawStretched%2A> ます。  
  
## <a name="controlling-the-mouse-pointer"></a>マウスポインターの制御  
 場合によっては、マウスポインターを使用できる領域を制限したり、マウスの位置を変更したりすることができます。 のプロパティを使用して、マウスの現在の位置を取得または設定でき <xref:System.Windows.Forms.Cursor.Position%2A> <xref:System.Windows.Forms.Cursor> ます。 また、マウスポインターを使用してプロパティを設定できる領域を制限することもでき <xref:System.Windows.Forms.Cursor.Clip%2A> ます。 既定では、クリップ領域は画面全体です。  
  
## <a name="changing-the-mouse-pointer"></a>マウスポインターを変更する  
 マウスポインターを変更することは、ユーザーにフィードバックを提供するための重要な方法です。 たとえば、およびイベントのハンドラーでマウスポインターを変更して、 <xref:System.Windows.Forms.Control.MouseEnter> <xref:System.Windows.Forms.Control.MouseLeave> 計算が行われていることをユーザーに通知し、コントロール内のユーザーの操作を制限することができます。 場合によっては、アプリケーションがドラッグアンドドロップ操作に関係しているときなど、システムイベントが原因でマウスポインターが変化することがあります。  
  
 マウスポインターを変更する主な方法は、 <xref:System.Windows.Forms.Control.Cursor%2A?displayProperty=nameWithType> <xref:System.Windows.Forms.Control.DefaultCursor%2A> コントロールのプロパティまたはプロパティを新しいに設定することです <xref:System.Windows.Forms.Cursor> 。 マウスポインターを変更する例については、クラスのコード例を参照してください <xref:System.Windows.Forms.Cursor> 。 また、クラスは、 <xref:System.Windows.Forms.Cursors> <xref:System.Windows.Forms.Cursor> 手に似たポインターなど、さまざまな種類のポインターに対してオブジェクトのセットを公開します。 砂時計に似た待機ポインターを表示するには、マウスポインターがコントロール上にあるときは常に、 <xref:System.Windows.Forms.Control.UseWaitCursor%2A> クラスのプロパティを使用し <xref:System.Windows.Forms.Control> ます。  
  
## <a name="see-also"></a>関連項目

- <xref:System.Windows.Forms.Cursor>
- [Windows フォーム アプリケーションにおけるマウス入力](mouse-input-in-a-windows-forms-application.md)
- [Windows フォームにおけるドラッグ アンド ドロップ機能](drag-and-drop-functionality-in-windows-forms.md)
