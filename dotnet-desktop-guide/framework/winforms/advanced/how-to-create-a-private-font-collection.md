---
title: '方法: プライベート フォント コレクションを作成する'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- private font collections [Windows Forms], creating
- fonts [Windows Forms], creating private collections
ms.assetid: 6533d5e5-a8dc-4b76-9fc4-3bf75c8b9212
ms.openlocfilehash: 0bb7293a5423004a13cf98b79bba0a6c411a7c97
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/09/2020
ms.locfileid: "96974838"
---
# <a name="how-to-create-a-private-font-collection"></a><span data-ttu-id="6a305-102">方法: プライベート フォント コレクションを作成する</span><span class="sxs-lookup"><span data-stu-id="6a305-102">How to: Create a Private Font Collection</span></span>
<span data-ttu-id="6a305-103">クラスは、 <xref:System.Drawing.Text.PrivateFontCollection> 抽象基本クラスから継承され <xref:System.Drawing.Text.FontCollection> ます。</span><span class="sxs-lookup"><span data-stu-id="6a305-103">The <xref:System.Drawing.Text.PrivateFontCollection> class inherits from the <xref:System.Drawing.Text.FontCollection> abstract base class.</span></span> <span data-ttu-id="6a305-104">オブジェクトを使用し <xref:System.Drawing.Text.PrivateFontCollection> て、アプリケーション専用の一連のフォントを維持することができます。</span><span class="sxs-lookup"><span data-stu-id="6a305-104">You can use a <xref:System.Drawing.Text.PrivateFontCollection> object to maintain a set of fonts specifically for your application.</span></span> <span data-ttu-id="6a305-105">プライベートフォントコレクションには、インストールされているシステムフォントだけでなく、コンピューターにインストールされていないフォントを含めることができます。</span><span class="sxs-lookup"><span data-stu-id="6a305-105">A private font collection can include installed system fonts as well as fonts that have not been installed on the computer.</span></span> <span data-ttu-id="6a305-106">フォントファイルをプライベートフォントコレクションに追加するには、 <xref:System.Drawing.Text.PrivateFontCollection.AddFontFile%2A> オブジェクトのメソッドを呼び出し <xref:System.Drawing.Text.PrivateFontCollection> ます。</span><span class="sxs-lookup"><span data-stu-id="6a305-106">To add a font file to a private font collection, call the <xref:System.Drawing.Text.PrivateFontCollection.AddFontFile%2A> method of a <xref:System.Drawing.Text.PrivateFontCollection> object.</span></span>  
  
 <span data-ttu-id="6a305-107"><xref:System.Drawing.Text.FontCollection.Families%2A>オブジェクトのプロパティには、 <xref:System.Drawing.Text.PrivateFontCollection> オブジェクトの配列が含まれてい <xref:System.Drawing.FontFamily> ます。</span><span class="sxs-lookup"><span data-stu-id="6a305-107">The <xref:System.Drawing.Text.FontCollection.Families%2A> property of a <xref:System.Drawing.Text.PrivateFontCollection> object contains an array of <xref:System.Drawing.FontFamily> objects.</span></span>  
  
 <span data-ttu-id="6a305-108">プライベートフォントコレクション内のフォントファミリの数は、必ずしもコレクションに追加されたフォントファイルの数と同じではありません。</span><span class="sxs-lookup"><span data-stu-id="6a305-108">The number of font families in a private font collection is not necessarily the same as the number of font files that have been added to the collection.</span></span> <span data-ttu-id="6a305-109">たとえば、ファイル ArialBd、Times. tff、および TimesBd. tff をコレクションに追加するとします。</span><span class="sxs-lookup"><span data-stu-id="6a305-109">For example, suppose you add the files ArialBd.tff, Times.tff, and TimesBd.tff to a collection.</span></span> <span data-ttu-id="6a305-110">2つのファイルがありますが、コレクション内のファミリは2つだけです。 tff と TimesBd は同じファミリに属しているためです。</span><span class="sxs-lookup"><span data-stu-id="6a305-110">There will be three files but only two families in the collection because Times.tff and TimesBd.tff belong to the same family.</span></span>  
  
