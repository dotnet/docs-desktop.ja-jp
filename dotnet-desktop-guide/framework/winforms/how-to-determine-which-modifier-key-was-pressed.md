---
title: '方法: どの修飾子キーが押されたかを判断する'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- keyboard input
- shift keys
- events [Windows Forms], mouse
- Keys.ControlKey enumeration member
- keys [Windows Forms], control keys
- user input [Windows Forms], checking for keyboard
- keys [Windows Forms], determining last pressed
- keys [Windows Forms], shift keys
- keys [Windows Forms], modifier keys
- control keys
- keys [Windows Forms], alt keys
- alt keys
- Keys.Shift enumeration member
- events [Windows Forms], keyboard
- keyboards [Windows Forms], keyboard input
- Keys.Alt enumeration member
- modifier keys
ms.assetid: 1e184048-0ae3-4067-a200-d4ba31dbc2cb
ms.openlocfilehash: 9140834b4849ecb143ac57a6f6ae20e2d870859b
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/09/2020
ms.locfileid: "96974347"
---
# <a name="how-to-determine-which-modifier-key-was-pressed"></a>方法: どの修飾子キーが押されたかを判断する

ユーザーのキーストロークを受け入れるアプリケーションを作成する場合、SHIFT キー、ALT キー、CTRL キーなどの修飾子キーを監視することもできます。 修飾子キーを他のキーと組み合わせて押すか、マウスをクリックすると、アプリケーションが適切に応答できるようになります。 たとえば、文字 S が押されている場合、画面に "s" が表示されることがありますが、CTRL + S キーを押すと、現在のドキュメントが保存されている可能性があります。 イベントを処理する場合は、 <xref:System.Windows.Forms.Control.KeyDown> <xref:System.Windows.Forms.KeyEventArgs.Modifiers%2A> <xref:System.Windows.Forms.KeyEventArgs> イベントハンドラーによって受信されるのプロパティによって、どの修飾子キーが押されたかが指定されます。 または、 <xref:System.Windows.Forms.KeyEventArgs.KeyData%2A> のプロパティは、 <xref:System.Windows.Forms.KeyEventArgs> 押された文字と、ビットごとの or を組み合わせた修飾子キーを指定します。 ただし、イベントまたはマウスイベントを処理している場合、 <xref:System.Windows.Forms.Control.KeyPress> イベントハンドラーはこの情報を受け取りません。 この場合は、クラスのプロパティを使用する必要があり <xref:System.Windows.Forms.Control.ModifierKeys%2A> <xref:System.Windows.Forms.Control> ます。 どちらの場合も、適切な <xref:System.Windows.Forms.Keys> 値とテストする値のビットごとの and を実行する必要があります。 <xref:System.Windows.Forms.Keys>列挙体は各修飾子キーのバリエーションを提供するので、ビットごとの and を正しい値で実行することが重要です。 たとえば、shift キーは、、およびによって表され <xref:System.Windows.Forms.Keys.Shift> <xref:System.Windows.Forms.Keys.ShiftKey> <xref:System.Windows.Forms.Keys.RShiftKey> <xref:System.Windows.Forms.Keys.LShiftKey> ます。また、シフトを修飾子キーとしてテストするための正しい値は <xref:System.Windows.Forms.Keys.Shift> です。 同様に、CTRL と ALT を修飾子としてテストするには、 <xref:System.Windows.Forms.Keys.Control> それぞれとの値をそれぞれ使用する必要があり <xref:System.Windows.Forms.Keys.Alt> ます。  
  
> [!NOTE]
> Visual Basic プログラマは、プロパティを使用してキー情報にアクセスすることもできます。 <xref:Microsoft.VisualBasic.Devices.Computer.Keyboard%2A>  
  
### <a name="to-determine-which-modifier-key-was-pressed"></a>どの修飾子キーが押されたかを調べるには  
  
- ビットごとの `AND` 演算子とプロパティを使用し、列挙体の値を使用して、 <xref:System.Windows.Forms.Control.ModifierKeys%2A> <xref:System.Windows.Forms.Keys> 特定の修飾子キーが押されているかどうかを判断します。 次のコード例は、イベントハンドラー内で SHIFT キーが押されているかどうかを確認する方法を示して <xref:System.Windows.Forms.Control.KeyPress> います。  
  
     [!code-cpp[System.Windows.Forms.DetermineModifierKey#5](~/samples/snippets/cpp/VS_Snippets_Winforms/System.Windows.Forms.DetermineModifierKey/cpp/form1.cpp#5)]
     [!code-csharp[System.Windows.Forms.DetermineModifierKey#5](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DetermineModifierKey/CS/form1.cs#5)]
     [!code-vb[System.Windows.Forms.DetermineModifierKey#5](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DetermineModifierKey/VB/form1.vb#5)]  
  
## <a name="see-also"></a>関連項目

- <xref:System.Windows.Forms.Keys>
- <xref:System.Windows.Forms.Control.ModifierKeys%2A>
- [Windows フォーム アプリケーションにおけるキーボード入力](keyboard-input-in-a-windows-forms-application.md)
- [方法: Visual Basic で CapsLock が On であるかどうかを確認する](/previous-versions/visualstudio/visual-studio-2010/9c9d1fz9(v=vs.100))
