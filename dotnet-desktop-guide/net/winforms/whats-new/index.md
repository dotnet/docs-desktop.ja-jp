---
title: Windows フォームの新機能
description: .NET 用の Windows フォームの新機能について学習します。 Windows フォーム。 .NET では、.NET Framework に対する新機能と拡張機能が提供されます。
ms.date: 11/05/2020
ms.topic: conceptual
ms.openlocfilehash: 5c22fdd2df68cd59b7bc0b93c6aa7223bdf06ec0
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/09/2020
ms.locfileid: "96992856"
---
# <a name="whats-new-windows-forms-net"></a><span data-ttu-id="45c2e-105">新機能 (Windows フォーム .NET)</span><span class="sxs-lookup"><span data-stu-id="45c2e-105">What's new (Windows Forms .NET)</span></span>

<span data-ttu-id="45c2e-106">.NET 5.0 用の Windows フォームには、.NET Framework に対する次の機能と拡張機能が追加されています。</span><span class="sxs-lookup"><span data-stu-id="45c2e-106">Windows Forms for .NET 5.0 adds the following features and enhancements over .NET Framework.</span></span>

<span data-ttu-id="45c2e-107">.NET Framework から .NET 5.0 に移行するときに注意する必要がある破壊的変更がいくつかあります。</span><span class="sxs-lookup"><span data-stu-id="45c2e-107">There are a few breaking changes you should be aware of when migrating from .NET Framework to .NET 5.0.</span></span> <span data-ttu-id="45c2e-108">詳細については、[Windows フォームでの破壊的変更](/dotnet/core/compatibility/winforms)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="45c2e-108">For more information, see [Breaking changes in Windows Forms](/dotnet/core/compatibility/winforms).</span></span>

## <a name="enhanced-features"></a><span data-ttu-id="45c2e-109">拡張機能</span><span class="sxs-lookup"><span data-stu-id="45c2e-109">Enhanced features</span></span>

- <span data-ttu-id="45c2e-110">Microsoft UI オートメーションのパターンは、ナレーターや Jaws などのユーザー補助ツールでより適切に動作します。</span><span class="sxs-lookup"><span data-stu-id="45c2e-110">Microsoft UI Automation patterns work better with accessibility tools like Narrator and Jaws.</span></span>
- <span data-ttu-id="45c2e-111">パフォーマンスが向上します。</span><span class="sxs-lookup"><span data-stu-id="45c2e-111">Improved performance.</span></span>
- <span data-ttu-id="45c2e-112">VB.NET プロジェクトのテンプレートでは、4k モニターなどの高 DPI 解像度の場合、既定で DPI SystemAware に設定されます。</span><span class="sxs-lookup"><span data-stu-id="45c2e-112">The VB.NET project template defaults to DPI SystemAware settings for high DPI resolutions such as 4k monitors.</span></span>
- <span data-ttu-id="45c2e-113">既定のフォントは、現在の Windows の設計上の推奨事項と一致します。</span><span class="sxs-lookup"><span data-stu-id="45c2e-113">The default font matches the current Windows design recommendations.</span></span>

  > [!CAUTION]
  > <span data-ttu-id="45c2e-114">これは、.NET Framework から移行されたアプリのレイアウトに影響を与える可能性があります。</span><span class="sxs-lookup"><span data-stu-id="45c2e-114">This may impact the layout of apps migrated from .NET Framework.</span></span>

## <a name="new-controls"></a><span data-ttu-id="45c2e-115">新しいコントロール</span><span class="sxs-lookup"><span data-stu-id="45c2e-115">New controls</span></span>

<span data-ttu-id="45c2e-116">Windows フォームが .NET Framework に移植された後に、次のコントロールが追加されました。</span><span class="sxs-lookup"><span data-stu-id="45c2e-116">The following controls have been added since Windows Forms was ported to .NET Framework:</span></span>

- <xref:System.Windows.Forms.TaskDialog?displayProperty=fullName>
  
  <span data-ttu-id="45c2e-117">タスク ダイアログは、情報の表示とユーザーからの単純な入力の受信に使用できるダイアログ ボックスです。</span><span class="sxs-lookup"><span data-stu-id="45c2e-117">A task dialog is a dialog box that can be used to display information and receive simple input from the user.</span></span> <span data-ttu-id="45c2e-118">メッセージ ボックスと同様に、ユーザーが設定したパラメーターに従って、オペレーティング システムによって書式設定されます。</span><span class="sxs-lookup"><span data-stu-id="45c2e-118">Like a message box, it's formatted by the operating system according to parameters you set.</span></span> <span data-ttu-id="45c2e-119">タスク ダイアログには、メッセージ ボックスよりも多くの機能があります。</span><span class="sxs-lookup"><span data-stu-id="45c2e-119">Task dialog has more features than a message box.</span></span> <span data-ttu-id="45c2e-120">詳細については、[タスク ダイアログのサンプル](https://github.com/dotnet/samples/tree/master/windowsforms/TaskDialogDemo)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="45c2e-120">For more information, see the [Task dialog sample](https://github.com/dotnet/samples/tree/master/windowsforms/TaskDialogDemo).</span></span>

