---
title: TableLayoutPanel コントロールにおける AutoSize 動作
ms.date: 03/30/2017
ms.topic: overview
helpviewer_keywords:
- AutoSize property [Windows Forms], tableLayoutPanel control
- controls [Windows Forms], sizing
- localizing forms
- layout [Windows Forms], AutoSize
- sizing [Windows Forms], automatic
- TableLayoutPanel control [Windows Forms], AutoSize behavior
- automatic sizing
- AutoSizeMode property
ms.assetid: 9233e0c3-2fa6-405e-8701-959479b1250e
ms.openlocfilehash: daeca48c4fcfaf83d6506ba07d60ec2dcfdcace7
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/09/2020
ms.locfileid: "96981095"
---
# <a name="autosize-behavior-in-the-tablelayoutpanel-control"></a><span data-ttu-id="f0aaf-102">TableLayoutPanel コントロールにおける AutoSize 動作</span><span class="sxs-lookup"><span data-stu-id="f0aaf-102">AutoSize Behavior in the TableLayoutPanel Control</span></span>
## <a name="distinct-autosize-behaviors"></a><span data-ttu-id="f0aaf-103">個別の AutoSize 動作</span><span class="sxs-lookup"><span data-stu-id="f0aaf-103">Distinct AutoSize Behaviors</span></span>  
 <span data-ttu-id="f0aaf-104">コントロールは、 <xref:System.Windows.Forms.TableLayoutPanel> 次の方法で自動サイズ変更の動作をサポートします。</span><span class="sxs-lookup"><span data-stu-id="f0aaf-104">The <xref:System.Windows.Forms.TableLayoutPanel> control supports automatic sizing behavior in the following ways:</span></span>  
  
- <span data-ttu-id="f0aaf-105">プロパティを使用し <xref:System.Windows.Forms.Control.AutoSize%2A> ます。</span><span class="sxs-lookup"><span data-stu-id="f0aaf-105">Through the <xref:System.Windows.Forms.Control.AutoSize%2A> property;</span></span>  
  
- <span data-ttu-id="f0aaf-106"><xref:System.Windows.Forms.TableLayoutStyle.SizeType%2A> <xref:System.Windows.Forms.TableLayoutPanel> コントロールの列と行のスタイルのプロパティを使用します。</span><span class="sxs-lookup"><span data-stu-id="f0aaf-106">Through the <xref:System.Windows.Forms.TableLayoutStyle.SizeType%2A> property on the <xref:System.Windows.Forms.TableLayoutPanel> control’s column and row styles.</span></span>  
  
### <a name="the-autosize-property-with-row-and-column-styles"></a><span data-ttu-id="f0aaf-107">行と列のスタイルを持つ AutoSize プロパティ</span><span class="sxs-lookup"><span data-stu-id="f0aaf-107">The AutoSize Property with Row and Column Styles</span></span>  
 <span data-ttu-id="f0aaf-108">次の表では、 <xref:System.Windows.Forms.Control.AutoSize%2A> プロパティと <xref:System.Windows.Forms.TableLayoutPanel> コントロールの列と行のスタイルの相互作用について説明します。</span><span class="sxs-lookup"><span data-stu-id="f0aaf-108">The following table describes the interaction between the <xref:System.Windows.Forms.Control.AutoSize%2A> property and the <xref:System.Windows.Forms.TableLayoutPanel> control’s column and row styles.</span></span>  
  
