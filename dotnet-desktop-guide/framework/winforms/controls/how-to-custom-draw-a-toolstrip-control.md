---
title: '方法: ToolStrip コントロールをカスタム描画する'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- toolbars [Windows Forms], custom drawing
- drawing [Windows Forms], owner
- ProfessionalColorTable class [Windows Forms], overriding
- examples [Windows Forms], toolbars
- drawing [Windows Forms], custom
- toolbars [Windows Forms], changing colors
- ToolStrip control [Windows Forms], drawing
- ToolStrip control [Windows Forms], changing colors
- custom drawing
- owner drawing
ms.assetid: 94e7d7bd-a752-441c-b5b3-7acf98881163
ms.openlocfilehash: 9f34c0d62370b72de2c3ddf68fcc5fada918faa3
ms.sourcegitcommit: d7d89e96c827b6e20d9353d34c0aa329fdae0144
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/03/2021
ms.locfileid: "99506673"
---
# <a name="how-to-custom-draw-a-toolstrip-control"></a><span data-ttu-id="21873-102">方法: ToolStrip コントロールをカスタム描画する</span><span class="sxs-lookup"><span data-stu-id="21873-102">How to: Custom Draw a ToolStrip Control</span></span>
<span data-ttu-id="21873-103"><xref:System.Windows.Forms.ToolStrip> コントロールに、次のレンダリング (描画) クラスが関連付けられています。</span><span class="sxs-lookup"><span data-stu-id="21873-103">The <xref:System.Windows.Forms.ToolStrip> controls have the following associated rendering (painting) classes:</span></span>  
  
- <span data-ttu-id="21873-104"><xref:System.Windows.Forms.ToolStripSystemRenderer> は、オペレーティング システムの外観とスタイルを提供します。</span><span class="sxs-lookup"><span data-stu-id="21873-104"><xref:System.Windows.Forms.ToolStripSystemRenderer> provides the appearance and style of your operating system.</span></span>  
  
- <span data-ttu-id="21873-105"><xref:System.Windows.Forms.ToolStripProfessionalRenderer> は、Microsoft Office の外観とスタイルを提供します。</span><span class="sxs-lookup"><span data-stu-id="21873-105"><xref:System.Windows.Forms.ToolStripProfessionalRenderer> provides the appearance and style of Microsoft Office.</span></span>  
  
- <span data-ttu-id="21873-106"><xref:System.Windows.Forms.ToolStripRenderer> は、その他の 2 つのレンダリング クラスの抽象基本クラスです。</span><span class="sxs-lookup"><span data-stu-id="21873-106"><xref:System.Windows.Forms.ToolStripRenderer> is the abstract base class for the other two rendering classes.</span></span>  
  
 <span data-ttu-id="21873-107"><xref:System.Windows.Forms.ToolStrip> をカスタムで描画 (オーナー描画) するために、レンダラー クラスの 1 つをオーバーライドして表示ロジックの特定の側面を変更できます。</span><span class="sxs-lookup"><span data-stu-id="21873-107">To custom draw (also known as owner draw) a <xref:System.Windows.Forms.ToolStrip>, you can override one of the renderer classes and change an aspect of the rendering logic.</span></span>  
  
 <span data-ttu-id="21873-108">次の手順は、カスタムの描画のさまざまな側面について説明します。</span><span class="sxs-lookup"><span data-stu-id="21873-108">The following procedures describe various aspects of custom drawing.</span></span>  
  
## <a name="switch-between-the-provided-renderers"></a><span data-ttu-id="21873-109">指定されたレンダラーを切り替える</span><span class="sxs-lookup"><span data-stu-id="21873-109">Switch between the provided renderers</span></span>
  
- <span data-ttu-id="21873-110"><xref:System.Windows.Forms.ToolStrip.RenderMode%2A> プロパティを任意の <xref:System.Windows.Forms.ToolStripRenderMode> の値に設定します。</span><span class="sxs-lookup"><span data-stu-id="21873-110">Set the <xref:System.Windows.Forms.ToolStrip.RenderMode%2A> property to the <xref:System.Windows.Forms.ToolStripRenderMode> value you want.</span></span>  
  
     <span data-ttu-id="21873-111"><xref:System.Windows.Forms.ToolStripRenderMode.ManagerRenderMode> と共に、静的な <xref:System.Windows.Forms.ToolStrip.RenderMode%2A> がアプリケーションのレンダラーを決定します。</span><span class="sxs-lookup"><span data-stu-id="21873-111">With <xref:System.Windows.Forms.ToolStripRenderMode.ManagerRenderMode>, the static <xref:System.Windows.Forms.ToolStrip.RenderMode%2A> determines the renderer for your application.</span></span> <span data-ttu-id="21873-112"><xref:System.Windows.Forms.ToolStripRenderMode> のその他の値は、<xref:System.Windows.Forms.ToolStripRenderMode.Custom>、<xref:System.Windows.Forms.ToolStripRenderMode.Professional>、および <xref:System.Windows.Forms.ToolStripRenderMode.System> です。</span><span class="sxs-lookup"><span data-stu-id="21873-112">The other values of <xref:System.Windows.Forms.ToolStripRenderMode> are <xref:System.Windows.Forms.ToolStripRenderMode.Custom>, <xref:System.Windows.Forms.ToolStripRenderMode.Professional>, and <xref:System.Windows.Forms.ToolStripRenderMode.System>.</span></span>  
  
