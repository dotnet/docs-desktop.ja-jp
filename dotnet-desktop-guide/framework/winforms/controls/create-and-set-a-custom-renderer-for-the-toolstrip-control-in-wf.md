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
# <a name="how-to-create-and-set-a-custom-renderer-for-the-toolstrip-control-in-windows-forms"></a><span data-ttu-id="58183-102">方法: Windows フォームに ToolStrip コントロールのカスタム レンダラーを作成して設定する</span><span class="sxs-lookup"><span data-stu-id="58183-102">How to: Create and Set a Custom Renderer for the ToolStrip Control in Windows Forms</span></span>
<span data-ttu-id="58183-103"><xref:System.Windows.Forms.ToolStrip> コントロールを使うと、テーマとスタイルを簡単にサポートできます。</span><span class="sxs-lookup"><span data-stu-id="58183-103"><xref:System.Windows.Forms.ToolStrip> controls give easy support to themes and styles.</span></span> <span data-ttu-id="58183-104"><xref:System.Windows.Forms.ToolStrip.Renderer%2A?displayProperty=nameWithType>プロパティまたは <xref:System.Windows.Forms.ToolStripManager.Renderer%2A?displayProperty=nameWithType> プロパティをカスタムレンダラーに設定することによって、完全にカスタムの外観と動作 (ルックアンドフィール) を実現できます。</span><span class="sxs-lookup"><span data-stu-id="58183-104">You can achieve completely custom appearance and behavior (look and feel) by setting either the <xref:System.Windows.Forms.ToolStrip.Renderer%2A?displayProperty=nameWithType> property or the <xref:System.Windows.Forms.ToolStripManager.Renderer%2A?displayProperty=nameWithType> property to a custom renderer.</span></span>  
  
 <span data-ttu-id="58183-105">レンダラーは、個々の、、 <xref:System.Windows.Forms.ToolStrip> 、またはコントロールに割り当てることができ <xref:System.Windows.Forms.MenuStrip> <xref:System.Windows.Forms.ContextMenuStrip> <xref:System.Windows.Forms.StatusStrip> ます。また、プロパティをに設定することにより、プロパティを使用し <xref:System.Windows.Forms.ToolStripManager.Renderer%2A> てすべてのオブジェクトに影響を与えることができ <xref:System.Windows.Forms.ToolStrip.RenderMode%2A?displayProperty=nameWithType> <xref:System.Windows.Forms.ToolStripRenderMode.ManagerRenderMode?displayProperty=nameWithType> ます。</span><span class="sxs-lookup"><span data-stu-id="58183-105">You can assign renderers to each individual <xref:System.Windows.Forms.ToolStrip>, <xref:System.Windows.Forms.MenuStrip>, <xref:System.Windows.Forms.ContextMenuStrip>, or <xref:System.Windows.Forms.StatusStrip> control, or you can use the <xref:System.Windows.Forms.ToolStripManager.Renderer%2A> property to affect all objects by setting the <xref:System.Windows.Forms.ToolStrip.RenderMode%2A?displayProperty=nameWithType> property to <xref:System.Windows.Forms.ToolStripRenderMode.ManagerRenderMode?displayProperty=nameWithType>.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="58183-106"><xref:System.Windows.Forms.ToolStrip.RenderMode%2A><xref:System.Windows.Forms.ToolStripRenderMode.Custom>の値がでない場合にのみ、を返し <xref:System.Windows.Forms.ToolStrip.Renderer%2A?displayProperty=nameWithType> `null` ます。</span><span class="sxs-lookup"><span data-stu-id="58183-106"><xref:System.Windows.Forms.ToolStrip.RenderMode%2A> returns <xref:System.Windows.Forms.ToolStripRenderMode.Custom> only if the value of <xref:System.Windows.Forms.ToolStrip.Renderer%2A?displayProperty=nameWithType> is not `null`.</span></span>  
  
### <a name="to-create-a-custom-renderer"></a><span data-ttu-id="58183-107">カスタムレンダラーを作成するには</span><span class="sxs-lookup"><span data-stu-id="58183-107">To create a custom renderer</span></span>  
  
