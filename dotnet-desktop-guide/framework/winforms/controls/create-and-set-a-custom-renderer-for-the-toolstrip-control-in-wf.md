---
title: '方法: ToolStrip コントロールのカスタムレンダラーを作成および設定する'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- ToolStrip control [Windows Forms], custom rendering
- toolbars [Windows Forms], rendering
- examples [Windows Forms], toolbars
- ToolStrip control [Windows Forms], rendering
ms.assetid: 88a804ba-679f-4ba3-938a-0dc396199c5b
ms.openlocfilehash: 49db0d785155f19b7220ac64011eaf4253aaa7e9
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/09/2020
ms.locfileid: "96974259"
---
# <a name="how-to-create-and-set-a-custom-renderer-for-the-toolstrip-control-in-windows-forms"></a>方法: Windows フォームに ToolStrip コントロールのカスタム レンダラーを作成して設定する
<xref:System.Windows.Forms.ToolStrip> コントロールを使うと、テーマとスタイルを簡単にサポートできます。 <xref:System.Windows.Forms.ToolStrip.Renderer%2A?displayProperty=nameWithType>プロパティまたは <xref:System.Windows.Forms.ToolStripManager.Renderer%2A?displayProperty=nameWithType> プロパティをカスタムレンダラーに設定することによって、完全にカスタムの外観と動作 (ルックアンドフィール) を実現できます。  
  
 レンダラーは、個々の、、 <xref:System.Windows.Forms.ToolStrip> 、またはコントロールに割り当てることができ <xref:System.Windows.Forms.MenuStrip> <xref:System.Windows.Forms.ContextMenuStrip> <xref:System.Windows.Forms.StatusStrip> ます。また、プロパティをに設定することにより、プロパティを使用し <xref:System.Windows.Forms.ToolStripManager.Renderer%2A> てすべてのオブジェクトに影響を与えることができ <xref:System.Windows.Forms.ToolStrip.RenderMode%2A?displayProperty=nameWithType> <xref:System.Windows.Forms.ToolStripRenderMode.ManagerRenderMode?displayProperty=nameWithType> ます。  
  
> [!NOTE]
> <xref:System.Windows.Forms.ToolStrip.RenderMode%2A><xref:System.Windows.Forms.ToolStripRenderMode.Custom>の値がでない場合にのみ、を返し <xref:System.Windows.Forms.ToolStrip.Renderer%2A?displayProperty=nameWithType> `null` ます。  
  
### <a name="to-create-a-custom-renderer"></a>カスタムレンダラーを作成するには  
  
1. クラスを拡張 <xref:System.Windows.Forms.ToolStripRenderer> します。  
  
2. 適切にオーバーライドして、必要なカスタムレンダリングを実装します.. *.* members  
  
    ```vb  
    Public Class RedTextRenderer  
        Inherits System.Windows.Forms.ToolStripRenderer  
        Protected Overrides Sub OnRenderItemText(ByVal e As _  
            ToolStripItemTextRenderEventArgs)
            e.TextColor = Color.Red  
            e.TextFont = New Font("Helvetica", 7, FontStyle.Bold)  
            MyBase.OnRenderItemText(e)  
        End Sub  
    End Class  
    ```  
  
    ```csharp  
    public class RedTextRenderer : _  
        System.Windows.Forms.ToolStripRenderer  
    {  
        protected override void _  
            OnRenderItemText(ToolStripItemTextRenderEventArgs e)  
        {  
            e.TextColor = Color.Red;  
            e.TextFont = new Font("Helvetica", 7, FontStyle.Bold);  
           base.OnRenderItemText(e);  
        }  
    }  
    ```  
  
### <a name="to-set-the-custom-renderer-to-be-the-current-renderer"></a>カスタムレンダラーを現在のレンダラーに設定するには  
  
1. 1つのカスタムレンダラーを設定するには、 <xref:System.Windows.Forms.ToolStrip> <xref:System.Windows.Forms.ToolStrip.Renderer%2A?displayProperty=nameWithType> プロパティをカスタムレンダラーに設定します。  
  
    ```vb  
    toolStrip1.Renderer = New RedTextRenderer()  
    ```  
  
    ```csharp  
    toolStrip1.Renderer = new RedTextRenderer();  
    ```  
  
2. または、アプリケーションに含まれるすべてのクラスのカスタムレンダラーを設定するには、 <xref:System.Windows.Forms.ToolStrip> <xref:System.Windows.Forms.ToolStripManager.Renderer%2A?displayProperty=nameWithType> プロパティをカスタムレンダラーに設定し、プロパティをに設定し <xref:System.Windows.Forms.ToolStrip.RenderMode%2A> <xref:System.Windows.Forms.ToolStripRenderMode.ManagerRenderMode> ます。  
  
    ```vb  
    toolStrip1.RenderMode = ToolStripRenderMode.ManagerRenderMode  
    ToolStripManager.Renderer = New RedTextRenderer()  
    ```  
  
    ```csharp  
    toolStrip1.RenderMode = ToolStripRenderMode.ManagerRenderMode;  
    ToolStripManager.Renderer = new RedTextRenderer();  
    ```  
  
## <a name="see-also"></a>関連項目

- <xref:System.Windows.Forms.ToolStripManager.Renderer%2A>
- <xref:System.Windows.Forms.ToolStripRenderer>
- <xref:System.Windows.Forms.ToolStrip.RenderMode%2A>
- [ToolStrip コントロールの概要](toolstrip-control-overview-windows-forms.md)
- [ToolStrip コントロールのアーキテクチャ](toolstrip-control-architecture.md)
- [ToolStrip テクノロジの概要](toolstrip-technology-summary.md)
