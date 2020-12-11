---
title: '方法: ToolStrip のテキストとイメージの外観を変更する'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- ToolStrip control [Windows Forms], appearance
- toolbars [Windows Forms], images
- examples [Windows Forms], toolbars
- toolbars [Windows Forms], appearance
- ToolStrip control [Windows Forms], images
- ToolStrip control [Windows Forms], text
- toolbars [Windows Forms], text
ms.assetid: d62dc9d1-2edd-4dfa-aed7-1335d6e13d86
ms.openlocfilehash: 7816e138e44554683c201895ece1f886ace8bfa6
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/09/2020
ms.locfileid: "96982567"
---
# <a name="how-to-change-the-appearance-of-toolstrip-text-and-images-in-windows-forms"></a><span data-ttu-id="94bca-102">方法: Windows フォーム内の ToolStrip テキストとイメージの外観を変更する</span><span class="sxs-lookup"><span data-stu-id="94bca-102">How to: Change the Appearance of ToolStrip Text and Images in Windows Forms</span></span>
<span data-ttu-id="94bca-103">テキストとイメージをに表示するかどうか、および <xref:System.Windows.Forms.ToolStripItem> それらを互いにどのように相対的に揃えるかを制御でき <xref:System.Windows.Forms.ToolStrip> ます。</span><span class="sxs-lookup"><span data-stu-id="94bca-103">You can control whether text and images are displayed on a <xref:System.Windows.Forms.ToolStripItem> and how they are aligned relative to each other and the <xref:System.Windows.Forms.ToolStrip>.</span></span>  
  
### <a name="to-define-what-is-displayed-on-a-toolstripitem"></a><span data-ttu-id="94bca-104">ToolStripItem に表示される内容を定義するには</span><span class="sxs-lookup"><span data-stu-id="94bca-104">To define what is displayed on a ToolStripItem</span></span>  
  
- <span data-ttu-id="94bca-105">プロパティを <xref:System.Windows.Forms.ToolStripItem.DisplayStyle%2A> 目的の値に設定します。</span><span class="sxs-lookup"><span data-stu-id="94bca-105">Set the <xref:System.Windows.Forms.ToolStripItem.DisplayStyle%2A> property to the desired value.</span></span> <span data-ttu-id="94bca-106">その可能性は `Image` 、、、 `ImageAndText` `None` 、および `Text` です。</span><span class="sxs-lookup"><span data-stu-id="94bca-106">The possibilities are `Image`, `ImageAndText`, `None`, and `Text`.</span></span> <span data-ttu-id="94bca-107">既定値は、`ImageAndText` です。</span><span class="sxs-lookup"><span data-stu-id="94bca-107">The default is `ImageAndText`.</span></span>  
  
    ```vb  
    ToolStripButton2.DisplayStyle = _  
        System.Windows.Forms.ToolStripItemDisplayStyle.Image  
    ```  
  
    ```csharp  
    toolStripButton2.DisplayStyle = System.Windows.Forms.ToolStripItemDisplayStyle.Image;  
    ```  
  
### <a name="to-align-text-on-a-toolstripitem"></a><span data-ttu-id="94bca-108">ToolStripItem のテキストを揃えるには</span><span class="sxs-lookup"><span data-stu-id="94bca-108">To align text on a ToolStripItem</span></span>  
  
- <span data-ttu-id="94bca-109">プロパティを <xref:System.Windows.Forms.ToolStripItem.TextAlign%2A> 目的の値に設定します。</span><span class="sxs-lookup"><span data-stu-id="94bca-109">Set the <xref:System.Windows.Forms.ToolStripItem.TextAlign%2A> property to the desired value.</span></span> <span data-ttu-id="94bca-110">Left、center、right を使用すると、上下左右の任意の組み合わせを使用できます。</span><span class="sxs-lookup"><span data-stu-id="94bca-110">The possibilities are any combination of top, middle, and bottom with left, center, and right.</span></span> <span data-ttu-id="94bca-111">既定値は、`MiddleCenter` です。</span><span class="sxs-lookup"><span data-stu-id="94bca-111">The default is `MiddleCenter`.</span></span>  
  
    ```vb  
    ToolStripSplitButton1.TextAlign = _  
        System.Drawing.ContentAlignment.MiddleRight  
    ```  
  
    ```csharp  
    toolStripSplitButton1.TextAlign = System.Drawing.ContentAlignment.MiddleRight;  
    ```  
  
