---
title: Firefox に対応した WPF プラグインがインストールされているかどうかを確認する
titleSuffix: ''
ms.date: 03/30/2017
helpviewer_keywords:
- plug-in for Firefox [WPF]
- detecting Firefox installation [WPF]
- checking for the Firefox plug-in [WPF]
- Firefox [WPF], detecting installation
- detecting whether the WPF plug-in for Firefox is installed [WPF]
ms.assetid: 5f839373-e3fb-44f1-88ad-4a0761f02189
ms.openlocfilehash: ed16f98b992f4c1a0cea3e13a0ab29d630789a67
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/09/2020
ms.locfileid: "96983119"
---
# <a name="how-to-detect-whether-the-wpf-plug-in-for-firefox-is-installed"></a><span data-ttu-id="5f913-102">方法: Firefox に対応した WPF プラグインがインストールされているかどうかを確認する</span><span class="sxs-lookup"><span data-stu-id="5f913-102">How to: Detect Whether the WPF Plug-In for Firefox Is Installed</span></span>

<span data-ttu-id="5f913-103">Firefox 用の Windows Presentation Foundation (WPF) プラグインを使用すると、XAML ブラウザー アプリケーション (XBAP) と Loose XAML ファイルを Mozilla Firefox ブラウザーで実行できます。</span><span class="sxs-lookup"><span data-stu-id="5f913-103">The Windows Presentation Foundation (WPF) plug-in for Firefox enables XAML browser applications (XBAPs) and loose XAML files to run in the Mozilla Firefox browser.</span></span> <span data-ttu-id="5f913-104">このトピックでは、Firefox 用 WPF プラグインがインストールされているかどうかを確認するために管理者が使用できる HTML と JavaScript で記述されたスクリプトを提供します。</span><span class="sxs-lookup"><span data-stu-id="5f913-104">This topic provides a script written in HTML and JavaScript that administrators can use to determine whether the WPF plug-in for Firefox is installed.</span></span>

> [!NOTE]
> <span data-ttu-id="5f913-105">.NET Framework のインストール、配置、検出については、「[開発者向けの .NET Framework のインストール](/dotnet/framework/install/guide-for-developers)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="5f913-105">For more information about installing, deploying, and detecting the .NET Framework, see [Install the .NET Framework for developers](/dotnet/framework/install/guide-for-developers).</span></span>

## <a name="example"></a><span data-ttu-id="5f913-106">例</span><span class="sxs-lookup"><span data-stu-id="5f913-106">Example</span></span>

<span data-ttu-id="5f913-107">.NET Framework 3.5 がインストールされている場合、クライアント コンピューターには Firefox 用の WPF プラグインが構成されます。</span><span class="sxs-lookup"><span data-stu-id="5f913-107">When the .NET Framework 3.5 is installed, the client computer is configured with a WPF plug-in for Firefox.</span></span> <span data-ttu-id="5f913-108">次のスクリプトの例では、Firefox 用の WPF プラグインを確認し、適切なステータス メッセージを表示します。</span><span class="sxs-lookup"><span data-stu-id="5f913-108">The following example script checks for the WPF plug-in for Firefox and then displays an appropriate status message.</span></span>

```html
<HTML>

  <HEAD>
    <TITLE>Test for the WPF plug-in for Firefox</TITLE>
    <META HTTP-EQUIV="Content-Type" CONTENT="text/html; charset=utf-8" />
    <SCRIPT type="text/javascript">
    <!--
    function OnLoad()
    {

       // Check for the WPF plug-in for Firefox and report
       var msg = "The WPF plug-in for Firefox is ";
       var wpfPlugin = navigator.plugins["Windows Presentation Foundation"];
       if( wpfPlugin != null ) {
          document.writeln(msg + " installed.");
       }
       else {
          document.writeln(msg + " not installed. Please install or reinstall the .NET Framework 3.5.");
       }
    }
    -->
    </SCRIPT>
  </HEAD>

  <BODY onload="OnLoad()" />

</HTML>
```

<span data-ttu-id="5f913-109">Firefox 用 WPF プラグインの確認が成功すると、次のステータス メッセージが表示されます。</span><span class="sxs-lookup"><span data-stu-id="5f913-109">If the check for the WPF plug-in for Firefox is successful, the following status message is displayed:</span></span>

`The WPF plug-in for Firefox is installed.`

<span data-ttu-id="5f913-110">それ以外の場合は、次のステータス メッセージが表示されます。</span><span class="sxs-lookup"><span data-stu-id="5f913-110">Otherwise, the following status message is displayed:</span></span>

`The WPF plug-in for Firefox is not installed. Please install or reinstall the .NET Framework 3.5.`

## <a name="see-also"></a><span data-ttu-id="5f913-111">関連項目</span><span class="sxs-lookup"><span data-stu-id="5f913-111">See also</span></span>

- [<span data-ttu-id="5f913-112">.NET Framework 3.0 がインストールされているかどうかを確認する</span><span class="sxs-lookup"><span data-stu-id="5f913-112">Detect Whether the .NET Framework 3.0 Is Installed</span></span>](how-to-detect-whether-the-net-framework-3-0-is-installed.md)
- [<span data-ttu-id="5f913-113">.NET Framework 3.5 がインストールされているかどうかを確認する</span><span class="sxs-lookup"><span data-stu-id="5f913-113">Detect Whether the .NET Framework 3.5 Is Installed</span></span>](how-to-detect-whether-the-net-framework-3-5-is-installed.md)
- [<span data-ttu-id="5f913-114">WPF XAML ブラウザー アプリケーションの概要</span><span class="sxs-lookup"><span data-stu-id="5f913-114">WPF XAML Browser Applications Overview</span></span>](wpf-xaml-browser-applications-overview.md)
