---
title: '方法: フォント ファミリとフォントを作成する'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- font families [Windows Forms], constructing
- fonts [Windows Forms], constructing
ms.assetid: d3a4a223-9492-4b54-9afd-db1c31c3cefd
ms.openlocfilehash: 2d609525858c7a8ff77c0b86900b4fc7d6b4e39a
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/09/2020
ms.locfileid: "96974428"
---
# <a name="how-to-construct-font-families-and-fonts"></a><span data-ttu-id="f4638-102">方法: フォント ファミリとフォントを作成する</span><span class="sxs-lookup"><span data-stu-id="f4638-102">How to: Construct Font Families and Fonts</span></span>
<span data-ttu-id="f4638-103">GDI + は、同じタイプフェイスを持つフォントをグループ化しますが、スタイルはフォントファミリによって異なります。</span><span class="sxs-lookup"><span data-stu-id="f4638-103">GDI+ groups fonts with the same typeface but different styles into font families.</span></span> <span data-ttu-id="f4638-104">たとえば、Arial フォントファミリには、次のフォントが含まれています。</span><span class="sxs-lookup"><span data-stu-id="f4638-104">For example, the Arial font family contains the following fonts:</span></span>  
  
- <span data-ttu-id="f4638-105">Arial 通常</span><span class="sxs-lookup"><span data-stu-id="f4638-105">Arial Regular</span></span>  
  
- <span data-ttu-id="f4638-106">Arial 太字</span><span class="sxs-lookup"><span data-stu-id="f4638-106">Arial Bold</span></span>  
  
- <span data-ttu-id="f4638-107">Arial 斜体</span><span class="sxs-lookup"><span data-stu-id="f4638-107">Arial Italic</span></span>  
  
- <span data-ttu-id="f4638-108">Arial 太字斜体</span><span class="sxs-lookup"><span data-stu-id="f4638-108">Arial Bold Italic</span></span>  
  
 <span data-ttu-id="f4638-109">GDI + では、標準、太字、斜体、太字の斜体の4つのスタイルを使用してファミリを形成します。</span><span class="sxs-lookup"><span data-stu-id="f4638-109">GDI+ uses four styles to form families: regular, bold, italic, and bold italic.</span></span> <span data-ttu-id="f4638-110">*ナロー* や *丸い* などの形容詞は、スタイルとは見なされません。代わりに、ファミリ名の一部になります。</span><span class="sxs-lookup"><span data-stu-id="f4638-110">Adjectives such as *narrow* and *rounded* are not considered styles; rather they are part of the family name.</span></span> <span data-ttu-id="f4638-111">たとえば、Arial ナローは、次のメンバーを持つフォントファミリです。</span><span class="sxs-lookup"><span data-stu-id="f4638-111">For example, Arial Narrow is a font family with the following members:</span></span>  
  
- <span data-ttu-id="f4638-112">Arial ナロー標準</span><span class="sxs-lookup"><span data-stu-id="f4638-112">Arial Narrow Regular</span></span>  
  
- <span data-ttu-id="f4638-113">Arial ナロー Bold</span><span class="sxs-lookup"><span data-stu-id="f4638-113">Arial Narrow Bold</span></span>  
  
- <span data-ttu-id="f4638-114">Arial ナロー斜体</span><span class="sxs-lookup"><span data-stu-id="f4638-114">Arial Narrow Italic</span></span>  
  
- <span data-ttu-id="f4638-115">Arial ナロー太字斜体</span><span class="sxs-lookup"><span data-stu-id="f4638-115">Arial Narrow Bold Italic</span></span>  
  
 <span data-ttu-id="f4638-116">GDI + を使用してテキストを描画するには、オブジェクトとオブジェクトを構築する必要があり <xref:System.Drawing.FontFamily> <xref:System.Drawing.Font> ます。</span><span class="sxs-lookup"><span data-stu-id="f4638-116">Before you can draw text with GDI+, you need to construct a <xref:System.Drawing.FontFamily> object and a <xref:System.Drawing.Font> object.</span></span> <span data-ttu-id="f4638-117"><xref:System.Drawing.FontFamily>オブジェクトはタイプフェイス (Arial など) を指定し、オブジェクトは <xref:System.Drawing.Font> サイズ、スタイル、および単位を指定します。</span><span class="sxs-lookup"><span data-stu-id="f4638-117">The <xref:System.Drawing.FontFamily> object specifies the typeface (for example, Arial), and the <xref:System.Drawing.Font> object specifies the size, style, and units.</span></span>  
  
