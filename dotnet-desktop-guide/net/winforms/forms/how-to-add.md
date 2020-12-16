---
title: フォームをプロジェクトに追加する
description: Visual Studio で .NET Windows フォーム プロジェクトに新しいフォームを追加する
ms.date: 10/26/2020
helpviewer_keywords:
- Windows Forms, create add form
ms.openlocfilehash: fb35c1b62ca0b7a21581c350ddca7f21f45ec27f
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/09/2020
ms.locfileid: "96942263"
---
# <a name="how-to-add-a-form-to-a-project-windows-forms-net"></a><span data-ttu-id="b97cc-103">プロジェクトにフォームを追加する方法 (Windows フォーム .NET)</span><span class="sxs-lookup"><span data-stu-id="b97cc-103">How to add a form to a project (Windows Forms .NET)</span></span>

<span data-ttu-id="b97cc-104">Visual Studio でプロジェクトにフォームを追加します。</span><span class="sxs-lookup"><span data-stu-id="b97cc-104">Add forms to your project with Visual Studio.</span></span> <span data-ttu-id="b97cc-105">自分のアプリに複数のフォームがある場合は、自分のアプリのスタートアップ フォームを選択し、複数のフォームを同時に表示することができます。</span><span class="sxs-lookup"><span data-stu-id="b97cc-105">When your app has multiple forms, you can choose which is the startup form for your app, and you can display multiple forms at the same time.</span></span>

[!INCLUDE [desktop guide under construction](../../includes/desktop-guide-preview-note.md)]

## <a name="add-a-new-form"></a><span data-ttu-id="b97cc-106">新しいフォームを追加する</span><span class="sxs-lookup"><span data-stu-id="b97cc-106">Add a new form</span></span>

<span data-ttu-id="b97cc-107">Visual Studio で新しいフォームを追加します。</span><span class="sxs-lookup"><span data-stu-id="b97cc-107">Add a new form with Visual Studio.</span></span>

01. <span data-ttu-id="b97cc-108">Visual Studio で **[プロジェクト エクスプローラー]** ウィンドウを見つけます。</span><span class="sxs-lookup"><span data-stu-id="b97cc-108">In Visual Studio, find the **Project Explorer** pane.</span></span> <span data-ttu-id="b97cc-109">プロジェクトを右クリックして、 **[追加]**  >  **[Form (Windows Forms)]\(フォーム (Windows フォーム)\)** を選択します。</span><span class="sxs-lookup"><span data-stu-id="b97cc-109">Right-click on the project and choose **Add** > **Form (Windows Forms)**.</span></span>

    :::image type="content" source="media/how-to-add/right-click.png" alt-text="ソリューション エクスプローラーを右クリックして、Windows フォーム プロジェクトに新しいフォームを追加する":::

01. <span data-ttu-id="b97cc-111">**[名前]** ボックスに、「*MyNewForm*」など、自分のフォームの名前を入力します。</span><span class="sxs-lookup"><span data-stu-id="b97cc-111">In the **Name** box, type a name for your form, such as *MyNewForm*.</span></span> <span data-ttu-id="b97cc-112">Visual Studio では、使用可能な既定の一意の名前が用意されています。</span><span class="sxs-lookup"><span data-stu-id="b97cc-112">Visual Studio will provide a default and unique name that you may use.</span></span>

    :::image type="content" source="media/how-to-add/new-form-dialog.png" alt-text="Visual Studio の Windows フォーム用の項目の追加ダイアログ":::

<span data-ttu-id="b97cc-114">フォームを追加すると、Visual Studio によってそのフォーム用のフォーム デザイナーが開かれます。</span><span class="sxs-lookup"><span data-stu-id="b97cc-114">Once the form has been added, Visual Studio opens the form designer for the form.</span></span>

## <a name="add-a-project-reference-to-a-form"></a><span data-ttu-id="b97cc-115">フォームにプロジェクト参照を追加する</span><span class="sxs-lookup"><span data-stu-id="b97cc-115">Add a project reference to a form</span></span>

<span data-ttu-id="b97cc-116">フォームにソース ファイルがある場合は、プロジェクトと同じフォルダーにそれらのファイルをコピーし、プロジェクトにフォームを追加できます。</span><span class="sxs-lookup"><span data-stu-id="b97cc-116">If you have the source files to a form, you can add the form to your project by copying the files into the same folder as your project.</span></span> <span data-ttu-id="b97cc-117">プロジェクトは、プロジェクトと同じフォルダーまたは子フォルダーにあるすべてのコード ファイルを自動的に参照します。</span><span class="sxs-lookup"><span data-stu-id="b97cc-117">The project automatically references any code files that are in the same folder or child folder of your project.</span></span>

