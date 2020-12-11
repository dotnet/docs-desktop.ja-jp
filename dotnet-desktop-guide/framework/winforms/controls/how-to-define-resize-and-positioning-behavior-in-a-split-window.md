---
title: '方法: 分割ウィンドウでのサイズ変更および位置指定動作を定義する'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- split windows [Windows Forms], resizing
- splitter windows [Windows Forms], resizing
- SplitContainer control [Windows Forms], resizing
ms.assetid: 9bf73f36-ed2d-4a02-b15a-0770eff4fdfa
ms.openlocfilehash: 8cdcfdfaa135a92ed6a6e96d4a72de2c97f2493d
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/09/2020
ms.locfileid: "96980875"
---
# <a name="how-to-define-resize-and-positioning-behavior-in-a-split-window"></a>方法: 分割ウィンドウでのサイズ変更および位置指定動作を定義する
コントロールのパネルは、 <xref:System.Windows.Forms.SplitContainer> ユーザーがサイズを変更して操作するのに適しています。 ただし、スプリッターがどこに配置され、どこに移動できるのかをプログラムで制御する必要がある場合もあります。  
  
 <xref:System.Windows.Forms.SplitContainer.SplitterIncrement%2A>コントロールのプロパティとその他のプロパティを使用すると、 <xref:System.Windows.Forms.SplitContainer> ユーザーインターフェイスの動作をニーズに合わせて細かく制御できます。 次の表はそのようなプロパティです。  
  
|名前|説明|  
|----------|-----------------|  
|<xref:System.Windows.Forms.SplitContainer.IsSplitterFixed%2A> プロパティ|キーボードまたはマウスを使ってスプリッターを移動可能にするかどうかを決定します。|  
|<xref:System.Windows.Forms.SplitContainer.SplitterDistance%2A> プロパティ|左端または上端から移動可能スプリッターバーまでの距離をピクセル単位で決定します。|  
|<xref:System.Windows.Forms.SplitContainer.SplitterIncrement%2A> プロパティ|ユーザーがスプリッターを移動できる最小距離をピクセル単位で指定します。|  
  
 次の例では、 <xref:System.Windows.Forms.SplitContainer.SplitterIncrement%2A> "スナップスプリッター" 効果を作成するようにプロパティを変更しています。ユーザーがスプリッターをドラッグすると、既定の1ではなく、10ピクセル単位で増加します。  
  
### <a name="to-define-splitcontainer-resize-behavior"></a>SplitContainer のサイズ変更動作を定義するには  
  
1. プロシージャでは、プロパティを目的のサイズに設定して、 <xref:System.Windows.Forms.SplitContainer.SplitterIncrement%2A> スプリッターの "スナップ" 動作が実現されるようにします。  
  
     次のコード例では、フォームのイベント内で、 <xref:System.Windows.Forms.Form.Load> コントロール内のスプリッター <xref:System.Windows.Forms.SplitContainer> が、ドラッグ時に10ピクセルジャンプするように設定されています。  
  
    ```vb  
    Private Sub Form1_Load(ByVal sender As System.Object, _  
        ByVal e As System.EventArgs) Handles MyBase.Load  
        Dim splitSnapper as new SplitContainer()  
        splitSnapper.SplitterIncrement = 10  
        splitSnapper.Dock = DockStyle.Fill  
        splitSnapper.Parent = me  
    End Sub  
    ```  
  
    ```csharp  
    private void Form1_Load(System.Object sender, System.EventArgs e)  
    {  
        SplitContainer splitSnapper = new SplitContainer();  
        splitSnapper.SplitterIncrement = 10;  
        splitSnapper.Dock = DockStyle.Fill;  
        splitSnapper.Parent = this;  
    }  
    ```  
  
     (Visual C#)フォームのコンストラクターに次のコードを配置して、イベントハンドラーを登録します。  
  
    ```csharp  
    this.Load += new System.EventHandler(this.Form1_Load);  
    ```  
  
     分割線を左または右に少し移動すると、認識効果は得られません。ただし、いずれかの方向でマウスポインターが10ピクセルになると、スプリッターは新しい位置にスナップされます。  
  
## <a name="see-also"></a>関連項目

- <xref:System.Windows.Forms.SplitContainer>
- <xref:System.Windows.Forms.SplitContainer.SplitterIncrement%2A>
