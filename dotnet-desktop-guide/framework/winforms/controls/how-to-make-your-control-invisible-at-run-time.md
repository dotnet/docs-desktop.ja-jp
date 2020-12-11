---
title: '方法: 実行時にコントロールを非表示にする'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- controls [Windows Forms], making invisible at run time
- invisible controls
- user controls [Windows Forms], invisible
- custom controls [Windows Forms], invisible
- run time [Windows Forms], making controls invisible
ms.assetid: 69eb2e72-32f5-4f79-a157-c2c5f60c1628
ms.openlocfilehash: e9af529541a40a951d6defea180dbbef04c8f3be
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/09/2020
ms.locfileid: "96974809"
---
# <a name="how-to-make-your-control-invisible-at-run-time"></a>方法: 実行時にコントロールを非表示にする
実行時に非表示になるユーザーコントロールを作成することが必要になる場合があります。 たとえば、アラームが鳴っている場合を除き、アラーム時計のコントロールは非表示になる場合があります。 これは、プロパティを設定することによって簡単に実現 <xref:System.Windows.Forms.Control.Visible%2A> できます。 <xref:System.Windows.Forms.Control.Visible%2A>プロパティがの場合 `true` 、コントロールは通常どおり表示されます。 `false`の場合、コントロールは非表示になります。 コントロールのコードは非表示のままでも実行できますが、ユーザーインターフェイスを使用してコントロールと対話することはできません。 ユーザー入力に応答する非表示コントロール (マウスのクリックなど) を作成する場合は、透過的なコントロールを作成する必要があります。 詳細については、「 [コントロールに透明な背景を付ける](how-to-give-your-control-a-transparent-background.md)」を参照してください。  
  
### <a name="to-make-your-control-invisible-at-run-time"></a>実行時にコントロールを非表示にするには  
  
1. <xref:System.Windows.Forms.Control.Visible%2A> プロパティを `false`に設定します。  
  
    ```vb  
    ' To set the Visible property from within your object's own code.  
    Me.Visible = False  
    ' To set the Visible property from another object.  
    myControl1.Visible = False  
    ```  
  
    ```csharp  
    // To set the Visible property from within your object's own code.  
    this.Visible = false;  
    // To set the Visible property from another object.  
    myControl1.Visible = false;  
    ```  
  
## <a name="see-also"></a>関連項目

- <xref:System.Windows.Forms.Control.Visible%2A>
- [.NET Framework を使用したカスタム Windows フォーム コントロールの開発](developing-custom-windows-forms-controls.md)
- [方法: コントロールに透明な背景を指定する](how-to-give-your-control-a-transparent-background.md)
