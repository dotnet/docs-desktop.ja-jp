---
title: パネルの背景を設定する
description: デザイナーを使用して、Windows フォームパネルの背景色と背景イメージを設定する方法について説明します。
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- background colors [Windows Forms], Windows Forms Panel controls
- background images [Windows Forms], Windows Forms Panel controls
- Panel control [Windows Forms], background
- colors [Windows Forms], Windows Forms Panel controls
ms.assetid: 096cbd8d-45cc-47b8-b1ef-a27f60ea8be0
ms.openlocfilehash: 109ff6184de9c79d1576207bbeb29ad939670b6f
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/09/2020
ms.locfileid: "96980260"
---
# <a name="how-to-set-the-background-of-a-windows-forms-panel"></a><span data-ttu-id="cfced-103">方法 : Windows フォーム パネルの背景を設定する</span><span class="sxs-lookup"><span data-stu-id="cfced-103">How to: Set the Background of a Windows Forms Panel</span></span>
<span data-ttu-id="cfced-104">Windows フォームコントロールには、 <xref:System.Windows.Forms.Panel> 背景色と背景画像の両方を表示できます。</span><span class="sxs-lookup"><span data-stu-id="cfced-104">A Windows Forms <xref:System.Windows.Forms.Panel> control can display both a background color and a background image.</span></span> <span data-ttu-id="cfced-105">プロパティは、 <xref:System.Windows.Forms.Control.BackColor%2A> ラベルやラジオボタンなど、含まれるコントロールの背景色を設定します。</span><span class="sxs-lookup"><span data-stu-id="cfced-105">The <xref:System.Windows.Forms.Control.BackColor%2A> property sets the background color for the contained controls, such as labels and radio buttons.</span></span> <span data-ttu-id="cfced-106"><xref:System.Windows.Forms.Control.BackgroundImage%2A>プロパティが設定されていない場合、 <xref:System.Windows.Forms.Control.BackColor%2A> パネル全体が選択されます。</span><span class="sxs-lookup"><span data-stu-id="cfced-106">If the <xref:System.Windows.Forms.Control.BackgroundImage%2A> property is not set, the <xref:System.Windows.Forms.Control.BackColor%2A> selection will fill the entire panel.</span></span> <span data-ttu-id="cfced-107">プロパティが設定されている場合、イメージは、 <xref:System.Windows.Forms.Control.BackgroundImage%2A> 含まれているコントロールの背後に表示されます。</span><span class="sxs-lookup"><span data-stu-id="cfced-107">If the <xref:System.Windows.Forms.Control.BackgroundImage%2A> property is set, the image will be displayed behind the contained controls.</span></span>  
  
### <a name="to-set-the-background-programmatically"></a><span data-ttu-id="cfced-108">バックグラウンドをプログラムによって設定するには</span><span class="sxs-lookup"><span data-stu-id="cfced-108">To set the background programmatically</span></span>  
  
1. <span data-ttu-id="cfced-109">パネルの <xref:System.Windows.Forms.Control.BackColor%2A> プロパティを型の値に設定 <xref:System.Drawing.Color?displayProperty=nameWithType> します。</span><span class="sxs-lookup"><span data-stu-id="cfced-109">Set the panel's <xref:System.Windows.Forms.Control.BackColor%2A> property to a value of type <xref:System.Drawing.Color?displayProperty=nameWithType>.</span></span>  
  
    ```vb  
    Panel1.BackColor = Color.AliceBlue  
    ```  
  
    ```csharp  
    panel1.BackColor = Color.AliceBlue;  
    ```  
  
    ```cpp  
    panel1->BackColor = Color::AliceBlue;  
    ```  
  
2. <span data-ttu-id="cfced-110"><xref:System.Windows.Forms.Control.BackgroundImage%2A>クラスのメソッドを使用して、パネルのプロパティを設定し <xref:System.Drawing.Image.FromFile%2A> <xref:System.Drawing.Image?displayProperty=nameWithType> ます。</span><span class="sxs-lookup"><span data-stu-id="cfced-110">Set the panel's <xref:System.Windows.Forms.Control.BackgroundImage%2A> property using the <xref:System.Drawing.Image.FromFile%2A> method of the <xref:System.Drawing.Image?displayProperty=nameWithType> class.</span></span>  
  
    ```vb  
    ' You should replace the bolded image
    ' in the sample below with an image of your own choosing.  
    Panel1.BackgroundImage = Image.FromFile _  
        (System.Environment.GetFolderPath _  
        (System.Environment.SpecialFolder.Personal) _  
        & "\Image.gif")  
    ```  
  
    ```csharp  
    // You should replace the bolded image
    // in the sample below with an image of your own choosing.  
    // Note the escape character used (@) when specifying the path.  
    panel1.BackgroundImage = Image.FromFile  
       (System.Environment.GetFolderPath  
       (System.Environment.SpecialFolder.Personal)  
       + @"\Image.gif");  
    ```  
  
    ```cpp  
    // You should replace the bolded image
    // in the sample below with an image of your own choosing.  
    panel1->BackgroundImage = Image::FromFile(String::Concat(  
       System::Environment::GetFolderPath  
       (System::Environment::SpecialFolder::Personal),  
       "\\Image.gif"));  
    ```  
  
## <a name="see-also"></a><span data-ttu-id="cfced-111">関連項目</span><span class="sxs-lookup"><span data-stu-id="cfced-111">See also</span></span>

- <xref:System.Windows.Forms.Control.BackColor%2A>
- <xref:System.Windows.Forms.Control.BackgroundImage%2A>
- [<span data-ttu-id="cfced-112">パネル コントロール</span><span class="sxs-lookup"><span data-stu-id="cfced-112">Panel Control</span></span>](panel-control-windows-forms.md)
- [<span data-ttu-id="cfced-113">Panel コントロールの概要</span><span class="sxs-lookup"><span data-stu-id="cfced-113">Panel Control Overview</span></span>](panel-control-overview-windows-forms.md)
