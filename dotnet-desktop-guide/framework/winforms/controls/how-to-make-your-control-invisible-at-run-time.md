---
title: '方法: 実行時にコントロールを非表示にする'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- controls [Windows Forms], making invisible at run time
- invisible controls
- user controls [Windows Forms], invisible
- custom controls [Windows Forms], invisible
- run time [Windows Forms], making controls invisible
ms.assetid: 69eb2e72-32f5-4f79-a157-c2c5f60c1628
ms.openlocfilehash: e9af529541a40a951d6defea180dbbef04c8f3be
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/09/2020
ms.locfileid: "96974809"
---
# <a name="how-to-make-your-control-invisible-at-run-time"></a><span data-ttu-id="7ded2-102">方法: 実行時にコントロールを非表示にする</span><span class="sxs-lookup"><span data-stu-id="7ded2-102">How to: Make Your Control Invisible at Run Time</span></span>
<span data-ttu-id="7ded2-103">実行時に非表示になるユーザーコントロールを作成することが必要になる場合があります。</span><span class="sxs-lookup"><span data-stu-id="7ded2-103">There are times when you might want to create a user control that is invisible at run time.</span></span> <span data-ttu-id="7ded2-104">たとえば、アラームが鳴っている場合を除き、アラーム時計のコントロールは非表示になる場合があります。</span><span class="sxs-lookup"><span data-stu-id="7ded2-104">For example, a control that is an alarm clock might be invisible except when the alarm was sounding.</span></span> <span data-ttu-id="7ded2-105">これは、プロパティを設定することによって簡単に実現 <xref:System.Windows.Forms.Control.Visible%2A> できます。</span><span class="sxs-lookup"><span data-stu-id="7ded2-105">This is easily accomplished by setting the <xref:System.Windows.Forms.Control.Visible%2A> property.</span></span> <span data-ttu-id="7ded2-106"><xref:System.Windows.Forms.Control.Visible%2A>プロパティがの場合 `true` 、コントロールは通常どおり表示されます。</span><span class="sxs-lookup"><span data-stu-id="7ded2-106">If the <xref:System.Windows.Forms.Control.Visible%2A> property is `true`, your control will appear as normal.</span></span> <span data-ttu-id="7ded2-107">`false`の場合、コントロールは非表示になります。</span><span class="sxs-lookup"><span data-stu-id="7ded2-107">If `false`, your control will be hidden.</span></span> <span data-ttu-id="7ded2-108">コントロールのコードは非表示のままでも実行できますが、ユーザーインターフェイスを使用してコントロールと対話することはできません。</span><span class="sxs-lookup"><span data-stu-id="7ded2-108">Although code in your control may still run while invisible, you will not be able to interact with the control through the user interface.</span></span> <span data-ttu-id="7ded2-109">ユーザー入力に応答する非表示コントロール (マウスのクリックなど) を作成する場合は、透過的なコントロールを作成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="7ded2-109">If you want to create an invisible control that still responds to user input (for example, mouse clicks), you should create a transparent control.</span></span> <span data-ttu-id="7ded2-110">詳細については、「 [コントロールに透明な背景を付ける](how-to-give-your-control-a-transparent-background.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="7ded2-110">For more information, see [Giving Your Control a Transparent Background](how-to-give-your-control-a-transparent-background.md).</span></span>  
  
### <a name="to-make-your-control-invisible-at-run-time"></a><span data-ttu-id="7ded2-111">実行時にコントロールを非表示にするには</span><span class="sxs-lookup"><span data-stu-id="7ded2-111">To make your control invisible at run time</span></span>  
  
1. <span data-ttu-id="7ded2-112"><xref:System.Windows.Forms.Control.Visible%2A> プロパティを `false`に設定します。</span><span class="sxs-lookup"><span data-stu-id="7ded2-112">Set the <xref:System.Windows.Forms.Control.Visible%2A> property to `false`.</span></span>  
  
    ```vb  
    ' To set the Visible property from within your object's own code.  
    Me.Visible = False  
    ' To set the Visible property from another object.  
    myControl1.Visible = False  
    ```  
  
    ```csharp  
    // To set the Visible property from within your object's own code.  
    this.Visible = false;  
    // To set the Visible property from another object.  
    myControl1.Visible = false;  
    ```  
  
## <a name="see-also"></a><span data-ttu-id="7ded2-113">関連項目</span><span class="sxs-lookup"><span data-stu-id="7ded2-113">See also</span></span>

- <xref:System.Windows.Forms.Control.Visible%2A>
- [<span data-ttu-id="7ded2-114">.NET Framework を使用したカスタム Windows フォーム コントロールの開発</span><span class="sxs-lookup"><span data-stu-id="7ded2-114">Developing Custom Windows Forms Controls with the .NET Framework</span></span>](developing-custom-windows-forms-controls.md)
- [<span data-ttu-id="7ded2-115">方法: コントロールに透明な背景を指定する</span><span class="sxs-lookup"><span data-stu-id="7ded2-115">How to: Give Your Control a Transparent Background</span></span>](how-to-give-your-control-a-transparent-background.md)
