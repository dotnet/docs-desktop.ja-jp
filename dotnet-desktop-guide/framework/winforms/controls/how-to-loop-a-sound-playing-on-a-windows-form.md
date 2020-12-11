---
title: '方法: Windows フォームでサウンドの再生をループする'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- sound loops
- SoundPlayer class [Windows Forms], play looping
- sounds [Windows Forms], looping
- playing sounds [Windows Forms], looping
ms.assetid: ea95dd46-10a3-46c0-8263-4b205f00df7f
ms.openlocfilehash: e14d9de2326234b86c1f24b227e86f822fbfdb71
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/09/2020
ms.locfileid: "96982855"
---
# <a name="how-to-loop-a-sound-playing-on-a-windows-form"></a><span data-ttu-id="f06b5-102">方法: Windows フォームでサウンドの再生をループする</span><span class="sxs-lookup"><span data-stu-id="f06b5-102">How to: Loop a Sound Playing on a Windows Form</span></span>
<span data-ttu-id="f06b5-103">サウンドを繰り返し再生するコード例を次に示します。</span><span class="sxs-lookup"><span data-stu-id="f06b5-103">The following code example plays a sound repeatedly.</span></span> <span data-ttu-id="f06b5-104">`stopPlayingButton_Click` イベント ハンドラー内のコードが実行されると、現在再生されているサウンドが停止します。</span><span class="sxs-lookup"><span data-stu-id="f06b5-104">When the code in the `stopPlayingButton_Click` event handler runs, any sound currently playing stops.</span></span> <span data-ttu-id="f06b5-105">サウンドが再生されていない場合は、何も起こりません。</span><span class="sxs-lookup"><span data-stu-id="f06b5-105">If no sound is playing, nothing happens.</span></span>  
  
## <a name="example"></a><span data-ttu-id="f06b5-106">例</span><span class="sxs-lookup"><span data-stu-id="f06b5-106">Example</span></span>  
 [!code-csharp[System.Media.SoundPlayer.PlayLooping#1](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Media.SoundPlayer.PlayLooping/CS/Form1.cs#1)]
 [!code-vb[System.Media.SoundPlayer.PlayLooping#1](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Media.SoundPlayer.PlayLooping/VB/Form1.vb#1)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="f06b5-107">コードのコンパイル</span><span class="sxs-lookup"><span data-stu-id="f06b5-107">Compiling the Code</span></span>  
 <span data-ttu-id="f06b5-108">この例で必要な要素は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="f06b5-108">This example requires:</span></span>  
  
- <span data-ttu-id="f06b5-109">System アセンブリおよび System.Windows.Forms アセンブリへの参照。</span><span class="sxs-lookup"><span data-stu-id="f06b5-109">References to the System and System.Windows.Forms assemblies.</span></span>  
  
- <span data-ttu-id="f06b5-110">ファイル名 `"c:\Windows\Media\chimes.wav"` を有効なファイル名に置き換えます。</span><span class="sxs-lookup"><span data-stu-id="f06b5-110">That you replace the file name `"c:\Windows\Media\chimes.wav"` with a valid file name.</span></span>  
  
## <a name="robust-programming"></a><span data-ttu-id="f06b5-111">信頼性の高いプログラミング</span><span class="sxs-lookup"><span data-stu-id="f06b5-111">Robust Programming</span></span>  
 <span data-ttu-id="f06b5-112">ファイルの操作は、適切な例外処理ブロックで囲む必要があります。</span><span class="sxs-lookup"><span data-stu-id="f06b5-112">File operations should be enclosed within appropriate exception-handling blocks.</span></span>  
  
 <span data-ttu-id="f06b5-113">次の条件を満たす場合は、例外が発生する可能性があります。</span><span class="sxs-lookup"><span data-stu-id="f06b5-113">The following conditions may cause an exception:</span></span>  
  
- <span data-ttu-id="f06b5-114">パス名が不適切である場合。</span><span class="sxs-lookup"><span data-stu-id="f06b5-114">The path name is malformed.</span></span> <span data-ttu-id="f06b5-115">たとえば、無効な文字が含まれている場合や、空白だけの場合などです (<xref:System.ArgumentException> クラス)。</span><span class="sxs-lookup"><span data-stu-id="f06b5-115">For example, it contains characters that are not valid or it is only white space (<xref:System.ArgumentException> class).</span></span>  
  
- <span data-ttu-id="f06b5-116">パスが読み取り専用である場合 (<xref:System.IO.IOException> クラス)。</span><span class="sxs-lookup"><span data-stu-id="f06b5-116">The path is read-only (<xref:System.IO.IOException> class).</span></span>  
  
- <span data-ttu-id="f06b5-117">パス名が `Nothing` である場合 (<xref:System.ArgumentNullException> クラス)。</span><span class="sxs-lookup"><span data-stu-id="f06b5-117">The path name is `Nothing` (<xref:System.ArgumentNullException> class).</span></span>  
  
- <span data-ttu-id="f06b5-118">パス名が長すぎる場合 (<xref:System.IO.PathTooLongException> クラス)。</span><span class="sxs-lookup"><span data-stu-id="f06b5-118">The path name is too long (<xref:System.IO.PathTooLongException> class).</span></span>  
  
- <span data-ttu-id="f06b5-119">パスが無効である場合 (<xref:System.IO.DirectoryNotFoundException> クラス)。</span><span class="sxs-lookup"><span data-stu-id="f06b5-119">The path is invalid (<xref:System.IO.DirectoryNotFoundException> class).</span></span>  
  
- <span data-ttu-id="f06b5-120">パスがコロン":" のみである場合 (<xref:System.NotSupportedException> クラス)。</span><span class="sxs-lookup"><span data-stu-id="f06b5-120">The path is only a colon ":" (<xref:System.NotSupportedException> class).</span></span>  
  
## <a name="net-framework-security"></a><span data-ttu-id="f06b5-121">.NET Framework セキュリティ</span><span class="sxs-lookup"><span data-stu-id="f06b5-121">.NET Framework Security</span></span>  
 <span data-ttu-id="f06b5-122">ファイル名からファイルの内容を判断しないでください。</span><span class="sxs-lookup"><span data-stu-id="f06b5-122">Do not make decisions about the contents of the file based on the name of the file.</span></span> <span data-ttu-id="f06b5-123">たとえば、Form1.vb というファイルは Visual Basic のソース ファイルではない可能性もあります。</span><span class="sxs-lookup"><span data-stu-id="f06b5-123">For example, the file Form1.vb may not be a Visual Basic source file.</span></span> <span data-ttu-id="f06b5-124">アプリケーションでデータを使用する前に、入力をすべて検証してください。</span><span class="sxs-lookup"><span data-stu-id="f06b5-124">Verify all inputs before using the data in your application.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f06b5-125">関連項目</span><span class="sxs-lookup"><span data-stu-id="f06b5-125">See also</span></span>

- <xref:System.Media.SoundPlayer.PlayLooping%2A>
- [<span data-ttu-id="f06b5-126">方法: Windows フォームからサウンドを再生する</span><span class="sxs-lookup"><span data-stu-id="f06b5-126">How to: Play a Sound from a Windows Form</span></span>](how-to-play-a-sound-from-a-windows-form.md)
- [<span data-ttu-id="f06b5-127">SoundPlayer クラスの概要</span><span class="sxs-lookup"><span data-stu-id="f06b5-127">SoundPlayer Class Overview</span></span>](soundplayer-class-overview.md)