1. <span data-ttu-id="58183-108">クラスを拡張 <xref:System.Windows.Forms.ToolStripRenderer> します。</span><span class="sxs-lookup"><span data-stu-id="58183-108">Extend the <xref:System.Windows.Forms.ToolStripRenderer> class.</span></span>  
  
2. <span data-ttu-id="58183-109">適切にオーバーライドして、必要なカスタムレンダリングを実装します.. *.*</span><span class="sxs-lookup"><span data-stu-id="58183-109">Implement desired custom rendering by overriding appropriate *On…*</span></span> <span data-ttu-id="58183-110">members</span><span class="sxs-lookup"><span data-stu-id="58183-110">members</span></span>  
  
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
  
### <a name="to-set-the-custom-renderer-to-be-the-current-renderer"></a><span data-ttu-id="58183-111">カスタムレンダラーを現在のレンダラーに設定するには</span><span class="sxs-lookup"><span data-stu-id="58183-111">To set the custom renderer to be the current renderer</span></span>  
  
1. <span data-ttu-id="58183-112">1つのカスタムレンダラーを設定するには、 <xref:System.Windows.Forms.ToolStrip> <xref:System.Windows.Forms.ToolStrip.Renderer%2A?displayProperty=nameWithType> プロパティをカスタムレンダラーに設定します。</span><span class="sxs-lookup"><span data-stu-id="58183-112">To set the custom renderer for one <xref:System.Windows.Forms.ToolStrip>, set the <xref:System.Windows.Forms.ToolStrip.Renderer%2A?displayProperty=nameWithType> property to the custom renderer.</span></span>  
  
    ```vb  
    toolStrip1.Renderer = New RedTextRenderer()  
    ```  
  
    ```csharp  
    toolStrip1.Renderer = new RedTextRenderer();  
    ```  
  
2. <span data-ttu-id="58183-113">または、アプリケーションに含まれるすべてのクラスのカスタムレンダラーを設定するには、 <xref:System.Windows.Forms.ToolStrip> <xref:System.Windows.Forms.ToolStripManager.Renderer%2A?displayProperty=nameWithType> プロパティをカスタムレンダラーに設定し、プロパティをに設定し <xref:System.Windows.Forms.ToolStrip.RenderMode%2A> <xref:System.Windows.Forms.ToolStripRenderMode.ManagerRenderMode> ます。</span><span class="sxs-lookup"><span data-stu-id="58183-113">Or to set the custom renderer for all <xref:System.Windows.Forms.ToolStrip> classes contained in your application: Set the <xref:System.Windows.Forms.ToolStripManager.Renderer%2A?displayProperty=nameWithType> property to the custom renderer and set the <xref:System.Windows.Forms.ToolStrip.RenderMode%2A> property to <xref:System.Windows.Forms.ToolStripRenderMode.ManagerRenderMode>.</span></span>  
  
    ```vb  
    toolStrip1.RenderMode = ToolStripRenderMode.ManagerRenderMode  
    ToolStripManager.Renderer = New RedTextRenderer()  
    ```  
  
    ```csharp  
    toolStrip1.RenderMode = ToolStripRenderMode.ManagerRenderMode;  
    ToolStripManager.Renderer = new RedTextRenderer();  
    ```  
  
## <a name="see-also"></a><span data-ttu-id="58183-114">関連項目</span><span class="sxs-lookup"><span data-stu-id="58183-114">See also</span></span>

- <xref:System.Windows.Forms.ToolStripManager.Renderer%2A>
- <xref:System.Windows.Forms.ToolStripRenderer>
- <xref:System.Windows.Forms.ToolStrip.RenderMode%2A>
- [<span data-ttu-id="58183-115">ToolStrip コントロールの概要</span><span class="sxs-lookup"><span data-stu-id="58183-115">ToolStrip Control Overview</span></span>](toolstrip-control-overview-windows-forms.md)
- [<span data-ttu-id="58183-116">ToolStrip コントロールのアーキテクチャ</span><span class="sxs-lookup"><span data-stu-id="58183-116">ToolStrip Control Architecture</span></span>](toolstrip-control-architecture.md)
- [<span data-ttu-id="58183-117">ToolStrip テクノロジの概要</span><span class="sxs-lookup"><span data-stu-id="58183-117">ToolStrip Technology Summary</span></span>](toolstrip-technology-summary.md)
