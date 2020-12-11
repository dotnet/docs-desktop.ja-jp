---
title: '方法: インストールされているフォントを列挙する'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- fonts [Windows Forms], enumerating installed
- examples [Windows Forms], fonts
ms.assetid: 26d74ef5-0f39-4eeb-8d20-00e66e014abe
ms.openlocfilehash: 92f27399cce9e03a4679c8a34fbdafcf28c32252
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/09/2020
ms.locfileid: "96981859"
---
# <a name="how-to-enumerate-installed-fonts"></a><span data-ttu-id="3b97a-102">方法: インストールされているフォントを列挙する</span><span class="sxs-lookup"><span data-stu-id="3b97a-102">How to: Enumerate Installed Fonts</span></span>
<span data-ttu-id="3b97a-103">クラスは、 <xref:System.Drawing.Text.InstalledFontCollection> 抽象基本クラスから継承され <xref:System.Drawing.Text.FontCollection> ます。</span><span class="sxs-lookup"><span data-stu-id="3b97a-103">The <xref:System.Drawing.Text.InstalledFontCollection> class inherits from the <xref:System.Drawing.Text.FontCollection> abstract base class.</span></span> <span data-ttu-id="3b97a-104">オブジェクトを使用し <xref:System.Drawing.Text.InstalledFontCollection> て、コンピューターにインストールされているフォントを列挙できます。</span><span class="sxs-lookup"><span data-stu-id="3b97a-104">You can use an <xref:System.Drawing.Text.InstalledFontCollection> object to enumerate the fonts installed on the computer.</span></span> <span data-ttu-id="3b97a-105"><xref:System.Drawing.Text.FontCollection.Families%2A>オブジェクトのプロパティ <xref:System.Drawing.Text.InstalledFontCollection> は、オブジェクトの配列です <xref:System.Drawing.FontFamily> 。</span><span class="sxs-lookup"><span data-stu-id="3b97a-105">The <xref:System.Drawing.Text.FontCollection.Families%2A> property of an <xref:System.Drawing.Text.InstalledFontCollection> object is an array of <xref:System.Drawing.FontFamily> objects.</span></span>  
  
## <a name="example"></a><span data-ttu-id="3b97a-106">例</span><span class="sxs-lookup"><span data-stu-id="3b97a-106">Example</span></span>  
 <span data-ttu-id="3b97a-107">次の例では、コンピューターにインストールされているすべてのフォントファミリの名前を一覧表示します。</span><span class="sxs-lookup"><span data-stu-id="3b97a-107">The following example lists the names of all the font families installed on the computer.</span></span> <span data-ttu-id="3b97a-108">このコードは、 <xref:System.Drawing.FontFamily.Name%2A> <xref:System.Drawing.FontFamily> プロパティによって返される配列内の各オブジェクトのプロパティを取得し <xref:System.Drawing.Text.FontCollection.Families%2A> ます。</span><span class="sxs-lookup"><span data-stu-id="3b97a-108">The code retrieves the <xref:System.Drawing.FontFamily.Name%2A> property of each <xref:System.Drawing.FontFamily> object in the array returned by the <xref:System.Drawing.Text.FontCollection.Families%2A> property.</span></span> <span data-ttu-id="3b97a-109">ファミリ名が取得されると、コンマ区切りのリストを形成するために連結されます。</span><span class="sxs-lookup"><span data-stu-id="3b97a-109">As the family names are retrieved, they are concatenated to form a comma-separated list.</span></span> <span data-ttu-id="3b97a-110">次に、 <xref:System.Drawing.Graphics.DrawString%2A> クラスのメソッドは、 <xref:System.Drawing.Graphics> コンマ区切りのリストを四角形に描画します。</span><span class="sxs-lookup"><span data-stu-id="3b97a-110">Then the <xref:System.Drawing.Graphics.DrawString%2A> method of the <xref:System.Drawing.Graphics> class draws the comma-separated list in a rectangle.</span></span>  
  
 <span data-ttu-id="3b97a-111">コード例を実行すると、出力は次の図に示すようになります。</span><span class="sxs-lookup"><span data-stu-id="3b97a-111">If you run the example code, the output will be similar to that shown in the following illustration:</span></span>  
  
 ![インストールされているフォントファミリを示すスクリーンショット。](./media/how-to-enumerate-installed-fonts/list-installed-font-families.png)  
  
 [!code-csharp[System.Drawing.FontsAndText#11](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.FontsAndText/CS/Class1.cs#11)]
 [!code-vb[System.Drawing.FontsAndText#11](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.FontsAndText/VB/Class1.vb#11)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="3b97a-113">コードのコンパイル</span><span class="sxs-lookup"><span data-stu-id="3b97a-113">Compiling the Code</span></span>  
 <span data-ttu-id="3b97a-114">前の例は、Windows フォームで使用するように設計されてい <xref:System.Windows.Forms.PaintEventArgs> `e` ます。これは、のパラメーターであるを必要とし <xref:System.Windows.Forms.PaintEventHandler> ます。</span><span class="sxs-lookup"><span data-stu-id="3b97a-114">The preceding example is designed for use with Windows Forms, and it requires <xref:System.Windows.Forms.PaintEventArgs> `e`, which is a parameter of <xref:System.Windows.Forms.PaintEventHandler>.</span></span> <span data-ttu-id="3b97a-115">また、名前空間をインポートする必要があり <xref:System.Drawing.Text> ます。</span><span class="sxs-lookup"><span data-stu-id="3b97a-115">In addition, you should import the <xref:System.Drawing.Text> namespace.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3b97a-116">関連項目</span><span class="sxs-lookup"><span data-stu-id="3b97a-116">See also</span></span>

- [<span data-ttu-id="3b97a-117">フォントとテキストの使用</span><span class="sxs-lookup"><span data-stu-id="3b97a-117">Using Fonts and Text</span></span>](using-fonts-and-text.md)
