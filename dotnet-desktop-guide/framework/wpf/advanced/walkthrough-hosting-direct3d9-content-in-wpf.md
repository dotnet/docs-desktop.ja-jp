---
title: WPF で Direct3D9 コンテンツをホストする
titleSuffix: ''
ms.date: 03/30/2017
helpviewer_keywords:
- Direct3D9 [WPF interoperability], hosting Direct3D9 content
- WPF [WPF], hosting Direct3D9 content
ms.assetid: 60983736-0ab5-42cc-8b16-e9fbde261a43
ms.openlocfilehash: e65b0c59268b44abed289e54181bf0bda9355664
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/09/2020
ms.locfileid: "96985524"
---
# <a name="walkthrough-hosting-direct3d9-content-in-wpf"></a><span data-ttu-id="3b222-102">チュートリアル: WPF での Direct3D9 コンテンツのホスト</span><span class="sxs-lookup"><span data-stu-id="3b222-102">Walkthrough: Hosting Direct3D9 Content in WPF</span></span>

<span data-ttu-id="3b222-103">このチュートリアルでは、Windows Presentation Foundation (WPF) アプリケーションで Direct3D9 コンテンツをホストする方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="3b222-103">This walkthrough shows how to host Direct3D9 content in a Windows Presentation Foundation (WPF) application.</span></span>

<span data-ttu-id="3b222-104">このチュートリアルでは次のタスクを実行します。</span><span class="sxs-lookup"><span data-stu-id="3b222-104">In this walkthrough, you perform the following tasks:</span></span>

- <span data-ttu-id="3b222-105">Direct3D9 コンテンツをホストする WPF プロジェクトを作成します。</span><span class="sxs-lookup"><span data-stu-id="3b222-105">Create a WPF project to host the Direct3D9 content.</span></span>

- <span data-ttu-id="3b222-106">Direct3D9 コンテンツをインポートします。</span><span class="sxs-lookup"><span data-stu-id="3b222-106">Import the Direct3D9 content.</span></span>

- <span data-ttu-id="3b222-107"><xref:System.Windows.Interop.D3DImage> クラスを使用して Direct3D9 コンテンツを表示します。</span><span class="sxs-lookup"><span data-stu-id="3b222-107">Display the Direct3D9 content by using the <xref:System.Windows.Interop.D3DImage> class.</span></span>

 <span data-ttu-id="3b222-108">完了すると、WPF アプリケーションで Direct3D9 コンテンツをホストする方法がわかります。</span><span class="sxs-lookup"><span data-stu-id="3b222-108">When you are finished, you will know how to host Direct3D9 content in a WPF application.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="3b222-109">必須コンポーネント</span><span class="sxs-lookup"><span data-stu-id="3b222-109">Prerequisites</span></span>

<span data-ttu-id="3b222-110">このチュートリアルを実行するには、次のコンポーネントが必要です。</span><span class="sxs-lookup"><span data-stu-id="3b222-110">You need the following components to complete this walkthrough:</span></span>

- <span data-ttu-id="3b222-111">Visual Studio</span><span class="sxs-lookup"><span data-stu-id="3b222-111">Visual Studio.</span></span>

- <span data-ttu-id="3b222-112">DirectX SDK 9 以降。</span><span class="sxs-lookup"><span data-stu-id="3b222-112">DirectX SDK 9 or later.</span></span>

