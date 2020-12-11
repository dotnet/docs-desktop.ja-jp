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
# <a name="display-of-asian-characters-with-the-imemode-property"></a><span data-ttu-id="4db94-102">ImeMode プロパティによるアジア言語の文字表示</span><span class="sxs-lookup"><span data-stu-id="4db94-102">Display of Asian Characters with the ImeMode Property</span></span>
<span data-ttu-id="4db94-103">プロパティは、 <xref:System.Windows.Forms.Control.ImeMode%2A> Input Method Editor (IME) の特定のモードを強制するために、フォームおよびコントロールによって使用されます。</span><span class="sxs-lookup"><span data-stu-id="4db94-103">The <xref:System.Windows.Forms.Control.ImeMode%2A> property is used by forms and controls to force a specific mode for an input method editor (IME).</span></span> <span data-ttu-id="4db94-104">IME は、日本語、中国語、韓国語のスクリプトを記述するために不可欠なコンポーネントです。これらの記述システムには、通常のキーボードではエンコードできない多くの文字があります。</span><span class="sxs-lookup"><span data-stu-id="4db94-104">The IME is an essential component for writing Chinese, Japanese, and Korean scripts, since these writing systems have more characters than can be encoded for a regular keyboard.</span></span> <span data-ttu-id="4db94-105">たとえば、特定のテキスト ボックスで ASCII 文字のみを許可したい場合があります。</span><span class="sxs-lookup"><span data-stu-id="4db94-105">For example, you may want to allow only ASCII characters in a particular text box.</span></span> <span data-ttu-id="4db94-106">このような場合は、プロパティをに設定することができ <xref:System.Windows.Forms.Control.ImeMode%2A> <xref:System.Windows.Forms.ImeMode> ます。ユーザーは、そのテキストボックスに ASCII 文字しか入力できません。</span><span class="sxs-lookup"><span data-stu-id="4db94-106">In such a case you can set the <xref:System.Windows.Forms.Control.ImeMode%2A> property to <xref:System.Windows.Forms.ImeMode> and users will only be able to enter ASCII characters for that particular text box.</span></span> <span data-ttu-id="4db94-107">プロパティの既定値 <xref:System.Windows.Forms.Control.ImeMode%2A> はである <xref:System.Windows.Forms.ImeMode> ため、フォームのプロパティを設定すると、フォーム上のすべてのコントロールがその設定を継承します。</span><span class="sxs-lookup"><span data-stu-id="4db94-107">The default value of the <xref:System.Windows.Forms.Control.ImeMode%2A> property is <xref:System.Windows.Forms.ImeMode>, so if you set the property for a form, all controls on the form will inherit that setting.</span></span> <span data-ttu-id="4db94-108">詳細については、「」および「」を参照してください <xref:System.Windows.Forms.Control.ImeMode%2A> <xref:System.Windows.Forms.ImeMode> 。</span><span class="sxs-lookup"><span data-stu-id="4db94-108">For more information, see <xref:System.Windows.Forms.Control.ImeMode%2A> ) and <xref:System.Windows.Forms.ImeMode>.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4db94-109">関連項目</span><span class="sxs-lookup"><span data-stu-id="4db94-109">See also</span></span>

- [<span data-ttu-id="4db94-110">Windows フォームアプリケーションのグローバル化</span><span class="sxs-lookup"><span data-stu-id="4db94-110">Globalizing Windows Forms applications</span></span>](globalizing-windows-forms.md)
