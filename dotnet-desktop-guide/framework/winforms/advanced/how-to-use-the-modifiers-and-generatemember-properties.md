---
title: '方法: Modifiers プロパティおよび GenerateMember プロパティを使用する'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
f1_keywords:
- Designer_GenerateMember
- Designer_Modifiers
helpviewer_keywords:
- base forms
- inheritance [Windows Forms], forms
- inherited forms [Windows Forms], Windows Forms
- inherited forms
- form inheritance
- Windows Forms, inheritance
ms.assetid: 3381a5e4-e1a3-44e2-a765-a0b758937b85
ms.openlocfilehash: 3fbaaae53aa60f6356c3a8daa0513de86ef2dacb
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/09/2020
ms.locfileid: "96981224"
---
# <a name="how-to-use-the-modifiers-and-generatemember-properties"></a><span data-ttu-id="e221b-102">方法: Modifiers プロパティおよび GenerateMember プロパティを使用する</span><span class="sxs-lookup"><span data-stu-id="e221b-102">How to: Use the Modifiers and GenerateMember Properties</span></span>

<span data-ttu-id="e221b-103">コンポーネントを Windows フォームに配置すると、デザイン環境によって、との2つのプロパティが提供されます。 `GenerateMember` `Modifiers`</span><span class="sxs-lookup"><span data-stu-id="e221b-103">When you place a component on a Windows Form, two properties are provided by the design environment: `GenerateMember` and `Modifiers`.</span></span> <span data-ttu-id="e221b-104">`GenerateMember`プロパティは、Windows フォームデザイナーがコンポーネントのメンバー変数を生成するタイミングを指定します。</span><span class="sxs-lookup"><span data-stu-id="e221b-104">The `GenerateMember` property specifies when the Windows Forms Designer generates a member variable for a component.</span></span> <span data-ttu-id="e221b-105">プロパティは、 `Modifiers` そのメンバー変数に割り当てられたアクセス修飾子です。</span><span class="sxs-lookup"><span data-stu-id="e221b-105">The `Modifiers` property is the access modifier assigned to that member variable.</span></span> <span data-ttu-id="e221b-106">プロパティの値がの場合、 `GenerateMember` `false` プロパティの値は `Modifiers` 無効です。</span><span class="sxs-lookup"><span data-stu-id="e221b-106">If the value of the `GenerateMember` property is `false`, the value of the `Modifiers` property has no effect.</span></span>

## <a name="specify-whether-a-component-is-a-member-of-the-form"></a><span data-ttu-id="e221b-107">コンポーネントがフォームのメンバーであるかどうかを指定する</span><span class="sxs-lookup"><span data-stu-id="e221b-107">Specify whether a component is a member of the form</span></span>

1. <span data-ttu-id="e221b-108">Visual Studio の Windows フォームデザイナーで、フォームを開きます。</span><span class="sxs-lookup"><span data-stu-id="e221b-108">In Visual Studio, in the Windows Forms Designer, open your form.</span></span>

2. <span data-ttu-id="e221b-109">**ツールボックス** を開き、フォームで3つのコントロールを配置し <xref:System.Windows.Forms.Button> ます。</span><span class="sxs-lookup"><span data-stu-id="e221b-109">Open the **Toolbox**, and on the form, place three <xref:System.Windows.Forms.Button> controls.</span></span>

3. <span data-ttu-id="e221b-110">次の `GenerateMember` `Modifiers` 表に従って、各コントロールのプロパティとプロパティを設定し <xref:System.Windows.Forms.Button> ます。</span><span class="sxs-lookup"><span data-stu-id="e221b-110">Set the `GenerateMember` and `Modifiers` properties for each <xref:System.Windows.Forms.Button> control according to the following table.</span></span>

    |<span data-ttu-id="e221b-111">ボタン名</span><span class="sxs-lookup"><span data-stu-id="e221b-111">Button name</span></span>|<span data-ttu-id="e221b-112">GenerateMember 値</span><span class="sxs-lookup"><span data-stu-id="e221b-112">GenerateMember value</span></span>|<span data-ttu-id="e221b-113">修飾子の値</span><span class="sxs-lookup"><span data-stu-id="e221b-113">Modifiers value</span></span>|
    |-----------------|--------------------------|---------------------|
    |`button1`|`true`|`private`|
    |`button2`|`true`|`protected`|
    |`button3`|`false`|<span data-ttu-id="e221b-114">変更なし</span><span class="sxs-lookup"><span data-stu-id="e221b-114">No change</span></span>|