## <a name="example"></a><span data-ttu-id="f4638-118">例</span><span class="sxs-lookup"><span data-stu-id="f4638-118">Example</span></span>  
 <span data-ttu-id="f4638-119">次の例では、サイズが16ピクセルの通常スタイルの Arial フォントを構築します。</span><span class="sxs-lookup"><span data-stu-id="f4638-119">The following example constructs a regular style Arial font with a size of 16 pixels.</span></span> <span data-ttu-id="f4638-120">次のコードでは、コンストラクターに渡される最初の引数 <xref:System.Drawing.Font.%23ctor%2A> は <xref:System.Drawing.FontFamily> オブジェクトです。</span><span class="sxs-lookup"><span data-stu-id="f4638-120">In the following code, the first argument passed to the <xref:System.Drawing.Font.%23ctor%2A> constructor is the <xref:System.Drawing.FontFamily> object.</span></span> <span data-ttu-id="f4638-121">2番目の引数は、4番目の引数によって識別される単位で計測されるフォントのサイズを指定します。</span><span class="sxs-lookup"><span data-stu-id="f4638-121">The second argument specifies the size of the font measured in units identified by the fourth argument.</span></span> <span data-ttu-id="f4638-122">3番目の引数は、スタイルを識別します。</span><span class="sxs-lookup"><span data-stu-id="f4638-122">The third argument identifies the style.</span></span>  
  
 <span data-ttu-id="f4638-123"><xref:System.Drawing.GraphicsUnit.Pixel> は列挙体のメンバーで、 <xref:System.Drawing.GraphicsUnit> <xref:System.Drawing.FontStyle.Regular> は列挙体のメンバーです <xref:System.Drawing.FontStyle> 。</span><span class="sxs-lookup"><span data-stu-id="f4638-123"><xref:System.Drawing.GraphicsUnit.Pixel> is a member of the <xref:System.Drawing.GraphicsUnit> enumeration, and <xref:System.Drawing.FontStyle.Regular> is a member of the <xref:System.Drawing.FontStyle> enumeration.</span></span>  
  
 [!code-csharp[System.Drawing.FontsAndText#61](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.FontsAndText/CS/Class1.cs#61)]
 [!code-vb[System.Drawing.FontsAndText#61](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.FontsAndText/VB/Class1.vb#61)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="f4638-124">コードのコンパイル</span><span class="sxs-lookup"><span data-stu-id="f4638-124">Compiling the Code</span></span>  
 <span data-ttu-id="f4638-125">前の例は、Windows フォームで使用するように設計されてい <xref:System.Windows.Forms.PaintEventArgs> `e` ます。これは、のパラメーターであるを必要とし <xref:System.Windows.Forms.PaintEventHandler> ます。</span><span class="sxs-lookup"><span data-stu-id="f4638-125">The preceding example is designed for use with Windows Forms, and it requires <xref:System.Windows.Forms.PaintEventArgs> `e`, which is a parameter of <xref:System.Windows.Forms.PaintEventHandler>.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f4638-126">関連項目</span><span class="sxs-lookup"><span data-stu-id="f4638-126">See also</span></span>

- [<span data-ttu-id="f4638-127">フォントとテキストの使用</span><span class="sxs-lookup"><span data-stu-id="f4638-127">Using Fonts and Text</span></span>](using-fonts-and-text.md)
- [<span data-ttu-id="f4638-128">Windows フォームにおけるグラフィックスと描画</span><span class="sxs-lookup"><span data-stu-id="f4638-128">Graphics and Drawing in Windows Forms</span></span>](graphics-and-drawing-in-windows-forms.md)
