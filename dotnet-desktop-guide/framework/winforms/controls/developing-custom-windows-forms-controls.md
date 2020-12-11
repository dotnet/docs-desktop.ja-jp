---
title: カスタムコントロールの開発
description: Windows フォームコントロールについて説明します。 具体的には、既存のコントロールの結合、既存のコントロールの拡張、独自のカスタムコントロールの作成について学習します。
ms.date: 03/30/2017
helpviewer_keywords:
- custom controls [Windows Forms], developing using code
- Control class [Windows Forms], Windows Forms
ms.assetid: 236cebc0-bd71-4f18-9fd6-5d0e592375df
ms.openlocfilehash: bf09f13be0c775a12fdc88c5b0934bafab9af740
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/09/2020
ms.locfileid: "96974173"
---
# <a name="developing-custom-windows-forms-controls-with-the-net-framework"></a><span data-ttu-id="c90c0-104">.NET Framework を使用したカスタム Windows フォーム コントロールの開発</span><span class="sxs-lookup"><span data-stu-id="c90c0-104">Developing Custom Windows Forms Controls with the .NET Framework</span></span>

<span data-ttu-id="c90c0-105">Windows フォーム コントロールは、ユーザー インターフェイスの機能をカプセル化して、クライアント側の Windows ベースのアプリケーションで使用される再利用可能なコンポーネントです。</span><span class="sxs-lookup"><span data-stu-id="c90c0-105">Windows Forms controls are reusable components that encapsulate user interface functionality and are used in client-side Windows-based applications.</span></span> <span data-ttu-id="c90c0-106">Windows フォームは、すぐに使用できる多数のコントロールを提供するだけでなく、独自のコントロールを開発するためのインフラストラクチャも提供します。</span><span class="sxs-lookup"><span data-stu-id="c90c0-106">Not only does Windows Forms provide many ready-to-use controls, it also provides the infrastructure for developing your own controls.</span></span> <span data-ttu-id="c90c0-107">既存のコントロールの結合、既存のコントロールの拡張、または独自のカスタム コントロールの記述ができます。</span><span class="sxs-lookup"><span data-stu-id="c90c0-107">You can combine existing controls, extend existing controls, or author your own custom controls.</span></span> <span data-ttu-id="c90c0-108">このセクションでは、Windows フォーム コントロールの開発に役立つ背景情報とサンプルを提供します。</span><span class="sxs-lookup"><span data-stu-id="c90c0-108">This section provides background information and samples to help you develop Windows Forms controls.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="c90c0-109">このセクションの内容</span><span class="sxs-lookup"><span data-stu-id="c90c0-109">In This Section</span></span>  

 [<span data-ttu-id="c90c0-110">Windows フォームでのコントロールの使用方法の概要</span><span class="sxs-lookup"><span data-stu-id="c90c0-110">Overview of Using Controls in Windows Forms</span></span>](overview-of-using-controls-in-windows-forms.md)  
 <span data-ttu-id="c90c0-111">Windows フォーム アプリケーションでのコントロールの使用の重要な要素を示しています。</span><span class="sxs-lookup"><span data-stu-id="c90c0-111">Highlights the essential elements of using controls in Windows Forms applications.</span></span>  
  
 [<span data-ttu-id="c90c0-112">さまざまなカスタム コントロール</span><span class="sxs-lookup"><span data-stu-id="c90c0-112">Varieties of Custom Controls</span></span>](varieties-of-custom-controls.md)  
 <span data-ttu-id="c90c0-113"><xref:System.Windows.Forms?displayProperty=nameWithType> 名前空間を使用して作成できる様々な種類のカスタム コントロールについて説明します。</span><span class="sxs-lookup"><span data-stu-id="c90c0-113">Describes the different kinds of custom controls you can author with the <xref:System.Windows.Forms?displayProperty=nameWithType> namespace.</span></span>  
  
 [<span data-ttu-id="c90c0-114">Windows フォーム コントロール開発の基本概念</span><span class="sxs-lookup"><span data-stu-id="c90c0-114">Windows Forms Control Development Basics</span></span>](windows-forms-control-development-basics.md)  
 <span data-ttu-id="c90c0-115">Windows フォーム コントロールの開発の最初の手順について説明します。</span><span class="sxs-lookup"><span data-stu-id="c90c0-115">Discusses the first steps in developing a Windows Forms control.</span></span>  
  
 [<span data-ttu-id="c90c0-116">Windows フォーム コントロールのプロパティ</span><span class="sxs-lookup"><span data-stu-id="c90c0-116">Properties in Windows Forms Controls</span></span>](properties-in-windows-forms-controls.md)  
 <span data-ttu-id="c90c0-117">Windows フォーム コントロールのプロパティを追加する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="c90c0-117">Shows how to add to properties to Windows Forms controls.</span></span>  
  
 [<span data-ttu-id="c90c0-118">Windows フォーム コントロールのイベント</span><span class="sxs-lookup"><span data-stu-id="c90c0-118">Events in Windows Forms Controls</span></span>](events-in-windows-forms-controls.md)  
 <span data-ttu-id="c90c0-119">Windows フォーム コントロールのイベントを処理して定義する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="c90c0-119">Shows how to handle and define events in Windows Forms controls.</span></span>  
  
 [<span data-ttu-id="c90c0-120">Windows フォーム コントロールの属性</span><span class="sxs-lookup"><span data-stu-id="c90c0-120">Attributes in Windows Forms Controls</span></span>](attributes-in-windows-forms-controls.md)  
 <span data-ttu-id="c90c0-121">カスタム コントロールとコンポーネントのプロパティや他のメンバーに適用できる属性について説明します。</span><span class="sxs-lookup"><span data-stu-id="c90c0-121">Describes the attributes you can apply to properties or other members of your custom controls and components.</span></span>  
  
 [<span data-ttu-id="c90c0-122">コントロールのカスタム描画およびレンダリング</span><span class="sxs-lookup"><span data-stu-id="c90c0-122">Custom Control Painting and Rendering</span></span>](custom-control-painting-and-rendering.md)  
 <span data-ttu-id="c90c0-123">コントロールの外観をカスタマイズする方法を示します。</span><span class="sxs-lookup"><span data-stu-id="c90c0-123">Shows how to customize the appearance of your controls.</span></span>  
  
 [<span data-ttu-id="c90c0-124">Windows フォーム コントロールのレイアウト</span><span class="sxs-lookup"><span data-stu-id="c90c0-124">Layout in Windows Forms Controls</span></span>](layout-in-windows-forms-controls.md)  
 <span data-ttu-id="c90c0-125">コントロールとフォームの高度なレイアウトを作成する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="c90c0-125">Shows how to create sophisticated layouts for your controls and forms.</span></span>  
  
 [<span data-ttu-id="c90c0-126">Windows フォーム コントロールのマルチスレッド処理</span><span class="sxs-lookup"><span data-stu-id="c90c0-126">Multithreading in Windows Forms Controls</span></span>](multithreading-in-windows-forms-controls.md)  
 <span data-ttu-id="c90c0-127">マルチスレッド コントロールを実装する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="c90c0-127">Shows how to implement multithreaded controls.</span></span>  
  
