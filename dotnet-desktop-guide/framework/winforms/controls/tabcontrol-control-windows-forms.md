---
title: TabControl コントロール
ms.date: 03/30/2017
helpviewer_keywords:
- TabControl control [Windows Forms]
- tab controls
- tab controls [Windows Forms], creating
- multipage dialog boxes
- dialog boxes [Windows Forms], creating multipage
- property pages [Windows Forms], creating
- tab dialog boxes
ms.assetid: 915091af-93ac-4d3d-8283-738dd2d21ea7
ms.openlocfilehash: c4f310629342e5302021bbc7dc5f92d473377397
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/09/2020
ms.locfileid: "96982408"
---
# <a name="tabcontrol-control-windows-forms"></a><span data-ttu-id="35a33-102">TabControl コントロール (Windows フォーム)</span><span class="sxs-lookup"><span data-stu-id="35a33-102">TabControl Control (Windows Forms)</span></span>
<span data-ttu-id="35a33-103">Windows フォーム `TabControl` は、ノートの仕切りや書類キャビネットのフォルダー セットのラベルに似た、複数のタブを表示します。</span><span class="sxs-lookup"><span data-stu-id="35a33-103">The Windows Forms `TabControl` displays multiple tabs, like dividers in a notebook or labels in a set of folders in a filing cabinet.</span></span> <span data-ttu-id="35a33-104">タブには画像やその他のコントロールを含めることができます。</span><span class="sxs-lookup"><span data-stu-id="35a33-104">The tabs can contain pictures and other controls.</span></span> <span data-ttu-id="35a33-105">プロパティ ページを作成するには、`TabControl` を使用します。</span><span class="sxs-lookup"><span data-stu-id="35a33-105">Use the `TabControl` to create property pages.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="35a33-106">このセクションの内容</span><span class="sxs-lookup"><span data-stu-id="35a33-106">In This Section</span></span>  
 [<span data-ttu-id="35a33-107">TabControl コントロールの概要</span><span class="sxs-lookup"><span data-stu-id="35a33-107">TabControl Control Overview</span></span>](tabcontrol-control-overview-windows-forms.md)  
 <span data-ttu-id="35a33-108">このコントロールについて、および主な機能とプロパティについて説明します。</span><span class="sxs-lookup"><span data-stu-id="35a33-108">Explains what this control is and its key features and properties.</span></span>  
  
 [<span data-ttu-id="35a33-109">方法: タブ ページにコントロールを追加する</span><span class="sxs-lookup"><span data-stu-id="35a33-109">How to: Add a Control to a Tab Page</span></span>](how-to-add-a-control-to-a-tab-page.md)  
 <span data-ttu-id="35a33-110">タブ ページにコントロールを表示するための手順を示します。</span><span class="sxs-lookup"><span data-stu-id="35a33-110">Gives directions for displaying controls on tab pages.</span></span>  
  
 [<span data-ttu-id="35a33-111">方法: Windows フォーム TabControl のタブを追加および削除する</span><span class="sxs-lookup"><span data-stu-id="35a33-111">How to: Add and Remove Tabs with the Windows Forms TabControl</span></span>](how-to-add-and-remove-tabs-with-the-windows-forms-tabcontrol.md)  
 <span data-ttu-id="35a33-112">デザイナーまたはコードのタブを追加および削除する方法を説明します。</span><span class="sxs-lookup"><span data-stu-id="35a33-112">Gives directions for adding and removing tabs in the designer or in code.</span></span>  
  
 [<span data-ttu-id="35a33-113">方法: Windows フォーム TabControl の表示形式を変更する</span><span class="sxs-lookup"><span data-stu-id="35a33-113">How to: Change the Appearance of the Windows Forms TabControl</span></span>](how-to-change-the-appearance-of-the-windows-forms-tabcontrol.md)  
 <span data-ttu-id="35a33-114">個々のタブの外観に影響するプロパティを調整するための手順を示します。</span><span class="sxs-lookup"><span data-stu-id="35a33-114">Gives directions for adjusting properties that affect the appearance of individual tabs.</span></span>  
  
 [<span data-ttu-id="35a33-115">方法: タブ ページを無効化する</span><span class="sxs-lookup"><span data-stu-id="35a33-115">How to: Disable Tab Pages</span></span>](how-to-disable-tab-pages.md)  
 <span data-ttu-id="35a33-116">ユーザーの資格情報に基づいて、タブのページへのアクセスを制限する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="35a33-116">Explains how to restrict access to a tab page, possibly based on user credentials.</span></span>  
  
 <span data-ttu-id="35a33-117">「[方法: デザイナーを使用して Windows フォーム TabControl を使用してタブを追加および削除](add-and-remove-tabs-with-wf-tabcontrol-using-the-designer.md)する」、「[方法: デザイナーを使用してタブページにコントロールを追加](how-to-add-a-control-to-a-tab-page-using-the-designer.md)する」も参照してください。</span><span class="sxs-lookup"><span data-stu-id="35a33-117">Also see [How to: Add and Remove Tabs with the Windows Forms TabControl Using the Designer](add-and-remove-tabs-with-wf-tabcontrol-using-the-designer.md), [How to: Add a Control to a Tab Page Using the Designer](how-to-add-a-control-to-a-tab-page-using-the-designer.md)</span></span>  
  
## <a name="reference"></a><span data-ttu-id="35a33-118">リファレンス</span><span class="sxs-lookup"><span data-stu-id="35a33-118">Reference</span></span>  
 <span data-ttu-id="35a33-119"><xref:System.Windows.Forms.TabControl> クラス</span><span class="sxs-lookup"><span data-stu-id="35a33-119"><xref:System.Windows.Forms.TabControl> class</span></span>  
 <span data-ttu-id="35a33-120">このクラスについて説明し、すべてのメンバーへのリンクの一覧を示します。</span><span class="sxs-lookup"><span data-stu-id="35a33-120">Describes this class and has links to all its members.</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="35a33-121">関連項目</span><span class="sxs-lookup"><span data-stu-id="35a33-121">Related Sections</span></span>  
 [<span data-ttu-id="35a33-122">Windows フォームのダイアログ ボックス</span><span class="sxs-lookup"><span data-stu-id="35a33-122">Dialog Boxes in Windows Forms</span></span>](../dialog-boxes-in-windows-forms.md)  
 <span data-ttu-id="35a33-123">多くの場合、タブを表示するダイアログ ボックスのタスクの一覧を示します。</span><span class="sxs-lookup"><span data-stu-id="35a33-123">Provides a list of tasks for dialog boxes, which often display tabs.</span></span>  
  
 [<span data-ttu-id="35a33-124">Windows フォームで使用するコントロール</span><span class="sxs-lookup"><span data-stu-id="35a33-124">Controls to Use on Windows Forms</span></span>](controls-to-use-on-windows-forms.md)  
 <span data-ttu-id="35a33-125">Windows フォーム コントロールの完全な一覧を、使用に関する情報リンクと共に提供します。</span><span class="sxs-lookup"><span data-stu-id="35a33-125">Provides a complete list of Windows Forms controls, with links to information on their use.</span></span>
