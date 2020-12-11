---
title: TableLayoutPanel コントロールの推奨される手順
ms.date: 03/30/2017
helpviewer_keywords:
- layout [Windows Forms]
- TableLayoutPanel control [Windows Forms], best practices
- forms [Windows Forms], best practices
- AutoSize property [Windows Forms], tableLayoutPanel control
- controls [Windows Forms], sizing
- TableLayoutPanel control [Windows Forms], AutoSize behavior
- layout [Windows Forms], AutoSize
- layout [Windows Forms], best practices
- best practices [Windows Forms], tableLayoutPanel control
- sizing [Windows Forms], automatic
- automatic sizing
ms.assetid: b6706efb-d7a4-45ec-8cf4-08fa993e3afb
ms.openlocfilehash: e46d0fe6913bec61bd56199b7cb56a9b24d15bd0
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/09/2020
ms.locfileid: "96981092"
---
# <a name="best-practices-for-the-tablelayoutpanel-control"></a><span data-ttu-id="2aabc-102">TableLayoutPanel コントロールの推奨される手順</span><span class="sxs-lookup"><span data-stu-id="2aabc-102">Best Practices for the TableLayoutPanel Control</span></span>
<span data-ttu-id="2aabc-103"><xref:System.Windows.Forms.TableLayoutPanel>コントロールには、Windows フォームでを使用する前に慎重に検討する必要がある強力なレイアウト機能が用意されています。</span><span class="sxs-lookup"><span data-stu-id="2aabc-103">The <xref:System.Windows.Forms.TableLayoutPanel> control provides powerful layout features that you should consider carefully before using on your Windows Forms.</span></span>

## <a name="recommendations"></a><span data-ttu-id="2aabc-104">推奨事項</span><span class="sxs-lookup"><span data-stu-id="2aabc-104">Recommendations</span></span>
 <span data-ttu-id="2aabc-105">次の推奨事項は、コントロールを <xref:System.Windows.Forms.TableLayoutPanel> 最大限に活用するのに役立ちます。</span><span class="sxs-lookup"><span data-stu-id="2aabc-105">The following recommendations will help you use the <xref:System.Windows.Forms.TableLayoutPanel> control to its best advantage.</span></span>

### <a name="targeted-use"></a><span data-ttu-id="2aabc-106">対象の使用</span><span class="sxs-lookup"><span data-stu-id="2aabc-106">Targeted Use</span></span>
 <span data-ttu-id="2aabc-107">コントロールは控えめに使用して <xref:System.Windows.Forms.TableLayoutPanel> ください。</span><span class="sxs-lookup"><span data-stu-id="2aabc-107">Use the <xref:System.Windows.Forms.TableLayoutPanel> control sparingly.</span></span> <span data-ttu-id="2aabc-108">サイズ変更可能なレイアウトが必要なすべての状況で使用しないでください。</span><span class="sxs-lookup"><span data-stu-id="2aabc-108">You should not use it in all situations that require a resizable layout.</span></span> <span data-ttu-id="2aabc-109">次の一覧では、コントロールを使用する場合の利点を最大限に活用できるレイアウトについて説明し <xref:System.Windows.Forms.TableLayoutPanel> ます。</span><span class="sxs-lookup"><span data-stu-id="2aabc-109">The following list describes layouts that benefit most from the use of the <xref:System.Windows.Forms.TableLayoutPanel> control:</span></span>

- <span data-ttu-id="2aabc-110">フォームの複数の部分が相互に比例してサイズ変更されるレイアウト。</span><span class="sxs-lookup"><span data-stu-id="2aabc-110">Layouts in which there are multiple parts of the form that resize proportionally to each other.</span></span>

- <span data-ttu-id="2aabc-111">設定に基づいてユーザーがカスタマイズ可能なフィールドを追加または削除するデータ入力フォームなど、実行時に動的に変更または生成されるレイアウト。</span><span class="sxs-lookup"><span data-stu-id="2aabc-111">Layouts that will be modified or generated dynamically at run time, such as data entry forms that have user-customizable fields added or subtracted based on preferences.</span></span>

- <span data-ttu-id="2aabc-112">全体の固定サイズのままにする必要があるレイアウト。</span><span class="sxs-lookup"><span data-stu-id="2aabc-112">Layouts that should remain at an overall fixed size.</span></span> <span data-ttu-id="2aabc-113">たとえば、800 x 600 よりも小さくする必要があるのに、ローカライズされた文字列をサポートする必要があるダイアログボックスがあるとします。</span><span class="sxs-lookup"><span data-stu-id="2aabc-113">For example, you may have a dialog box that should remain smaller than 800 x 600, but you need to support localized strings.</span></span>

 <span data-ttu-id="2aabc-114">次の一覧では、コントロールを使用することによる利点が得られないレイアウトについて説明し <xref:System.Windows.Forms.TableLayoutPanel> ます。</span><span class="sxs-lookup"><span data-stu-id="2aabc-114">The following list describes layouts that do not benefit greatly from using the <xref:System.Windows.Forms.TableLayoutPanel> control:</span></span>

- <span data-ttu-id="2aabc-115">ラベルの1つの列とテキスト入力領域の1つの列でなる単純なデータ入力フォーム。</span><span class="sxs-lookup"><span data-stu-id="2aabc-115">Simple data entry forms with a single column of labels and a single column of text-entry areas.</span></span>

