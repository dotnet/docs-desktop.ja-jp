---
title: コントロールのプロパティ
ms.date: 03/30/2017
helpviewer_keywords:
- custom controls [Windows Forms], properties overview (using code)
- controls [Windows Forms], properties
- properties [Windows Forms]
ms.assetid: 2785279b-fb57-4937-8f6b-2050e475db6f
ms.openlocfilehash: 3f9873ff032497a9cda6de199ed9db5ee9522d81
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/09/2020
ms.locfileid: "96974388"
---
# <a name="properties-in-windows-forms-controls"></a><span data-ttu-id="5a7c3-102">Windows フォーム コントロールのプロパティ</span><span class="sxs-lookup"><span data-stu-id="5a7c3-102">Properties in Windows Forms Controls</span></span>

<span data-ttu-id="5a7c3-103">Windows フォームコントロールは、基本クラスを形成する多くのプロパティを継承し <xref:System.Windows.Forms.Control?displayProperty=nameWithType> ます。</span><span class="sxs-lookup"><span data-stu-id="5a7c3-103">A Windows Forms control inherits many properties form the base class <xref:System.Windows.Forms.Control?displayProperty=nameWithType>.</span></span> <span data-ttu-id="5a7c3-104">これには、、、、、、、、、、、、などのプロパティが含ま <xref:System.Windows.Forms.Control.Font%2A> <xref:System.Windows.Forms.Control.ForeColor%2A> <xref:System.Windows.Forms.Control.BackColor%2A> <xref:System.Windows.Forms.Control.Bounds%2A> <xref:System.Windows.Forms.Control.ClientRectangle%2A> <xref:System.Windows.Forms.Control.DisplayRectangle%2A> <xref:System.Windows.Forms.Control.Enabled%2A> <xref:System.Windows.Forms.Control.Focused%2A> <xref:System.Windows.Forms.Control.Height%2A> <xref:System.Windows.Forms.Control.Width%2A> <xref:System.Windows.Forms.Control.Visible%2A> <xref:System.Windows.Forms.Control.AutoSize%2A> れます。</span><span class="sxs-lookup"><span data-stu-id="5a7c3-104">These include properties such as <xref:System.Windows.Forms.Control.Font%2A>, <xref:System.Windows.Forms.Control.ForeColor%2A>, <xref:System.Windows.Forms.Control.BackColor%2A>, <xref:System.Windows.Forms.Control.Bounds%2A>, <xref:System.Windows.Forms.Control.ClientRectangle%2A>, <xref:System.Windows.Forms.Control.DisplayRectangle%2A>, <xref:System.Windows.Forms.Control.Enabled%2A>, <xref:System.Windows.Forms.Control.Focused%2A>, <xref:System.Windows.Forms.Control.Height%2A>, <xref:System.Windows.Forms.Control.Width%2A>, <xref:System.Windows.Forms.Control.Visible%2A>, <xref:System.Windows.Forms.Control.AutoSize%2A>, and many others.</span></span> <span data-ttu-id="5a7c3-105">継承されたプロパティの詳細については、「」を参照してください <xref:System.Windows.Forms.Control?displayProperty=nameWithType> 。</span><span class="sxs-lookup"><span data-stu-id="5a7c3-105">For details about inherited properties, see <xref:System.Windows.Forms.Control?displayProperty=nameWithType>.</span></span>  
  
 <span data-ttu-id="5a7c3-106">コントロールで継承されたプロパティをオーバーライドしたり、新しいプロパティを定義したりできます。</span><span class="sxs-lookup"><span data-stu-id="5a7c3-106">You can override inherited properties in your control as well as define new properties.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="5a7c3-107">このセクションの内容</span><span class="sxs-lookup"><span data-stu-id="5a7c3-107">In This Section</span></span>  

 [<span data-ttu-id="5a7c3-108">プロパティの定義</span><span class="sxs-lookup"><span data-stu-id="5a7c3-108">Defining a Property</span></span>](defining-a-property-in-windows-forms-controls.md)  
 <span data-ttu-id="5a7c3-109">カスタム コントロールまたはカスタム コンポーネントのプロパティを実装する方法と、そのプロパティをデザイン環境に統合する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="5a7c3-109">Shows how to implement a property for a custom control or component and shows how to integrate the property into the design environment.</span></span>  
  
 [<span data-ttu-id="5a7c3-110">ShouldSerialize メソッドと Reset メソッドによる既定値の定義</span><span class="sxs-lookup"><span data-stu-id="5a7c3-110">Defining Default Values with the ShouldSerialize and Reset Methods</span></span>](defining-default-values-with-the-shouldserialize-and-reset-methods.md)  
 <span data-ttu-id="5a7c3-111">カスタム コントロールまたはカスタム コンポーネントの既定のプロパティ値を定義する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="5a7c3-111">Shows how to define default property values for a custom control or component.</span></span>  
  
 [<span data-ttu-id="5a7c3-112">プロパティ変更イベント</span><span class="sxs-lookup"><span data-stu-id="5a7c3-112">Property-Changed Events</span></span>](property-changed-events.md)  
 <span data-ttu-id="5a7c3-113">プロパティ値が変更されたときに、プロパティ変更通知を有効にする方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="5a7c3-113">Describes how to enable property-change notifications when a property value changes.</span></span>  
  
 [<span data-ttu-id="5a7c3-114">方法: 内在コントロールのプロパティを公開する</span><span class="sxs-lookup"><span data-stu-id="5a7c3-114">How to: Expose Properties of Constituent Controls</span></span>](how-to-expose-properties-of-constituent-controls.md)  
 <span data-ttu-id="5a7c3-115">カスタム複合コントロール内の内在コントロールのプロパティを公開する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="5a7c3-115">Shows how to expose properties of constituent controls in a custom composite control.</span></span>  
  
 [<span data-ttu-id="5a7c3-116">カスタム コントロールへのメソッドの実装</span><span class="sxs-lookup"><span data-stu-id="5a7c3-116">Method Implementation in Custom Controls</span></span>](method-implementation-in-custom-controls.md)  
 <span data-ttu-id="5a7c3-117">カスタム コントロールおよびカスタム コンポーネントにメソッドを実装する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="5a7c3-117">Describes how to implement methods in custom controls and components.</span></span>  
  
