---
title: Visual Studio で InkCanvas を作成する
ms.date: 08/15/2018
dev_langs:
- csharp
- vb
helpviewer_keywords:
- procedural code in lieu of XAML [WPF]
- XAML [WPF], procedural code in lieu of
- InkCanvas (WPF)
ms.assetid: 760332dd-594a-475d-865b-01659db8cab7
ms.openlocfilehash: b8087d6db04f7024b9ee48f28002bee04045a14b
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/09/2020
ms.locfileid: "96984363"
---
# <a name="get-started-with-ink-in-wpf"></a><span data-ttu-id="7976d-102">WPF でのインクの概要</span><span class="sxs-lookup"><span data-stu-id="7976d-102">Get Started with Ink in WPF</span></span>

<span data-ttu-id="7976d-103">Windows Presentation Foundation (WPF) には、デジタル インクをアプリに簡単に組み込むことができるインク機能があります。</span><span class="sxs-lookup"><span data-stu-id="7976d-103">Windows Presentation Foundation (WPF) has an ink feature that makes it easy to incorporate digital ink into your app.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="7976d-104">必須コンポーネント</span><span class="sxs-lookup"><span data-stu-id="7976d-104">Prerequisites</span></span>

<span data-ttu-id="7976d-105">次の例を使用するには、まず [Visual Studio](https://visualstudio.microsoft.com/downloads/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=inline+link&utm_content=download+vs2019) をインストールします。</span><span class="sxs-lookup"><span data-stu-id="7976d-105">To use the following examples, first install [Visual Studio](https://visualstudio.microsoft.com/downloads/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=inline+link&utm_content=download+vs2019).</span></span> <span data-ttu-id="7976d-106">また、基本的な WPF アプリの作成方法を理解するためにも役立ちます。</span><span class="sxs-lookup"><span data-stu-id="7976d-106">It also helps to know how to write basic WPF apps.</span></span> <span data-ttu-id="7976d-107">WPF の概要については、「[チュートリアル: 初めての WPF デスクトップ アプリケーション](../getting-started/walkthrough-my-first-wpf-desktop-application.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="7976d-107">For help getting started with WPF, see [Walkthrough: My first WPF desktop application](../getting-started/walkthrough-my-first-wpf-desktop-application.md).</span></span>

## <a name="quick-start"></a><span data-ttu-id="7976d-108">クイック スタート</span><span class="sxs-lookup"><span data-stu-id="7976d-108">Quick Start</span></span>

<span data-ttu-id="7976d-109">このセクションは、インクを収集する簡単な WPF アプリケーションを作成するために役立ちます。</span><span class="sxs-lookup"><span data-stu-id="7976d-109">This section helps you write a simple WPF application that collects ink.</span></span>

### <a name="got-ink"></a><span data-ttu-id="7976d-110">インクを用意できたら</span><span class="sxs-lookup"><span data-stu-id="7976d-110">Got Ink?</span></span>

<span data-ttu-id="7976d-111">インクをサポートする WPF アプリを作成するには:</span><span class="sxs-lookup"><span data-stu-id="7976d-111">To create a WPF app that supports ink:</span></span>

1. <span data-ttu-id="7976d-112">Visual Studio を開きます。</span><span class="sxs-lookup"><span data-stu-id="7976d-112">Open Visual Studio.</span></span>

2. <span data-ttu-id="7976d-113">新しい **WPF アプリ** を作成します。</span><span class="sxs-lookup"><span data-stu-id="7976d-113">Create a new **WPF App**.</span></span>

   <span data-ttu-id="7976d-114">**[新しいプロジェクト]** ダイアログで、 **[インストール済み]**  >  **[Visual C#]** または **[Visual Basic]**  >  **[Windows デスクトップ]** カテゴリを展開します。</span><span class="sxs-lookup"><span data-stu-id="7976d-114">In the **New Project** dialog, expand the **Installed** > **Visual C#** or **Visual Basic** > **Windows Desktop** category.</span></span> <span data-ttu-id="7976d-115">次に、 **[WPF アプリ (.NET Framework)]** アプリ テンプレートを選択します。</span><span class="sxs-lookup"><span data-stu-id="7976d-115">Then, select the **WPF App (.NET Framework)** app template.</span></span> <span data-ttu-id="7976d-116">名前を入力し、 **[OK]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="7976d-116">Enter a name, and then select **OK**.</span></span>

   <span data-ttu-id="7976d-117">Visual Studio によってプロジェクトが作成され、デザイナーで *MainWindow.xaml* が開きます。</span><span class="sxs-lookup"><span data-stu-id="7976d-117">Visual Studio creates the project, and *MainWindow.xaml* opens in the designer.</span></span>

3. <span data-ttu-id="7976d-118">`<Grid>` タグの間に「`<InkCanvas/>`」と入力します。</span><span class="sxs-lookup"><span data-stu-id="7976d-118">Type `<InkCanvas/>` between the `<Grid>` tags.</span></span>

   ![InkCanvas タグを使用する XAML デザイナー](./media/getting-started-with-ink/inkcanvas-xaml.png)

4. <span data-ttu-id="7976d-120">**F5** キーを押して、デバッガーでアプリケーションを起動します。</span><span class="sxs-lookup"><span data-stu-id="7976d-120">Press **F5** to launch your application in the debugger.</span></span>

5. <span data-ttu-id="7976d-121">スタイラスまたはマウスを使用して、ウィンドウに「**hello world**」と入力します。</span><span class="sxs-lookup"><span data-stu-id="7976d-121">Using a stylus or mouse, write **hello world** in the window.</span></span>

<span data-ttu-id="7976d-122">これで、わずか 12 回のキーストロークで "hello world" アプリケーションに相当するインクを作成できました。</span><span class="sxs-lookup"><span data-stu-id="7976d-122">You've written the ink equivalent of a "hello world" application with only 12 keystrokes!</span></span>

### <a name="spice-up-your-app"></a><span data-ttu-id="7976d-123">アプリにスパイスを加える</span><span class="sxs-lookup"><span data-stu-id="7976d-123">Spice Up Your App</span></span>

<span data-ttu-id="7976d-124">WPF のいくつかの機能を活用してみましょう。</span><span class="sxs-lookup"><span data-stu-id="7976d-124">Let’s take advantage of some features of the WPF.</span></span> <span data-ttu-id="7976d-125">開始タグと終了タグの間のすべて \<Window> を、次のマークアップに置き換えます。</span><span class="sxs-lookup"><span data-stu-id="7976d-125">Replace everything between the opening and closing \<Window> tags with the following markup:</span></span>

```xaml
<Page>
  <InkCanvas Name="myInkCanvas" MouseRightButtonUp="RightMouseUpHandler">
    <InkCanvas.Background>
      <LinearGradientBrush>
        <GradientStop Color="Yellow" Offset="0.0" />
          <GradientStop Color="Blue" Offset="0.5" />
            <GradientStop Color="HotPink" Offset="1.0" />
              </LinearGradientBrush>
    </InkCanvas.Background>
  </InkCanvas>
</Page>
```

<span data-ttu-id="7976d-126">この XAML によって、インク サーフェイスにグラデーション ブラシの背景が作成されます。</span><span class="sxs-lookup"><span data-stu-id="7976d-126">This XAML creates a gradient brush background on your inking surface.</span></span>

![WPF アプリのインク サーフェイスのグラデーション カラー](./media/getting-started-with-ink/gradient-colors.png)

### <a name="add-some-code-behind-the-xaml"></a><span data-ttu-id="7976d-128">XAML の背後にコードを追加する</span><span class="sxs-lookup"><span data-stu-id="7976d-128">Add Some Code Behind the XAML</span></span>

<span data-ttu-id="7976d-129">XAML を使用すると、ユーザー インターフェイスの設計がとても簡単になりますが、実際のアプリケーションでは、イベントを処理するためのコードを追加する必要があります。</span><span class="sxs-lookup"><span data-stu-id="7976d-129">While XAML makes it very easy to design the user interface, any real-world application needs to add code to handle events.</span></span> <span data-ttu-id="7976d-130">マウスの右クリックに応じてインクを拡大する簡単な例を次に示します。</span><span class="sxs-lookup"><span data-stu-id="7976d-130">Here is a simple example that zooms in on the ink in response to a right-click from a mouse.</span></span>

1. <span data-ttu-id="7976d-131">XAML で `MouseRightButtonUp` ハンドラーを設定します。</span><span class="sxs-lookup"><span data-stu-id="7976d-131">Set the `MouseRightButtonUp` handler in your XAML:</span></span>

   [!code-xaml[DigitalInkTopics#3](~/samples/snippets/csharp/VS_Snippets_Wpf/DigitalInkTopics/CSharp/Window2.xaml#3)]

1. <span data-ttu-id="7976d-132">**ソリューション エクスプローラー** で、MainWindow.xaml を展開し、分離コード ファイル (MainWindow.xaml.cs または MainWindow.xaml.vb) を開きます。</span><span class="sxs-lookup"><span data-stu-id="7976d-132">In **Solution Explorer**, expand MainWindow.xaml and open the code-behind file (MainWindow.xaml.cs or MainWindow.xaml.vb).</span></span> <span data-ttu-id="7976d-133">次のイベント ハンドラー コードを追加します。</span><span class="sxs-lookup"><span data-stu-id="7976d-133">Add the following event handler code:</span></span>

   [!code-csharp[DigitalInkTopics#4](~/samples/snippets/csharp/VS_Snippets_Wpf/DigitalInkTopics/CSharp/Window2.xaml.cs#4)]
   [!code-vb[DigitalInkTopics#4](~/samples/snippets/visualbasic/VS_Snippets_Wpf/DigitalInkTopics/VisualBasic/Window2.xaml.vb#4)]

1. <span data-ttu-id="7976d-134">アプリケーションを実行します。</span><span class="sxs-lookup"><span data-stu-id="7976d-134">Run the application.</span></span> <span data-ttu-id="7976d-135">何らかのインクを追加してから、マウスで右クリックするか、スタイラスで同等の長押しを実行します。</span><span class="sxs-lookup"><span data-stu-id="7976d-135">Add some ink, and then right-click with the mouse or perform a press-and-hold equivalent with a stylus.</span></span>

   <span data-ttu-id="7976d-136">マウスの右ボタンでクリックするたびにディスプレイが拡大されます。</span><span class="sxs-lookup"><span data-stu-id="7976d-136">The display zooms in each time you click with the right mouse button.</span></span>

### <a name="use-procedural-code-instead-of-xaml"></a><span data-ttu-id="7976d-137">XAML ではなく手続き型コードを使用する</span><span class="sxs-lookup"><span data-stu-id="7976d-137">Use Procedural Code Instead of XAML</span></span>

<span data-ttu-id="7976d-138">手続き型コードからすべての WPF 機能にアクセスできます。</span><span class="sxs-lookup"><span data-stu-id="7976d-138">You can access all WPF features from procedural code.</span></span> <span data-ttu-id="7976d-139">XAML をまったく使用しない WPF 用の "Hello Ink World" アプリケーションを作成するには、次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="7976d-139">Follow these steps to create a "Hello Ink World" application for WPF that doesn’t use any XAML at all.</span></span>

1. <span data-ttu-id="7976d-140">Visual Studio で新しいコンソール アプリケーション プロジェクトを作成します。</span><span class="sxs-lookup"><span data-stu-id="7976d-140">Create a new console application project in Visual Studio.</span></span>

   <span data-ttu-id="7976d-141">**[新しいプロジェクト]** ダイアログで、 **[インストール済み]**  >  **[Visual C#]** または **[Visual Basic]**  >  **[Windows デスクトップ]** カテゴリを展開します。</span><span class="sxs-lookup"><span data-stu-id="7976d-141">In the **New Project** dialog, expand the **Installed** > **Visual C#** or **Visual Basic** > **Windows Desktop** category.</span></span> <span data-ttu-id="7976d-142">次に、 **[コンソール アプリ (.NET Framework)]** アプリ テンプレートを選択します。</span><span class="sxs-lookup"><span data-stu-id="7976d-142">Then, select the **Console App (.NET Framework)** app template.</span></span> <span data-ttu-id="7976d-143">名前を入力し、 **[OK]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="7976d-143">Enter a name, and then select **OK**.</span></span>

1. <span data-ttu-id="7976d-144">次のコードを Program.cs または Program.vb ファイルに貼り付けます。</span><span class="sxs-lookup"><span data-stu-id="7976d-144">Paste the following code into the Program.cs or Program.vb file:</span></span>

   [!code-csharp[InkCanvasConsoleApp#1](~/samples/snippets/csharp/VS_Snippets_Wpf/InkCanvasConsoleApp/CSharp/Program.cs#1)]
   [!code-vb[InkCanvasConsoleApp#1](~/samples/snippets/visualbasic/VS_Snippets_Wpf/InkCanvasConsoleApp/VisualBasic/Module1.vb#1)]

1. <span data-ttu-id="7976d-145">**ソリューション エクスプローラー** で **[参照]** を右クリックし、 **[参照の追加]** を選択して、PresentationCore、PresentationFramework、および WindowsBase アセンブリへの参照を追加します。</span><span class="sxs-lookup"><span data-stu-id="7976d-145">Add references to the PresentationCore, PresentationFramework, and WindowsBase assemblies by right-clicking on **References** in **Solution Explorer** and choosing **Add Reference**.</span></span>

   ![PresentationCore および PresentationFramework を示す参照マネージャー](./media/getting-started-with-ink/reference-manager-presentationcore-presentationframework.png)

1. <span data-ttu-id="7976d-147">**F5** キーを押してアプリケーションをビルドします。</span><span class="sxs-lookup"><span data-stu-id="7976d-147">Build the application by pressing **F5**.</span></span>

## <a name="see-also"></a><span data-ttu-id="7976d-148">関連項目</span><span class="sxs-lookup"><span data-stu-id="7976d-148">See also</span></span>

- [<span data-ttu-id="7976d-149">デジタル インク</span><span class="sxs-lookup"><span data-stu-id="7976d-149">Digital Ink</span></span>](digital-ink.md)
- [<span data-ttu-id="7976d-150">インクの収集</span><span class="sxs-lookup"><span data-stu-id="7976d-150">Collecting Ink</span></span>](collecting-ink.md)
- [<span data-ttu-id="7976d-151">手書き認識</span><span class="sxs-lookup"><span data-stu-id="7976d-151">Handwriting Recognition</span></span>](handwriting-recognition.md)
- [<span data-ttu-id="7976d-152">インクの格納</span><span class="sxs-lookup"><span data-stu-id="7976d-152">Storing Ink</span></span>](storing-ink.md)