## <a name="reference"></a><span data-ttu-id="c90c0-128">リファレンス</span><span class="sxs-lookup"><span data-stu-id="c90c0-128">Reference</span></span>  

 <xref:System.Windows.Forms.Control?displayProperty=nameWithType>  
 <span data-ttu-id="c90c0-129">このクラスについて説明し、すべてのメンバーへのリンクの一覧を示します。</span><span class="sxs-lookup"><span data-stu-id="c90c0-129">Describes this class and has links to all of its members.</span></span>  
  
 <xref:System.Windows.Forms.UserControl?displayProperty=nameWithType>  
 <span data-ttu-id="c90c0-130">このクラスについて説明し、すべてのメンバーへのリンクの一覧を示します。</span><span class="sxs-lookup"><span data-stu-id="c90c0-130">Describes this class and has links to all of its members.</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="c90c0-131">関連項目</span><span class="sxs-lookup"><span data-stu-id="c90c0-131">Related Sections</span></span>  

 <span data-ttu-id="c90c0-132">[コンポーネントのデザイン時属性](/previous-versions/visualstudio/visual-studio-2013/tk67c2t8(v=vs.120))</span><span class="sxs-lookup"><span data-stu-id="c90c0-132">[Design-Time Attributes for Components](/previous-versions/visualstudio/visual-studio-2013/tk67c2t8(v=vs.120))</span></span>  
 <span data-ttu-id="c90c0-133">ビジュアル デザイナーでデザインするときに正しく表示されるようにコンポーネントとコントロールに適用するメタデータ属性の一覧を表示します。</span><span class="sxs-lookup"><span data-stu-id="c90c0-133">Lists metadata attributes to apply to components and controls so that they are displayed correctly at design time in visual designers.</span></span>  
  
 <span data-ttu-id="c90c0-134">[デザイン時サポートの拡張](/previous-versions/visualstudio/visual-studio-2013/37899azc(v=vs.120))</span><span class="sxs-lookup"><span data-stu-id="c90c0-134">[Extending Design-Time Support](/previous-versions/visualstudio/visual-studio-2013/37899azc(v=vs.120))</span></span>  
 <span data-ttu-id="c90c0-135">デザイン時サポートを提供するエディターやデザイナーなどのクラスを実装する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="c90c0-135">Describes how to implement classes such as editors and designers that provide design-time support.</span></span>  
  
 <span data-ttu-id="c90c0-136">[方法 : コンポーネントおよびコントロールのライセンス処理を行う](/previous-versions/visualstudio/visual-studio-2013/fe8b1eh9(v=vs.120))</span><span class="sxs-lookup"><span data-stu-id="c90c0-136">[How to: License Components and Controls](/previous-versions/visualstudio/visual-studio-2013/fe8b1eh9(v=vs.120))</span></span>  
 <span data-ttu-id="c90c0-137">コントロールやコンポーネントのライセンスを実装する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="c90c0-137">Describes how to implement licensing in your control or component.</span></span>  
  
 <span data-ttu-id="c90c0-138">「[デザイン時の Windows フォーム コントロールの開発](developing-windows-forms-controls-at-design-time.md)」も参照してください。</span><span class="sxs-lookup"><span data-stu-id="c90c0-138">Also see [Developing Windows Forms Controls at Design Time](developing-windows-forms-controls-at-design-time.md).</span></span>
