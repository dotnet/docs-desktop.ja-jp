---
title: '方法 : データ入力用のサイズ変更可能な Windows フォームを作成する'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- TableLayoutPanel control [Windows Forms]
- layout [Windows Forms], resizing
- forms [Windows Forms], creating resizable
- Windows Forms, resizable
ms.assetid: babdf198-404c-485d-a914-ed370c6ecd99
ms.openlocfilehash: c0cf79941a55f7412694b6ef9e8797e48aa069a1
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/09/2020
ms.locfileid: "96982184"
---
# <a name="how-to-create-a-resizable-windows-form-for-data-entry"></a><span data-ttu-id="7887c-102">方法 : データ入力用のサイズ変更可能な Windows フォームを作成する</span><span class="sxs-lookup"><span data-stu-id="7887c-102">How to: Create a Resizable Windows Form for Data Entry</span></span>

<span data-ttu-id="7887c-103">レイアウトが優れていると、その親フォームの寸法の変更に柔軟に対応できます。</span><span class="sxs-lookup"><span data-stu-id="7887c-103">A good layout responds well to changes in the dimensions of its parent form.</span></span> <span data-ttu-id="7887c-104"><xref:System.Windows.Forms.TableLayoutPanel> コントロールを使用すると、フォームの寸法の変更に応じて一貫した方法でコントロールの位置とサイズが変更されるように、フォームのレイアウトを調整できます。</span><span class="sxs-lookup"><span data-stu-id="7887c-104">You can use the <xref:System.Windows.Forms.TableLayoutPanel> control to arrange the layout of your form to resize and position your controls in a consistent way as the form's dimensions change.</span></span> <span data-ttu-id="7887c-105"><xref:System.Windows.Forms.TableLayoutPanel> コントロールは、コントロールの内容の変更によってレイアウトの変更が生じる場合にも便利です。</span><span class="sxs-lookup"><span data-stu-id="7887c-105">The <xref:System.Windows.Forms.TableLayoutPanel> control is also useful when changes in the contents of your controls cause changes in the layout.</span></span> <span data-ttu-id="7887c-106">この手順で説明するプロセスは、Visual Studio 環境内で実行できます。</span><span class="sxs-lookup"><span data-stu-id="7887c-106">The process covered in this procedure can be done within the Visual Studio environment.</span></span>  <span data-ttu-id="7887c-107">「[チュートリアル: データ入力用のサイズ変更可能な Windows フォームの作成](/previous-versions/visualstudio/visual-studio-2010/991eahec(v=vs.100))」も参照してください。</span><span class="sxs-lookup"><span data-stu-id="7887c-107">Also see [Walkthrough: Creating a Resizable Windows Form for Data Entry](/previous-versions/visualstudio/visual-studio-2010/991eahec(v=vs.100)).</span></span>  
  
## <a name="example"></a><span data-ttu-id="7887c-108">例</span><span class="sxs-lookup"><span data-stu-id="7887c-108">Example</span></span>  

 <span data-ttu-id="7887c-109">ユーザーによるフォームのサイズ変更に適切に対応するレイアウトを <xref:System.Windows.Forms.TableLayoutPanel> コントロールを使用して作成する方法を次の例に示します。</span><span class="sxs-lookup"><span data-stu-id="7887c-109">The following example demonstrates how to use a <xref:System.Windows.Forms.TableLayoutPanel> control to build a layout that responds well when the user resizes the form.</span></span> <span data-ttu-id="7887c-110">また、ローカリゼーションに適切に対応するレイアウトも示します。</span><span class="sxs-lookup"><span data-stu-id="7887c-110">It also demonstrates a layout that responds well to localization.</span></span>  
  
 [!code-cpp[System.Windows.Forms.TableLayoutPanel.DataEntryForm#1](~/samples/snippets/cpp/VS_Snippets_Winforms/System.Windows.Forms.TableLayoutPanel.DataEntryForm/cpp/basicdataentryform.cpp#1)]
 [!code-csharp[System.Windows.Forms.TableLayoutPanel.DataEntryForm#1](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.TableLayoutPanel.DataEntryForm/CS/basicdataentryform.cs#1)]
 [!code-vb[System.Windows.Forms.TableLayoutPanel.DataEntryForm#1](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.TableLayoutPanel.DataEntryForm/VB/basicdataentryform.vb#1)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="7887c-111">コードのコンパイル</span><span class="sxs-lookup"><span data-stu-id="7887c-111">Compiling the Code</span></span>  

 <span data-ttu-id="7887c-112">この例で必要な要素は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="7887c-112">This example requires:</span></span>  
  
- <span data-ttu-id="7887c-113">System、System.Data、System.Drawing、および System.Windows.Forms の各アセンブリへの参照。</span><span class="sxs-lookup"><span data-stu-id="7887c-113">References to the System, System.Data, System.Drawing and System.Windows.Forms assemblies.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7887c-114">関連項目</span><span class="sxs-lookup"><span data-stu-id="7887c-114">See also</span></span>

- <xref:System.Windows.Forms.FlowLayoutPanel>
- <xref:System.Windows.Forms.TableLayoutPanel>
- [<span data-ttu-id="7887c-115">方法 : TableLayoutPanel コントロールで子コントロールを固定およびドッキングする</span><span class="sxs-lookup"><span data-stu-id="7887c-115">How to: Anchor and Dock Child Controls in a TableLayoutPanel Control</span></span>](how-to-anchor-and-dock-child-controls-in-a-tablelayoutpanel-control.md)
- [<span data-ttu-id="7887c-116">方法 : ローカリゼーションに対応した Windows フォーム レイアウトをデザインする</span><span class="sxs-lookup"><span data-stu-id="7887c-116">How to: Design a Windows Forms Layout that Responds Well to Localization</span></span>](how-to-design-a-windows-forms-layout-that-responds-well-to-localization.md)
