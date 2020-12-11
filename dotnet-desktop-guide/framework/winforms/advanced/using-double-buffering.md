---
title: ダブル バッファリングの使用
ms.date: 03/30/2017
helpviewer_keywords:
- graphics [Windows Forms], double buffering
- double buffering
- flicker [Windows Forms], reducing in Windows Forms
- buffering [Windows Forms], double buffering
ms.assetid: dc484e33-7101-4e4b-ada5-d3c96155fbcd
ms.openlocfilehash: 5b22336221c7bdda3c9dd7adf23308a2b0bad450
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/09/2020
ms.locfileid: "96975233"
---
# <a name="using-double-buffering"></a><span data-ttu-id="61b0c-102">ダブル バッファリングの使用</span><span class="sxs-lookup"><span data-stu-id="61b0c-102">Using Double Buffering</span></span>
<span data-ttu-id="61b0c-103">ダブルバッファリングされたグラフィックスを使用すると、複雑な描画操作を含むアプリケーションのちらつきを減らすことができます。</span><span class="sxs-lookup"><span data-stu-id="61b0c-103">You can use double-buffered graphics to reduce flicker in your applications that contain complex painting operations.</span></span> <span data-ttu-id="61b0c-104">.NET Framework には、ダブルバッファリングの組み込みサポートが含まれています。また、グラフィックスを手動で管理して表示することもできます。</span><span class="sxs-lookup"><span data-stu-id="61b0c-104">The .NET Framework contains built-in support for double-buffering or you can manage and render graphics manually.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="61b0c-105">このセクションの内容</span><span class="sxs-lookup"><span data-stu-id="61b0c-105">In This Section</span></span>  
 [<span data-ttu-id="61b0c-106">ダブル バッファリングされたグラフィックス</span><span class="sxs-lookup"><span data-stu-id="61b0c-106">Double Buffered Graphics</span></span>](double-buffered-graphics.md)  
 <span data-ttu-id="61b0c-107">ダブルバッファリングの概念と、.NET Framework サポートの概要について説明します。</span><span class="sxs-lookup"><span data-stu-id="61b0c-107">Introduces double buffering concept and outlines .NET Framework support.</span></span>  
  
 [<span data-ttu-id="61b0c-108">方法: フォームとコントロールのダブル バッファリングを行うことによってグラフィックスのちらつきを軽減する</span><span class="sxs-lookup"><span data-stu-id="61b0c-108">How to: Reduce Graphics Flicker with Double Buffering for Forms and Controls</span></span>](how-to-reduce-graphics-flicker-with-double-buffering-for-forms-and-controls.md)  
 <span data-ttu-id="61b0c-109">.NET Framework で既定のダブルバッファリングサポートを使用する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="61b0c-109">Demonstrates how to use the default double buffering support in the .NET Framework.</span></span>  
  
 [<span data-ttu-id="61b0c-110">方法: バッファリングされたグラフィックスを手動で管理する</span><span class="sxs-lookup"><span data-stu-id="61b0c-110">How to: Manually Manage Buffered Graphics</span></span>](how-to-manually-manage-buffered-graphics.md)  
 <span data-ttu-id="61b0c-111">アプリケーションでダブルバッファリングを管理する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="61b0c-111">Shows how to manage double buffering in applications.</span></span>  
  
 [<span data-ttu-id="61b0c-112">方法: バッファリングされたグラフィックスを手動で描画する</span><span class="sxs-lookup"><span data-stu-id="61b0c-112">How to: Manually Render Buffered Graphics</span></span>](how-to-manually-render-buffered-graphics.md)  
 <span data-ttu-id="61b0c-113">ダブルバッファリングされたグラフィックスを表示する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="61b0c-113">Demonstrates how to render double-buffered graphics.</span></span>  
  
## <a name="reference"></a><span data-ttu-id="61b0c-114">リファレンス</span><span class="sxs-lookup"><span data-stu-id="61b0c-114">Reference</span></span>  
 <span data-ttu-id="61b0c-115"><xref:System.Windows.Forms.Control.SetStyle%2A> ダブルバッファリングを有効にする制御メソッド。</span><span class="sxs-lookup"><span data-stu-id="61b0c-115"><xref:System.Windows.Forms.Control.SetStyle%2A> Control method that enables double buffering.</span></span>  
  
 <span data-ttu-id="61b0c-116"><xref:System.Drawing.BufferedGraphicsContext> グラフィックスバッファーを作成するためのメソッドを提供します。</span><span class="sxs-lookup"><span data-stu-id="61b0c-116"><xref:System.Drawing.BufferedGraphicsContext> Provides methods for creating graphics buffers.</span></span>  
  
 <xref:System.Drawing.BufferedGraphicsManager>  
 <span data-ttu-id="61b0c-117">アプリケーションドメインのバッファーされたグラフィックスコンテキストへのアクセスを提供します。</span><span class="sxs-lookup"><span data-stu-id="61b0c-117">Provides access to the buffered graphics context for a application domain.</span></span>