|<span data-ttu-id="f0aaf-109">AutoSize 設定</span><span class="sxs-lookup"><span data-stu-id="f0aaf-109">AutoSize setting</span></span>|<span data-ttu-id="f0aaf-110">スタイルの相互作用</span><span class="sxs-lookup"><span data-stu-id="f0aaf-110">Style interaction</span></span>|  
|----------------------|-----------------------|  
|`false`|<span data-ttu-id="f0aaf-111"><xref:System.Windows.Forms.TableLayoutPanel>コントロールは左から右に進み、列または行の領域または次の順序で割り当てられます。</span><span class="sxs-lookup"><span data-stu-id="f0aaf-111">The <xref:System.Windows.Forms.TableLayoutPanel> control proceeds from left to right, and allocates space for the column or row or in the following order.</span></span><br /><br /> <span data-ttu-id="f0aaf-112">1. <xref:System.Windows.Forms.TableLayoutStyle.SizeType%2A> プロパティがに設定され <xref:System.Windows.Forms.SizeType.Absolute> ている場合、またはで指定されたピクセル数 <xref:System.Windows.Forms.ColumnStyle.Width%2A> <xref:System.Windows.Forms.RowStyle.Height%2A> が割り当てられます。</span><span class="sxs-lookup"><span data-stu-id="f0aaf-112">1.  If the <xref:System.Windows.Forms.TableLayoutStyle.SizeType%2A> property is set to <xref:System.Windows.Forms.SizeType.Absolute>, the number of pixels specified by <xref:System.Windows.Forms.ColumnStyle.Width%2A> or <xref:System.Windows.Forms.RowStyle.Height%2A> is allocated.</span></span><br /><span data-ttu-id="f0aaf-113">2. <xref:System.Windows.Forms.TableLayoutStyle.SizeType%2A> プロパティがに設定され <xref:System.Windows.Forms.SizeType.AutoSize> ている場合、子コントロールのメソッドによって返されたピクセル数 <xref:System.Windows.Forms.Control.GetPreferredSize%2A> が割り当てられます。</span><span class="sxs-lookup"><span data-stu-id="f0aaf-113">2.  If the <xref:System.Windows.Forms.TableLayoutStyle.SizeType%2A> property is set to <xref:System.Windows.Forms.SizeType.AutoSize>, the number of pixels returned by the child control’s <xref:System.Windows.Forms.Control.GetPreferredSize%2A> method is allocated.</span></span><br /><span data-ttu-id="f0aaf-114">3. すべての <xref:System.Windows.Forms.SizeType.Absolute> および <xref:System.Windows.Forms.SizeType.AutoSize> 列または行の領域が割り当てられた後、がに設定されている列または行を使用して、 <xref:System.Windows.Forms.TableLayoutStyle.SizeType%2A> <xref:System.Windows.Forms.SizeType.Percent> 残りの空き領域を均等に割り当てます。</span><span class="sxs-lookup"><span data-stu-id="f0aaf-114">3.  After space for all <xref:System.Windows.Forms.SizeType.Absolute> and <xref:System.Windows.Forms.SizeType.AutoSize> columns or rows is allocated, any columns or rows with <xref:System.Windows.Forms.TableLayoutStyle.SizeType%2A> set to <xref:System.Windows.Forms.SizeType.Percent> are used to proportionally allocate the remaining free space</span></span>|  
|`true`|<span data-ttu-id="f0aaf-115">前の操作と同様に、 <xref:System.Windows.Forms.SizeType.Percent> 列または行が自動サイズ変更の側面を取得するという例外があります。</span><span class="sxs-lookup"><span data-stu-id="f0aaf-115">Similar to the previous interaction, with the exception that <xref:System.Windows.Forms.SizeType.Percent> columns or rows acquire an automatic sizing aspect.</span></span><br /><br /> <span data-ttu-id="f0aaf-116">コントロールは、列または行を拡張して <xref:System.Windows.Forms.TableLayoutPanel> 適切な空き領域を作成します。これにより、スタイルが設定された列または行がコンテンツをクリップすることはありません <xref:System.Windows.Forms.SizeType.Percent> 。</span><span class="sxs-lookup"><span data-stu-id="f0aaf-116">The <xref:System.Windows.Forms.TableLayoutPanel> control expands the column or row to create adequate free space, so that no column or row with <xref:System.Windows.Forms.SizeType.Percent> styling clips its contents.</span></span> <span data-ttu-id="f0aaf-117">コントロールは、 <xref:System.Windows.Forms.TableLayoutPanel> プロパティまたはプロパティに従って、新しい領域を均等に割り当て <xref:System.Windows.Forms.ColumnStyle.Width%2A> <xref:System.Windows.Forms.RowStyle.Height%2A> ます。</span><span class="sxs-lookup"><span data-stu-id="f0aaf-117">The <xref:System.Windows.Forms.TableLayoutPanel> control allocates the new space proportionally according to the <xref:System.Windows.Forms.ColumnStyle.Width%2A> or <xref:System.Windows.Forms.RowStyle.Height%2A> property.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="f0aaf-118">関連項目</span><span class="sxs-lookup"><span data-stu-id="f0aaf-118">See also</span></span>

- <xref:System.Windows.Forms.TableLayoutPanel>
- [<span data-ttu-id="f0aaf-119">TableLayoutPanel コントロールの概要</span><span class="sxs-lookup"><span data-stu-id="f0aaf-119">TableLayoutPanel Control Overview</span></span>](tablelayoutpanel-control-overview.md)
