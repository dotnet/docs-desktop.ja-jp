---
title: IWpfHostSupport
ms.date: 03/30/2017
helpviewer_keywords:
- IWpfHostSupport interface [WPF]
ms.assetid: cc5a0281-de81-4cc1-87e4-0e46b1a811e9
ms.openlocfilehash: eb4b6a22a6f2f5de138ff3795dd32058f87cdb7a
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/09/2020
ms.locfileid: "96974316"
---
# <a name="iwpfhostsupport"></a><span data-ttu-id="cfe08-102">IWpfHostSupport</span><span class="sxs-lookup"><span data-stu-id="cfe08-102">IWpfHostSupport</span></span>

<span data-ttu-id="cfe08-103">PresentationHost.exe を使用して [!INCLUDE[TLA#tla_winclient](../../../includes/tlasharptla-winclient-md.md)] コンテンツをホストするアプリケーションでは、このインターフェイスを実装して、ホストと PresentationHost.exe の間の統合ポイントを提供します。</span><span class="sxs-lookup"><span data-stu-id="cfe08-103">Applications that host [!INCLUDE[TLA#tla_winclient](../../../includes/tlasharptla-winclient-md.md)] content via PresentationHost.exe implement this interface to provide a point of integration between the host and PresentationHost.exe.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="cfe08-104">Remarks</span><span class="sxs-lookup"><span data-stu-id="cfe08-104">Remarks</span></span>  

 <span data-ttu-id="cfe08-105">Web ブラウザーなどの Win32 アプリケーションでは、XAML ブラウザー アプリケーション (XBAP) や Loose XAML などの WPF コンテンツをホストできます。</span><span class="sxs-lookup"><span data-stu-id="cfe08-105">Win32 applications such as Web browsers can host WPF content, including XAML browser applications (XBAPs) and loose XAML.</span></span> <span data-ttu-id="cfe08-106">WPF コンテンツをホストするには、Win32 アプリケーションで [WebBrowser コントロール](/previous-versions/windows/internet-explorer/ie-developer/platform-apis/aa752040(v=vs.85))のインスタンスを作成します。</span><span class="sxs-lookup"><span data-stu-id="cfe08-106">To host WPF content, Win32 applications create an instance of the [WebBrowser control](/previous-versions/windows/internet-explorer/ie-developer/platform-apis/aa752040(v=vs.85)).</span></span> <span data-ttu-id="cfe08-107">ホストされるためには、WPF で PresentationHost.exe のインスタンスを作成します。このインスタンスで、[WebBrowser コントロール](/previous-versions/windows/internet-explorer/ie-developer/platform-apis/aa752040(v=vs.85))に表示するため、ホストされる WPF コンテンツをホストに提供します。</span><span class="sxs-lookup"><span data-stu-id="cfe08-107">To be hosted, WPF creates an instance of PresentationHost.exe, which provides the hosted WPF content to the host for display in the [WebBrowser control](/previous-versions/windows/internet-explorer/ie-developer/platform-apis/aa752040(v=vs.85)).</span></span>  
  
 <span data-ttu-id="cfe08-108">`IWpfHostSupport` によって有効になる統合により、PresentationHost.exe では次のことを行うことができます。</span><span class="sxs-lookup"><span data-stu-id="cfe08-108">The integration enabled by `IWpfHostSupport` allows PresentationHost.exe to:</span></span>  
  
- <span data-ttu-id="cfe08-109">ホスト アプリケーションに必要な生入力デバイス (ヒューマン インターフェイス デバイス) を検出して登録します。</span><span class="sxs-lookup"><span data-stu-id="cfe08-109">Discover and register with the raw input devices (Human Interface Devices) that the host application is interested in.</span></span>  
  
- <span data-ttu-id="cfe08-110">登録されている生入力デバイスから入力メッセージを受け取り、適切なメッセージをホスト アプリケーションに転送します。</span><span class="sxs-lookup"><span data-stu-id="cfe08-110">Receive input messages from the registered raw input devices and forward appropriate messages to the host application.</span></span>  
  
- <span data-ttu-id="cfe08-111">ホスト アプリケーションで、進行状況とエラーのカスタム ユーザー インターフェイスを照会します。</span><span class="sxs-lookup"><span data-stu-id="cfe08-111">Query the host application for custom progress and error user interfaces.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="cfe08-112">この API は、ローカル クライアント コンピューターでの使用のみを目的とし、サポートされています。</span><span class="sxs-lookup"><span data-stu-id="cfe08-112">This API is only intended and supported for use on the local client machine</span></span>  
  
## <a name="members"></a><span data-ttu-id="cfe08-113">メンバー</span><span class="sxs-lookup"><span data-stu-id="cfe08-113">Members</span></span>  
  
|<span data-ttu-id="cfe08-114">メンバー</span><span class="sxs-lookup"><span data-stu-id="cfe08-114">Member</span></span>|<span data-ttu-id="cfe08-115">説明</span><span class="sxs-lookup"><span data-stu-id="cfe08-115">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="cfe08-116">GetRawInputDevices</span><span class="sxs-lookup"><span data-stu-id="cfe08-116">GetRawInputDevices</span></span>](getrawinputdevices.md)|<span data-ttu-id="cfe08-117">PresentationHost.exe が、ホスト アプリケーションに必要な未加工入力デバイス (ヒューマン インターフェイス デバイス) を検出できるようにします。</span><span class="sxs-lookup"><span data-stu-id="cfe08-117">Allows PresentationHost.exe to discover the raw input devices (Human Interface Devices) that the host application is interested in.</span></span>|  
|[<span data-ttu-id="cfe08-118">FilterInputMessage</span><span class="sxs-lookup"><span data-stu-id="cfe08-118">FilterInputMessage</span></span>](filterinputmessage.md)|<span data-ttu-id="cfe08-119">E_NOTIMPL が返されない限り、メッセージを受信するたびに PresentationHost.exe によって呼び出されます。</span><span class="sxs-lookup"><span data-stu-id="cfe08-119">Called by PresentationHost.exe whenever a message is received unless E_NOTIMPL is returned.</span></span>|  
|[<span data-ttu-id="cfe08-120">GetCustomUI</span><span class="sxs-lookup"><span data-stu-id="cfe08-120">GetCustomUI</span></span>](getcustomui.md)|<span data-ttu-id="cfe08-121">既定では、PresentationHost.exe によって、WPF コンテンツが配置されるときに表示される、配置の進行状況と配置エラーの独自のユーザー インターフェイスが提供されます。</span><span class="sxs-lookup"><span data-stu-id="cfe08-121">By default, PresentationHost.exe provides its own deployment progress and deployment error user interfaces that are displayed when WPF content is deployed.</span></span>|