## <a name="example"></a><span data-ttu-id="6a305-111">例</span><span class="sxs-lookup"><span data-stu-id="6a305-111">Example</span></span>  
 <span data-ttu-id="6a305-112">次の例では、オブジェクトに次の3つのフォントファイルを追加し <xref:System.Drawing.Text.PrivateFontCollection> ます。</span><span class="sxs-lookup"><span data-stu-id="6a305-112">The following example adds the following three font files to a <xref:System.Drawing.Text.PrivateFontCollection> object:</span></span>  
  
- <span data-ttu-id="6a305-113">C: \\ *systemroot*\ フォント \ \ ff (Arial、regular)</span><span class="sxs-lookup"><span data-stu-id="6a305-113">C:\\*systemroot*\Fonts\Arial.tff (Arial, regular)</span></span>  
  
- <span data-ttu-id="6a305-114">C: \\ *systemroot*\Fonts\CourBI.tff (Courier new、太字斜体)</span><span class="sxs-lookup"><span data-stu-id="6a305-114">C:\\*systemroot*\Fonts\CourBI.tff (Courier New, bold italic)</span></span>  
  
- <span data-ttu-id="6a305-115">C: \\ *systemroot*\Fonts\TimesBd.tff (Times New Roman, bold)</span><span class="sxs-lookup"><span data-stu-id="6a305-115">C:\\*systemroot*\Fonts\TimesBd.tff (Times New Roman, bold)</span></span>  
  
 <span data-ttu-id="6a305-116">このコードは、オブジェクトのプロパティからオブジェクトの配列を取得し <xref:System.Drawing.FontFamily> <xref:System.Drawing.Text.FontCollection.Families%2A> <xref:System.Drawing.Text.PrivateFontCollection> ます。</span><span class="sxs-lookup"><span data-stu-id="6a305-116">The code retrieves an array of <xref:System.Drawing.FontFamily> objects from the <xref:System.Drawing.Text.FontCollection.Families%2A> property of the <xref:System.Drawing.Text.PrivateFontCollection> object.</span></span>  
  
 <span data-ttu-id="6a305-117">コードは、コレクション内の各オブジェクトに対して、メソッドを呼び出して、 <xref:System.Drawing.FontFamily> <xref:System.Drawing.FontFamily.IsStyleAvailable%2A> さまざまなスタイル (標準、太字、斜体、太字の斜体、下線、および取り消し線) が使用可能かどうかを判断します。</span><span class="sxs-lookup"><span data-stu-id="6a305-117">For each <xref:System.Drawing.FontFamily> object in the collection, the code calls the <xref:System.Drawing.FontFamily.IsStyleAvailable%2A> method to determine whether various styles (regular, bold, italic, bold italic, underline, and strikeout) are available.</span></span> <span data-ttu-id="6a305-118">メソッドに渡される引数 <xref:System.Drawing.FontFamily.IsStyleAvailable%2A> は、列挙体のメンバーです <xref:System.Drawing.FontStyle> 。</span><span class="sxs-lookup"><span data-stu-id="6a305-118">The arguments passed to the <xref:System.Drawing.FontFamily.IsStyleAvailable%2A> method are members of the <xref:System.Drawing.FontStyle> enumeration.</span></span>  
  
 <span data-ttu-id="6a305-119">特定のファミリ/スタイルの組み合わせを使用できる場合は、 <xref:System.Drawing.Font> そのファミリとスタイルを使用してオブジェクトが作成されます。</span><span class="sxs-lookup"><span data-stu-id="6a305-119">If a given family/style combination is available, a <xref:System.Drawing.Font> object is constructed using that family and style.</span></span> <span data-ttu-id="6a305-120">コンストラクターに渡される最初の引数 <xref:System.Drawing.Font.%23ctor%2A> は、フォントファミリ名です ( <xref:System.Drawing.FontFamily> 他の種類のコンストラクターの場合と同様に、オブジェクトではありません <xref:System.Drawing.Font.%23ctor%2A> )。</span><span class="sxs-lookup"><span data-stu-id="6a305-120">The first argument passed to the <xref:System.Drawing.Font.%23ctor%2A> constructor is the font family name (not a <xref:System.Drawing.FontFamily> object as is the case for other variations of the <xref:System.Drawing.Font.%23ctor%2A> constructor).</span></span> <span data-ttu-id="6a305-121"><xref:System.Drawing.Font>オブジェクトが構築されると、 <xref:System.Drawing.Graphics.DrawString%2A> クラスのメソッドに渡され、 <xref:System.Drawing.Graphics> スタイルの名前と共にファミリ名が表示されます。</span><span class="sxs-lookup"><span data-stu-id="6a305-121">After the <xref:System.Drawing.Font> object is constructed, it is passed to the <xref:System.Drawing.Graphics.DrawString%2A> method of the <xref:System.Drawing.Graphics> class to display the family name along with the name of the style.</span></span>  
  
 <span data-ttu-id="6a305-122">次のコードの出力は、次の図に示す出力に似ています。</span><span class="sxs-lookup"><span data-stu-id="6a305-122">The output of the following code is similar to the output shown in the following illustration:</span></span>  
  
 ![さまざまなフォントのテキストを表示するスクリーンショット。](./media/how-to-create-a-private-font-collection/various-fonts-text-output.png)  
  
 <span data-ttu-id="6a305-124">Arial。 tff (次のコード例ではプライベートフォントコレクションに追加されています) は、Arial 標準スタイルのフォントファイルです。</span><span class="sxs-lookup"><span data-stu-id="6a305-124">Arial.tff (which was added to the private font collection in the following code example) is the font file for the Arial regular style.</span></span> <span data-ttu-id="6a305-125">ただし、プログラムの出力には、Arial フォントファミリに対して通常とは異なるいくつかのスタイルが表示されていることに注意してください。</span><span class="sxs-lookup"><span data-stu-id="6a305-125">Note, however, that the program output shows several available styles other than regular for the Arial font family.</span></span> <span data-ttu-id="6a305-126">これは、GDI + が標準スタイルの太字、斜体、太字の斜体スタイルをシミュレートできるためです。</span><span class="sxs-lookup"><span data-stu-id="6a305-126">That is because GDI+ can simulate the bold, italic, and bold italic styles from the regular style.</span></span> <span data-ttu-id="6a305-127">GDI + では、標準スタイルから下線と strikeouts を生成することもできます。</span><span class="sxs-lookup"><span data-stu-id="6a305-127">GDI+ can also produce underlines and strikeouts from the regular style.</span></span>  
  
 <span data-ttu-id="6a305-128">同様に、GDI + は、太字スタイルまたは斜体スタイルから太字の斜体スタイルをシミュレートできます。</span><span class="sxs-lookup"><span data-stu-id="6a305-128">Similarly, GDI+ can simulate the bold italic style from either the bold style or the italic style.</span></span> <span data-ttu-id="6a305-129">プログラムの出力は、タイムファミリでは、タイムファミリでも太字の斜体スタイルを使用できることを示しています。 tff (Times New Roman, bold) は、コレクション内の唯一の時刻ファイルです。</span><span class="sxs-lookup"><span data-stu-id="6a305-129">The program output shows that the bold italic style is available for the Times family even though TimesBd.tff (Times New Roman, bold) is the only Times file in the collection.</span></span>  
  
 [!code-csharp[System.Drawing.FontsAndText#51](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.FontsAndText/CS/Class1.cs#51)]
 [!code-vb[System.Drawing.FontsAndText#51](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.FontsAndText/VB/Class1.vb#51)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="6a305-130">コードのコンパイル</span><span class="sxs-lookup"><span data-stu-id="6a305-130">Compiling the Code</span></span>  
 <span data-ttu-id="6a305-131">前の例は、Windows フォームで使用するように設計されてい <xref:System.Windows.Forms.PaintEventArgs> `e` ます。これは、のパラメーターであるを必要とし <xref:System.Windows.Forms.PaintEventHandler> ます。</span><span class="sxs-lookup"><span data-stu-id="6a305-131">The preceding example is designed for use with Windows Forms, and it requires <xref:System.Windows.Forms.PaintEventArgs> `e`, which is a parameter of <xref:System.Windows.Forms.PaintEventHandler>.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6a305-132">関連項目</span><span class="sxs-lookup"><span data-stu-id="6a305-132">See also</span></span>

- <xref:System.Drawing.Text.PrivateFontCollection>
- [<span data-ttu-id="6a305-133">フォントとテキストの使用</span><span class="sxs-lookup"><span data-stu-id="6a305-133">Using Fonts and Text</span></span>](using-fonts-and-text.md)
