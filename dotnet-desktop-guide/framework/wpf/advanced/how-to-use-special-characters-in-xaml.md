---
title: '方法: XAML で特殊文字を使用する'
description: Windows Presentation Foundation の XAML ファイルで使用するために、Visual Studio の Unicode UTF-8 ファイル形式で特殊文字をエンコードするための構文について説明します。
ms.date: 03/30/2017
helpviewer_keywords:
- Unicode UTF-8 file format
- UTF-8 file format
- characters [WPF], special
- typography [WPF], special characters
- special characters [WPF]
ms.assetid: a57776d1-f353-4794-afa0-bfa3c712ed1c
ms.openlocfilehash: b627f7ee1d6ab80d5d1cd14de0339a1afad3ec62
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/09/2020
ms.locfileid: "96985195"
---
# <a name="how-to-use-special-characters-in-xaml"></a><span data-ttu-id="43baa-103">方法: XAML で特殊文字を使用する</span><span class="sxs-lookup"><span data-stu-id="43baa-103">How to: Use Special Characters in XAML</span></span>
<span data-ttu-id="43baa-104">マークアップ ファイルを Visual Studio で作成すると、自動的に Unicode UTF-8 ファイル形式で保存されます。つまり、アクセント記号など、ほとんどの特殊文字が正しくエンコードされます。</span><span class="sxs-lookup"><span data-stu-id="43baa-104">Markup files that are created in Visual Studio are automatically saved in the Unicode UTF-8 file format, which means that most special characters, such as accent marks, are encoded correctly.</span></span> <span data-ttu-id="43baa-105">ただし、一般的に使用される一連の特殊文字で、別の方法で処理されるものがあります。</span><span class="sxs-lookup"><span data-stu-id="43baa-105">However, there is a set of commonly-used special characters that are handled differently.</span></span> <span data-ttu-id="43baa-106">これらの特殊文字は、 [W3C (World Wide Web コンソーシアム) の XML 標準](https://www.w3resource.com/xml/reserved-markup-characters.php)に準拠してエンコードされます。</span><span class="sxs-lookup"><span data-stu-id="43baa-106">These special characters follow the World [Wide Web Consortium (W3C) XML standard for encoding](https://www.w3resource.com/xml/reserved-markup-characters.php).</span></span>

<span data-ttu-id="43baa-107">この一連の特殊文字をエンコードするための構文を次の表に示します。</span><span class="sxs-lookup"><span data-stu-id="43baa-107">The following table shows the syntax for encoding this set of special characters:</span></span>

| <span data-ttu-id="43baa-108">文字</span><span class="sxs-lookup"><span data-stu-id="43baa-108">Character</span></span> | <span data-ttu-id="43baa-109">構文</span><span class="sxs-lookup"><span data-stu-id="43baa-109">Syntax</span></span>   | <span data-ttu-id="43baa-110">説明</span><span class="sxs-lookup"><span data-stu-id="43baa-110">Description</span></span>          |
|-----------|----------|----------------------|
| `<`       | `&lt;`   | <span data-ttu-id="43baa-111">より小さい記号</span><span class="sxs-lookup"><span data-stu-id="43baa-111">Less than symbol.</span></span>    |
| `>`       | `&gt;`   | <span data-ttu-id="43baa-112">より大きい記号</span><span class="sxs-lookup"><span data-stu-id="43baa-112">Greater than sign.</span></span>   |
| `&`       | `&amp;`  | <span data-ttu-id="43baa-113">アンパサンド記号</span><span class="sxs-lookup"><span data-stu-id="43baa-113">Ampersand symbol.</span></span>    |
| `"`       | `&quot;` | <span data-ttu-id="43baa-114">二重引用符記号</span><span class="sxs-lookup"><span data-stu-id="43baa-114">Double quote symbol.</span></span> |
| `'`       | `&apos;` | <span data-ttu-id="43baa-115">一重引用符記号。</span><span class="sxs-lookup"><span data-stu-id="43baa-115">Single quote symbol.</span></span> |

> [!NOTE]
> <span data-ttu-id="43baa-116">Windows メモ帳などのテキスト エディターを使用してマークアップ ファイルを作成する場合は、エンコードされた特殊文字を保持するために、ファイルを Unicode UTF-8 ファイル形式で保存する必要があります。</span><span class="sxs-lookup"><span data-stu-id="43baa-116">If you create a markup file using a text editor, such as Windows Notepad, you must save the file in the Unicode UTF-8 file format in order to preserve any encoded special characters.</span></span>

<span data-ttu-id="43baa-117">次の例では、マークアップを作成するときにテキストで特殊文字を使用する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="43baa-117">The following example shows how you can use special characters in text when creating markup.</span></span>

## <a name="example"></a><span data-ttu-id="43baa-118">例</span><span class="sxs-lookup"><span data-stu-id="43baa-118">Example</span></span>

[!code-xaml[SpecialCharsSnippets#SpecialCharsSnippet1](~/samples/snippets/csharp/VS_Snippets_Wpf/SpecialCharsSnippets/CS/Window1.xaml#specialcharssnippet1)]