## <a name="reference"></a><span data-ttu-id="5a7c3-118">リファレンス</span><span class="sxs-lookup"><span data-stu-id="5a7c3-118">Reference</span></span>  

 <xref:System.Windows.Forms.UserControl>  
 <span data-ttu-id="5a7c3-119">複合コントロールを実装するための基本クラスについて説明します。</span><span class="sxs-lookup"><span data-stu-id="5a7c3-119">Documents the base class for implementing composite controls.</span></span>  
  
 <xref:System.ComponentModel.TypeConverterAttribute>  
 <span data-ttu-id="5a7c3-120">カスタムプロパティ型に使用するを指定する属性を文書にし <xref:System.ComponentModel.TypeConverter> ます。</span><span class="sxs-lookup"><span data-stu-id="5a7c3-120">Documents the attribute that specifies the <xref:System.ComponentModel.TypeConverter> to use for a custom property type.</span></span>  
  
 <xref:System.ComponentModel.EditorAttribute>  
 <span data-ttu-id="5a7c3-121">カスタムプロパティに使用するを指定する属性を文書にし <xref:System.Drawing.Design.UITypeEditor> ます。</span><span class="sxs-lookup"><span data-stu-id="5a7c3-121">Documents the attribute that specifies the <xref:System.Drawing.Design.UITypeEditor> to use for a custom property.</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="5a7c3-122">関連項目</span><span class="sxs-lookup"><span data-stu-id="5a7c3-122">Related Sections</span></span>  

 [<span data-ttu-id="5a7c3-123">Windows フォーム コントロールの属性</span><span class="sxs-lookup"><span data-stu-id="5a7c3-123">Attributes in Windows Forms Controls</span></span>](attributes-in-windows-forms-controls.md)  
 <span data-ttu-id="5a7c3-124">カスタム コントロールとコンポーネントのプロパティや他のメンバーに適用できる属性について説明します。</span><span class="sxs-lookup"><span data-stu-id="5a7c3-124">Describes the attributes you can apply to properties or other members of your custom controls and components.</span></span>  
  
 <span data-ttu-id="5a7c3-125">[コンポーネントのデザイン時属性](/previous-versions/visualstudio/visual-studio-2013/tk67c2t8(v=vs.120))</span><span class="sxs-lookup"><span data-stu-id="5a7c3-125">[Design-Time Attributes for Components](/previous-versions/visualstudio/visual-studio-2013/tk67c2t8(v=vs.120))</span></span>  
 <span data-ttu-id="5a7c3-126">ビジュアル デザイナーでデザインするときに正しく表示されるようにコンポーネントとコントロールに適用するメタデータ属性の一覧を表示します。</span><span class="sxs-lookup"><span data-stu-id="5a7c3-126">Lists metadata attributes to apply to components and controls so that they are displayed correctly at design time in visual designers.</span></span>  
  
 <span data-ttu-id="5a7c3-127">[デザイン時サポートの拡張](/previous-versions/visualstudio/visual-studio-2013/37899azc(v=vs.120))</span><span class="sxs-lookup"><span data-stu-id="5a7c3-127">[Extending Design-Time Support](/previous-versions/visualstudio/visual-studio-2013/37899azc(v=vs.120))</span></span>  
 <span data-ttu-id="5a7c3-128">デザイン時サポートを提供するエディターやデザイナーなどのクラスを実装する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="5a7c3-128">Describes how to implement classes such as editors and designers that provide design-time support.</span></span>