## <a name="change-the-officestyle-borders"></a><span data-ttu-id="21873-113">Office スタイルの境界線を変更する</span><span class="sxs-lookup"><span data-stu-id="21873-113">Change the Office–style borders</span></span>
  
- <span data-ttu-id="21873-114"><xref:System.Windows.Forms.ToolStripProfessionalRenderer.OnRenderToolStripBorder%2A?displayProperty=nameWithType> をオーバーライドしますが、基本クラスは呼び出しません。</span><span class="sxs-lookup"><span data-stu-id="21873-114">Override <xref:System.Windows.Forms.ToolStripProfessionalRenderer.OnRenderToolStripBorder%2A?displayProperty=nameWithType>, but do not call the base class.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="21873-115"><xref:System.Windows.Forms.ToolStripRenderer>、<xref:System.Windows.Forms.ToolStripSystemRenderer>、および <xref:System.Windows.Forms.ToolStripProfessionalRenderer> に対して、このメソッドのバージョンがあります。</span><span class="sxs-lookup"><span data-stu-id="21873-115">There is a version of this method for <xref:System.Windows.Forms.ToolStripRenderer>, <xref:System.Windows.Forms.ToolStripSystemRenderer>, and <xref:System.Windows.Forms.ToolStripProfessionalRenderer>.</span></span>  
  
## <a name="change-the-professionalcolortable"></a><span data-ttu-id="21873-116">ProfessionalColorTable を変更する</span><span class="sxs-lookup"><span data-stu-id="21873-116">Change the ProfessionalColorTable</span></span>
  
- <span data-ttu-id="21873-117"><xref:System.Windows.Forms.ProfessionalColorTable> をオーバーライドして必要な色を変更します。</span><span class="sxs-lookup"><span data-stu-id="21873-117">Override <xref:System.Windows.Forms.ProfessionalColorTable> and change the colors you want.</span></span>  

  ```csharp
  public partial class Form1 : Form
  {
      public Form1()
      {
          InitializeComponent();
      }
  
      private void Form1_Load(object sender, EventArgs e)
      {
          var colorTable = new MyColorTable();
          toolStrip1.Renderer = new ToolStripProfessionalRenderer(colorTable);
      }
  
      class MyColorTable: ProfessionalColorTable
      {
          public override System.Drawing.Color ButtonPressedGradientBegin => Color.Red;
          public override System.Drawing.Color ButtonPressedGradientMiddle => Color.Blue;
          public override System.Drawing.Color ButtonPressedGradientEnd => Color.Green;
          public override System.Drawing.Color ButtonSelectedGradientBegin => Color.Yellow;
          public override System.Drawing.Color ButtonSelectedGradientMiddle => Color.Orange;
          public override System.Drawing.Color ButtonSelectedGradientEnd => Color.Violet;
      }
  }
  ```

  ```vb
  Public Class Form1
      Private Sub Form1_Load(sender As Object, e As EventArgs) Handles MyBase.Load
          Dim colorTable As New MyColorTable
          ToolStrip1.Renderer = New ToolStripProfessionalRenderer(colorTable)
      End Sub
  
      Class MyColorTable
          Inherits ProfessionalColorTable
  
          Public Overrides ReadOnly Property ButtonPressedGradientBegin() As System.Drawing.Color
              Get
                  Return Color.Red
              End Get
          End Property
  
          Public Overrides ReadOnly Property ButtonPressedGradientMiddle() As System.Drawing.Color
              Get
                  Return Color.Blue
              End Get
          End Property
  
          Public Overrides ReadOnly Property ButtonPressedGradientEnd() As System.Drawing.Color
              Get
                  Return Color.Green
              End Get
          End Property
  
          Public Overrides ReadOnly Property ButtonSelectedGradientBegin() As System.Drawing.Color
              Get
                  Return Color.Yellow
              End Get
          End Property
  
          Public Overrides ReadOnly Property ButtonSelectedGradientMiddle() As System.Drawing.Color
              Get
                  Return Color.Orange
              End Get
          End Property
  
          Public Overrides ReadOnly Property ButtonSelectedGradientEnd() As System.Drawing.Color
              Get
                  Return Color.Violet
              End Get
          End Property
      End Class
  End Class
  ```
  