- <span data-ttu-id="2aabc-116">サイズ変更が発生したときに使用可能なすべての領域を埋める必要がある、1つの大きな表示領域があるフォーム。</span><span class="sxs-lookup"><span data-stu-id="2aabc-116">Forms with a single large display area that should fill all the available space when a resize occurs.</span></span> <span data-ttu-id="2aabc-117">この例として、1つのコントロールを表示するフォームが <xref:System.Windows.Forms.PropertyGrid> あります。</span><span class="sxs-lookup"><span data-stu-id="2aabc-117">An example of this is a form that displays a single <xref:System.Windows.Forms.PropertyGrid> control.</span></span> <span data-ttu-id="2aabc-118">この場合は、フォームのサイズが変更されたときに他のものが展開されないため、アンカーを使用します。</span><span class="sxs-lookup"><span data-stu-id="2aabc-118">In this case, use anchoring, because nothing else should expand when the form is resized.</span></span>

 <span data-ttu-id="2aabc-119">コントロールに必要なコントロールを慎重に選択して <xref:System.Windows.Forms.TableLayoutPanel> ください。</span><span class="sxs-lookup"><span data-stu-id="2aabc-119">Choose carefully which controls need to be in a <xref:System.Windows.Forms.TableLayoutPanel> control.</span></span> <span data-ttu-id="2aabc-120">アンカーを使用してテキストを30% 拡張する余地がある場合は、プロパティのみを使用することを検討してください <xref:System.Windows.Forms.Control.Anchor%2A> 。</span><span class="sxs-lookup"><span data-stu-id="2aabc-120">If you have room for your text to grow by 30% using anchoring, consider using the <xref:System.Windows.Forms.Control.Anchor%2A> property only.</span></span> <span data-ttu-id="2aabc-121">レイアウトに必要な領域を見積もることができる場合は、 <xref:System.Windows.Forms.Control.Dock%2A> との使用 <xref:System.Windows.Forms.Control.Anchor%2A> は、残りの領域と動作の詳細を推定するよりも簡単です <xref:System.Windows.Forms.Control.AutoSize%2A> 。</span><span class="sxs-lookup"><span data-stu-id="2aabc-121">If you can estimate the space required by your layout, use of <xref:System.Windows.Forms.Control.Dock%2A> and <xref:System.Windows.Forms.Control.Anchor%2A> is easier than estimating the details of remaining space and <xref:System.Windows.Forms.Control.AutoSize%2A> behavior.</span></span>

 <span data-ttu-id="2aabc-122">一般に、コントロールを使用してレイアウトをデザインする場合は、 <xref:System.Windows.Forms.TableLayoutPanel> デザインをできるだけ単純なものにしてください。</span><span class="sxs-lookup"><span data-stu-id="2aabc-122">In general, when designing your layout with the <xref:System.Windows.Forms.TableLayoutPanel> control, keep the design as simple as possible.</span></span>

### <a name="use-the-document-outline-window"></a><span data-ttu-id="2aabc-123">[ドキュメントアウトライン] ウィンドウを使用する</span><span class="sxs-lookup"><span data-stu-id="2aabc-123">Use the Document Outline Window</span></span>
 <span data-ttu-id="2aabc-124">[ドキュメントアウトライン] ウィンドウには、レイアウトのツリービューが表示されます。このビューを使用して、コントロールの z オーダーと親子関係を操作できます。</span><span class="sxs-lookup"><span data-stu-id="2aabc-124">The Document Outline window gives you a tree view of your layout, which you can use to manipulate the z-order and parent-child relationships of your controls.</span></span> <span data-ttu-id="2aabc-125">[ **表示] メニュー** の [ **その他のウィンドウ**] をポイントし、[ **ドキュメントアウトライン**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="2aabc-125">From the **View menu**, select **Other Windows**, then select **Document Outline**.</span></span>

### <a name="avoid-nesting"></a><span data-ttu-id="2aabc-126">入れ子の回避</span><span class="sxs-lookup"><span data-stu-id="2aabc-126">Avoid Nesting</span></span>
 <span data-ttu-id="2aabc-127"><xref:System.Windows.Forms.TableLayoutPanel>コントロール内で他のコントロールを入れ子にしないように <xref:System.Windows.Forms.TableLayoutPanel> します。</span><span class="sxs-lookup"><span data-stu-id="2aabc-127">Avoid nesting other <xref:System.Windows.Forms.TableLayoutPanel> controls within a <xref:System.Windows.Forms.TableLayoutPanel> control.</span></span> <span data-ttu-id="2aabc-128">入れ子になったレイアウトのデバッグは困難な場合があります。</span><span class="sxs-lookup"><span data-stu-id="2aabc-128">Debugging nested layouts can be difficult.</span></span>

### <a name="avoid-visual-inheritance"></a><span data-ttu-id="2aabc-129">ビジュアルの継承を避ける</span><span class="sxs-lookup"><span data-stu-id="2aabc-129">Avoid Visual Inheritance</span></span>
 <span data-ttu-id="2aabc-130">コントロールは、visual <xref:System.Windows.Forms.TableLayoutPanel> Studio の Windows フォームデザイナーでのビジュアル継承をサポートしていません。</span><span class="sxs-lookup"><span data-stu-id="2aabc-130">The <xref:System.Windows.Forms.TableLayoutPanel> control does not support visual inheritance in the Windows Forms Designer in Visual Studio.</span></span> <span data-ttu-id="2aabc-131"><xref:System.Windows.Forms.TableLayoutPanel>派生クラスのコントロールは、デザイン時に "locked" として表示されます。</span><span class="sxs-lookup"><span data-stu-id="2aabc-131">A <xref:System.Windows.Forms.TableLayoutPanel> control in a derived class appears as "locked" at design time.</span></span>

## <a name="see-also"></a><span data-ttu-id="2aabc-132">関連項目</span><span class="sxs-lookup"><span data-stu-id="2aabc-132">See also</span></span>

- <xref:System.Windows.Forms.TableLayoutPanel>
- <xref:System.Windows.Forms.FlowLayoutPanel>
