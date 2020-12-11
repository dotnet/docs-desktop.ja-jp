---
title: '方法: Windows フォームからサウンドを再生する'
description: 実行時に特定のパスで Windows フォームからサウンドを再生する方法について説明します。 また、コードと .NET セキュリティフレームワークをコンパイルする方法についても説明します。
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- playing sounds [Windows Forms], Windows Forms
- sounds [Windows Forms], playing
- sounds
- My.Computer.Audio object [Windows Forms], playing sounds
- examples [Windows Forms], sounds
ms.assetid: 3d3350b7-1ebd-4e05-a738-48ca1160a19d
ms.openlocfilehash: beb17d994e224f41b2b590ecb1401988cdad314d
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/09/2020
ms.locfileid: "96982844"
---
# <a name="how-to-play-a-sound-from-a-windows-form"></a><span data-ttu-id="e0a26-104">方法: Windows フォームからサウンドを再生する</span><span class="sxs-lookup"><span data-stu-id="e0a26-104">How to: Play a Sound from a Windows Form</span></span>
<span data-ttu-id="e0a26-105">この例では、実行時に指定されたパスでサウンドを再生します。</span><span class="sxs-lookup"><span data-stu-id="e0a26-105">This example plays a sound at a given path at run time.</span></span>

## <a name="example"></a><span data-ttu-id="e0a26-106">例</span><span class="sxs-lookup"><span data-stu-id="e0a26-106">Example</span></span>

```vb
Sub PlaySimpleSound()
    My.Computer.Audio.Play("c:\Windows\Media\chimes.wav")
End Sub
```

```csharp
private void playSimpleSound()
{
    SoundPlayer simpleSound = new SoundPlayer(@"c:\Windows\Media\chimes.wav");
    simpleSound.Play();
}
```

## <a name="compiling-the-code"></a><span data-ttu-id="e0a26-107">コードのコンパイル</span><span class="sxs-lookup"><span data-stu-id="e0a26-107">Compiling the Code</span></span>
 <span data-ttu-id="e0a26-108">この例で必要な要素は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="e0a26-108">This example requires:</span></span>

- <span data-ttu-id="e0a26-109">ファイル名 `"c:\Windows\Media\chimes.wav"` を有効なファイル名に置き換えます。</span><span class="sxs-lookup"><span data-stu-id="e0a26-109">That you replace the file name `"c:\Windows\Media\chimes.wav"` with a valid file name.</span></span>

- <span data-ttu-id="e0a26-110">Visual名前空間への参照 <xref:System.Media?displayProperty=nameWithType> 。</span><span class="sxs-lookup"><span data-stu-id="e0a26-110">(C#) A reference to the <xref:System.Media?displayProperty=nameWithType> namespace.</span></span>

## <a name="robust-programming"></a><span data-ttu-id="e0a26-111">信頼性の高いプログラミング</span><span class="sxs-lookup"><span data-stu-id="e0a26-111">Robust Programming</span></span>
 <span data-ttu-id="e0a26-112">ファイルの操作は、適切な構造の例外処理ブロックで囲む必要があります。</span><span class="sxs-lookup"><span data-stu-id="e0a26-112">File operations should be enclosed within appropriate structured exception handling blocks.</span></span>

 <span data-ttu-id="e0a26-113">次の条件を満たす場合は、例外が発生する可能性があります。</span><span class="sxs-lookup"><span data-stu-id="e0a26-113">The following conditions may cause an exception:</span></span>

- <span data-ttu-id="e0a26-114">パス名が不適切である場合。</span><span class="sxs-lookup"><span data-stu-id="e0a26-114">The path name is malformed.</span></span> <span data-ttu-id="e0a26-115">たとえば、不正な文字が含まれている場合や、空白だけの場合などがその例です (<xref:System.ArgumentException> クラス)。</span><span class="sxs-lookup"><span data-stu-id="e0a26-115">For example, it contains illegal characters or is only white space (<xref:System.ArgumentException> class).</span></span>

- <span data-ttu-id="e0a26-116">パスが読み取り専用である場合 (<xref:System.IO.IOException> クラス)。</span><span class="sxs-lookup"><span data-stu-id="e0a26-116">The path is read-only (<xref:System.IO.IOException> class).</span></span>

- <span data-ttu-id="e0a26-117">パス名が `null` である場合 (<xref:System.ArgumentNullException> クラス)。</span><span class="sxs-lookup"><span data-stu-id="e0a26-117">The path name is `null` (<xref:System.ArgumentNullException> class).</span></span>

- <span data-ttu-id="e0a26-118">パス名が長すぎる場合 (<xref:System.IO.PathTooLongException> クラス)。</span><span class="sxs-lookup"><span data-stu-id="e0a26-118">The path name is too long (<xref:System.IO.PathTooLongException> class).</span></span>

- <span data-ttu-id="e0a26-119">パスが無効である場合 (<xref:System.IO.DirectoryNotFoundException> クラス)。</span><span class="sxs-lookup"><span data-stu-id="e0a26-119">The path is invalid (<xref:System.IO.DirectoryNotFoundException> class).</span></span>

- <span data-ttu-id="e0a26-120">パスはコロン ":" (クラス) にすぎ <xref:System.NotSupportedException> ません。</span><span class="sxs-lookup"><span data-stu-id="e0a26-120">The path is only a colon, ":" (<xref:System.NotSupportedException> class).</span></span>

## <a name="net-framework-security"></a><span data-ttu-id="e0a26-121">.NET Framework セキュリティ</span><span class="sxs-lookup"><span data-stu-id="e0a26-121">.NET Framework Security</span></span>
 <span data-ttu-id="e0a26-122">ファイル名からファイルの内容を判断しないでください。</span><span class="sxs-lookup"><span data-stu-id="e0a26-122">Do not make decisions about the contents of the file based on the name of the file.</span></span> <span data-ttu-id="e0a26-123">たとえば、`Form1.vb` というファイルは Visual Basic のソース ファイルではない可能性もあります。</span><span class="sxs-lookup"><span data-stu-id="e0a26-123">For example, the file `Form1.vb` may not be a Visual Basic source file.</span></span> <span data-ttu-id="e0a26-124">アプリケーションでデータを使用する前に、入力をすべて検証してください。</span><span class="sxs-lookup"><span data-stu-id="e0a26-124">Verify all inputs before using the data in your application.</span></span>

## <a name="see-also"></a><span data-ttu-id="e0a26-125">関連項目</span><span class="sxs-lookup"><span data-stu-id="e0a26-125">See also</span></span>

- <xref:System.Media.SoundPlayer>
- [<span data-ttu-id="e0a26-126">方法: Windows フォーム内でサウンドを非同期的に読み込む</span><span class="sxs-lookup"><span data-stu-id="e0a26-126">How to: Load a Sound Asynchronously within a Windows Form</span></span>](how-to-load-a-sound-asynchronously-within-a-windows-form.md)
