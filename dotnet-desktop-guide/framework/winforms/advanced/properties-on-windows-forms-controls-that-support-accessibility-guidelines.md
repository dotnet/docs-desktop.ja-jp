---
title: コントロールのアクセシビリティプロパティ
ms.date: 03/30/2017
helpviewer_keywords:
- Windows Forms, accessibility properties of controls
- accessibility [Windows Forms], Windows Forms control properties
ms.assetid: ad3567a6-313b-4708-9e15-f487a831f049
ms.openlocfilehash: 73d81f5b5f656ed5ef90bdd9b6fe1b3293123f97
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/09/2020
ms.locfileid: "96979729"
---
# <a name="properties-on-windows-forms-controls-that-support-accessibility-guidelines"></a><span data-ttu-id="52c32-102">ユーザ補助ガイドラインをサポートする Windows フォーム コントロールのプロパティ</span><span class="sxs-lookup"><span data-stu-id="52c32-102">Properties on Windows Forms Controls That Support Accessibility Guidelines</span></span>
<span data-ttu-id="52c32-103">キーボードフォーカスの公開や画面要素の公開など、アクセシビリティに関する多くのガイドラインをサポートするために、Windows フォームの標準ツールボックスのコントロール。</span><span class="sxs-lookup"><span data-stu-id="52c32-103">Controls on the standard toolbox for Windows Forms support many of the accessibility guidelines, including exposing the keyboard focus and exposing the screen elements.</span></span>  
  
## <a name="planning-ahead-for-accessibility"></a><span data-ttu-id="52c32-104">ユーザー補助のための事前計画</span><span class="sxs-lookup"><span data-stu-id="52c32-104">Planning Ahead for Accessibility</span></span>  
 <span data-ttu-id="52c32-105">コントロールのプロパティは、次の表に示すように、他のアクセシビリティガイドラインをサポートするために使用できます。</span><span class="sxs-lookup"><span data-stu-id="52c32-105">The controls' properties can be used to support other accessibility guidelines as shown in the following table.</span></span> <span data-ttu-id="52c32-106">また、メニューを使用して、プログラムの機能へのアクセスを提供する必要があります。</span><span class="sxs-lookup"><span data-stu-id="52c32-106">Additionally, you should use menus to provide access to program features.</span></span>  
  
