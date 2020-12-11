---
title: ユーザーヘルプの統合
ms.date: 03/30/2017
helpviewer_keywords:
- Help [Windows Forms], Windows Forms (using designer)
- Windows Forms, Help (using designer)
- HTML Help [Windows Forms], Windows Forms (using designer)
- Help [Windows Forms], Windows applications (using designer)
- forms. Help (using designer)
- Windows applications [Windows Forms], Help (using designer)
ms.assetid: a8563d25-8a75-4bc7-a024-f1870591b50f
ms.openlocfilehash: e1d9921b01c1fafe690a2727f2a45443d6f42728
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/09/2020
ms.locfileid: "96981696"
---
# <a name="integrating-user-help-in-windows-forms"></a><span data-ttu-id="2cfa2-102">Windows フォームでのヘルプの統合</span><span class="sxs-lookup"><span data-stu-id="2cfa2-102">Integrating User Help in Windows Forms</span></span>
<span data-ttu-id="2cfa2-103">Windows ベースのアプリケーションの構築については、重要なものの、見過ごされることが多いので、ユーザーが混乱を招くことがあります。</span><span class="sxs-lookup"><span data-stu-id="2cfa2-103">An essential, but often overlooked, aspect of building Windows-based applications is the Help system, as this is where users turn for assistance in times of confusion.</span></span> <span data-ttu-id="2cfa2-104">Windows フォームは、 [HelpProvider コンポーネント](../controls/helpprovider-component-windows-forms.md)によって提供される2種類のヘルプをサポートしています。</span><span class="sxs-lookup"><span data-stu-id="2cfa2-104">Windows Forms support two different types of Help, each provided by the [HelpProvider Component](../controls/helpprovider-component-windows-forms.md).</span></span> <span data-ttu-id="2cfa2-105">最初の方法では、HTML または HTML ヘルプ1のヘルプファイルにユーザーをポイントします。*x* 以上の形式。</span><span class="sxs-lookup"><span data-stu-id="2cfa2-105">The first involves pointing the user to a Help file of either HTML or HTML Help 1.*x* or greater format.</span></span> <span data-ttu-id="2cfa2-106">2番目の方法では、個々のコントロールについて簡単な「何ができるか」と入力します。これは、ダイアログボックスで特に便利です。</span><span class="sxs-lookup"><span data-stu-id="2cfa2-106">The second can display brief "What's This"-type Help on individual controls; this is especially useful on dialog boxes.</span></span> <span data-ttu-id="2cfa2-107">どちらの種類のヘルプも同じ形式で使用できます。</span><span class="sxs-lookup"><span data-stu-id="2cfa2-107">Both types of Help can be used on the same form.</span></span>  
  
 <span data-ttu-id="2cfa2-108">また、 [ツールヒントコンポーネント](../controls/tooltip-component-windows-forms.md) を使用して、Windows フォームのコントロールに個別のヘルプを提供することもできます。</span><span class="sxs-lookup"><span data-stu-id="2cfa2-108">Additionally, the [ToolTip Component](../controls/tooltip-component-windows-forms.md) can be used to provide individual Help for controls on Windows Forms.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="2cfa2-109">このセクションの内容</span><span class="sxs-lookup"><span data-stu-id="2cfa2-109">In This Section</span></span>  
 [<span data-ttu-id="2cfa2-110">方法: Windows アプリケーションにヘルプを提供する</span><span class="sxs-lookup"><span data-stu-id="2cfa2-110">How to: Provide Help in a Windows Application</span></span>](how-to-provide-help-in-a-windows-application.md)  
 <span data-ttu-id="2cfa2-111">コンポーネントを使用して、 `HelpProvider` ヘルプシステム内のファイルにコントロールをリンクする方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="2cfa2-111">Explains how to use the `HelpProvider` component to link controls to files in a Help system.</span></span>  
  
 [<span data-ttu-id="2cfa2-112">方法: ポップアップ ヘルプを表示する</span><span class="sxs-lookup"><span data-stu-id="2cfa2-112">How to: Display Pop-up Help</span></span>](how-to-display-pop-up-help.md)  
 <span data-ttu-id="2cfa2-113">コンポーネントを使用して `HelpProvider` Windows フォームのポップアップヘルプを表示する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="2cfa2-113">Explains how to use the `HelpProvider` component to show pop-up Help on Windows Forms.</span></span>  
  
 [<span data-ttu-id="2cfa2-114">ツールヒントを使用したコントロールのヘルプ</span><span class="sxs-lookup"><span data-stu-id="2cfa2-114">Control Help Using ToolTips</span></span>](control-help-using-tooltips.md)  
 <span data-ttu-id="2cfa2-115">コンポーネントを使用して `ToolTip` コントロール固有のヘルプを表示する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="2cfa2-115">Describes using the `ToolTip` component to show control-specific Help.</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="2cfa2-116">関連項目</span><span class="sxs-lookup"><span data-stu-id="2cfa2-116">Related Sections</span></span>  
 [<span data-ttu-id="2cfa2-117">HelpProvider コンポーネント</span><span class="sxs-lookup"><span data-stu-id="2cfa2-117">HelpProvider Component</span></span>](../controls/helpprovider-component-windows-forms.md)  
 <span data-ttu-id="2cfa2-118">コンポーネントの基本について説明し `HelpProvider` ます。</span><span class="sxs-lookup"><span data-stu-id="2cfa2-118">Explains the basics of the `HelpProvider` component.</span></span>  
  
 [<span data-ttu-id="2cfa2-119">ToolTip コンポーネント</span><span class="sxs-lookup"><span data-stu-id="2cfa2-119">ToolTip Component</span></span>](../controls/tooltip-component-windows-forms.md)  
 <span data-ttu-id="2cfa2-120">コンポーネントの基本について説明し `ToolTip` ます。</span><span class="sxs-lookup"><span data-stu-id="2cfa2-120">Explains the basics of the `ToolTip` component.</span></span>  
  
 [<span data-ttu-id="2cfa2-121">Windows フォームの概要</span><span class="sxs-lookup"><span data-stu-id="2cfa2-121">Windows Forms Overview</span></span>](../windows-forms-overview.md)  
 <span data-ttu-id="2cfa2-122">Windows フォームの基本について説明します。</span><span class="sxs-lookup"><span data-stu-id="2cfa2-122">Explains the basics of Windows Forms.</span></span>  
  
 [<span data-ttu-id="2cfa2-123">Windows フォーム</span><span class="sxs-lookup"><span data-stu-id="2cfa2-123">Windows Forms</span></span>](../index.yml)  
 <span data-ttu-id="2cfa2-124">Windows フォームの概要について説明します。</span><span class="sxs-lookup"><span data-stu-id="2cfa2-124">Provides an overview of Windows Forms.</span></span>
