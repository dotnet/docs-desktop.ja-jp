---
title: RealTimeStylus を無効にする
ms.date: 03/30/2017
ms.assetid: e0525309-5ede-4782-837d-dbf6e5554859
ms.openlocfilehash: c2500b494f76c85e4b23823a44a180d85d5092ff
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/09/2020
ms.locfileid: "96983724"
---
# <a name="disable-the-realtimestylus-for-wpf-applications"></a><span data-ttu-id="471df-102">WPF アプリケーションのリアルタイムなスタイラス入力を無効にする</span><span class="sxs-lookup"><span data-stu-id="471df-102">Disable the RealTimeStylus for WPF Applications</span></span>

<span data-ttu-id="471df-103">Windows Presentation Foundation (WPF) には、Windows 7 のタッチ入力を処理するためのサポートが組み込まれています。</span><span class="sxs-lookup"><span data-stu-id="471df-103">Windows Presentation Foundation (WPF) has built in support for processing Windows 7 touch input.</span></span> <span data-ttu-id="471df-104">このサポートは、タブレット プラットフォームでの <xref:System.Windows.UIElement.OnStylusDown%2A>、<xref:System.Windows.UIElement.OnStylusUp%2A>、および <xref:System.Windows.UIElement.OnStylusMove%2A> イベントとしてのリアルタイム スタイラス入力によって行われます。</span><span class="sxs-lookup"><span data-stu-id="471df-104">The support comes through the tablet platform’s real-time stylus input as <xref:System.Windows.UIElement.OnStylusDown%2A>, <xref:System.Windows.UIElement.OnStylusUp%2A>, and <xref:System.Windows.UIElement.OnStylusMove%2A> events.</span></span> <span data-ttu-id="471df-105">Windows 7 では、Win32 WM_TOUCH ウィンドウ メッセージとしてマルチタッチ入力も提供されます。</span><span class="sxs-lookup"><span data-stu-id="471df-105">Windows 7 also provides multi-touch input as Win32 WM_TOUCH window messages.</span></span> <span data-ttu-id="471df-106">これらの 2 つの API を同じ HWND で同時に使用することはできません。</span><span class="sxs-lookup"><span data-stu-id="471df-106">These two APIs are mutually exclusive on the same HWND.</span></span> <span data-ttu-id="471df-107">タブレット プラットフォームによるタッチ入力 (WPF アプリケーションの既定値) を有効にすると、WM_TOUCH メッセージは無効になります。</span><span class="sxs-lookup"><span data-stu-id="471df-107">Enabling touch input via the tablet platform (the default for WPF applications) disables WM_TOUCH messages.</span></span> <span data-ttu-id="471df-108">そのため、WM_TOUCH を使用して WPF ウィンドウからタッチ メッセージを受け取るには、WPF の組み込みスタイラス サポートを無効にする必要があります。</span><span class="sxs-lookup"><span data-stu-id="471df-108">As a result, to use WM_TOUCH to receive touch messages from a WPF window, you must disable the built-in stylus support in WPF.</span></span> <span data-ttu-id="471df-109">これは、WM_TOUCH を使用するコンポーネントをホストする WPF ウィンドウなどのシナリオに適用されます。</span><span class="sxs-lookup"><span data-stu-id="471df-109">This is applicable in a scenario such as a WPF window hosting a component that uses WM_TOUCH.</span></span>  
  
 <span data-ttu-id="471df-110">WPF によるスタイラス入力のリッスンを無効にするには、WPF ウィンドウによって追加されるすべてのタブレット サポートを削除します。</span><span class="sxs-lookup"><span data-stu-id="471df-110">To disable WPF listening to stylus input, remove any tablet support added by the WPF window.</span></span>  
  
## <a name="example"></a><span data-ttu-id="471df-111">例</span><span class="sxs-lookup"><span data-stu-id="471df-111">Example</span></span>  
 <span data-ttu-id="471df-112">次のサンプル コードでは、リフレクションを使用して既定のタブレット プラットフォームのサポートを削除する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="471df-112">The following sample code shows how to remove the default tablet platform support by using reflection.</span></span>  
  
```csharp  
public static void DisableWPFTabletSupport()  
{  
    // Get a collection of the tablet devices for this window.
    TabletDeviceCollection devices = System.Windows.Input.Tablet.TabletDevices;  
  
    if (devices.Count > 0)  
    {
        // Get the Type of InputManager.  
        Type inputManagerType = typeof(System.Windows.Input.InputManager);  
  
        // Call the StylusLogic method on the InputManager.Current instance.  
        object stylusLogic = inputManagerType.InvokeMember("StylusLogic",  
                    BindingFlags.GetProperty | BindingFlags.Instance | BindingFlags.NonPublic,  
                    null, InputManager.Current, null);  
  
        if (stylusLogic != null)  
        {  
            //  Get the type of the stylusLogic returned from the call to StylusLogic.  
            Type stylusLogicType = stylusLogic.GetType();  
  
            // Loop until there are no more devices to remove.  
            while (devices.Count > 0)  
            {  
                // Remove the first tablet device in the devices collection.  
                stylusLogicType.InvokeMember("OnTabletRemoved",  
                        BindingFlags.InvokeMethod | BindingFlags.Instance | BindingFlags.NonPublic,  
                        null, stylusLogic, new object[] { (uint)0 });  
            }
        }  
  
    }  
}  
```  
  
## <a name="see-also"></a><span data-ttu-id="471df-113">関連項目</span><span class="sxs-lookup"><span data-stu-id="471df-113">See also</span></span>

- [<span data-ttu-id="471df-114">スタイラスからの入力のインターセプト</span><span class="sxs-lookup"><span data-stu-id="471df-114">Intercepting Input from the Stylus</span></span>](intercepting-input-from-the-stylus.md)
