---
title: WPF コントロールの使用
ms.date: 03/30/2017
helpviewer_keywords:
- Windows Forms Designer [Windows Forms], interoperability with WPF
- interoperability [WPF]
ms.assetid: 03c85dce-26ad-44cd-bc1d-8e0cb56de096
ms.openlocfilehash: e2e9fd6f0828d76494ed3d602b00b5d67770fc47
ms.sourcegitcommit: 7f48b9ecf8a30db42c8ecea0dd4df577736631a2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/28/2021
ms.locfileid: "98957540"
---
# <a name="use-wpf-controls-in-windows-forms-apps"></a><span data-ttu-id="8f0af-102">Windows フォームアプリで WPF コントロールを使用する</span><span class="sxs-lookup"><span data-stu-id="8f0af-102">Use WPF controls in Windows Forms apps</span></span>

<span data-ttu-id="8f0af-103">Windows フォームベースのアプリケーションでは、Windows Presentation Foundation (WPF) コントロールを使用できます。</span><span class="sxs-lookup"><span data-stu-id="8f0af-103">You can use Windows Presentation Foundation (WPF) controls in Windows Forms-based applications.</span></span> <span data-ttu-id="8f0af-104">これらは2つの異なるビューテクノロジですが、円滑に相互運用されます。</span><span class="sxs-lookup"><span data-stu-id="8f0af-104">Although these are two different view technologies, they interoperate smoothly.</span></span>

<span data-ttu-id="8f0af-105">Visual Studio の Windows フォームデザイナーには、Windows Presentation Foundation コントロールをホストするためのビジュアルデザイン環境が用意されています。</span><span class="sxs-lookup"><span data-stu-id="8f0af-105">The Windows Forms Designer in Visual Studio provides a visual design environment for hosting Windows Presentation Foundation controls.</span></span> <span data-ttu-id="8f0af-106">WPF コントロールは、という名前の特殊な Windows フォームコントロールによってホストされ <xref:System.Windows.Forms.Integration.ElementHost> ます。</span><span class="sxs-lookup"><span data-stu-id="8f0af-106">A WPF control is hosted by a special Windows Forms control that's named <xref:System.Windows.Forms.Integration.ElementHost>.</span></span> <span data-ttu-id="8f0af-107">このコントロールにより、WPF コントロールはフォームのレイアウトに参加し、キーボードおよびマウスメッセージを受け取ることができます。</span><span class="sxs-lookup"><span data-stu-id="8f0af-107">This control enables the WPF control to participate in the form's layout and to receive keyboard and mouse messages.</span></span> <span data-ttu-id="8f0af-108">デザイン時には、 <xref:System.Windows.Forms.Integration.ElementHost> Windows フォームコントロールと同じようにコントロールを配置できます。</span><span class="sxs-lookup"><span data-stu-id="8f0af-108">At design time, you can arrange the <xref:System.Windows.Forms.Integration.ElementHost> control just as you would any Windows Forms control.</span></span>

<span data-ttu-id="8f0af-109">WPF ベースのアプリケーションでは、Windows フォームコントロールを使用することもできます。</span><span class="sxs-lookup"><span data-stu-id="8f0af-109">You can also use Windows Forms controls in WPF-based applications.</span></span> <span data-ttu-id="8f0af-110">詳細については、「 [Visual Studio での XAML のデザイン](/visualstudio/xaml-tools/designing-xaml-in-visual-studio)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="8f0af-110">For more information, see [Design XAML in Visual Studio](/visualstudio/xaml-tools/designing-xaml-in-visual-studio).</span></span>

## <a name="see-also"></a><span data-ttu-id="8f0af-111">関連項目</span><span class="sxs-lookup"><span data-stu-id="8f0af-111">See also</span></span>

- [<span data-ttu-id="8f0af-112">WPF と Windows フォームの相互運用</span><span class="sxs-lookup"><span data-stu-id="8f0af-112">WPF and Windows Forms interoperation</span></span>](/dotnet/framework/wpf/advanced/wpf-and-windows-forms-interoperation)
