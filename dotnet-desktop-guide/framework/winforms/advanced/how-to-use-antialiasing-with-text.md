---
title: '方法: テキストでのアンチエイリアシングの使用'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- strings [Windows Forms], smoothing drawn
- antialiasing [Windows Forms], using with text
- text [Windows Forms], smoothing
- text [Windows Forms], antialiasing
- strings [Windows Forms], antialiasing when drawing
ms.assetid: 48fc34f3-f236-4b01-a0cb-f0752e6d22ae
ms.openlocfilehash: 632ed329173d134495a424b34ca7c71e402607bf
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/09/2020
ms.locfileid: "96981728"
---
# <a name="how-to-use-antialiasing-with-text"></a><span data-ttu-id="cbc1b-102">方法: テキストでのアンチエイリアシングの使用</span><span class="sxs-lookup"><span data-stu-id="cbc1b-102">How to: Use Antialiasing with Text</span></span>
<span data-ttu-id="cbc1b-103">*アンチエイリアシング* とは、描画されたグラフィックスとテキストのギザギザの端を滑らかにして、外観や読みやすさを向上させることを指します。</span><span class="sxs-lookup"><span data-stu-id="cbc1b-103">*Antialiasing* refers to the smoothing of jagged edges of drawn graphics and text to improve their appearance or readability.</span></span> <span data-ttu-id="cbc1b-104">マネージ GDI + クラスを使用すると、高品質のアンチエイリアシングテキストと、低品質のテキストを表示できます。</span><span class="sxs-lookup"><span data-stu-id="cbc1b-104">With the managed GDI+ classes, you can render high quality antialiased text, as well as lower quality text.</span></span> <span data-ttu-id="cbc1b-105">通常、品質の高いレンダリングは、低品質のレンダリングよりも処理時間が長くなります。</span><span class="sxs-lookup"><span data-stu-id="cbc1b-105">Typically, higher quality rendering takes more processing time than lower quality rendering.</span></span> <span data-ttu-id="cbc1b-106">テキスト品質レベルを設定するには、 <xref:System.Drawing.Graphics.TextRenderingHint%2A> のプロパティを <xref:System.Drawing.Graphics> 列挙体のいずれかの要素に設定します。 <xref:System.Drawing.Text.TextRenderingHint></span><span class="sxs-lookup"><span data-stu-id="cbc1b-106">To set the text quality level, set the <xref:System.Drawing.Graphics.TextRenderingHint%2A> property of a <xref:System.Drawing.Graphics> to one of the elements of the <xref:System.Drawing.Text.TextRenderingHint> enumeration</span></span>  
  
## <a name="example"></a><span data-ttu-id="cbc1b-107">例</span><span class="sxs-lookup"><span data-stu-id="cbc1b-107">Example</span></span>  
 <span data-ttu-id="cbc1b-108">次のコード例では、2つの異なる品質設定を使用してテキストを描画します。</span><span class="sxs-lookup"><span data-stu-id="cbc1b-108">The following code example draws text with two different quality settings.</span></span>  
  
 [!code-csharp[System.Drawing.FontsAndText#21](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.FontsAndText/CS/Class1.cs#21)]
 [!code-vb[System.Drawing.FontsAndText#21](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.FontsAndText/VB/Class1.vb#21)]  

 <span data-ttu-id="cbc1b-109">次の図は、コード例の出力を示しています。</span><span class="sxs-lookup"><span data-stu-id="cbc1b-109">The following illustration shows the output of the example code:</span></span>  
  
 ![2つの異なる品質設定のテキストを表示するスクリーンショット。](./media/how-to-use-antialiasing-with-text/antialiasing-text-quality-settings.png)  
  
## <a name="compiling-the-code"></a><span data-ttu-id="cbc1b-111">コードのコンパイル</span><span class="sxs-lookup"><span data-stu-id="cbc1b-111">Compiling the Code</span></span>  
 <span data-ttu-id="cbc1b-112">上記のコード例は、Windows フォームで使用するように設計されてい <xref:System.Windows.Forms.PaintEventArgs> `e` ます。これは、のパラメーターであるを必要とし <xref:System.Windows.Forms.PaintEventHandler> ます。</span><span class="sxs-lookup"><span data-stu-id="cbc1b-112">The preceding code example is designed for use with Windows Forms, and it requires <xref:System.Windows.Forms.PaintEventArgs> `e`, which is a parameter of <xref:System.Windows.Forms.PaintEventHandler>.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="cbc1b-113">関連項目</span><span class="sxs-lookup"><span data-stu-id="cbc1b-113">See also</span></span>

- [<span data-ttu-id="cbc1b-114">フォントとテキストの使用</span><span class="sxs-lookup"><span data-stu-id="cbc1b-114">Using Fonts and Text</span></span>](using-fonts-and-text.md)
