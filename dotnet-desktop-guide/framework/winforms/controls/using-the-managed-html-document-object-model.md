---
title: マネージド HTML DOM (Document Object Model) の使用
ms.date: 03/30/2017
helpviewer_keywords:
- managed HTML DOM
ms.assetid: a017dd5c-cd7b-47e4-952c-f4f54cb48409
ms.openlocfilehash: fe84cabfaabdc14c7dec6cb69653d41b4c6f6416
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/09/2020
ms.locfileid: "96983931"
---
# <a name="using-the-managed-html-document-object-model"></a><span data-ttu-id="4c421-102">マネージド HTML DOM (Document Object Model) の使用</span><span class="sxs-lookup"><span data-stu-id="4c421-102">Using the Managed HTML Document Object Model</span></span>
<span data-ttu-id="4c421-103">マネージ HTML ドキュメントオブジェクトモデル (DOM) は、Internet Explorer によって公開される HTML クラスの .NET Framework に基づいたラッパーを提供します。</span><span class="sxs-lookup"><span data-stu-id="4c421-103">The managed HTML document object model (DOM) provides a wrapper based on the .NET Framework for the HTML classes exposed by Internet Explorer.</span></span> <span data-ttu-id="4c421-104">これらのクラスを使用して、コントロールでホストされている HTML ページを操作し <xref:System.Windows.Forms.WebBrowser> たり、最初から新しいページを作成したりします。</span><span class="sxs-lookup"><span data-stu-id="4c421-104">Use these classes to manipulate HTML pages hosted in the <xref:System.Windows.Forms.WebBrowser> control, or to build new pages from the beginning.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="4c421-105">このセクションの内容</span><span class="sxs-lookup"><span data-stu-id="4c421-105">In This Section</span></span>  
 [<span data-ttu-id="4c421-106">方法: マネージド HTML DOM (Document Object Model) にアクセスする</span><span class="sxs-lookup"><span data-stu-id="4c421-106">How to: Access the Managed HTML Document Object Model</span></span>](how-to-access-the-managed-html-document-object-model.md)  
 <span data-ttu-id="4c421-107"><xref:System.Windows.Forms.HtmlDocument>Windows フォームアプリケーションまたは Internet Explorer でホストされているのいずれかから有効なインスタンスを取得する方法について説明し <xref:System.Windows.Forms.UserControl> ます。</span><span class="sxs-lookup"><span data-stu-id="4c421-107">Describes how to obtain a valid instance of <xref:System.Windows.Forms.HtmlDocument> from either a Windows Forms application or a <xref:System.Windows.Forms.UserControl> hosted in Internet Explorer.</span></span>  
  
 [<span data-ttu-id="4c421-108">方法: マネージド HTML DOM (Document Object Model) の HTML ソースにアクセスする</span><span class="sxs-lookup"><span data-stu-id="4c421-108">How to: Access the HTML Source in the Managed HTML Document Object Model</span></span>](how-to-access-the-html-source-in-the-managed-html-document-object-model.md)  
 <span data-ttu-id="4c421-109">元の変更されていない HTML ソースを取得する方法、および DOM の現在の状態を反映する "ライブ" ソースを取得する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="4c421-109">Describes how to obtain the original, unmodified HTML source, and how to obtain the "live" source that reflects the current state of the DOM.</span></span>  
  
 [<span data-ttu-id="4c421-110">方法: マネージド HTML DOM (Document Object Model) の要素のスタイルを変更する</span><span class="sxs-lookup"><span data-stu-id="4c421-110">How to: Change Styles on an Element in the Managed HTML Document Object Model</span></span>](how-to-change-styles-on-an-element-in-the-managed-html-document-object-model.md)  
 <span data-ttu-id="4c421-111">要素の視覚的な表示を制御するために使用されるスタイルを操作する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="4c421-111">Describes how to manipulate styles, which are used to control the visual display of elements.</span></span>  
  
 [<span data-ttu-id="4c421-112">マネージド HTML DOM (Document Object Model) へのアクセス</span><span class="sxs-lookup"><span data-stu-id="4c421-112">Accessing Frames in the Managed HTML Document Object Model</span></span>](accessing-frames-in-the-managed-html-document-object-model.md)  
 <span data-ttu-id="4c421-113">フレームとフレームセットについて説明します。また、フレームの DOM にアクセスする方法についても説明します。</span><span class="sxs-lookup"><span data-stu-id="4c421-113">Describes what frames and framesets are, and how to access the DOM of a frame.</span></span>  
  
 [<span data-ttu-id="4c421-114">マネージド HTML DOM (Document Object Model) の非公開メンバーへのアクセス</span><span class="sxs-lookup"><span data-stu-id="4c421-114">Accessing Unexposed Members on the Managed HTML Document Object Model</span></span>](accessing-unexposed-members-on-the-managed-html-document-object-model.md)  
 <span data-ttu-id="4c421-115">マネージドに相当するものがない、基になる DOM のメンバーにアクセスする方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="4c421-115">Describes how to access members of the underlying DOM that do not have a managed equivalent.</span></span>  
  
## <a name="reference"></a><span data-ttu-id="4c421-116">関連項目</span><span class="sxs-lookup"><span data-stu-id="4c421-116">Reference</span></span>  
 <xref:System.Windows.Forms.HtmlDocument>  
  
 <xref:System.Windows.Forms.HtmlElement>  
  
 <xref:System.Windows.Forms.HtmlWindow>  
  
## <a name="related-sections"></a><span data-ttu-id="4c421-117">関連項目</span><span class="sxs-lookup"><span data-stu-id="4c421-117">Related Sections</span></span>  
 [<span data-ttu-id="4c421-118">WebBrowser コントロール</span><span class="sxs-lookup"><span data-stu-id="4c421-118">WebBrowser Control</span></span>](webbrowser-control-windows-forms.md)  
