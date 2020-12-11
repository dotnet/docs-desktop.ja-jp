---
title: '方法: ファイルに関連付けられているアイコンを抽出する'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- displaying a file name and its file type icon in a ListView control [Windows Forms]
- file name extension icons [Windows Forms], displaying in a ListView
- extracting icons associated with a file type [Windows Forms]
ms.assetid: 88e2ad8b-c34f-415a-84f2-dad756b5c928
ms.openlocfilehash: 28769144b0e1c631a31c3c541747a6215f861d0e
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/09/2020
ms.locfileid: "96981343"
---
# <a name="how-to-extract-the-icon-associated-with-a-file-in-windows-forms"></a><span data-ttu-id="1a4cb-102">方法: Windows フォームでファイルに関連付けられているアイコンを抽出する</span><span class="sxs-lookup"><span data-stu-id="1a4cb-102">How to: Extract the Icon Associated with a File in Windows Forms</span></span>
<span data-ttu-id="1a4cb-103">多くのファイルには、関連付けられたファイルの種類を視覚的に表現するアイコンが組み込まれています。</span><span class="sxs-lookup"><span data-stu-id="1a4cb-103">Many files have embedded icons that provide a visual representation of the associated file type.</span></span> <span data-ttu-id="1a4cb-104">たとえば、Microsoft Word 文書には、それらを Word 文書として識別するアイコンが含まれています。</span><span class="sxs-lookup"><span data-stu-id="1a4cb-104">For example, Microsoft Word documents contain an icon that identifies them as Word documents.</span></span> <span data-ttu-id="1a4cb-105">リストコントロールまたはテーブルコントロールにファイルを表示する場合、各ファイル名の横にあるファイルの種類を表すアイコンを表示することができます。</span><span class="sxs-lookup"><span data-stu-id="1a4cb-105">When displaying files in a list control or table control, you may want to display the icon representing the file type next to each file name.</span></span> <span data-ttu-id="1a4cb-106">これは、メソッドを使用して簡単に行うことができ <xref:System.Drawing.Icon.ExtractAssociatedIcon%2A> ます。</span><span class="sxs-lookup"><span data-stu-id="1a4cb-106">You can do this easily by using the <xref:System.Drawing.Icon.ExtractAssociatedIcon%2A> method.</span></span>  
  
## <a name="example"></a><span data-ttu-id="1a4cb-107">例</span><span class="sxs-lookup"><span data-stu-id="1a4cb-107">Example</span></span>  
 <span data-ttu-id="1a4cb-108">次のコード例は、ファイルに関連付けられたアイコンを抽出し、ファイル名とそれに関連付けられているアイコンをコントロールに表示する方法を示して <xref:System.Windows.Forms.ListView> います。</span><span class="sxs-lookup"><span data-stu-id="1a4cb-108">The following code example demonstrates how to extract the icon associated with a file and display the file name and its associated icon in a <xref:System.Windows.Forms.ListView> control.</span></span>  
  
 [!code-csharp[System.Drawing.Icon.ExtractAssociatedIconEx#1](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.Icon.ExtractAssociatedIconEx/CS/Form1.cs#1)]
 [!code-vb[System.Drawing.Icon.ExtractAssociatedIconEx#1](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.Icon.ExtractAssociatedIconEx/VB/Form1.vb#1)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="1a4cb-109">コードのコンパイル</span><span class="sxs-lookup"><span data-stu-id="1a4cb-109">Compiling the Code</span></span>  
 <span data-ttu-id="1a4cb-110">この例をコンパイルするには、次のようにします。</span><span class="sxs-lookup"><span data-stu-id="1a4cb-110">To compile the example:</span></span>  
  
- <span data-ttu-id="1a4cb-111">前のコードを Windows フォームに貼り付け、 `ExtractAssociatedIconExample` フォームのコンストラクターまたはイベント処理メソッドからメソッドを呼び出し <xref:System.Windows.Forms.Form.Load> ます。</span><span class="sxs-lookup"><span data-stu-id="1a4cb-111">Paste the preceding code into a Windows Form, and call the `ExtractAssociatedIconExample` method from the form's constructor or <xref:System.Windows.Forms.Form.Load> event-handling method.</span></span>  
  
     <span data-ttu-id="1a4cb-112">フォームが名前空間をインポートすることを確認する必要があり <xref:System.IO> ます。</span><span class="sxs-lookup"><span data-stu-id="1a4cb-112">You will need to make sure that your form imports the <xref:System.IO> namespace.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1a4cb-113">関連項目</span><span class="sxs-lookup"><span data-stu-id="1a4cb-113">See also</span></span>

- [<span data-ttu-id="1a4cb-114">イメージ、ビットマップ、およびメタファイル</span><span class="sxs-lookup"><span data-stu-id="1a4cb-114">Images, Bitmaps, and Metafiles</span></span>](images-bitmaps-and-metafiles.md)
- [<span data-ttu-id="1a4cb-115">ListView コントロール</span><span class="sxs-lookup"><span data-stu-id="1a4cb-115">ListView Control</span></span>](../controls/listview-control-windows-forms.md)
