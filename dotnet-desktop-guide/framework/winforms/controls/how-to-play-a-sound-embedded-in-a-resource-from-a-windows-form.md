---
title: '方法: Windows フォームからリソースに埋め込まれたサウンドを再生する'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- sounds [Windows Forms], playing from resources
- resources [Windows Forms], playing sounds
- playing sounds [Windows Forms], from resources
- SoundPlayer class [Windows Forms], playing sounds from resources
ms.assetid: 7d148bb6-8a1e-47d7-a08d-35828d2e688f
ms.openlocfilehash: 49235f9cb035c5a09c26b427f855fc00e818fe1c
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/09/2020
ms.locfileid: "96974790"
---
# <a name="how-to-play-a-sound-embedded-in-a-resource-from-a-windows-form"></a>方法: Windows フォームからリソースに埋め込まれたサウンドを再生する
クラスを使用して、 <xref:System.Media.SoundPlayer> 埋め込みリソースからサウンドを再生できます。  
  
## <a name="example"></a>例  
 [!code-csharp[System.Windows.Forms.Sound#10](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Sound/CS/soundtestform.cs#10)]
 [!code-vb[System.Windows.Forms.Sound#10](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Sound/VB/soundtestform.vb#10)]  
  
## <a name="compiling-the-code"></a>コードのコンパイル  
 この例で必要な要素は次のとおりです。  
  
 <xref:System.Media?displayProperty=nameWithType>名前空間をインポートしています。  
  
 サウンド ファイルを、埋め込まれたリソースとしてプロジェクトに取り込み。  
  
 "" を、 \<AssemblyName> サウンドファイルが埋め込まれているアセンブリの名前に置き換えます。 ".dll" というサフィックスは含めないでください。  
  
## <a name="see-also"></a>関連項目

- <xref:System.Media.SoundPlayer>
- [方法: Windows フォームからサウンドを再生する](how-to-play-a-sound-from-a-windows-form.md)
- [方法: Windows フォームでサウンドの再生をループする](how-to-loop-a-sound-playing-on-a-windows-form.md)
