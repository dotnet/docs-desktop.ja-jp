---
title: デザイナーを使用してコントロールを型にバインドする
ms.date: 03/30/2017
helpviewer_keywords:
- controls [Windows Forms], binding to a type
- BindingSource component [Windows Forms], binding to a type
- types [Windows Forms], binding controls to
ms.assetid: 5ab984b5-c2d0-4638-a572-1c84013e8746
ms.openlocfilehash: 2257489e123ceeea819ad3538952db51b726c7e5
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/09/2020
ms.locfileid: "96980955"
---
# <a name="how-to-bind-a-windows-forms-control-to-a-type-using-the-designer"></a><span data-ttu-id="2c41b-102">方法: デザイナーを使って Windows フォーム コントロールを型にバインドする</span><span class="sxs-lookup"><span data-stu-id="2c41b-102">How to: Bind a Windows Forms Control to a Type Using the Designer</span></span>

<span data-ttu-id="2c41b-103">データをやり取りするコントロールを作成する際、オブジェクトではなく型にコントロールをバインドすることが必要な場合があります。</span><span class="sxs-lookup"><span data-stu-id="2c41b-103">When you are building controls that interact with data, you sometimes need to bind a control to a type, rather than an object.</span></span> <span data-ttu-id="2c41b-104">データを使用できないが、データ バインド コントロールで型のパブリック インターフェイスからデータを表示する必要がある場合、通常はデザイン時にコントロールを型にバインドする必要があります。</span><span class="sxs-lookup"><span data-stu-id="2c41b-104">You typically need to bind a control to a type at design time, when data may not be available, but you still want your data-bound controls to display data from a type's public interface.</span></span> <span data-ttu-id="2c41b-105">次の手順では、 <xref:System.Windows.Forms.BindingSource> 型にバインドされる新しいを作成する方法と、型のプロパティの1つをのプロパティにバインドする方法について説明し <xref:System.Windows.Forms.TextBox.Text%2A> <xref:System.Windows.Forms.TextBox> ます。</span><span class="sxs-lookup"><span data-stu-id="2c41b-105">The following procedures demonstrate how to create a new <xref:System.Windows.Forms.BindingSource> that is bound to a type, and then how to bind one of the type's properties to the <xref:System.Windows.Forms.TextBox.Text%2A> property of a <xref:System.Windows.Forms.TextBox>.</span></span>

### <a name="to-bind-the-bindingsource-to-a-type"></a><span data-ttu-id="2c41b-106">BindingSource を型にバインドするには</span><span class="sxs-lookup"><span data-stu-id="2c41b-106">To bind the BindingSource to a type</span></span>