### <a name="to-align-an-image-on-a-toolstripitem"></a><span data-ttu-id="94bca-112">ToolStripItem 上のイメージを整列させるには</span><span class="sxs-lookup"><span data-stu-id="94bca-112">To align an image on a ToolStripItem</span></span>  
  
- <span data-ttu-id="94bca-113">プロパティを <xref:System.Windows.Forms.ToolStripItem.ImageAlign%2A> 目的の値に設定します。</span><span class="sxs-lookup"><span data-stu-id="94bca-113">Set the <xref:System.Windows.Forms.ToolStripItem.ImageAlign%2A> property to the desired value.</span></span> <span data-ttu-id="94bca-114">Left、center、right を使用すると、上下左右の任意の組み合わせを使用できます。</span><span class="sxs-lookup"><span data-stu-id="94bca-114">The possibilities are any combination of top, middle, and bottom with left, center, and right.</span></span> <span data-ttu-id="94bca-115">既定値は、`MiddleLeft` です。</span><span class="sxs-lookup"><span data-stu-id="94bca-115">The default is `MiddleLeft`.</span></span>  
  
    ```vb  
    ToolStripSplitButton1.ImageAlign = _  
        System.Drawing.ContentAlignment.MiddleRight  
    ```  
  
    ```csharp  
    toolStripSplitButton1.ImageAlign = System.Drawing.ContentAlignment.MiddleRight;  
    ```  
  
### <a name="to-define-how-toolstripitem-text-and-images-are-displayed-relative-to-each-other"></a><span data-ttu-id="94bca-116">ToolStripItem テキストと画像を相互に相対的に表示する方法を定義するには</span><span class="sxs-lookup"><span data-stu-id="94bca-116">To define how ToolStripItem text and images are displayed relative to each other</span></span>  
  
- <span data-ttu-id="94bca-117">プロパティを <xref:System.Windows.Forms.ToolStripItem.TextImageRelation%2A> 目的の値に設定します。</span><span class="sxs-lookup"><span data-stu-id="94bca-117">Set the <xref:System.Windows.Forms.ToolStripItem.TextImageRelation%2A> property to the desired value.</span></span> <span data-ttu-id="94bca-118">設定できる値は、`ImageAboveText`、`ImageBeforeText`、`Overlay`、`TextAboveImage`、および `TextBeforeImage` です。</span><span class="sxs-lookup"><span data-stu-id="94bca-118">The possibilities are `ImageAboveText`, `ImageBeforeText`, `Overlay`, `TextAboveImage`, and `TextBeforeImage`.</span></span> <span data-ttu-id="94bca-119">既定値は、`ImageBeforeText` です。</span><span class="sxs-lookup"><span data-stu-id="94bca-119">The default is `ImageBeforeText`.</span></span>  
  
    ```vb  
    ToolStripButton1.TextImageRelation = _  
        System.Windows.Forms.TextImageRelation.ImageAboveText  
    ```  
  
    ```csharp  
    toolStripButton1.TextImageRelation = System.Windows.Forms.TextImageRelation.ImageAboveText;  
    ```  
  
## <a name="see-also"></a><span data-ttu-id="94bca-120">関連項目</span><span class="sxs-lookup"><span data-stu-id="94bca-120">See also</span></span>

- <xref:System.Windows.Forms.ToolStrip>
- [<span data-ttu-id="94bca-121">ToolStrip コントロールの概要</span><span class="sxs-lookup"><span data-stu-id="94bca-121">ToolStrip Control Overview</span></span>](toolstrip-control-overview-windows-forms.md)
- [<span data-ttu-id="94bca-122">ToolStrip コントロールのアーキテクチャ</span><span class="sxs-lookup"><span data-stu-id="94bca-122">ToolStrip Control Architecture</span></span>](toolstrip-control-architecture.md)
- [<span data-ttu-id="94bca-123">ToolStrip テクノロジの概要</span><span class="sxs-lookup"><span data-stu-id="94bca-123">ToolStrip Technology Summary</span></span>](toolstrip-technology-summary.md)