- <span data-ttu-id="3b222-113">WPF 互換形式の Direct3D9 コンテンツを含む DLL。</span><span class="sxs-lookup"><span data-stu-id="3b222-113">A DLL that contains Direct3D9 content in a WPF-compatible format.</span></span> <span data-ttu-id="3b222-114">詳細については、「[WPF と Direct3D9 の相互運用性](wpf-and-direct3d9-interoperation.md)」と「[チュートリアル: WPF でホストするための Direct3D9 コンテンツの作成](walkthrough-creating-direct3d9-content-for-hosting-in-wpf.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="3b222-114">For more information, see [WPF and Direct3D9 Interoperation](wpf-and-direct3d9-interoperation.md) and [Walkthrough: Creating Direct3D9 Content for Hosting in WPF](walkthrough-creating-direct3d9-content-for-hosting-in-wpf.md).</span></span>

## <a name="creating-the-wpf-project"></a><span data-ttu-id="3b222-115">WPF プロジェクトの作成</span><span class="sxs-lookup"><span data-stu-id="3b222-115">Creating the WPF Project</span></span>

<span data-ttu-id="3b222-116">最初の手順は、WPF アプリケーションのプロジェクトを作成することです。</span><span class="sxs-lookup"><span data-stu-id="3b222-116">The first step is to create the project for the WPF application.</span></span>

### <a name="to-create-the-wpf-project"></a><span data-ttu-id="3b222-117">WPF プロジェクトを作成するには</span><span class="sxs-lookup"><span data-stu-id="3b222-117">To create the WPF project</span></span>

<span data-ttu-id="3b222-118">Visual C# で `D3DHost` という名前の新しい WPF アプリケーション プロジェクトを作成します。</span><span class="sxs-lookup"><span data-stu-id="3b222-118">Create a new WPF Application project in Visual C# named `D3DHost`.</span></span> <span data-ttu-id="3b222-119">詳細については、「[チュートリアル:初めての WPF デスクトップ アプリケーション](../getting-started/walkthrough-my-first-wpf-desktop-application.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="3b222-119">For more information, see [Walkthrough: My first WPF desktop application](../getting-started/walkthrough-my-first-wpf-desktop-application.md).</span></span>

<span data-ttu-id="3b222-120">MainWindow.xaml が WPF デザイナーで開きます。</span><span class="sxs-lookup"><span data-stu-id="3b222-120">MainWindow.xaml opens in the WPF Designer.</span></span>

## <a name="importing-the-direct3d9-content"></a><span data-ttu-id="3b222-121">Direct3D9 コンテンツのインポート</span><span class="sxs-lookup"><span data-stu-id="3b222-121">Importing the Direct3D9 Content</span></span>

<span data-ttu-id="3b222-122">`DllImport` 属性を使用して、アンマネージド DLL から Direct3D9 コンテンツをインポートします。</span><span class="sxs-lookup"><span data-stu-id="3b222-122">You import the Direct3D9 content from an unmanaged DLL by using the `DllImport` attribute.</span></span>

### <a name="to-import-direct3d9-content"></a><span data-ttu-id="3b222-123">Direct3D9 コンテンツをインポートするには</span><span class="sxs-lookup"><span data-stu-id="3b222-123">To import Direct3D9 content</span></span>

1. <span data-ttu-id="3b222-124">コード エディターで MainWindow.xaml.cs を開きます。</span><span class="sxs-lookup"><span data-stu-id="3b222-124">Open MainWindow.xaml.cs in the Code Editor.</span></span>

2. <span data-ttu-id="3b222-125">自動生成されたコードを次のコードに置き換えます。</span><span class="sxs-lookup"><span data-stu-id="3b222-125">Replace the automatically generated code with the following code.</span></span>

    [!code-csharp[System.Windows.Interop.D3DImage#1](~/samples/snippets/csharp/VS_Snippets_Wpf/System.Windows.Interop.D3DImage/CS/window1.xaml.cs#1)]

## <a name="hosting-the-direct3d9-content"></a><span data-ttu-id="3b222-126">Direct3D9 コンテンツのホスト</span><span class="sxs-lookup"><span data-stu-id="3b222-126">Hosting the Direct3D9 Content</span></span>

<span data-ttu-id="3b222-127">最後に、<xref:System.Windows.Interop.D3DImage> クラスを使用して Direct3D9 コンテンツをホストします。</span><span class="sxs-lookup"><span data-stu-id="3b222-127">Finally, use the <xref:System.Windows.Interop.D3DImage> class to host the Direct3D9 content.</span></span>

### <a name="to-host-the-direct3d9-content"></a><span data-ttu-id="3b222-128">Direct3D9 コンテンツをホストするには</span><span class="sxs-lookup"><span data-stu-id="3b222-128">To host the Direct3D9 content</span></span>

1. <span data-ttu-id="3b222-129">MainWindow.xaml で、自動生成された XAML を次の XAML に置き換えます。</span><span class="sxs-lookup"><span data-stu-id="3b222-129">In MainWindow.xaml, replace the automatically generated XAML with the following XAML.</span></span>

    [!code-xaml[System.Windows.Interop.D3DImage#10](~/samples/snippets/csharp/VS_Snippets_Wpf/System.Windows.Interop.D3DImage/CS/window1.xaml#10)]

2. <span data-ttu-id="3b222-130">プロジェクトをビルドします。</span><span class="sxs-lookup"><span data-stu-id="3b222-130">Build the project.</span></span>

3. <span data-ttu-id="3b222-131">Direct3D9 コンテンツを含む DLL を bin/Debug フォルダーにコピーします。</span><span class="sxs-lookup"><span data-stu-id="3b222-131">Copy the DLL that contains the Direct3D9 content to the bin/Debug folder.</span></span>

4. <span data-ttu-id="3b222-132">F5 キーを押してプロジェクトを実行します。</span><span class="sxs-lookup"><span data-stu-id="3b222-132">Press F5 to run the project.</span></span>

    <span data-ttu-id="3b222-133">Direct3D9 コンテンツが WPF アプリケーション内に表示されます。</span><span class="sxs-lookup"><span data-stu-id="3b222-133">The Direct3D9 content appears within the WPF application.</span></span>

## <a name="see-also"></a><span data-ttu-id="3b222-134">関連項目</span><span class="sxs-lookup"><span data-stu-id="3b222-134">See also</span></span>

- <xref:System.Windows.Interop.D3DImage>
- [<span data-ttu-id="3b222-135">Direct3D9 および WPF の相互運用性のパフォーマンスに関する考慮事項</span><span class="sxs-lookup"><span data-stu-id="3b222-135">Performance Considerations for Direct3D9 and WPF Interoperability</span></span>](performance-considerations-for-direct3d9-and-wpf-interoperability.md)