1. <span data-ttu-id="2c41b-107">Windows フォームプロジェクトを作成します ([**ファイル**] [  >  **新しい**  >  **プロジェクト**] [  >  **Visual C#** ] または [ **Visual Basic**  >  **クラシックデスクトップ**  >  **Windows フォームアプリケーション**])。</span><span class="sxs-lookup"><span data-stu-id="2c41b-107">Create a Windows Forms project (**File** > **New** > **Project** > **Visual C#** or **Visual Basic** > **Classic Desktop** > **Windows Forms Application**).</span></span>

2. <span data-ttu-id="2c41b-108">**デザイン** ビューで、コンポーネントをフォームにドラッグし <xref:System.Windows.Forms.BindingSource> ます。</span><span class="sxs-lookup"><span data-stu-id="2c41b-108">In **Design** view, drag a <xref:System.Windows.Forms.BindingSource> component onto the form.</span></span>

3. <span data-ttu-id="2c41b-109">[ **プロパティ** ] ウィンドウで、プロパティの矢印をクリックし <xref:System.Windows.Forms.BindingSource.DataSource%2A> ます。</span><span class="sxs-lookup"><span data-stu-id="2c41b-109">In the **Properties** window, click the arrow for the <xref:System.Windows.Forms.BindingSource.DataSource%2A> property.</span></span>

4. <span data-ttu-id="2c41b-110">**DataSource UI 型エディター** で、**[プロジェクト データ ソースの追加]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="2c41b-110">In the **DataSource UI Type Editor**, click **Add Project Data Source**.</span></span>

5. <span data-ttu-id="2c41b-111">**[データ ソースの種類を選択]** ページで、**[オブジェクト]** を選択して **[次へ]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="2c41b-111">On the **Choose a Data Source Type** page, select **Object** and click **Next**.</span></span>

6. <span data-ttu-id="2c41b-112">バインド先となる型を選択します。</span><span class="sxs-lookup"><span data-stu-id="2c41b-112">Select the type to bind to:</span></span>

    - <span data-ttu-id="2c41b-113">バインド先となる型が現在のプロジェクトにある場合、または、型を含むアセンブリが参照として既に追加されている場合は、ノードを展開し、目的の型を探して選択します。</span><span class="sxs-lookup"><span data-stu-id="2c41b-113">If the type you want to bind to is in the current project, or the assembly that contains the type is already added as a reference, expand the nodes to find the type you want, and then select it.</span></span>

      <span data-ttu-id="2c41b-114">\- または -</span><span class="sxs-lookup"><span data-stu-id="2c41b-114">\-or-</span></span>

    - <span data-ttu-id="2c41b-115">バインド先の型が、現在参照の一覧にない別のアセンブリにある場合は、[ **参照の追加**] をクリックし、[ **プロジェクト** ] タブをクリックします。目的のビジネスオブジェクトが含まれているプロジェクトを選択し、[ **OK]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="2c41b-115">If the type you want to bind to is in another assembly, not currently in the list of references, click **Add Reference**, and then click the **Projects** tab. Select the project that contains the business object you want and click **OK**.</span></span> <span data-ttu-id="2c41b-116">このプロジェクトは、アセンブリの一覧に表示されるため、ノードを展開し、目的の型を探して選択します。</span><span class="sxs-lookup"><span data-stu-id="2c41b-116">This project will appear in the list of assemblies, so you can expand the nodes to find the type you want, and then select it.</span></span>

      > [!NOTE]
      > <span data-ttu-id="2c41b-117">フレームワークまたは Microsoft アセンブリの型にバインドする場合は、**[Microsoft または System で始まるアセンブリを表示しない]** チェックボックスをオフにします。</span><span class="sxs-lookup"><span data-stu-id="2c41b-117">If you want to bind to a type in a framework or Microsoft assembly, clear the **Hide assemblies that begin with Microsoft or System** check box.</span></span>

7. <span data-ttu-id="2c41b-118">**[次へ]** をクリックし、 **[完了]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="2c41b-118">Click **Next**, and then click **Finish**.</span></span>

### <a name="to-bind-the-control-to-the-bindingsource"></a><span data-ttu-id="2c41b-119">コントロールを BindingSource にバインドするには</span><span class="sxs-lookup"><span data-stu-id="2c41b-119">To bind the control to the BindingSource</span></span>

1. <span data-ttu-id="2c41b-120">フォームに <xref:System.Windows.Forms.TextBox> を追加します。</span><span class="sxs-lookup"><span data-stu-id="2c41b-120">Add a <xref:System.Windows.Forms.TextBox> to the form.</span></span>

2. <span data-ttu-id="2c41b-121">**[プロパティ]** ウィンドウで **(DataBindings)** ノードを展開します。</span><span class="sxs-lookup"><span data-stu-id="2c41b-121">In the **Properties** window, expand the **(DataBindings)** node.</span></span>

3. <span data-ttu-id="2c41b-122">プロパティの横にある矢印をクリックし <xref:System.Windows.Forms.TextBox.Text%2A> ます。</span><span class="sxs-lookup"><span data-stu-id="2c41b-122">Click the arrow next to the <xref:System.Windows.Forms.TextBox.Text%2A> property.</span></span>

4. <span data-ttu-id="2c41b-123">**DATASOURCE UI 型エディター** で、前に追加したのノードを展開 <xref:System.Windows.Forms.BindingSource> し、のプロパティにバインドするバインドされた型のプロパティを選択し <xref:System.Windows.Forms.TextBox.Text%2A> <xref:System.Windows.Forms.TextBox> ます。</span><span class="sxs-lookup"><span data-stu-id="2c41b-123">In the **DataSource UI Type Editor**, expand the node for the <xref:System.Windows.Forms.BindingSource> added previously, and select the property of the bound type you want to bind to the <xref:System.Windows.Forms.TextBox.Text%2A> property of the <xref:System.Windows.Forms.TextBox>.</span></span>

## <a name="see-also"></a><span data-ttu-id="2c41b-124">関連項目</span><span class="sxs-lookup"><span data-stu-id="2c41b-124">See also</span></span>

- [<span data-ttu-id="2c41b-125">BindingSource コンポーネント</span><span class="sxs-lookup"><span data-stu-id="2c41b-125">BindingSource Component</span></span>](bindingsource-component.md)
- [<span data-ttu-id="2c41b-126">方法: Windows フォーム コントロールを型にバインドする</span><span class="sxs-lookup"><span data-stu-id="2c41b-126">How to: Bind a Windows Forms Control to a Type</span></span>](how-to-bind-a-windows-forms-control-to-a-type.md)
- [<span data-ttu-id="2c41b-127">Visual Studio でのデータへのコントロールのバインド</span><span class="sxs-lookup"><span data-stu-id="2c41b-127">Bind controls to data in Visual Studio</span></span>](/visualstudio/data-tools/bind-controls-to-data-in-visual-studio)