## <a name="change-rendering-for-all-toolstrips"></a><span data-ttu-id="21873-118">すべての ToolStrips の表示を変更する</span><span class="sxs-lookup"><span data-stu-id="21873-118">Change rendering for all ToolStrips</span></span>
  
1. <span data-ttu-id="21873-119"><xref:System.Windows.Forms.ToolStripManager.RenderMode%2A?displayProperty=nameWithType> プロパティを使用して、設定されているレンダラーのいずれかを選択します。</span><span class="sxs-lookup"><span data-stu-id="21873-119">Use the <xref:System.Windows.Forms.ToolStripManager.RenderMode%2A?displayProperty=nameWithType> property to choose one of the provided renderers.</span></span>  
  
2. <span data-ttu-id="21873-120"><xref:System.Windows.Forms.ToolStripManager.Renderer%2A?displayProperty=nameWithType> を使用して、カスタム レンダラーを割り当てます。</span><span class="sxs-lookup"><span data-stu-id="21873-120">Use <xref:System.Windows.Forms.ToolStripManager.Renderer%2A?displayProperty=nameWithType> to assign a custom renderer.</span></span>  
  
3. <span data-ttu-id="21873-121"><xref:System.Windows.Forms.ToolStrip.RenderMode%2A?displayProperty=nameWithType> が既定値の <xref:System.Windows.Forms.ToolStripRenderMode.ManagerRenderMode> に設定されていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="21873-121">Ensure that <xref:System.Windows.Forms.ToolStrip.RenderMode%2A?displayProperty=nameWithType> is set to the default value of <xref:System.Windows.Forms.ToolStripRenderMode.ManagerRenderMode>.</span></span>  
  
## <a name="turn-off-the-office-colors"></a><span data-ttu-id="21873-122">オフィスの色をオフにする</span><span class="sxs-lookup"><span data-stu-id="21873-122">Turn off the Office colors</span></span>
  
- <span data-ttu-id="21873-123"><xref:System.Windows.Forms.ToolStripManager.VisualStylesEnabled%2A?displayProperty=nameWithType> を `false` に設定します。</span><span class="sxs-lookup"><span data-stu-id="21873-123">Set <xref:System.Windows.Forms.ToolStripManager.VisualStylesEnabled%2A?displayProperty=nameWithType> to `false`.</span></span>  
  
## <a name="turn-off-the-office-colors-for-one-toolstrip"></a><span data-ttu-id="21873-124">1つの ToolStrip でオフィスの色をオフにする</span><span class="sxs-lookup"><span data-stu-id="21873-124">Turn off the Office colors for one ToolStrip</span></span>
  
- <span data-ttu-id="21873-125">次のコード例に似たコードを使用します。</span><span class="sxs-lookup"><span data-stu-id="21873-125">Use code similar to the following code example.</span></span>  

  ```csharp
  ProfessionalColorTable colorTable = new ProfessionalColorTable();
  colorTable.UseSystemColors = true;
  toolStrip1.Renderer = new ToolStripProfessionalRenderer(colorTable);
  ```
  
  ```vb
  Dim colorTable As New ProfessionalColorTable
  colorTable.UseSystemColors = True
  ToolStrip1.Renderer = new ToolStripProfessionalRenderer(colorTable)
  ```
  
## <a name="see-also"></a><span data-ttu-id="21873-126">関連項目</span><span class="sxs-lookup"><span data-stu-id="21873-126">See also</span></span>

- <xref:System.Windows.Forms.ToolStripSystemRenderer>
- <xref:System.Windows.Forms.ToolStripProfessionalRenderer>
- <xref:System.Windows.Forms.ToolStripRenderer>
- [<span data-ttu-id="21873-127">組み込みのオーナー描画サポートを備えたコントロール</span><span class="sxs-lookup"><span data-stu-id="21873-127">Controls with Built-In Owner-Drawing Support</span></span>](controls-with-built-in-owner-drawing-support.md)
- [<span data-ttu-id="21873-128">方法: Windows フォームで ToolStrip コントロールのカスタムレンダラーを作成および設定する</span><span class="sxs-lookup"><span data-stu-id="21873-128">How to: Create and Set a Custom Renderer for the ToolStrip Control in Windows Forms</span></span>](create-and-set-a-custom-renderer-for-the-toolstrip-control-in-wf.md)
- [<span data-ttu-id="21873-129">ToolStrip コントロールの概要</span><span class="sxs-lookup"><span data-stu-id="21873-129">ToolStrip Control Overview</span></span>](toolstrip-control-overview-windows-forms.md)
