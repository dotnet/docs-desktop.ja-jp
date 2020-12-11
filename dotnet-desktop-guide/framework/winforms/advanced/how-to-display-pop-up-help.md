---
title: '方法: ポップアップ ヘルプを表示する'
ms.date: 03/30/2017
helpviewer_keywords:
- pop-up Help
- Help [Windows Forms], pop-up Help
- Windows Forms, displaying Help
- forms [Windows Forms], displaying Help
- modal dialog boxes [Windows Forms], pop-up Help
- F1 Help [Windows Forms], in dialog boxes
- HelpProvider component [Windows Forms]
- Help [Windows Forms], adding to dialog boxes
ms.assetid: 218aa81e-e87e-4d67-af05-11627bbdce3b
ms.openlocfilehash: a3b40f49119fcf7900f1f0c8b77c5d83fe81144c
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/09/2020
ms.locfileid: "96974406"
---
# <a name="how-to-display-pop-up-help"></a><span data-ttu-id="b3157-102">方法: ポップアップヘルプを表示する</span><span class="sxs-lookup"><span data-stu-id="b3157-102">How to: Display pop-up Help</span></span>

<span data-ttu-id="b3157-103">Windows フォームに関するヘルプを表示する方法の1つは、プロパティを使用してアクセスできる、タイトルバーの右側にある [ **ヘルプ** ] ボタンを使用する方法です <xref:System.Windows.Forms.Form.HelpButton%2A> 。</span><span class="sxs-lookup"><span data-stu-id="b3157-103">One way to display Help on Windows Forms is through the **Help** button, located on the right side of the title bar, accessible through the <xref:System.Windows.Forms.Form.HelpButton%2A> property.</span></span> <span data-ttu-id="b3157-104">この種類のヘルプの表示は、ダイアログ ボックスでの使用に適しています。</span><span class="sxs-lookup"><span data-stu-id="b3157-104">This type of Help display is well-suited for use with dialog boxes.</span></span> <span data-ttu-id="b3157-105">モーダル形式で表示されるダイアログ ボックス (<xref:System.Windows.Forms.Form.ShowDialog%2A> メソッドを使用) は、別のウィンドウにフォーカスを移動するときはモーダル ダイアログ ボックスを閉じる必要があるため、外部のヘルプ システムを起動する場合は問題が発生します。</span><span class="sxs-lookup"><span data-stu-id="b3157-105">Dialog boxes shown modally (with the <xref:System.Windows.Forms.Form.ShowDialog%2A> method) have trouble bringing up external Help systems, because modal dialog boxes need to be closed before focus can shift to another window.</span></span> <span data-ttu-id="b3157-106">また、[ **ヘルプ** ] ボタンを使用するには、タイトルバーに [ **最小化** ] ボタンまたは [ **最大化** ] ボタンが表示されないようにする必要があります。</span><span class="sxs-lookup"><span data-stu-id="b3157-106">Additionally, using the **Help** button requires that there is no **Minimize** button or **Maximize** button shown in the title bar.</span></span> <span data-ttu-id="b3157-107">これは標準のダイアログボックスの規則であり、通常、フォームには [ **最小化** ] ボタンと [ **最大化** ] ボタンがあります。</span><span class="sxs-lookup"><span data-stu-id="b3157-107">This is a standard dialog-box convention, whereas forms usually have **Minimize** and **Maximize** buttons.</span></span>