- <xref:Microsoft.Web.WebView2.WinForms.WebView2?displayProperty=fullName>

  <span data-ttu-id="45c2e-121">最新の Web をサポートする新しい Web ブラウザー コントロール。</span><span class="sxs-lookup"><span data-stu-id="45c2e-121">A new web browser control with modern web support.</span></span> <span data-ttu-id="45c2e-122">Edge (Chromium) ベース。</span><span class="sxs-lookup"><span data-stu-id="45c2e-122">Based on Edge (Chromium).</span></span> <span data-ttu-id="45c2e-123">詳細については、「[Windows フォームでの WebView2 の概要](/microsoft-edge/webview2/gettingstarted/winforms)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="45c2e-123">For more information, see [Getting started with WebView2 in Windows Forms](/microsoft-edge/webview2/gettingstarted/winforms).</span></span>

## <a name="enhanced-controls"></a><span data-ttu-id="45c2e-124">強化されたコントロール</span><span class="sxs-lookup"><span data-stu-id="45c2e-124">Enhanced controls</span></span>

- <xref:System.Windows.Forms.ListView?displayProperty=fullName>

  - <span data-ttu-id="45c2e-125">折りたたみ可能なグループをサポート</span><span class="sxs-lookup"><span data-stu-id="45c2e-125">Supports collapsible groups</span></span>
  - <span data-ttu-id="45c2e-126">フッター</span><span class="sxs-lookup"><span data-stu-id="45c2e-126">Footers</span></span>
  - <span data-ttu-id="45c2e-127">字幕、タスク、およびタイトルの画像をグループ化</span><span class="sxs-lookup"><span data-stu-id="45c2e-127">Group subtitle, task, and title images</span></span>

- <xref:System.Windows.Forms.FolderBrowserDialog?displayProperty=fullName>

  <span data-ttu-id="45c2e-128">このダイアログは、古い Windows 7 エクスペリエンスではなく、最新の Windows エクスペリエンスを使用するようにアップグレードされました。</span><span class="sxs-lookup"><span data-stu-id="45c2e-128">This dialog has been upgraded to use the modern Windows experience instead of the old Windows 7 experience.</span></span>

- <xref:System.Windows.Forms.FileDialog?displayProperty=fullName>

  - <span data-ttu-id="45c2e-129"><xref:System.Windows.Forms.FileDialog.ClientGuid> のサポートが追加されました。</span><span class="sxs-lookup"><span data-stu-id="45c2e-129">Added support for <xref:System.Windows.Forms.FileDialog.ClientGuid>.</span></span>

    <span data-ttu-id="45c2e-130">`ClientGuid` を使用すると、呼び出し元のアプリケーションで GUID とダイアログの保持された状態を関連付けることができます。</span><span class="sxs-lookup"><span data-stu-id="45c2e-130">`ClientGuid` enables a calling application to associate a GUID with a dialog's persisted state.</span></span> <span data-ttu-id="45c2e-131">ダイアログの状態には、最後にアクセスしたフォルダーおよびダイアログの位置やサイズなどの要因を含めることができます。</span><span class="sxs-lookup"><span data-stu-id="45c2e-131">A dialog's state can include factors such as the last visited folder and the position and size of the dialog.</span></span> <span data-ttu-id="45c2e-132">通常、この状態は実行可能ファイルの名前に基づいて保持されます。</span><span class="sxs-lookup"><span data-stu-id="45c2e-132">Typically, this state is persisted based on the name of the executable file.</span></span> <span data-ttu-id="45c2e-133">`ClientGuid` を使用すると、アプリケーションで同じアプリケーション内の異なる状態のダイアログを保持できます。</span><span class="sxs-lookup"><span data-stu-id="45c2e-133">With `ClientGuid`, an application can persist  different states of the dialog within the same application.</span></span>

- <xref:System.Windows.Forms.TextRenderer?displayProperty=fullName>

  <span data-ttu-id="45c2e-134">レンダリング テキストのパフォーマンスを向上させるために <xref:System.ReadOnlySpan%601> のサポートが追加されました。</span><span class="sxs-lookup"><span data-stu-id="45c2e-134">Support added for <xref:System.ReadOnlySpan%601> to enhance performance of rendering text.</span></span>

## <a name="see-also"></a><span data-ttu-id="45c2e-135">関連項目</span><span class="sxs-lookup"><span data-stu-id="45c2e-135">See also</span></span>

- [<span data-ttu-id="45c2e-136">Windows フォームでの破壊的変更</span><span class="sxs-lookup"><span data-stu-id="45c2e-136">Breaking changes in Windows Forms</span></span>](/dotnet/core/compatibility/winforms)
- [<span data-ttu-id="45c2e-137">チュートリアル: 新しい WinForms アプリを作成する (Windows フォーム .NET)</span><span class="sxs-lookup"><span data-stu-id="45c2e-137">Tutorial: Create a new WinForms app (Windows Forms .NET)</span></span>](../get-started/create-app-visual-studio.md)
- [<span data-ttu-id="45c2e-138">Windows フォーム デスクトップ アプリを .NET 5 に移行する方法</span><span class="sxs-lookup"><span data-stu-id="45c2e-138">How to migrate a Windows Forms desktop app to .NET 5</span></span>](../migration/index.md)