4. <span data-ttu-id="e221b-115">ソリューションをビルドします。</span><span class="sxs-lookup"><span data-stu-id="e221b-115">Build the solution.</span></span>

5. <span data-ttu-id="e221b-116">**ソリューション エクスプローラー** で、 **[すべてのファイルを表示]** ボタンをクリックします。</span><span class="sxs-lookup"><span data-stu-id="e221b-116">In **Solution Explorer**, click the **Show All Files** button.</span></span>

6. <span data-ttu-id="e221b-117">**Form1** ノードを開き、**コードエディター** で、 **form1.vb** または **Form1.Designer.cs** ファイルを開きます。</span><span class="sxs-lookup"><span data-stu-id="e221b-117">Open the **Form1** node, and in the **Code Editor**,open the **Form1.Designer.vb** or **Form1.Designer.cs** file.</span></span> <span data-ttu-id="e221b-118">このファイルには、Windows フォームデザイナーによって出力されるコードが含まれています。</span><span class="sxs-lookup"><span data-stu-id="e221b-118">This file contains the code emitted by the Windows Forms Designer.</span></span>

7. <span data-ttu-id="e221b-119">3つのボタンの宣言を見つけます。</span><span class="sxs-lookup"><span data-stu-id="e221b-119">Find the declarations for the three buttons.</span></span> <span data-ttu-id="e221b-120">次のコード例は、プロパティとプロパティによって指定された違いを示して `GenerateMember` `Modifiers` います。</span><span class="sxs-lookup"><span data-stu-id="e221b-120">The following code example shows the differences specified by the `GenerateMember` and `Modifiers` properties.</span></span>

     [!code-csharp[System.Windows.Forms.GenerateMember#3](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.GenerateMember/CS/Form1.cs#3)]
     [!code-vb[System.Windows.Forms.GenerateMember#3](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.GenerateMember/VB/Form1.vb#3)]

     [!code-csharp[System.Windows.Forms.GenerateMember#2](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.GenerateMember/CS/Form1.cs#2)]
     [!code-vb[System.Windows.Forms.GenerateMember#2](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.GenerateMember/VB/Form1.vb#2)]

> [!NOTE]
> <span data-ttu-id="e221b-121">既定では、Windows フォームデザイナーは、 `private` の `Friend` ようなコンテナーコントロールに (Visual Basic) 修飾子を割り当て <xref:System.Windows.Forms.Panel> ます。</span><span class="sxs-lookup"><span data-stu-id="e221b-121">By default, the Windows Forms Designer assigns the `private` (`Friend` in Visual Basic) modifier to container controls like <xref:System.Windows.Forms.Panel>.</span></span> <span data-ttu-id="e221b-122">ベース <xref:System.Windows.Forms.UserControl> または <xref:System.Windows.Forms.Form> コンテナーコントロールがある場合は、継承されたコントロールおよびフォームで新しい子を受け取ることはできません。</span><span class="sxs-lookup"><span data-stu-id="e221b-122">If your base <xref:System.Windows.Forms.UserControl> or <xref:System.Windows.Forms.Form> has a container control, it will not accept new children in inherited controls and forms.</span></span> <span data-ttu-id="e221b-123">この問題を解決するには、基本コンテナーコントロールの修飾子をまたはに変更し `protected` `public` ます。</span><span class="sxs-lookup"><span data-stu-id="e221b-123">The solution is to change the modifier of the base container control to `protected` or `public`.</span></span>

## <a name="see-also"></a><span data-ttu-id="e221b-124">関連項目</span><span class="sxs-lookup"><span data-stu-id="e221b-124">See also</span></span>

- <xref:System.Windows.Forms.Button>
- [<span data-ttu-id="e221b-125">Windows フォームのビジュアルの継承</span><span class="sxs-lookup"><span data-stu-id="e221b-125">Windows Forms Visual Inheritance</span></span>](windows-forms-visual-inheritance.md)
- [<span data-ttu-id="e221b-126">チュートリアル: ビジュアル継承のデモンストレーション</span><span class="sxs-lookup"><span data-stu-id="e221b-126">Walkthrough: Demonstrating Visual Inheritance</span></span>](walkthrough-demonstrating-visual-inheritance.md)
- [<span data-ttu-id="e221b-127">方法: Windows フォームを継承する</span><span class="sxs-lookup"><span data-stu-id="e221b-127">How to: Inherit Windows Forms</span></span>](how-to-inherit-windows-forms.md)
