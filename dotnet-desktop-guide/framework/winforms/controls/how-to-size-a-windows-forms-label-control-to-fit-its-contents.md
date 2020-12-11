---
title: コンテンツに合わせてラベルコントロールのサイズを変更する
ms.date: 03/30/2017
helpviewer_keywords:
- captions [Windows Forms], sizing
- sizing controls
- size [Windows Forms], controls
- labels [Windows Forms], sizing to fit contents
- Label control [Windows Forms], sizing to fit contents
ms.assetid: 99648964-63b2-438c-980e-d24103ad602b
ms.openlocfilehash: 6a563693feaa5074f5d13f0b82cc4d0305a79c23
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/09/2020
ms.locfileid: "96982804"
---
# <a name="how-to-size-a-windows-forms-label-control-to-fit-its-contents"></a><span data-ttu-id="60944-102">方法: Windows フォーム Label コントロールのサイズを内容に合わせて変更する</span><span class="sxs-lookup"><span data-stu-id="60944-102">How to: Size a Windows Forms Label Control to Fit Its Contents</span></span>
<span data-ttu-id="60944-103">Windows フォーム <xref:System.Windows.Forms.Label> コントロールは単一行または複数行にすることができ、サイズを固定するか、キャプションに合わせて自動的にサイズを変更することができます。</span><span class="sxs-lookup"><span data-stu-id="60944-103">The Windows Forms <xref:System.Windows.Forms.Label> control can be single-line or multi-line, and it can be either fixed in size or can automatically resize itself to accommodate its caption.</span></span> <span data-ttu-id="60944-104"><xref:System.Windows.Forms.Label.AutoSize%2A>プロパティを使用すると、コントロールのサイズを大きくしたり小さくしたりすることができます。これは、実行時にキャプションが変化する場合に特に便利です。</span><span class="sxs-lookup"><span data-stu-id="60944-104">The <xref:System.Windows.Forms.Label.AutoSize%2A> property helps you size the controls to fit larger or smaller captions, which is particularly useful if the caption will change at run time.</span></span>  
  
### <a name="to-make-a-label-control-resize-dynamically-to-fit-its-contents"></a><span data-ttu-id="60944-105">コンテンツに合わせてラベルコントロールのサイズを動的に変更するには</span><span class="sxs-lookup"><span data-stu-id="60944-105">To make a label control resize dynamically to fit its contents</span></span>  
  
1. <span data-ttu-id="60944-106"><xref:System.Windows.Forms.Label.AutoSize%2A>プロパティをに設定 `true` します。</span><span class="sxs-lookup"><span data-stu-id="60944-106">Set its <xref:System.Windows.Forms.Label.AutoSize%2A> property to `true`.</span></span>  
  
 <span data-ttu-id="60944-107">がに設定されている場合、可能であれ <xref:System.Windows.Forms.Label.AutoSize%2A> `false` ば、プロパティで指定された単語 <xref:System.Windows.Forms.Label.Text%2A> は次の行に折り返されますが、コントロールは拡張されません。</span><span class="sxs-lookup"><span data-stu-id="60944-107">If <xref:System.Windows.Forms.Label.AutoSize%2A> is set to `false`, the words specified in the <xref:System.Windows.Forms.Label.Text%2A> property will wrap to the next line if possible, but the control will not grow.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="60944-108">関連項目</span><span class="sxs-lookup"><span data-stu-id="60944-108">See also</span></span>

- [<span data-ttu-id="60944-109">方法: Windows フォームの Label コントロールでアクセス キーを作成する</span><span class="sxs-lookup"><span data-stu-id="60944-109">How to: Create Access Keys with Windows Forms Label Controls</span></span>](how-to-create-access-keys-with-windows-forms-label-controls.md)
- [<span data-ttu-id="60944-110">Label コントロールの概要</span><span class="sxs-lookup"><span data-stu-id="60944-110">Label Control Overview</span></span>](label-control-overview-windows-forms.md)
- [<span data-ttu-id="60944-111">Label コントロール</span><span class="sxs-lookup"><span data-stu-id="60944-111">Label Control</span></span>](label-control-windows-forms.md)
