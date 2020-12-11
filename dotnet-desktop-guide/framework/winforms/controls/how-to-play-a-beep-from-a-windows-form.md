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
# <a name="how-to-play-a-beep-from-a-windows-form"></a>方法: Windows フォームからビープ音を再生する
実行時にビープ音を再生する例を次に示します。

## <a name="example"></a>例

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
> C# のコードサンプルで再生されるサウンドは、システムのサウンド設定によって決まり <xref:System.Media.SystemSounds.Beep%2A> ます。 詳細については、「<xref:System.Media.SystemSounds>」を参照してください。

## <a name="compiling-the-code"></a>コードのコンパイル
 C# の場合、この例では名前空間への参照が必要です <xref:System.Media?displayProperty=nameWithType> 。

## <a name="see-also"></a>関連項目

- <xref:Microsoft.VisualBasic.Interaction.Beep%2A>
- <xref:System.Media.SoundPlayer>
- [方法: Windows フォームからシステム サウンドを再生する](how-to-play-a-system-sound-from-a-windows-form.md)
- [方法: Windows フォームからサウンドを再生する](how-to-play-a-sound-from-a-windows-form.md)
