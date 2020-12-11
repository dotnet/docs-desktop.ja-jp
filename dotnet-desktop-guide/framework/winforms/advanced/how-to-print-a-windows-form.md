---
title: '方法: Windows フォームを印刷する'
description: CopyFromScreen メソッドを使用して、現在の Windows フォームのコピーをプログラムで印刷する方法について説明します。
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- Windows Forms, printing
- printing [Windows Forms]
- printing a form
- printing [Windows Forms], printing a form
ms.assetid: c8dff5f8-f56a-4c07-ae31-64643b31f8fc
ms.openlocfilehash: b59ea4b5347903b36a166c4f8ac0d8d7db18635e
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/09/2020
ms.locfileid: "96981296"
---
# <a name="how-to-print-a-windows-form"></a><span data-ttu-id="07637-103">方法: Windows フォームを印刷する</span><span class="sxs-lookup"><span data-stu-id="07637-103">How to: Print a Windows Form</span></span>
<span data-ttu-id="07637-104">開発プロセスの一環として、通常は Windows フォームのコピーを印刷します。</span><span class="sxs-lookup"><span data-stu-id="07637-104">As part of the development process, you typically will want to print a copy of your Windows Form.</span></span> <span data-ttu-id="07637-105">次のコード例は、メソッドを使用して、現在のフォームのコピーを印刷する方法を示して <xref:System.Drawing.Graphics.CopyFromScreen%2A> います。</span><span class="sxs-lookup"><span data-stu-id="07637-105">The following code example shows how to print a copy of the current form by using the <xref:System.Drawing.Graphics.CopyFromScreen%2A> method.</span></span>  
  
## <a name="example"></a><span data-ttu-id="07637-106">例</span><span class="sxs-lookup"><span data-stu-id="07637-106">Example</span></span>  
 [!code-csharp[System.Drawing.Graphics.CopyFromScreen#1](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.Graphics.CopyFromScreen/CS/Form1.cs#1)]
 [!code-vb[System.Drawing.Graphics.CopyFromScreen#1](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.Graphics.CopyFromScreen/VB/Form1.vb#1)]  
  
## <a name="robust-programming"></a><span data-ttu-id="07637-107">信頼性の高いプログラミング</span><span class="sxs-lookup"><span data-stu-id="07637-107">Robust Programming</span></span>  
 <span data-ttu-id="07637-108">次の条件を満たす場合は、例外が発生する可能性があります。</span><span class="sxs-lookup"><span data-stu-id="07637-108">The following conditions may cause an exception:</span></span>  
  
- <span data-ttu-id="07637-109">プリンターにアクセスするためのアクセス許可がありません。</span><span class="sxs-lookup"><span data-stu-id="07637-109">You do not have permission to access the printer.</span></span>  
  
- <span data-ttu-id="07637-110">プリンターがインストールされていません。</span><span class="sxs-lookup"><span data-stu-id="07637-110">There is no printer installed.</span></span>  
  
## <a name="net-framework-security"></a><span data-ttu-id="07637-111">.NET Framework セキュリティ</span><span class="sxs-lookup"><span data-stu-id="07637-111">.NET Framework Security</span></span>  
 <span data-ttu-id="07637-112">このコード例を実行するには、コンピューターで使用するプリンターにアクセスするためのアクセス許可が必要です。</span><span class="sxs-lookup"><span data-stu-id="07637-112">In order to run this code example, you must have permission to access the printer you use with your computer.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="07637-113">関連項目</span><span class="sxs-lookup"><span data-stu-id="07637-113">See also</span></span>

- <xref:System.Drawing.Printing.PrintDocument>
- [<span data-ttu-id="07637-114">方法: GDI+ を使用してイメージをレンダリングする</span><span class="sxs-lookup"><span data-stu-id="07637-114">How to: Render Images with GDI+</span></span>](how-to-render-images-with-gdi.md)
- [<span data-ttu-id="07637-115">方法: Windows フォームでグラフィックスを印刷する</span><span class="sxs-lookup"><span data-stu-id="07637-115">How to: Print Graphics in Windows Forms</span></span>](how-to-print-graphics-in-windows-forms.md)
