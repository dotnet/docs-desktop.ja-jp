---
title: '方法: Visual Studio を構成して Web サービスを呼び出す XAML ブラウザー アプリケーションをデバッグする'
ms.date: 03/30/2017
helpviewer_keywords:
- debugging XBAPs that call a Web service [WPF]
- debugging security exceptions for XBAPs [WPF]
- security exception for XBAPs [WPF], debugging
- configuring Visual Studio to debug XAML browser applications [WPF]
- configuring Visual Studio to debug XBAPs [WPF]
ms.assetid: fd1db082-a7bb-4c4b-9331-6ad74a0682d0
ms.openlocfilehash: d8cfae2fb47876d578c51e5f4acdfe0c31e752fe
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/09/2020
ms.locfileid: "96984959"
---
# <a name="how-to-configure-visual-studio-to-debug-a-xaml-browser-application-to-call-a-web-service"></a><span data-ttu-id="7af81-102">方法: Visual Studio を構成して Web サービスを呼び出す XAML ブラウザー アプリケーションをデバッグする</span><span class="sxs-lookup"><span data-stu-id="7af81-102">How to: Configure Visual Studio to Debug a XAML Browser Application to Call a Web Service</span></span>
<span data-ttu-id="7af81-103">XAML ブラウザー アプリケーション (XBAP) は、インターネット ゾーン アクセス許可セットに制限された部分信頼セキュリティ サンドボックス内で実行されます。</span><span class="sxs-lookup"><span data-stu-id="7af81-103">XAML browser applications (XBAPs) run within a partial-trust security sandbox that is restricted to the Internet zone set of permissions.</span></span> <span data-ttu-id="7af81-104">このアクセス許可セットでは、Web サービスの呼び出しが、XBAP アプリケーションの起点サイトにある Web サービスのみに制限されます。</span><span class="sxs-lookup"><span data-stu-id="7af81-104">This permission set restricts Web service calls to only Web services that are located at the XBAP application's site of origin.</span></span> <span data-ttu-id="7af81-105">ただし、XBAP が Visual Studio 2005 からデバッグされている場合、それが参照している Web サービスと同じ起点サイトであるとは見なされません。</span><span class="sxs-lookup"><span data-stu-id="7af81-105">When an XBAP is debugged from Visual Studio 2005, though, it is not considered to have the same site of origin as the Web service it references.</span></span> <span data-ttu-id="7af81-106">これにより、XBAP が Web サービスを呼び出そうとすると、セキュリティ例外が発生します。</span><span class="sxs-lookup"><span data-stu-id="7af81-106">This causes security exceptions to be raised when the XBAP attempts to call the Web service.</span></span> <span data-ttu-id="7af81-107">ただし、Visual Studio 2005 XAML ブラウザー アプリケーション (WPF) プロジェクトは、デバッグ中に呼び出される Web サービスと同じ起点サイトを持つことをシミュレートするように構成できます。</span><span class="sxs-lookup"><span data-stu-id="7af81-107">However, a Visual Studio 2005 XAML Browser Application (WPF) project can be configured to simulate having the same site of origin as the Web service it calls while debugging.</span></span> <span data-ttu-id="7af81-108">これにより、XBAP では、セキュリティ例外を発生させることなく、Web サービスを安全に呼び出すことができます。</span><span class="sxs-lookup"><span data-stu-id="7af81-108">This allows the XBAP to safely call the Web service without causing security exceptions.</span></span>

## <a name="configuring-visual-studio"></a><span data-ttu-id="7af81-109">Visual Studio の構成</span><span class="sxs-lookup"><span data-stu-id="7af81-109">Configuring Visual Studio</span></span>
 <span data-ttu-id="7af81-110">Web サービスを呼び出す XBAP をデバッグするように Visual Studio 2005 を構成するには:</span><span class="sxs-lookup"><span data-stu-id="7af81-110">To configure Visual Studio 2005 to debug an XBAP that calls a Web service:</span></span>

1. <span data-ttu-id="7af81-111">**ソリューション エクスプローラー** でプロジェクトを選択し、 **[プロジェクト]** メニューの **[プロパティ]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="7af81-111">With a project selected in **Solution Explorer**, on the **Project** menu, click **Properties**.</span></span>

2. <span data-ttu-id="7af81-112">**プロジェクト デザイナー** で、 **[デバッグ]** タブをクリックします。</span><span class="sxs-lookup"><span data-stu-id="7af81-112">In the **Project Designer**, click the **Debug** tab.</span></span>

