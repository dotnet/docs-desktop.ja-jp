---
title: ImeMode プロパティによるアジア言語の文字表示
ms.date: 03/30/2017
helpviewer_keywords:
- Asian languages [Windows Forms], displaying with ImeMode
- Chinese characters [Windows Forms], displaying with ImeMode
- IME mode
- Japanese characters [Windows Forms], displaying with ImeMode
- international applications [Windows Forms], character display
- international characters
- Korean characters
- Asian languages
- Input Method Editor (IME), mode
- localization [Windows Forms], character sets
- globalization [Windows Forms], character sets
ms.assetid: c60ae399-0dab-4f07-9dea-6dbfb15ec0ae
ms.openlocfilehash: 25602e1a878443bd54411dfd6481581abebda5c7
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/09/2020
ms.locfileid: "96974439"
---
# <a name="display-of-asian-characters-with-the-imemode-property"></a>ImeMode プロパティによるアジア言語の文字表示
プロパティは、 <xref:System.Windows.Forms.Control.ImeMode%2A> Input Method Editor (IME) の特定のモードを強制するために、フォームおよびコントロールによって使用されます。 IME は、日本語、中国語、韓国語のスクリプトを記述するために不可欠なコンポーネントです。これらの記述システムには、通常のキーボードではエンコードできない多くの文字があります。 たとえば、特定のテキスト ボックスで ASCII 文字のみを許可したい場合があります。 このような場合は、プロパティをに設定することができ <xref:System.Windows.Forms.Control.ImeMode%2A> <xref:System.Windows.Forms.ImeMode> ます。ユーザーは、そのテキストボックスに ASCII 文字しか入力できません。 プロパティの既定値 <xref:System.Windows.Forms.Control.ImeMode%2A> はである <xref:System.Windows.Forms.ImeMode> ため、フォームのプロパティを設定すると、フォーム上のすべてのコントロールがその設定を継承します。 詳細については、「」および「」を参照してください <xref:System.Windows.Forms.Control.ImeMode%2A> <xref:System.Windows.Forms.ImeMode> 。  
  
## <a name="see-also"></a>関連項目

- [Windows フォームアプリケーションのグローバル化](globalizing-windows-forms.md)
