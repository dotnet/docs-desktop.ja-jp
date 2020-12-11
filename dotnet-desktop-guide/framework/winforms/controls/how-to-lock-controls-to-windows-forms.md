---
title: コントロールをロックする
ms.date: 03/30/2017
helpviewer_keywords:
- Windows Forms controls, locking
- controls [Windows Forms], locking
ms.assetid: 94efe0d2-c14e-4d14-b903-63ea9b07e290
author: jillre
ms.author: jillfra
manager: jillfra
ms.openlocfilehash: 16eb151dc435614e1edc82bf9f0acf3974f36690
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/09/2020
ms.locfileid: "96980760"
---
# <a name="how-to-lock-controls-to-windows-forms"></a><span data-ttu-id="1eeb5-102">方法: Windows フォームにコントロールをロックする</span><span class="sxs-lookup"><span data-stu-id="1eeb5-102">How to: Lock controls to Windows Forms</span></span>

<span data-ttu-id="1eeb5-103">Windows アプリケーションのユーザーインターフェイス (UI) をデザインするときに、コントロールが正しく配置されると、コントロールをロックすることができます。これにより、他のプロパティを設定するときに誤って移動したりサイズを変更したりすることはありません。</span><span class="sxs-lookup"><span data-stu-id="1eeb5-103">When you design the user interface (UI) of your Windows application, you can lock the controls once they are positioned correctly, so that you do not inadvertently move or resize them when setting other properties.</span></span>

<span data-ttu-id="1eeb5-104">また、フォーム上のすべてのコントロールを一度にロックおよびロック解除することもできます。これは、多くのコントロールを持つフォームに便利です。または、個々のコントロールのロックを解除することもできます。</span><span class="sxs-lookup"><span data-stu-id="1eeb5-104">Additionally, you can lock and unlock all the controls on the form at once, which is helpful for forms with many controls, or you can unlock individual controls.</span></span> <span data-ttu-id="1eeb5-105">すべてのコントロールをフォーム上に配置したら、それらをすべて所定の場所にロックして、不適切な移動を防ぐことができます。</span><span class="sxs-lookup"><span data-stu-id="1eeb5-105">Once you have placed all the controls where you want them on the form, lock them all in place to prevent erroneous movement.</span></span>

## <a name="to-lock-a-control"></a><span data-ttu-id="1eeb5-106">コントロールをロックするには</span><span class="sxs-lookup"><span data-stu-id="1eeb5-106">To lock a control</span></span>

<span data-ttu-id="1eeb5-107">Visual Studio の [ **プロパティ** ] ウィンドウで、[ **Locked** ] プロパティを選択し、[ **true**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="1eeb5-107">In the **Properties** window of Visual Studio, select the **Locked** property and then select **true**.</span></span> <span data-ttu-id="1eeb5-108">(名前をダブルクリックすると、プロパティの設定が切り替わります)。</span><span class="sxs-lookup"><span data-stu-id="1eeb5-108">(Double-clicking the name toggles the property setting.)</span></span>

<span data-ttu-id="1eeb5-109">または、コントロールを右クリックし、[ **コントロールのロック**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="1eeb5-109">Alternatively, right-click the control and choose **Lock Controls**.</span></span>

> [!NOTE]
> <span data-ttu-id="1eeb5-110">コントロールをロックすると、デザイン画面上の新しいサイズまたは位置にドラッグできなくなります。</span><span class="sxs-lookup"><span data-stu-id="1eeb5-110">Locking controls prevents them from being dragged to a new size or location on the design surface.</span></span> <span data-ttu-id="1eeb5-111">ただし、コントロールのサイズや位置は、[ **プロパティ** ] ウィンドウまたはコードで変更することもできます。</span><span class="sxs-lookup"><span data-stu-id="1eeb5-111">However, you can still change the size or location of controls by means of the **Properties** window or in code.</span></span>

## <a name="to-lock-all-the-controls-on-a-form"></a><span data-ttu-id="1eeb5-112">フォーム上のすべてのコントロールをロックするには</span><span class="sxs-lookup"><span data-stu-id="1eeb5-112">To lock all the controls on a form</span></span>

<span data-ttu-id="1eeb5-113">[ **書式** ] メニューの [ **コントロールのロック**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="1eeb5-113">From the **Format** menu, choose **Lock Controls**.</span></span>

> [!NOTE]
> <span data-ttu-id="1eeb5-114">フォームがコントロールであるため、このコマンドはフォームのサイズもロックします。</span><span class="sxs-lookup"><span data-stu-id="1eeb5-114">This command locks the form's size as well, because a form is a control.</span></span>

## <a name="to-unlock-all-locked-controls-on-a-form"></a><span data-ttu-id="1eeb5-115">フォーム上のロックされているすべてのコントロールのロックを解除するには</span><span class="sxs-lookup"><span data-stu-id="1eeb5-115">To unlock all locked controls on a form</span></span>

<span data-ttu-id="1eeb5-116">[ **書式** ] メニューの [ **コントロールのロック**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="1eeb5-116">From the **Format** menu, choose **Lock Controls**.</span></span>

<span data-ttu-id="1eeb5-117">フォーム上の以前にロックされていたすべてのコントロールのロックが解除されます。</span><span class="sxs-lookup"><span data-stu-id="1eeb5-117">All previously locked controls on the form are now unlocked.</span></span>

## <a name="to-unlock-locked-controls-individually"></a><span data-ttu-id="1eeb5-118">ロックされたコントロールを個別にロック解除するには</span><span class="sxs-lookup"><span data-stu-id="1eeb5-118">To unlock locked controls individually</span></span>

<span data-ttu-id="1eeb5-119">[ **プロパティ** ] ウィンドウで、[ **Locked** ] プロパティを選択し、[ **false**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="1eeb5-119">In the **Properties** window, select the **Locked** property and then select **false**.</span></span> <span data-ttu-id="1eeb5-120">(名前をダブルクリックすると、プロパティの設定が切り替わります)。</span><span class="sxs-lookup"><span data-stu-id="1eeb5-120">(Double-clicking the name toggles the property setting.)</span></span>

## <a name="see-also"></a><span data-ttu-id="1eeb5-121">関連項目</span><span class="sxs-lookup"><span data-stu-id="1eeb5-121">See also</span></span>

- [<span data-ttu-id="1eeb5-122">Windows フォームコントロール</span><span class="sxs-lookup"><span data-stu-id="1eeb5-122">Windows Forms Controls</span></span>](index.md)
- [<span data-ttu-id="1eeb5-123">各 Windows フォーム コントロールのラベル設定とショートカットの作成</span><span class="sxs-lookup"><span data-stu-id="1eeb5-123">Labeling Individual Windows Forms Controls and Providing Shortcuts to Them</span></span>](labeling-individual-windows-forms-controls-and-providing-shortcuts-to-them.md)
- [<span data-ttu-id="1eeb5-124">Windows フォームで使用するコントロール</span><span class="sxs-lookup"><span data-stu-id="1eeb5-124">Controls to Use on Windows Forms</span></span>](controls-to-use-on-windows-forms.md)
- [<span data-ttu-id="1eeb5-125">Windows フォーム コントロールの機能別一覧</span><span class="sxs-lookup"><span data-stu-id="1eeb5-125">Windows Forms Controls by Function</span></span>](windows-forms-controls-by-function.md)
