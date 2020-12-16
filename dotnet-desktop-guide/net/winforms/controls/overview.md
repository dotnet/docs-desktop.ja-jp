---
title: コントロールの使用の概要
description: .NET 用の Windows フォームでのコントロールの使用方法について説明します。 コントロールは、ユーザーに機能を提供する再利用可能なコンポーネントです。 すぐに使用できるさまざまなコントロールが用意されています。 新しいコントロールを作成することもできます。
ms.date: 10/26/2020
ms.topic: overview
dev_langs:
- csharp
- vb
helpviewer_keywords:
- Windows Forms, controls
- controls [Windows Forms]
- custom controls [Windows Forms]
ms.openlocfilehash: 7476ce47a1767a2ab13c25a7408f5861014e7de8
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/09/2020
ms.locfileid: "96942335"
---
# <a name="overview-of-using-controls-windows-forms-net"></a><span data-ttu-id="01e7b-106">コントロールの使用の概要 (Windows フォーム .NET)</span><span class="sxs-lookup"><span data-stu-id="01e7b-106">Overview of using controls (Windows Forms .NET)</span></span>

<span data-ttu-id="01e7b-107">Windows フォーム コントロールは、ユーザー インターフェイスの機能をカプセル化して、クライアント側の Windows ベースのアプリケーションで使用される再利用可能なコンポーネントです。</span><span class="sxs-lookup"><span data-stu-id="01e7b-107">Windows Forms controls are reusable components that encapsulate user interface functionality and are used in client-side, Windows-based applications.</span></span> <span data-ttu-id="01e7b-108">Windows フォームは、すぐに使用できる多数のコントロールを提供するだけでなく、独自のコントロールを開発するためのインフラストラクチャも提供します。</span><span class="sxs-lookup"><span data-stu-id="01e7b-108">Not only does Windows Forms provide many ready-to-use controls, it also provides the infrastructure for developing your own controls.</span></span> <span data-ttu-id="01e7b-109">既存のコントロールの結合、既存のコントロールの拡張、または独自のカスタム コントロールの記述ができます。</span><span class="sxs-lookup"><span data-stu-id="01e7b-109">You can combine existing controls, extend existing controls, or author your own custom controls.</span></span> <span data-ttu-id="01e7b-110">詳細については、「[カスタム コントロールの種類](custom.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="01e7b-110">For more information, see [Types of custom controls](custom.md).</span></span>

[!INCLUDE [desktop guide under construction](../../includes/desktop-guide-preview-note.md)]

## <a name="adding-controls"></a><span data-ttu-id="01e7b-111">コントロールの追加</span><span class="sxs-lookup"><span data-stu-id="01e7b-111">Adding controls</span></span>

<span data-ttu-id="01e7b-112">コントロールは、Visual Studio デザイナーを使用して追加します。</span><span class="sxs-lookup"><span data-stu-id="01e7b-112">Controls are added through the Visual Studio Designer.</span></span> <span data-ttu-id="01e7b-113">デザイナーを使用すると、コントロールの配置、サイズ変更、配置、および移動を行うことができます。</span><span class="sxs-lookup"><span data-stu-id="01e7b-113">With the Designer, you can place, size, align, and move controls.</span></span> <span data-ttu-id="01e7b-114">または、コードを使用してコントロールを追加することもできます。</span><span class="sxs-lookup"><span data-stu-id="01e7b-114">Alternatively, controls can be added through code.</span></span> <span data-ttu-id="01e7b-115">詳細については、「[コントロールを追加する (Windows フォーム)](how-to-add-to-a-form.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="01e7b-115">For more information, see [Add a control (Windows Forms)](how-to-add-to-a-form.md).</span></span>

## <a name="layout-options"></a><span data-ttu-id="01e7b-116">レイアウト オプション</span><span class="sxs-lookup"><span data-stu-id="01e7b-116">Layout options</span></span>

<span data-ttu-id="01e7b-117">親の上に表示されるコントロールの位置は、親サーフェイスの左上に対して相対的な <xref:System.Windows.Forms.Control.Location> プロパティの値によって決まります。</span><span class="sxs-lookup"><span data-stu-id="01e7b-117">The position a control appears on a parent is determined by the value of the <xref:System.Windows.Forms.Control.Location> property relative to the top-left of the parent surface.</span></span> <span data-ttu-id="01e7b-118">親の左上の位置座標は `(x0,y0)` です。</span><span class="sxs-lookup"><span data-stu-id="01e7b-118">The top-left position coordinate in the parent is `(x0,y0)`.</span></span> <span data-ttu-id="01e7b-119">コントロールのサイズは、<xref:System.Windows.Forms.Control.Size> プロパティによって決定され、コントロールの幅と高さを表します。</span><span class="sxs-lookup"><span data-stu-id="01e7b-119">The size of the control is determined by the <xref:System.Windows.Forms.Control.Size> property and represents the width and height of the control.</span></span>

<span data-ttu-id="01e7b-120">手動での配置やサイズ変更以外にも、コントロールの自動配置に役立つさまざまなコンテナー コントロールが用意されています。</span><span class="sxs-lookup"><span data-stu-id="01e7b-120">Besides manual positioning and sizing, various container controls are provided that help with automatic placement of controls.</span></span>

<span data-ttu-id="01e7b-121">詳細については、「[コントロールの位置とレイアウト](layout.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="01e7b-121">For more information, see [Position and layout of controls](layout.md).</span></span>
<!-- TODO

## Control events

-->

## <a name="see-also"></a><span data-ttu-id="01e7b-122">関連項目</span><span class="sxs-lookup"><span data-stu-id="01e7b-122">See also</span></span>

- [<span data-ttu-id="01e7b-123">コントロールの位置とレイアウト</span><span class="sxs-lookup"><span data-stu-id="01e7b-123">Position and layout of controls</span></span>](layout.md)
- [<span data-ttu-id="01e7b-124">Label コントロールの概要 (Windows フォーム .NET)</span><span class="sxs-lookup"><span data-stu-id="01e7b-124">Label control overview (Windows Forms .NET)</span></span>](labels.md)
- [<span data-ttu-id="01e7b-125">コントロールを追加する (Windows フォーム .NET)</span><span class="sxs-lookup"><span data-stu-id="01e7b-125">Add a control (Windows Forms .NET)</span></span>](how-to-add-to-a-form.md)
