---
title: Unmanaged apps
ms.date: 03/30/2017
helpviewer_keywords:
- ActiveX controls [Windows Forms]
- COM interop [Windows Forms], Windows Forms
- COM [Windows Forms]
- Windows Forms, unmanaged
- Windows Forms, interop
ms.assetid: 81bc100c-fa49-4614-85a6-0f7ab59eac8a
ms.openlocfilehash: 2d60eef2788f144a4b14facdce6e179e7d0fc3c6
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/09/2020
ms.locfileid: "96975193"
---
# <a name="windows-forms-and-unmanaged-applications"></a><span data-ttu-id="4bf48-102">Windows フォームとアンマネージ アプリケーション</span><span class="sxs-lookup"><span data-stu-id="4bf48-102">Windows Forms and Unmanaged Applications</span></span>

<span data-ttu-id="4bf48-103">Windows フォーム アプリケーションとコントロールは、いくつかの注意事項がありますが、アンマネージ アプリケーションと相互運用できます。</span><span class="sxs-lookup"><span data-stu-id="4bf48-103">Windows Forms applications and controls can interoperate with unmanaged applications, with some caveats.</span></span> <span data-ttu-id="4bf48-104">次のセクションでは、Windows フォーム アプリケーションとコントロールがサポートするシナリオと構成、および、サポートしないシナリオと構成について説明します。</span><span class="sxs-lookup"><span data-stu-id="4bf48-104">The following sections describe the scenarios and configurations that Windows Forms applications and controls support and those that they do not support.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="4bf48-105">このセクションの内容</span><span class="sxs-lookup"><span data-stu-id="4bf48-105">In This Section</span></span>  

 [<span data-ttu-id="4bf48-106">Windows フォームおよびアンマネージ アプリケーションの概要</span><span class="sxs-lookup"><span data-stu-id="4bf48-106">Windows Forms and Unmanaged Applications Overview</span></span>](windows-forms-and-unmanaged-applications-overview.md)  
 <span data-ttu-id="4bf48-107">アンマネージ アプリケーションで使用する Windows フォーム コントロールを実装する方法に関する一般的な情報を提供します。</span><span class="sxs-lookup"><span data-stu-id="4bf48-107">Offers general information about how to use and implement Windows Forms controls that work with unmanaged applications.</span></span>  
  
 [<span data-ttu-id="4bf48-108">方法: ShowDialog メソッドで Windows フォームを表示して COM 相互運用機能をサポートする</span><span class="sxs-lookup"><span data-stu-id="4bf48-108">How to: Support COM Interop by Displaying a Windows Form with the ShowDialog Method</span></span>](com-interop-by-displaying-a-windows-form-shadow.md)  
 <span data-ttu-id="4bf48-109"><xref:System.Windows.Forms.Form.ShowDialog%2A?displayProperty=nameWithType> メソッドを使用して Windows フォームをアンマネージ アプリケーションで実行する方法を示すコード例を提供します。</span><span class="sxs-lookup"><span data-stu-id="4bf48-109">Provides a code example that shows how to use the <xref:System.Windows.Forms.Form.ShowDialog%2A?displayProperty=nameWithType> method to run a Windows Form in an unmanaged application.</span></span>  
  
 [<span data-ttu-id="4bf48-110">方法: 独自のスレッドで各 Windows フォームを表示して COM 相互運用機能をサポートする</span><span class="sxs-lookup"><span data-stu-id="4bf48-110">How to: Support COM Interop by Displaying Each Windows Form on Its Own Thread</span></span>](how-to-support-com-interop-by-displaying-each-windows-form-on-its-own-thread.md)  
 <span data-ttu-id="4bf48-111">独自のスレッドで Windows フォームを実行する方法を示すコード例を提供します。</span><span class="sxs-lookup"><span data-stu-id="4bf48-111">Provides a code example that shows how to run a Windows Form on its own thread.</span></span>  
  
 <span data-ttu-id="4bf48-112">「 [チュートリアル: Windows フォームを別個のスレッドに表示することによって COM 相互運用をサポートする](/previous-versions/visualstudio/visual-studio-2010/ms233639(v=vs.100))」も参照してください。</span><span class="sxs-lookup"><span data-stu-id="4bf48-112">Also see [Walkthrough: Supporting COM Interop by Displaying Each Windows Form on Its Own Thread](/previous-versions/visualstudio/visual-studio-2010/ms233639(v=vs.100)).</span></span>  
  
## <a name="reference"></a><span data-ttu-id="4bf48-113">リファレンス</span><span class="sxs-lookup"><span data-stu-id="4bf48-113">Reference</span></span>  

 <xref:System.Windows.Forms.Form.ShowDialog%2A?displayProperty=nameWithType>  
 <span data-ttu-id="4bf48-114">Windows フォーム用の個別のスレッドの作成に使用します。</span><span class="sxs-lookup"><span data-stu-id="4bf48-114">Used to create a separate thread for a Windows Form.</span></span>  
  
 <xref:System.Windows.Forms.Application.Run%2A?displayProperty=nameWithType>  
 <span data-ttu-id="4bf48-115">スレッドのメッセージ ループを開始します。</span><span class="sxs-lookup"><span data-stu-id="4bf48-115">Starts a message loop for a thread.</span></span>  
  
 <xref:System.Windows.Forms.Control.Invoke%2A>  
 <span data-ttu-id="4bf48-116">フォームにアンマネージ アプリケーションからの呼び出しをマーシャリングします。</span><span class="sxs-lookup"><span data-stu-id="4bf48-116">Marshals calls from an unmanaged application to a form.</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="4bf48-117">関連項目</span><span class="sxs-lookup"><span data-stu-id="4bf48-117">Related Sections</span></span>  

 [<span data-ttu-id="4bf48-118">COM への .NET Framework コンポーネントの公開</span><span class="sxs-lookup"><span data-stu-id="4bf48-118">Exposing .NET Framework Components to COM</span></span>](/dotnet/framework/interop/exposing-dotnet-components-to-co)  
 <span data-ttu-id="4bf48-119">.NET Framework の型をアンマネージ アプリケーションで使用する方法に関する一般情報を提供します。</span><span class="sxs-lookup"><span data-stu-id="4bf48-119">Offers general information about how to use .NET Framework types in unmanaged applications.</span></span>
