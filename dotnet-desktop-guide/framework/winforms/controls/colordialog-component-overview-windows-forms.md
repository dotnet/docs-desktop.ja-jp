---
title: ColorDialog コンポーネントの概要
ms.date: 03/30/2017
f1_keywords:
- ColorDialog
helpviewer_keywords:
- color dialog box [Windows Forms], about color dialog box
- ColorDialog component [Windows Forms], about ColorDialog
ms.assetid: 6dbdd8f0-f697-4728-bb09-7ea156f6d800
ms.openlocfilehash: 48d9d5072335908f85e65933dadafb1b69f28528
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/09/2020
ms.locfileid: "96974299"
---
# <a name="colordialog-component-overview-windows-forms"></a><span data-ttu-id="2944b-102">ColorDialog コンポーネントの概要 (Windows フォーム)</span><span class="sxs-lookup"><span data-stu-id="2944b-102">ColorDialog Component Overview (Windows Forms)</span></span>
<span data-ttu-id="2944b-103">Windows フォーム <xref:System.Windows.Forms.ColorDialog> コンポーネントは、ユーザーがパレットから色を選択し、そのパレットにカスタムの色を追加できるようにする、事前に構成されたダイアログボックスです。</span><span class="sxs-lookup"><span data-stu-id="2944b-103">The Windows Forms <xref:System.Windows.Forms.ColorDialog> component is a pre-configured dialog box that allows the user to select a color from a palette and to add custom colors to that palette.</span></span> <span data-ttu-id="2944b-104">このダイアログ ボックスは、他の Windows ベースのアプリケーションで表示される色を選択するためのダイアログ ボックスと同じです。</span><span class="sxs-lookup"><span data-stu-id="2944b-104">It is the same dialog box that you see in other Windows-based applications to select colors.</span></span> <span data-ttu-id="2944b-105">このコントロールは、独自のダイアログ ボックスを使用しない簡易ソリューションとして、Windows ベースのアプリケーションの中で使用します。</span><span class="sxs-lookup"><span data-stu-id="2944b-105">Use it within your Windows-based application as a simple solution in lieu of configuring your own dialog box.</span></span>  
  
 <span data-ttu-id="2944b-106">ダイアログボックスで選択した色がプロパティに返され <xref:System.Windows.Forms.ColorDialog.Color%2A> ます。</span><span class="sxs-lookup"><span data-stu-id="2944b-106">The color selected in the dialog box is returned in the <xref:System.Windows.Forms.ColorDialog.Color%2A> property.</span></span> <span data-ttu-id="2944b-107"><xref:System.Windows.Forms.ColorDialog.AllowFullOpen%2A>プロパティがに設定されている場合 `false` 、[カスタム色の定義] ボタンは無効になり、ユーザーはパレットの定義済みの色に制限されます。</span><span class="sxs-lookup"><span data-stu-id="2944b-107">If the <xref:System.Windows.Forms.ColorDialog.AllowFullOpen%2A> property is set to `false`, the "Define Custom Colors" button is disabled and the user is restricted to the predefined colors in the palette.</span></span> <span data-ttu-id="2944b-108"><xref:System.Windows.Forms.ColorDialog.SolidColorOnly%2A>プロパティがに設定されている場合 `true` 、ユーザーはディザーカラーを選択できません。</span><span class="sxs-lookup"><span data-stu-id="2944b-108">If the <xref:System.Windows.Forms.ColorDialog.SolidColorOnly%2A> property is set to `true`, the user cannot select dithered colors.</span></span> <span data-ttu-id="2944b-109">ダイアログボックスを表示するには、メソッドを呼び出す必要があり <xref:System.Windows.Forms.CommonDialog.ShowDialog%2A> ます。</span><span class="sxs-lookup"><span data-stu-id="2944b-109">To display the dialog box, you must call its <xref:System.Windows.Forms.CommonDialog.ShowDialog%2A> method.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2944b-110">関連項目</span><span class="sxs-lookup"><span data-stu-id="2944b-110">See also</span></span>

- <xref:System.Windows.Forms.ColorDialog>
- [<span data-ttu-id="2944b-111">ColorDialog コンポーネント</span><span class="sxs-lookup"><span data-stu-id="2944b-111">ColorDialog Component</span></span>](colordialog-component-windows-forms.md)
- [<span data-ttu-id="2944b-112">ダイアログ ボックス コントロールおよびコンポーネント</span><span class="sxs-lookup"><span data-stu-id="2944b-112">Dialog-Box Controls and Components</span></span>](dialog-box-controls-and-components-windows-forms.md)
- [<span data-ttu-id="2944b-113">方法: Windows フォーム ColorDialog コンポーネントの表示形式を変更する</span><span class="sxs-lookup"><span data-stu-id="2944b-113">How to: Change the Appearance of the Windows Forms ColorDialog Component</span></span>](how-to-change-the-appearance-of-the-windows-forms-colordialog-component.md)
