---
title: '方法: Windows フォームからビープ音を再生する'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- sounds [Windows Forms], beep
- Windows Forms, sounds
- sounds [Windows Forms], playing
- forms [Windows Forms], sounds
- examples [Windows Forms], sounds
ms.assetid: 7ea5cded-4888-4f35-8f28-5cab1a55c973
ms.openlocfilehash: 7fecc5d5b7259b743926713f87d9303596803582
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/09/2020
ms.locfileid: "96980748"
---
# <a name="how-to-play-a-beep-from-a-windows-form"></a><span data-ttu-id="fb551-102">方法: Windows フォームからビープ音を再生する</span><span class="sxs-lookup"><span data-stu-id="fb551-102">How to: Play a Beep from a Windows Form</span></span>
<span data-ttu-id="fb551-103">実行時にビープ音を再生する例を次に示します。</span><span class="sxs-lookup"><span data-stu-id="fb551-103">This example plays a beep at run time.</span></span>

## <a name="example"></a><span data-ttu-id="fb551-104">例</span><span class="sxs-lookup"><span data-stu-id="fb551-104">Example</span></span>

```vb
Public Sub OnePing()
    Beep()
End Sub
```

```csharp
public void onePing()
{
    SystemSounds.Beep.Play();
}
```

> [!NOTE]
> <span data-ttu-id="fb551-105">C# のコードサンプルで再生されるサウンドは、システムのサウンド設定によって決まり <xref:System.Media.SystemSounds.Beep%2A> ます。</span><span class="sxs-lookup"><span data-stu-id="fb551-105">The sound played in the C# code sample is determined by the <xref:System.Media.SystemSounds.Beep%2A> system sound setting.</span></span> <span data-ttu-id="fb551-106">詳細については、「<xref:System.Media.SystemSounds>」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="fb551-106">For more information, see <xref:System.Media.SystemSounds>.</span></span>

## <a name="compiling-the-code"></a><span data-ttu-id="fb551-107">コードのコンパイル</span><span class="sxs-lookup"><span data-stu-id="fb551-107">Compiling the Code</span></span>
 <span data-ttu-id="fb551-108">C# の場合、この例では名前空間への参照が必要です <xref:System.Media?displayProperty=nameWithType> 。</span><span class="sxs-lookup"><span data-stu-id="fb551-108">For C#, this example requires  a reference to the <xref:System.Media?displayProperty=nameWithType> namespace.</span></span>

## <a name="see-also"></a><span data-ttu-id="fb551-109">関連項目</span><span class="sxs-lookup"><span data-stu-id="fb551-109">See also</span></span>

- <xref:Microsoft.VisualBasic.Interaction.Beep%2A>
- <xref:System.Media.SoundPlayer>
- [<span data-ttu-id="fb551-110">方法: Windows フォームからシステム サウンドを再生する</span><span class="sxs-lookup"><span data-stu-id="fb551-110">How to: Play a System Sound from a Windows Form</span></span>](how-to-play-a-system-sound-from-a-windows-form.md)
- [<span data-ttu-id="fb551-111">方法: Windows フォームからサウンドを再生する</span><span class="sxs-lookup"><span data-stu-id="fb551-111">How to: Play a Sound from a Windows Form</span></span>](how-to-play-a-sound-from-a-windows-form.md)
