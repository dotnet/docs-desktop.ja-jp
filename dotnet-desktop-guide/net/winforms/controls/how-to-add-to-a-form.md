---
title: フォームにコントロールを追加する
description: .NET 用の Windows フォームでコントロールをフォームに追加する方法について説明します
ms.date: 10/26/2020
dev_langs:
- csharp
- vb
helpviewer_keywords:
- Windows Forms controls, adding to form
- controls [Windows Forms], adding
ms.openlocfilehash: 44a20f135eb0f1503a6e5204a33aa8dca092123f
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/09/2020
ms.locfileid: "96942287"
---
# <a name="add-a-control-windows-forms-net"></a><span data-ttu-id="86f0f-103">コントロールを追加する (Windows フォーム .NET)</span><span class="sxs-lookup"><span data-stu-id="86f0f-103">Add a control (Windows Forms .NET)</span></span>

<span data-ttu-id="86f0f-104">ほとんどのフォームは、ユーザー インターフェイス (UI) を定義するために、フォームのサーフェイスにコントロールを追加して設計されます。</span><span class="sxs-lookup"><span data-stu-id="86f0f-104">Most forms are designed by adding controls to the surface of the form to define a user interface (UI).</span></span> <span data-ttu-id="86f0f-105">"*コントロール*" は、情報の表示やユーザー入力の受け入れに使用される、フォーム上のコンポーネントです。</span><span class="sxs-lookup"><span data-stu-id="86f0f-105">A *control* is a component on a form used to display information or accept user input.</span></span><!-- TODO For more information about controls, see [Forms overview](..\forms\overview.md). -->

<span data-ttu-id="86f0f-106">コントロールをフォームに追加する主な方法としては、Visual Studio デザイナーを使用しますが、実行時にコードを使用して、フォーム上のコントロールを管理することもできます。</span><span class="sxs-lookup"><span data-stu-id="86f0f-106">The primary way a control is added to a form is through the Visual Studio Designer, but you can also manage the controls on a form at run time through code.</span></span>

[!INCLUDE [desktop guide under construction](../../includes/desktop-guide-preview-note.md)]

## <a name="add-with-designer"></a><span data-ttu-id="86f0f-107">デザイナーを使用して追加する</span><span class="sxs-lookup"><span data-stu-id="86f0f-107">Add with Designer</span></span>

<span data-ttu-id="86f0f-108">Visual Studio でフォームをデザインするには、フォーム デザイナーを使用します。</span><span class="sxs-lookup"><span data-stu-id="86f0f-108">Visual Studio uses the Forms Designer to design forms.</span></span> <span data-ttu-id="86f0f-109">[コントロール] ウィンドウが表示され、アプリで使用できるすべてのコントロールが一覧表示されます。</span><span class="sxs-lookup"><span data-stu-id="86f0f-109">There is a Controls pane which lists all the controls available to your app.</span></span> <span data-ttu-id="86f0f-110">このウィンドウからコントロールを追加するには、2 つの方法があります。</span><span class="sxs-lookup"><span data-stu-id="86f0f-110">You can add controls from the pane in two ways:</span></span>

### <a name="add-the-control-by-double-clicking"></a><span data-ttu-id="86f0f-111">ダブルクリックしてコントロールを追加する</span><span class="sxs-lookup"><span data-stu-id="86f0f-111">Add the control by double-clicking</span></span>

<span data-ttu-id="86f0f-112">コントロールをダブルクリックすると、既定の設定で、現在開いているフォームに自動的に追加されます。</span><span class="sxs-lookup"><span data-stu-id="86f0f-112">When a control is double-clicked, it is automatically added to the current open form with default settings.</span></span>

:::image type="content" source="media/how-to-add-to-a-form/toolbox-double-click.gif" alt-text="Visual Studio for .NET の Windows フォームのツールボックスでコントロールをダブルクリックします":::

### <a name="add-the-control-by-drawing"></a><span data-ttu-id="86f0f-114">描画によってコントロールを追加する</span><span class="sxs-lookup"><span data-stu-id="86f0f-114">Add the control by drawing</span></span>

<span data-ttu-id="86f0f-115">コントロールをクリックして選択します。</span><span class="sxs-lookup"><span data-stu-id="86f0f-115">Select the control by clicking on it.</span></span> <span data-ttu-id="86f0f-116">フォームで領域をドラッグして選択します。</span><span class="sxs-lookup"><span data-stu-id="86f0f-116">In your form, drag-select a region.</span></span> <span data-ttu-id="86f0f-117">コントロールは、選択した領域のサイズに合わせて配置されます。</span><span class="sxs-lookup"><span data-stu-id="86f0f-117">The control will be placed to fit the size of the region you selected.</span></span>

:::image type="content" source="media/how-to-add-to-a-form/toolbox-drag-draw.gif" alt-text="Visual Studio for .NET の Windows フォームのツールボックスからコントロールをドラッグして選択して、描画します":::

## <a name="add-with-code"></a><span data-ttu-id="86f0f-119">コードを使用して追加する</span><span class="sxs-lookup"><span data-stu-id="86f0f-119">Add with code</span></span>

<span data-ttu-id="86f0f-120">フォームの <xref:System.Windows.Forms.Control.Controls%2A> コレクションを使用して、コントロールを作成し、実行時にフォームに追加することができます。</span><span class="sxs-lookup"><span data-stu-id="86f0f-120">Controls can be created and then added to a form at run time with the form's <xref:System.Windows.Forms.Control.Controls%2A> collection.</span></span> <span data-ttu-id="86f0f-121">また、このコレクションを使用して、フォームからコントロールを削除することもできます。</span><span class="sxs-lookup"><span data-stu-id="86f0f-121">This collection can also be used to remove controls from a form.</span></span>

<span data-ttu-id="86f0f-122">次のコードでは、[Label](xref:System.Windows.Forms.Label) と [TextBox](xref:System.Windows.Forms.TextBox) という 2 つのコントロールを追加して配置します。</span><span class="sxs-lookup"><span data-stu-id="86f0f-122">The following code adds and positions two controls, a [Label](xref:System.Windows.Forms.Label) and a [TextBox](xref:System.Windows.Forms.TextBox):</span></span>

:::code language="csharp" source="snippets/how-to-add-to-a-form/cs/Form1.cs" id="CreateControl":::

:::code language="vb" source="snippets/how-to-add-to-a-form/vb/Form1.vb" id="CreateControl":::

## <a name="see-also"></a><span data-ttu-id="86f0f-123">関連項目</span><span class="sxs-lookup"><span data-stu-id="86f0f-123">See also</span></span>

- [<span data-ttu-id="86f0f-124">方法 : Windows フォーム コントロールによって表示されるテキストを設定する</span><span class="sxs-lookup"><span data-stu-id="86f0f-124">How to: Set the Text Displayed by a Windows Forms Control</span></span>](how-to-set-the-display-text.md)
- [<span data-ttu-id="86f0f-125">方法: コントロールにアクセス キーのショートカットを追加する</span><span class="sxs-lookup"><span data-stu-id="86f0f-125">How to: Add an access key shortcut to a control</span></span>](how-to-create-access-keys.md)
- <xref:System.Windows.Forms.Label>
- <xref:System.Windows.Forms.TextBox>
- <xref:System.Windows.Forms.Button>
