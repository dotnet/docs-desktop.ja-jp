---
title: 基本フォームの外観を変更した場合の影響
ms.date: 03/30/2017
helpviewer_keywords:
- parent forms [Windows Forms]
- inherited forms [Windows Forms], modifications to base form
- Windows Forms, base form appearance
- base forms
- inheritance [Windows Forms], forms
ms.assetid: 1c3f2b29-a05c-4c6f-aa1a-4e66b94f343a
ms.openlocfilehash: 1eda19f754d0b8d446ac9190b432ff0b6106847b
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/09/2020
ms.locfileid: "96975029"
---
# <a name="effects-of-modifying-a-base-forms-appearance"></a><span data-ttu-id="ab205-102">基本フォームの外観を変更した場合の影響</span><span class="sxs-lookup"><span data-stu-id="ab205-102">Effects of modifying a base form's appearance</span></span>

<span data-ttu-id="ab205-103">アプリケーションの開発中に、同じプロジェクト (または他のプロジェクト) 内の他のフォームの継承元となる、基本フォームの外観の変更が必要になることがよくあります。</span><span class="sxs-lookup"><span data-stu-id="ab205-103">During application development, you may often need to change the appearance of the base form from which other forms in the project (or in other projects) are inheriting.</span></span>

<span data-ttu-id="ab205-104">デザイン時にプロパティの設定の変更やコントロールの追加または削除によって基本フォームの外観を変更した場合、基本フォームを含むプロジェクトをビルドしたときに、継承されたフォームに変更が反映されます。</span><span class="sxs-lookup"><span data-stu-id="ab205-104">At design time, changes to the base form's appearance (be it the setting of properties or the addition and subtraction of controls) are reflected on inherited forms when the project containing the base form is built.</span></span> <span data-ttu-id="ab205-105">基本フォームの変更を保存するだけでは、変更は反映されません。</span><span class="sxs-lookup"><span data-stu-id="ab205-105">It is not sufficient for you to simply save the changes to the base form.</span></span> <span data-ttu-id="ab205-106">プロジェクトをビルドするには、**[ビルド]** メニューの **[ビルド]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="ab205-106">To build a project, choose **Build** from the **Build** menu.</span></span>

<span data-ttu-id="ab205-107">実行時に基本フォームに変更を加えても、既にインスタンス化されている継承されたフォームには反映されません。</span><span class="sxs-lookup"><span data-stu-id="ab205-107">Modifications made to the base form at run time have no affect on inherited forms that are already instantiated.</span></span>

## <a name="see-also"></a><span data-ttu-id="ab205-108">関連項目</span><span class="sxs-lookup"><span data-stu-id="ab205-108">See also</span></span>

- [<span data-ttu-id="ab205-109">base</span><span class="sxs-lookup"><span data-stu-id="ab205-109">base</span></span>](/dotnet/csharp/language-reference/keywords/base)
- [<span data-ttu-id="ab205-110">方法: Windows フォームを継承する</span><span class="sxs-lookup"><span data-stu-id="ab205-110">How to: Inherit Windows Forms</span></span>](how-to-inherit-windows-forms.md)
- [<span data-ttu-id="ab205-111">Windows フォームのビジュアルの継承</span><span class="sxs-lookup"><span data-stu-id="ab205-111">Windows Forms Visual Inheritance</span></span>](windows-forms-visual-inheritance.md)