|<span data-ttu-id="52c32-107">Control プロパティ</span><span class="sxs-lookup"><span data-stu-id="52c32-107">Control Property</span></span>|<span data-ttu-id="52c32-108">アクセシビリティに関する考慮事項</span><span class="sxs-lookup"><span data-stu-id="52c32-108">Considerations for Accessibility</span></span>|  
|----------------------|--------------------------------------|  
|<span data-ttu-id="52c32-109">AccessibleDescription</span><span class="sxs-lookup"><span data-stu-id="52c32-109">AccessibleDescription</span></span>|<span data-ttu-id="52c32-110">説明は、スクリーンリーダーなどのユーザー補助機能に報告されます。</span><span class="sxs-lookup"><span data-stu-id="52c32-110">The description is reported to accessibility aids such as screen readers.</span></span> <span data-ttu-id="52c32-111">ユーザー補助機能は専用のプログラムおよびデバイスで、障碍を持つユーザーがコンピューターをより効果的に使用するよう助けます。</span><span class="sxs-lookup"><span data-stu-id="52c32-111">Accessibility aids are specialized programs and devices that help people with disabilities use computers more effectively.</span></span>|  
|<span data-ttu-id="52c32-112">AccessibleName</span><span class="sxs-lookup"><span data-stu-id="52c32-112">AccessibleName</span></span>|<span data-ttu-id="52c32-113">ユーザー補助機能に報告される名前。</span><span class="sxs-lookup"><span data-stu-id="52c32-113">The name that will be reported to the accessibility aids.</span></span>|  
|<span data-ttu-id="52c32-114">AccessibleRole</span><span class="sxs-lookup"><span data-stu-id="52c32-114">AccessibleRole</span></span>|<span data-ttu-id="52c32-115">ユーザーインターフェイスでの要素の使用方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="52c32-115">Describes the use of the element in the user interface.</span></span>|  
|<span data-ttu-id="52c32-116">TabIndex</span><span class="sxs-lookup"><span data-stu-id="52c32-116">TabIndex</span></span>|<span data-ttu-id="52c32-117">フォームを使用して、実用的なナビゲーションパスを作成します。</span><span class="sxs-lookup"><span data-stu-id="52c32-117">Creates a sensible navigational path through the form.</span></span> <span data-ttu-id="52c32-118">テキストボックスなどの固有のラベルを持たないコントロールは、関連付けられているラベルをタブオーダーの直前に配置することが重要です。</span><span class="sxs-lookup"><span data-stu-id="52c32-118">It is important for controls without intrinsic labels, such as text boxes, to have their associated label immediately precede them in the tab order.</span></span>|  
|<span data-ttu-id="52c32-119">Text</span><span class="sxs-lookup"><span data-stu-id="52c32-119">Text</span></span>|<span data-ttu-id="52c32-120">アクセスキーを作成するには、"&" 文字を使用します。</span><span class="sxs-lookup"><span data-stu-id="52c32-120">Use the "&" character to create access keys.</span></span> <span data-ttu-id="52c32-121">アクセスキーの使用は、ドキュメント化されたキーボードアクセスを機能に提供することの一部です。</span><span class="sxs-lookup"><span data-stu-id="52c32-121">Using access keys is part of providing documented keyboard access to features.</span></span>|  
|<span data-ttu-id="52c32-122">フォント サイズ</span><span class="sxs-lookup"><span data-stu-id="52c32-122">Font Size</span></span>|<span data-ttu-id="52c32-123">フォントサイズを調整できない場合は、10ポイント以上に設定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="52c32-123">If the font size is not adjustable, then it should be set to 10 points or larger.</span></span> <span data-ttu-id="52c32-124">フォームのフォントサイズを設定すると、その後フォームに追加されたすべてのコントロールのサイズが同じになります。</span><span class="sxs-lookup"><span data-stu-id="52c32-124">Once the form's font size is set, all the controls added to the form thereafter will have the same size.</span></span>|  
|<span data-ttu-id="52c32-125">前景色</span><span class="sxs-lookup"><span data-stu-id="52c32-125">Forecolor</span></span>|<span data-ttu-id="52c32-126">このプロパティが既定値に設定されている場合は、ユーザーの色の設定がフォームで使用されます。</span><span class="sxs-lookup"><span data-stu-id="52c32-126">If this property is set to the default, then the user's color preferences will be used on the form.</span></span>|  
|<span data-ttu-id="52c32-127">背景色</span><span class="sxs-lookup"><span data-stu-id="52c32-127">Backcolor</span></span>|<span data-ttu-id="52c32-128">このプロパティが既定値に設定されている場合は、ユーザーの色の設定がフォームで使用されます。</span><span class="sxs-lookup"><span data-stu-id="52c32-128">If this property is set to the default, then the user's color preferences will be used on the form.</span></span>|  
|<span data-ttu-id="52c32-129">BackgroundImage</span><span class="sxs-lookup"><span data-stu-id="52c32-129">BackgroundImage</span></span>|<span data-ttu-id="52c32-130">テキストを読みやすくするには、このプロパティを空白のままにします。</span><span class="sxs-lookup"><span data-stu-id="52c32-130">Leave this property blank to make text more readable.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="52c32-131">関連項目</span><span class="sxs-lookup"><span data-stu-id="52c32-131">See also</span></span>

- [<span data-ttu-id="52c32-132">チュートリアル: ユーザー補助対応の Windows ベースのアプリケーションの作成</span><span class="sxs-lookup"><span data-stu-id="52c32-132">Walkthrough: Creating an Accessible Windows-based Application</span></span>](walkthrough-creating-an-accessible-windows-based-application.md)