<span data-ttu-id="b3157-108">また、 <xref:System.Windows.Forms.HelpProvider> ポップアップヘルプを実装している場合でも、コンポーネントを使用して、ヘルプシステム内のファイルにコントロールをリンクすることもできます。</span><span class="sxs-lookup"><span data-stu-id="b3157-108">You can also use the <xref:System.Windows.Forms.HelpProvider> component to link controls to files in a Help system, even if you have implemented pop-up Help.</span></span> <span data-ttu-id="b3157-109">詳細については、「 [Windows アプリケーションでのヘルプの提供](how-to-provide-help-in-a-windows-application.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="b3157-109">For more information, see [Providing Help in a Windows Application](how-to-provide-help-in-a-windows-application.md).</span></span>

## <a name="display-pop-up-help"></a><span data-ttu-id="b3157-110">ポップアップヘルプを表示する</span><span class="sxs-lookup"><span data-stu-id="b3157-110">Display pop-up Help</span></span>

1. <span data-ttu-id="b3157-111">Visual Studio で、[ツールボックス] から [HelpProvider](../controls/helpprovider-component-windows-forms.md) コンポーネントをフォームにドラッグします。</span><span class="sxs-lookup"><span data-stu-id="b3157-111">In Visual Studio, drag a [HelpProvider](../controls/helpprovider-component-windows-forms.md) component from the Toolbox to your form.</span></span>

   <span data-ttu-id="b3157-112">これは、Windows フォーム デザイナーの下部にあるトレイ内に配置されます。</span><span class="sxs-lookup"><span data-stu-id="b3157-112">It will sit in the tray at the bottom of the Windows Forms Designer.</span></span>

2. <span data-ttu-id="b3157-113">[プロパティ] ウィンドウで、<xref:System.Windows.Forms.Form.HelpButton%2A> プロパティを `true` に設定します。</span><span class="sxs-lookup"><span data-stu-id="b3157-113">In the Properties window, set the <xref:System.Windows.Forms.Form.HelpButton%2A> property to `true`.</span></span> <span data-ttu-id="b3157-114">これで、フォームのタイトル バーの右側に疑問符の付いたボタンが表示されます。</span><span class="sxs-lookup"><span data-stu-id="b3157-114">This will display a button with a question mark in it on the right side of the title bar of the form.</span></span>

3. <span data-ttu-id="b3157-115"><xref:System.Windows.Forms.Form.HelpButton%2A> が表示されるには、フォームの <xref:System.Windows.Forms.Form.MinimizeBox%2A> プロパティと <xref:System.Windows.Forms.Form.MaximizeBox%2A> プロパティを `false` に設定し、<xref:System.Windows.Forms.Form.ControlBox%2A> プロパティを `true` に設定し、<xref:System.Windows.Forms.Form.FormBorderStyle%2A> プロパティを<xref:System.Windows.Forms.FormBorderStyle.FixedSingle>、<xref:System.Windows.Forms.FormBorderStyle.Fixed3D>、<xref:System.Windows.Forms.FormBorderStyle.FixedDialog>、または <xref:System.Windows.Forms.FormBorderStyle.Sizable> のいずれかの値に設定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="b3157-115">In order for the <xref:System.Windows.Forms.Form.HelpButton%2A> to display, the form's <xref:System.Windows.Forms.Form.MinimizeBox%2A> and <xref:System.Windows.Forms.Form.MaximizeBox%2A> properties must be set to `false`, the <xref:System.Windows.Forms.Form.ControlBox%2A> property set to `true`, and the <xref:System.Windows.Forms.Form.FormBorderStyle%2A> property to one of the following values: <xref:System.Windows.Forms.FormBorderStyle.FixedSingle>, <xref:System.Windows.Forms.FormBorderStyle.Fixed3D>, <xref:System.Windows.Forms.FormBorderStyle.FixedDialog> or <xref:System.Windows.Forms.FormBorderStyle.Sizable>.</span></span>

4. <span data-ttu-id="b3157-116">フォーム上のヘルプを表示し、[プロパティ] ウィンドウのヘルプの文字列を設定するコントロールを選択します。</span><span class="sxs-lookup"><span data-stu-id="b3157-116">Select the control for which you want to show help on your form and set the Help string in the Properties window.</span></span> <span data-ttu-id="b3157-117">これは、 [ツールヒント](../controls/tooltip-component-windows-forms.md)のようなウィンドウに表示されるテキストの文字列です。</span><span class="sxs-lookup"><span data-stu-id="b3157-117">This is the string of text that will be displayed in a window similar to a [ToolTip](../controls/tooltip-component-windows-forms.md).</span></span>

5. <span data-ttu-id="b3157-118">**F5** キーを押します。</span><span class="sxs-lookup"><span data-stu-id="b3157-118">Press **F5**.</span></span>

6. <span data-ttu-id="b3157-119">タイトルバーの [ **ヘルプ** ] ボタンをクリックし、ヘルプ文字列を設定したコントロールをクリックします。</span><span class="sxs-lookup"><span data-stu-id="b3157-119">Press the **Help** button on the title bar and click the control on which you set the Help string.</span></span>

## <a name="see-also"></a><span data-ttu-id="b3157-120">関連項目</span><span class="sxs-lookup"><span data-stu-id="b3157-120">See also</span></span>

- [<span data-ttu-id="b3157-121">ツールヒントを使用したコントロールのヘルプ</span><span class="sxs-lookup"><span data-stu-id="b3157-121">Control Help Using ToolTips</span></span>](control-help-using-tooltips.md)
- [<span data-ttu-id="b3157-122">Windows フォームでのヘルプの統合</span><span class="sxs-lookup"><span data-stu-id="b3157-122">Integrating User Help in Windows Forms</span></span>](integrating-user-help-in-windows-forms.md)
- [<span data-ttu-id="b3157-123">Windows フォーム</span><span class="sxs-lookup"><span data-stu-id="b3157-123">Windows Forms</span></span>](../index.yml)
