---
title: 作業の開始
description: .NET Framework のサブセットである Windows Presentation Foundation (WPF) の UI フレームワークを使用して、デスクトップ クライアント アプリケーションを作成します。
ms.date: 01/26/2018
helpviewer_keywords:
- getting started [WPF]
- introduction [WPF]
- WPF [WPF], getting started
ms.assetid: 04f91da8-708c-46c7-8172-f1695ec847cd
ms.openlocfilehash: 63ac5df12774b7ecead8c19786b0a48e0092317d
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/09/2020
ms.locfileid: "96992844"
---
# <a name="get-started-wpf"></a><span data-ttu-id="b1454-103">WPF の使用を開始する</span><span class="sxs-lookup"><span data-stu-id="b1454-103">Get started (WPF)</span></span>

<span data-ttu-id="b1454-104">Windows Presentation Foundation (WPF) は、デスクトップ クライアント アプリケーションを作成する UI フレームワークです。</span><span class="sxs-lookup"><span data-stu-id="b1454-104">Windows Presentation Foundation (WPF) is a UI framework that creates desktop client applications.</span></span> <span data-ttu-id="b1454-105">WPF の開発プラットフォームは、アプリケーション モデル、リソース、コントロール、グラフィックス、レイアウト、データ バインディング、ドキュメント、セキュリティなどのさまざまなアプリケーション開発機能の一式をサポートします。</span><span class="sxs-lookup"><span data-stu-id="b1454-105">The WPF development platform supports a broad set of application development features, including an application model, resources, controls, graphics, layout, data binding, documents, and security.</span></span> <span data-ttu-id="b1454-106">WPF は .NET Framework のサブセットであるため、以前 ASP.NET や Windows フォームを使用して .NET Framework でアプリケーションを構築したことがあれば、プログラミングには馴染みがあるでしょう。</span><span class="sxs-lookup"><span data-stu-id="b1454-106">It is a subset of the .NET Framework, so if you have previously built applications with the .NET Framework using ASP.NET or Windows Forms, the programming experience should be familiar.</span></span> <span data-ttu-id="b1454-107">WPF は、Extensible Application Markup Language (XAML) を使用して、アプリケーションのプログラミング用に、宣言型モデルを提供します。</span><span class="sxs-lookup"><span data-stu-id="b1454-107">WPF uses the Extensible Application Markup Language (XAML) to provide a declarative model for application programming.</span></span> <span data-ttu-id="b1454-108">このセクションには、WPFの概要とその導入に役立つトピックが複数含まれています。</span><span class="sxs-lookup"><span data-stu-id="b1454-108">This section has topics that introduce and help you get started with WPF.</span></span>  
  
## <a name="where-should-i-start"></a><span data-ttu-id="b1454-109">まず、何を行う必要がありますか。</span><span class="sxs-lookup"><span data-stu-id="b1454-109">Where should I start?</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="b1454-110">すぐに使用を開始したい</span><span class="sxs-lookup"><span data-stu-id="b1454-110">I want to jump right in…</span></span>|[<span data-ttu-id="b1454-111">チュートリアル: 初めての WPF デスクトップ アプリケーション</span><span class="sxs-lookup"><span data-stu-id="b1454-111">Walkthrough: My first WPF desktop application</span></span>](walkthrough-my-first-wpf-desktop-application.md)|  
|<span data-ttu-id="b1454-112">アプリケーションの UI のデザイン方法</span><span class="sxs-lookup"><span data-stu-id="b1454-112">How do I design the application UI?</span></span>|[<span data-ttu-id="b1454-113">Visual Studio で XAML をデザインする</span><span class="sxs-lookup"><span data-stu-id="b1454-113">Designing XAML in Visual Studio</span></span>](/visualstudio/designers/designing-xaml-in-visual-studio)|  
|<span data-ttu-id="b1454-114">.NET の初心者向け</span><span class="sxs-lookup"><span data-stu-id="b1454-114">New to .NET?</span></span>|[<span data-ttu-id="b1454-115">.NET Framework の概要</span><span class="sxs-lookup"><span data-stu-id="b1454-115">Overview of the .NET Framework</span></span>](/dotnet/framework/get-started/overview)<br /><br /> [<span data-ttu-id="b1454-116">Visual C# と Visual Basic の概要</span><span class="sxs-lookup"><span data-stu-id="b1454-116">Getting Started with Visual C# and Visual Basic</span></span>](/visualstudio/ide/quickstart-visual-basic-console)|  
|<span data-ttu-id="b1454-117">WPF の詳細な説明...</span><span class="sxs-lookup"><span data-stu-id="b1454-117">Tell me more about WPF…</span></span>|[<span data-ttu-id="b1454-118">Visual Studio での WPF の概要</span><span class="sxs-lookup"><span data-stu-id="b1454-118">Introduction to WPF in Visual Studio</span></span>](introduction-to-wpf-in-vs.md)<br /><br /> [<span data-ttu-id="b1454-119">XAML の概要 (WPF)</span><span class="sxs-lookup"><span data-stu-id="b1454-119">XAML Overview (WPF)</span></span>](/dotnet/desktop-wpf/fundamentals/xaml)<br /><br /> [<span data-ttu-id="b1454-120">コントロール</span><span class="sxs-lookup"><span data-stu-id="b1454-120">Controls</span></span>](../controls/index.md)<br /><br /> [<span data-ttu-id="b1454-121">データ バインディングの概要</span><span class="sxs-lookup"><span data-stu-id="b1454-121">Data Binding Overview</span></span>](/dotnet/desktop-wpf/data/data-binding-overview)|  
|<span data-ttu-id="b1454-122">Windows フォームの開発者向け</span><span class="sxs-lookup"><span data-stu-id="b1454-122">Are you a Windows Forms developer?</span></span>|[<span data-ttu-id="b1454-123">Windows フォーム コントロールおよび同等の WPF コントロール</span><span class="sxs-lookup"><span data-stu-id="b1454-123">Windows Forms Controls and Equivalent WPF Controls</span></span>](../advanced/windows-forms-controls-and-equivalent-wpf-controls.md)<br /><br /> [<span data-ttu-id="b1454-124">WPF と Windows フォームの相互運用性</span><span class="sxs-lookup"><span data-stu-id="b1454-124">WPF and Windows Forms Interoperation</span></span>](../advanced/wpf-and-windows-forms-interoperation.md)|  
  
## <a name="see-also"></a><span data-ttu-id="b1454-125">関連項目</span><span class="sxs-lookup"><span data-stu-id="b1454-125">See also</span></span>

- [<span data-ttu-id="b1454-126">クラス ライブラリ</span><span class="sxs-lookup"><span data-stu-id="b1454-126">Class Library</span></span>](../class-library-wpf.md)
- [<span data-ttu-id="b1454-127">アプリケーションの開発</span><span class="sxs-lookup"><span data-stu-id="b1454-127">Application Development</span></span>](../app-development/index.md)
- [<span data-ttu-id="b1454-128">.NET Framework デベロッパー センター</span><span class="sxs-lookup"><span data-stu-id="b1454-128">.NET Framework Developer Center</span></span>](https://dotnet.microsoft.com)