3. <span data-ttu-id="7af81-113">**[開始動作]** セクションで **[外部プログラムの開始]** を選択し、次のように入力します。</span><span class="sxs-lookup"><span data-stu-id="7af81-113">In the **Start Action** section, select **Start external program** and enter the following:</span></span>

     `C:\WINDOWS\System32\PresentationHost.exe`

4. <span data-ttu-id="7af81-114">**[開始オプション]** セクションで、 **[コマンドライン引数]** テキスト ボックスに次のように入力します。</span><span class="sxs-lookup"><span data-stu-id="7af81-114">In the **Start Options** section, enter the following into the **Command line arguments** text box:</span></span>

     <span data-ttu-id="7af81-115">`-debug`  *filename*</span><span class="sxs-lookup"><span data-stu-id="7af81-115">`-debug`  *filename*</span></span>

     <span data-ttu-id="7af81-116">**-debug** パラメーターの *filename* の値は、.xbap ファイル名です。次はその例です。</span><span class="sxs-lookup"><span data-stu-id="7af81-116">The *filename* value for the **-debug** parameter is the .xbap filename; for example:</span></span>

     `-debug c:\example.xbap`

> [!NOTE]
> <span data-ttu-id="7af81-117">これは、Visual Studio 2005 XAML ブラウザー アプリケーション (WPF) プロジェクト テンプレートで作成されるソリューションの既定の構成です。</span><span class="sxs-lookup"><span data-stu-id="7af81-117">This is the default configuration for solutions that are created with the Visual Studio 2005 XAML Browser Application (WPF) project template.</span></span>

1. <span data-ttu-id="7af81-118">**ソリューション エクスプローラー** でプロジェクトを選択し、 **[プロジェクト]** メニューの **[プロパティ]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="7af81-118">With a project selected in **Solution Explorer**, on the **Project** menu, click **Properties**.</span></span>

2. <span data-ttu-id="7af81-119">**プロジェクト デザイナー** で、 **[デバッグ]** タブをクリックします。</span><span class="sxs-lookup"><span data-stu-id="7af81-119">In the **Project Designer**, click the **Debug** tab.</span></span>

3. <span data-ttu-id="7af81-120">**[開始オプション]** セクションで、次のコマンド ライン パラメーターを **[コマンドライン引数]** テキスト ボックスに追加します。</span><span class="sxs-lookup"><span data-stu-id="7af81-120">In the **Start Options** section, add the following command-line parameter to the **Command line arguments** text box:</span></span>

     <span data-ttu-id="7af81-121">`-debugSecurityZoneURL`  *URL*</span><span class="sxs-lookup"><span data-stu-id="7af81-121">`-debugSecurityZoneURL`  *URL*</span></span>

     <span data-ttu-id="7af81-122">**-debugSecurityZoneURL** パラメーターの *URL* の値は、アプリケーションの起点サイトとしてシミュレートする場所の URL です。</span><span class="sxs-lookup"><span data-stu-id="7af81-122">The *URL* value for the **-debugSecurityZoneURL** parameter is the URL for the location that you want to simulate as being the site of origin of your application.</span></span>

 <span data-ttu-id="7af81-123">例として、次の URL の Web サービスを使用する XAML ブラウザー アプリケーション (XBAP) を考えてみます。</span><span class="sxs-lookup"><span data-stu-id="7af81-123">As an example, consider a XAML browser application (XBAP) that uses a Web service with the following URL:</span></span>

 `http://services.msdn.microsoft.com/ContentServices/ContentService.asmx`

 <span data-ttu-id="7af81-124">この Web サービスの起点サイト URL は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="7af81-124">The site of origin URL for this Web service is:</span></span>

 `http://services.msdn.microsoft.com`

 <span data-ttu-id="7af81-125">その結果、完全な **-debugSecurityZoneURL** コマンド ライン パラメーターと値は次のようになります。</span><span class="sxs-lookup"><span data-stu-id="7af81-125">Consequently, the complete **-debugSecurityZoneURL** command-line parameter and value is:</span></span>

 `-debugSecurityZoneURL http://services.msdn.microsoft.com`

## <a name="see-also"></a><span data-ttu-id="7af81-126">関連項目</span><span class="sxs-lookup"><span data-stu-id="7af81-126">See also</span></span>

- [<span data-ttu-id="7af81-127">WPF ホスト (PresentationHost.exe)</span><span class="sxs-lookup"><span data-stu-id="7af81-127">WPF Host (PresentationHost.exe)</span></span>](wpf-host-presentationhost-exe.md)
