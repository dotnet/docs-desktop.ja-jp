---
title: スプラッシュ スクリーンを追加する方法
description: Windows Presentation Foundation (WPF) アプリケーションにスタートアップ ウィンドウまたはスプラッシュ スクリーンを追加する方法について説明します。
ms.date: 08/18/2018
helpviewer_keywords:
- WPF [WPF], splash screen
- startup window [WPF]
- SplashScreen class [WPF]
- splash screen [WPF]
ms.assetid: d70a25c4-5fb9-4c27-b01d-b1b8ef39b3fd
ms.openlocfilehash: 99a20dca755b7fd066ed6068ed2efa4cca8acaa9
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/09/2020
ms.locfileid: "96983776"
---
# <a name="how-to-add-a-splash-screen-to-a-wpf-application"></a><span data-ttu-id="daf23-103">方法: スプラッシュ スクリーンを WPF アプリケーションに追加する</span><span class="sxs-lookup"><span data-stu-id="daf23-103">How to: Add a Splash Screen to a WPF Application</span></span>

<span data-ttu-id="daf23-104">このトピックでは、Windows Presentation Foundation (WPF) アプリケーションにスタートアップ ウィンドウ ("*スプラッシュ スクリーン*") を追加する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="daf23-104">This topic shows how to add a startup window, or *splash screen*, to a Windows Presentation Foundation (WPF) application.</span></span>

## <a name="to-add-an-existing-image-as-a-splash-screen"></a><span data-ttu-id="daf23-105">既存の画像をスプラッシュ スクリーンとして追加するには</span><span class="sxs-lookup"><span data-stu-id="daf23-105">To add an existing image as a splash screen</span></span>

1. <span data-ttu-id="daf23-106">スプラッシュ スクリーンとして使用する画像を作成または検索します。</span><span class="sxs-lookup"><span data-stu-id="daf23-106">Create or find an image that you want to use for the splash screen.</span></span> <span data-ttu-id="daf23-107">Windows Imaging Component (WIC) でサポートされている任意の画像形式を使用できます。</span><span class="sxs-lookup"><span data-stu-id="daf23-107">You can use any image format that is supported by the Windows Imaging Component (WIC).</span></span> <span data-ttu-id="daf23-108">たとえば、BMP、GIF、JPEG、PNG、または TIFF 形式を使用できます。</span><span class="sxs-lookup"><span data-stu-id="daf23-108">For example, you can use the BMP, GIF, JPEG, PNG, or TIFF format.</span></span>

2. <span data-ttu-id="daf23-109">WPF アプリケーション プロジェクトに画像ファイルを追加します。</span><span class="sxs-lookup"><span data-stu-id="daf23-109">Add the image file to the WPF Application project.</span></span>

3. <span data-ttu-id="daf23-110">**ソリューション エクスプローラー** で、画像を選択します。</span><span class="sxs-lookup"><span data-stu-id="daf23-110">In **Solution Explorer**, select the image.</span></span>

4. <span data-ttu-id="daf23-111">プロパティ ウィンドウで、 **[ビルド アクション]** プロパティのドロップダウン矢印をクリックします。</span><span class="sxs-lookup"><span data-stu-id="daf23-111">In the Properties window, click the drop-down arrow for the **Build Action** property.</span></span>

5. <span data-ttu-id="daf23-112">ドロップダウン リストから **[スプラッシュスクリーン]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="daf23-112">Select **SplashScreen** from the drop-down list.</span></span>

6. <span data-ttu-id="daf23-113">**F5** キーを押してアプリケーションをビルドし、実行します。</span><span class="sxs-lookup"><span data-stu-id="daf23-113">Press **F5** to build and run the application.</span></span>

     <span data-ttu-id="daf23-114">スプラッシュ スクリーンの画像が画面の中央に表示された後、メイン アプリケーション ウィンドウが表示されると消えます。</span><span class="sxs-lookup"><span data-stu-id="daf23-114">The splash screen image appears in the center of the screen, and then fades when the main application window appears.</span></span>

## <a name="to-exclude-the-splash-screen-from-build"></a><span data-ttu-id="daf23-115">ビルドからスプラッシュ スクリーンを除外するには</span><span class="sxs-lookup"><span data-stu-id="daf23-115">To exclude the splash screen from build</span></span>

1. <span data-ttu-id="daf23-116">**ソリューション エクスプローラー** で、スプラッシュ スクリーンの画像を選択します。</span><span class="sxs-lookup"><span data-stu-id="daf23-116">In **Solution Explorer**, select the splash screen image.</span></span>

2. <span data-ttu-id="daf23-117">**[プロパティ]** ウィンドウで、 **[ビルド アクション]** を **[なし]** に設定します。</span><span class="sxs-lookup"><span data-stu-id="daf23-117">In the **Properties** window, set the **Build Action** to **None**.</span></span>

## <a name="to-remove-the-splash-screen-from-an-application"></a><span data-ttu-id="daf23-118">アプリケーションからスプラッシュ スクリーンを削除するには</span><span class="sxs-lookup"><span data-stu-id="daf23-118">To remove the splash screen from an application</span></span>

<span data-ttu-id="daf23-119">**ソリューション エクスプローラー** で、スプラッシュ スクリーンの画像を削除します。</span><span class="sxs-lookup"><span data-stu-id="daf23-119">In **Solution Explorer**, delete the splash screen image.</span></span>

## <a name="see-also"></a><span data-ttu-id="daf23-120">関連項目</span><span class="sxs-lookup"><span data-stu-id="daf23-120">See also</span></span>

- <xref:System.Windows.SplashScreen>
- <span data-ttu-id="daf23-121">[方法: 既存の項目をプロジェクトに追加する](/previous-versions/visualstudio/visual-studio-2010/9f4t9t92(v=vs.100))</span><span class="sxs-lookup"><span data-stu-id="daf23-121">[How to: Add Existing Items to a Project](/previous-versions/visualstudio/visual-studio-2010/9f4t9t92(v=vs.100))</span></span>