<span data-ttu-id="b97cc-118">フォームは、_form2.cs_ (_form2_ はファイル名の例です) と _form2.Designer.cs_ の同じ名前の 2 つのファイルで構成されています。</span><span class="sxs-lookup"><span data-stu-id="b97cc-118">Forms are made up of two files that share the same name: _form2.cs_ (_form2_ being an example of a file name) and _form2.Designer.cs_.</span></span> <span data-ttu-id="b97cc-119">同じ名前の (_form2.resx_) リソース ファイルが存在する場合もあります。</span><span class="sxs-lookup"><span data-stu-id="b97cc-119">Sometimes a resource file exists, sharing the same name, _form2.resx_.</span></span> <span data-ttu-id="b97cc-120">前の例の _form2_ は、ベースのファイル名です。</span><span class="sxs-lookup"><span data-stu-id="b97cc-120">In in the previous example, _form2_ represents the base file name.</span></span> <span data-ttu-id="b97cc-121">すべての関連ファイルをプロジェクト フォルダーにコピーします。</span><span class="sxs-lookup"><span data-stu-id="b97cc-121">You'll want to copy all related files to your project folder.</span></span>

<span data-ttu-id="b97cc-122">または、Visual Studio を使用して、プロジェクトにファイルをインポートします。</span><span class="sxs-lookup"><span data-stu-id="b97cc-122">Alternatively, you can use Visual Studio to import a file into your project.</span></span> <span data-ttu-id="b97cc-123">既存のファイルをプロジェクトに追加すると、ファイルはプロジェクトと同じフォルダーにコピーされます。</span><span class="sxs-lookup"><span data-stu-id="b97cc-123">When you add an existing file to your project, the file is copied into the same folder as your project.</span></span>

01. <span data-ttu-id="b97cc-124">Visual Studio で **[プロジェクト エクスプローラー]** ウィンドウを見つけます。</span><span class="sxs-lookup"><span data-stu-id="b97cc-124">In Visual Studio, find the **Project Explorer** pane.</span></span> <span data-ttu-id="b97cc-125">プロジェクトを右クリックして、 **[編集]**  >  **[既存の項目]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="b97cc-125">Right-click on the project and choose **Add** > **Existing Item**.</span></span>

    :::image type="content" source="media/how-to-add/existing-right-click.png" alt-text="ソリューション エクスプローラーを右クリックして、Windows フォーム プロジェクトに既存のフォームを追加する":::

02. <span data-ttu-id="b97cc-127">自分のフォーム ファイルを含むフォルダーに移動します。</span><span class="sxs-lookup"><span data-stu-id="b97cc-127">Navigate to the folder containing your form files.</span></span>

03. <span data-ttu-id="b97cc-128">_form2.cs_ ファイルを選択します。ここで _form2_ は、関連するフォーム ファイルのベース ファイル名です。</span><span class="sxs-lookup"><span data-stu-id="b97cc-128">Select the _form2.cs_ file, where _form2_ is the base file name of the related form files.</span></span> <span data-ttu-id="b97cc-129">_form2.Designer.cs_ などのその他のファイルは選択しないでください。</span><span class="sxs-lookup"><span data-stu-id="b97cc-129">Don't select the other files, such as _form2.Designer.cs_.</span></span>

## <a name="see-also"></a><span data-ttu-id="b97cc-130">関連項目</span><span class="sxs-lookup"><span data-stu-id="b97cc-130">See also</span></span>

- [<span data-ttu-id="b97cc-131">フォームの位置とサイズを設定する方法 (Windows フォーム .NET)</span><span class="sxs-lookup"><span data-stu-id="b97cc-131">How to position and size a form (Windows Forms .NET)</span></span>](how-to-position-and-resize.md)
- [<span data-ttu-id="b97cc-132">イベントの概要 (Windows フォーム .NET)</span><span class="sxs-lookup"><span data-stu-id="b97cc-132">Events overview (Windows Forms .NET)</span></span>](events.md)
- [<span data-ttu-id="b97cc-133">コントロールの位置とレイアウト (Windows フォーム .NET)</span><span class="sxs-lookup"><span data-stu-id="b97cc-133">Position and layout of controls (Windows Forms .NET)</span></span>](../controls/layout.md)
