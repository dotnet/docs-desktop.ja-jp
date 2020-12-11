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
# <a name="how-to-use-special-characters-in-xaml"></a>方法: XAML で特殊文字を使用する
マークアップ ファイルを Visual Studio で作成すると、自動的に Unicode UTF-8 ファイル形式で保存されます。つまり、アクセント記号など、ほとんどの特殊文字が正しくエンコードされます。 ただし、一般的に使用される一連の特殊文字で、別の方法で処理されるものがあります。 これらの特殊文字は、 [W3C (World Wide Web コンソーシアム) の XML 標準](https://www.w3resource.com/xml/reserved-markup-characters.php)に準拠してエンコードされます。

この一連の特殊文字をエンコードするための構文を次の表に示します。

| 文字 | 構文   | 説明          |
|-----------|----------|----------------------|
| `<`       | `&lt;`   | より小さい記号    |
| `>`       | `&gt;`   | より大きい記号   |
| `&`       | `&amp;`  | アンパサンド記号    |
| `"`       | `&quot;` | 二重引用符記号 |
| `'`       | `&apos;` | 一重引用符記号。 |

> [!NOTE]
> Windows メモ帳などのテキスト エディターを使用してマークアップ ファイルを作成する場合は、エンコードされた特殊文字を保持するために、ファイルを Unicode UTF-8 ファイル形式で保存する必要があります。

次の例では、マークアップを作成するときにテキストで特殊文字を使用する方法を示します。

## <a name="example"></a>例

[!code-xaml[SpecialCharsSnippets#SpecialCharsSnippet1](~/samples/snippets/csharp/VS_Snippets_Wpf/SpecialCharsSnippets/CS/Window1.xaml#specialcharssnippet1)]
