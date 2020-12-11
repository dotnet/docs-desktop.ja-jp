---
title: コントロールから継承する
ms.date: 03/30/2017
helpviewer_keywords:
- inheritance [Windows Forms], custom controls
- inheritance [Windows Forms], control
- Windows Forms controls, inheritance
- inheritance [Windows Forms], walkthroughs
- custom controls [Windows Forms], inheritance
ms.assetid: 09476da0-8d4c-4a4c-b969-649519dfb438
author: jillre
ms.author: jillfra
manager: jillfra
ms.openlocfilehash: 83bd1b09049dc4650e6b48d1cb0dbe6b452eda26
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/09/2020
ms.locfileid: "96982715"
---
# <a name="walkthrough-inherit-from-a-windows-forms-control-with-c"></a><span data-ttu-id="c60b7-102">チュートリアル: Windows フォームコントロールから C を継承する\#</span><span class="sxs-lookup"><span data-stu-id="c60b7-102">Walkthrough: Inherit from a Windows Forms Control with C\#</span></span>

<span data-ttu-id="c60b7-103">C# では、 *継承* によって強力なカスタムコントロールを作成できます。</span><span class="sxs-lookup"><span data-stu-id="c60b7-103">With C#, you can create powerful custom controls through *inheritance*.</span></span> <span data-ttu-id="c60b7-104">継承を使用すると、標準の Windows フォーム コントロールの固有の機能をすべて保持しながら、カスタム機能も組み込んだコントロールを作成できます。</span><span class="sxs-lookup"><span data-stu-id="c60b7-104">Through inheritance you are able to create controls that retain all of the inherent functionality of standard Windows Forms controls but also incorporate custom functionality.</span></span> <span data-ttu-id="c60b7-105">このチュートリアルでは、`ValueButton` という単純な継承されたコントロールを作成します。</span><span class="sxs-lookup"><span data-stu-id="c60b7-105">In this walkthrough, you will create a simple inherited control called `ValueButton`.</span></span> <span data-ttu-id="c60b7-106">このボタンは、標準の Windows フォームコントロールから機能を継承し、と <xref:System.Windows.Forms.Button> 呼ばれるカスタムプロパティを公開し `ButtonValue` ます。</span><span class="sxs-lookup"><span data-stu-id="c60b7-106">This button will inherit functionality from the standard Windows Forms <xref:System.Windows.Forms.Button> control, and will expose a custom property called `ButtonValue`.</span></span>

## <a name="create-the-project"></a><span data-ttu-id="c60b7-107">プロジェクトの作成</span><span class="sxs-lookup"><span data-stu-id="c60b7-107">Create the Project</span></span>

<span data-ttu-id="c60b7-108">新しいプロジェクトを作成するときは、ルート名前空間、アセンブリ名、プロジェクト名を設定し、既定のコンポーネントが適切な名前空間に含まれるようにするために、プロジェクトの名前を指定します。</span><span class="sxs-lookup"><span data-stu-id="c60b7-108">When you create a new project, you specify its name in order to set the root namespace, assembly name, and project name, and to ensure that the default component will be in the correct namespace.</span></span>

### <a name="to-create-the-valuebuttonlib-control-library-and-the-valuebutton-control"></a><span data-ttu-id="c60b7-109">ValueButtonLib コントロール ライブラリと ValueButton コントロールを作成するには</span><span class="sxs-lookup"><span data-stu-id="c60b7-109">To create the ValueButtonLib control library and the ValueButton control</span></span>

1. <span data-ttu-id="c60b7-110">Visual Studio で、新しい **Windows フォームコントロールライブラリ** プロジェクトを作成し、 **valuebuttonlib** という名前を指定します。</span><span class="sxs-lookup"><span data-stu-id="c60b7-110">In Visual Studio, create a new **Windows Forms Control Library** project, and name it **ValueButtonLib**.</span></span>

     <span data-ttu-id="c60b7-111">プロジェクト名 `ValueButtonLib` は、既定でルート名前空間にも割り当てられます。</span><span class="sxs-lookup"><span data-stu-id="c60b7-111">The project name, `ValueButtonLib`, is also assigned to the root namespace by default.</span></span> <span data-ttu-id="c60b7-112">ルート名前空間は、アセンブリ内のコンポーネント名の修飾に使用されます。</span><span class="sxs-lookup"><span data-stu-id="c60b7-112">The root namespace is used to qualify the names of components in the assembly.</span></span> <span data-ttu-id="c60b7-113">たとえば、`ValueButton` という名前のコンポーネントが 2 つのアセンブリに含まれている場合、`ValueButtonLib.ValueButton` を使用して目的の `ValueButton` コンポーネントを指定できます。</span><span class="sxs-lookup"><span data-stu-id="c60b7-113">For example, if two assemblies provide components named `ValueButton`, you can specify your `ValueButton` component using `ValueButtonLib.ValueButton`.</span></span> <span data-ttu-id="c60b7-114">詳細については、「[名前空間](/dotnet/csharp/programming-guide/namespaces/index)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="c60b7-114">For more information, see [Namespaces](/dotnet/csharp/programming-guide/namespaces/index).</span></span>

2. <span data-ttu-id="c60b7-115">**ソリューション エクスプローラー** で、**[UserControl1.cs]** を右クリックし、ショートカット メニューの **[名前の変更]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="c60b7-115">In **Solution Explorer**, right-click **UserControl1.cs**, then choose **Rename** from the shortcut menu.</span></span> <span data-ttu-id="c60b7-116">ファイル名を **ValueButton.cs** に変更します。</span><span class="sxs-lookup"><span data-stu-id="c60b7-116">Change the file name to **ValueButton.cs**.</span></span> <span data-ttu-id="c60b7-117">コード要素 "`UserControl1`" へのすべての参照の名前を変更するかどうかをたずねられたら、**[はい]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="c60b7-117">Click the **Yes** button when you are asked if you want to rename all references to the code element '`UserControl1`'.</span></span>

3. <span data-ttu-id="c60b7-118">**ソリューション エクスプローラー** で、**[ValueButton.cs]** を右クリックし、**[コードの表示]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="c60b7-118">In **Solution Explorer**, right-click **ValueButton.cs** and select **View Code**.</span></span>

4. <span data-ttu-id="c60b7-119">ステートメントの `class` 行を探し、 `public partial class ValueButton` このコントロールが継承する型をに変更し <xref:System.Windows.Forms.UserControl> <xref:System.Windows.Forms.Button> ます。</span><span class="sxs-lookup"><span data-stu-id="c60b7-119">Locate the `class` statement line, `public partial class ValueButton`, and change the type from which this control inherits from <xref:System.Windows.Forms.UserControl> to <xref:System.Windows.Forms.Button>.</span></span> <span data-ttu-id="c60b7-120">これにより、継承されたコントロールがコントロールのすべての機能を継承できるように <xref:System.Windows.Forms.Button> なります。</span><span class="sxs-lookup"><span data-stu-id="c60b7-120">This allows your inherited control to inherit all the functionality of the <xref:System.Windows.Forms.Button> control.</span></span>

5. <span data-ttu-id="c60b7-121">**ソリューション エクスプローラー** で、**[ValueButton.cs]** ノードを開いて、デザイナーによって生成されたコード ファイル (**ValueButton.Designer.cs**) を表示します。</span><span class="sxs-lookup"><span data-stu-id="c60b7-121">In **Solution Explorer**, open the **ValueButton.cs** node to display the designer-generated code file, **ValueButton.Designer.cs**.</span></span> <span data-ttu-id="c60b7-122">**コードエディター** でこのファイルを開きます。</span><span class="sxs-lookup"><span data-stu-id="c60b7-122">Open this file in the **Code Editor**.</span></span>

6. <span data-ttu-id="c60b7-123">メソッドを見つけ `InitializeComponent` て、プロパティを割り当てる行を削除し <xref:System.Windows.Forms.ContainerControl.AutoScaleMode%2A> ます。</span><span class="sxs-lookup"><span data-stu-id="c60b7-123">Locate the `InitializeComponent` method and remove the line that assigns the <xref:System.Windows.Forms.ContainerControl.AutoScaleMode%2A> property.</span></span> <span data-ttu-id="c60b7-124">このプロパティはコントロールに存在しません <xref:System.Windows.Forms.Button> 。</span><span class="sxs-lookup"><span data-stu-id="c60b7-124">This property does not exist in the <xref:System.Windows.Forms.Button> control.</span></span>

7. <span data-ttu-id="c60b7-125">**[ファイル]** メニューの **[すべて保存]** をクリックして、プロジェクトを保存します。</span><span class="sxs-lookup"><span data-stu-id="c60b7-125">From the **File** menu, choose **Save All** to save the project.</span></span>

    > [!NOTE]
    > <span data-ttu-id="c60b7-126">ビジュアル デザイナーは使用できなくなっています。</span><span class="sxs-lookup"><span data-stu-id="c60b7-126">A visual designer is no longer available.</span></span> <span data-ttu-id="c60b7-127">コントロールは <xref:System.Windows.Forms.Button> 独自の描画を行うため、デザイナーで外観を変更することはできません。</span><span class="sxs-lookup"><span data-stu-id="c60b7-127">Because the <xref:System.Windows.Forms.Button> control does its own painting, you are unable to modify its appearance in the designer.</span></span> <span data-ttu-id="c60b7-128">ビジュアル表現は、コード内で変更されない限り、から継承したクラス (つまり、) とまったく同じになり <xref:System.Windows.Forms.Button> ます。</span><span class="sxs-lookup"><span data-stu-id="c60b7-128">Its visual representation will be exactly the same as that of the class it inherits from (that is, <xref:System.Windows.Forms.Button>) unless modified in the code.</span></span> <span data-ttu-id="c60b7-129">UI 要素のないコンポーネントをデザイン サーフェイスに追加することは可能です。</span><span class="sxs-lookup"><span data-stu-id="c60b7-129">You can still add components, which have no UI elements, to the design surface.</span></span>

## <a name="add-a-property-to-your-inherited-control"></a><span data-ttu-id="c60b7-130">継承されたコントロールにプロパティを追加する</span><span class="sxs-lookup"><span data-stu-id="c60b7-130">Add a Property to Your Inherited Control</span></span>

<span data-ttu-id="c60b7-131">継承された Windows フォーム コントロールの考えられる用途の 1 つとして、外観は標準の Windows フォーム コントロールと同じでありながら、カスタム プロパティを公開するコントロールの作成があります。</span><span class="sxs-lookup"><span data-stu-id="c60b7-131">One possible use of inherited Windows Forms controls is the creation of controls that are identical in look and feel of standard Windows Forms controls, but expose custom properties.</span></span> <span data-ttu-id="c60b7-132">このセクションでは、`ButtonValue` というプロパティをコントロールに追加します。</span><span class="sxs-lookup"><span data-stu-id="c60b7-132">In this section, you will add a property called `ButtonValue` to your control.</span></span>

### <a name="to-add-the-value-property"></a><span data-ttu-id="c60b7-133">Value プロパティを追加するには</span><span class="sxs-lookup"><span data-stu-id="c60b7-133">To add the Value property</span></span>

1. <span data-ttu-id="c60b7-134">**ソリューション エクスプローラー** で、**[ValueButton.cs]** を右クリックし、ショートカット メニューの **[コードの表示]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="c60b7-134">In **Solution Explorer**, right-click **ValueButton.cs**, and then click **View Code** from the shortcut menu.</span></span>

2. <span data-ttu-id="c60b7-135">`class` ステートメントを探します。</span><span class="sxs-lookup"><span data-stu-id="c60b7-135">Locate the `class` statement.</span></span> <span data-ttu-id="c60b7-136">`{` の直後に次のコードを入力します。</span><span class="sxs-lookup"><span data-stu-id="c60b7-136">Immediately after the `{`, type the following code:</span></span>

    ```csharp
    // Creates the private variable that will store the value of your
    // property.
    private int varValue;
    // Declares the property.
    public int ButtonValue
    {
       // Sets the method for retrieving the value of your property.
       get
       {
          return varValue;
       }
       // Sets the method for setting the value of your property.
       set
       {
          varValue = value;
       }
    }
    ```

     <span data-ttu-id="c60b7-137">このコードでは、`ButtonValue` プロパティを格納し、取得するメソッドを設定しています。</span><span class="sxs-lookup"><span data-stu-id="c60b7-137">This code sets the methods by which the `ButtonValue` property is stored and retrieved.</span></span> <span data-ttu-id="c60b7-138">`get` ステートメントは、返された値を `varValue` プライベート変数に格納されている値に設定します。`set` ステートメントは、`value` キーワードを使用してプライベート変数の値を設定します。</span><span class="sxs-lookup"><span data-stu-id="c60b7-138">The `get` statement sets the value returned to the value that is stored in the private variable `varValue`, and the `set` statement sets the value of the private variable by use of the `value` keyword.</span></span>

3. <span data-ttu-id="c60b7-139">**[ファイル]** メニューの **[すべて保存]** をクリックして、プロジェクトを保存します。</span><span class="sxs-lookup"><span data-stu-id="c60b7-139">From the **File** menu, choose **Save All** to save the project.</span></span>

## <a name="test-the-control"></a><span data-ttu-id="c60b7-140">コントロールをテストする</span><span class="sxs-lookup"><span data-stu-id="c60b7-140">Test the control</span></span>

<span data-ttu-id="c60b7-141">コントロールはスタンドアロン プロジェクトではないため、コンテナー内でホストする必要があります。</span><span class="sxs-lookup"><span data-stu-id="c60b7-141">Controls are not stand-alone projects; they must be hosted in a container.</span></span> <span data-ttu-id="c60b7-142">コントロールをテストするには、コントロールを実行するテスト プロジェクトを指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="c60b7-142">In order to test your control, you must provide a test project for it to run in.</span></span> <span data-ttu-id="c60b7-143">また、コントロールをビルド (コンパイル) して、テスト プロジェクトからアクセスできるようにする必要があります。</span><span class="sxs-lookup"><span data-stu-id="c60b7-143">You must also make your control accessible to the test project by building (compiling) it.</span></span> <span data-ttu-id="c60b7-144">このセクションでは、コントロールをビルドし、Windows フォームでテストします。</span><span class="sxs-lookup"><span data-stu-id="c60b7-144">In this section, you will build your control and test it in a Windows Form.</span></span>

### <a name="to-build-your-control"></a><span data-ttu-id="c60b7-145">コントロールをビルドするには</span><span class="sxs-lookup"><span data-stu-id="c60b7-145">To build your control</span></span>

<span data-ttu-id="c60b7-146">**[ビルド]** メニューの **[ソリューションのビルド]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="c60b7-146">On the **Build** menu, click **Build Solution**.</span></span> <span data-ttu-id="c60b7-147">コンパイル エラーも警告も発生せずに、ビルドが正常に完了します。</span><span class="sxs-lookup"><span data-stu-id="c60b7-147">The build should be successful with no compiler errors or warnings.</span></span>

### <a name="to-create-a-test-project"></a><span data-ttu-id="c60b7-148">テスト プロジェクトを作成するには</span><span class="sxs-lookup"><span data-stu-id="c60b7-148">To create a test project</span></span>

1. <span data-ttu-id="c60b7-149">**[ファイル]** メニューの **[追加]** をポイントし、**[新しいプロジェクト]** をクリックして **[新しいプロジェクトの追加]** ダイアログ ボックスを開きます。</span><span class="sxs-lookup"><span data-stu-id="c60b7-149">On the **File** menu, point to **Add** and then click **New Project** to open the **Add New Project** dialog box.</span></span>

2. <span data-ttu-id="c60b7-150">**[Visual C#]** ノードの下の **[Windows]** ノードを選択し、**[Windows フォーム アプリケーション]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="c60b7-150">Select the **Windows** node, beneath the **Visual C#** node, and click **Windows Forms Application**.</span></span>

3. <span data-ttu-id="c60b7-151">[ **名前** ] ボックスに「 **Test**」と入力します。</span><span class="sxs-lookup"><span data-stu-id="c60b7-151">In the **Name** box, enter **Test**.</span></span>

4. <span data-ttu-id="c60b7-152">**ソリューション エクスプローラー** で、テスト プロジェクトの **[参照設定]** ノードを右クリックし、ショートカット メニューの **[参照の追加]** をクリックして **[参照の追加]** ダイアログ ボックスを表示します。</span><span class="sxs-lookup"><span data-stu-id="c60b7-152">In **Solution Explorer**, right-click the **References** node for your test project, then select **Add Reference** from the shortcut menu to display the **Add Reference** dialog box.</span></span>

5. <span data-ttu-id="c60b7-153">**[プロジェクト]** というラベルのタブをクリックします。</span><span class="sxs-lookup"><span data-stu-id="c60b7-153">Click the tab labeled **Projects**.</span></span> <span data-ttu-id="c60b7-154">ValueButtonLib プロジェクトが **プロジェクト名** の下に一覧表示されます。</span><span class="sxs-lookup"><span data-stu-id="c60b7-154">Your ValueButtonLib project will be listed under **Project Name**.</span></span> <span data-ttu-id="c60b7-155">プロジェクトをダブルクリックして、テスト プロジェクトへの参照を追加します。</span><span class="sxs-lookup"><span data-stu-id="c60b7-155">Double-click the project to add the reference to the test project.</span></span>

6. <span data-ttu-id="c60b7-156">**ソリューション エクスプローラー** で、**[Test]** を右クリックし、**[ビルド]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="c60b7-156">In **Solution Explorer,** right-click **Test** and select **Build**.</span></span>

### <a name="to-add-your-control-to-the-form"></a><span data-ttu-id="c60b7-157">コントロールをフォームに追加するには</span><span class="sxs-lookup"><span data-stu-id="c60b7-157">To add your control to the form</span></span>

1. <span data-ttu-id="c60b7-158">**ソリューション エクスプローラー** で、**[Form1.cs]** を右クリックし、ショートカット メニューの **[デザイナーの表示]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="c60b7-158">In **Solution Explorer**, right-click **Form1.cs** and choose **View Designer** from the shortcut menu.</span></span>

2. <span data-ttu-id="c60b7-159">**ツールボックス** で、[ **Valuebuttonlib コンポーネント**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="c60b7-159">In the **Toolbox**, select **ValueButtonLib Components**.</span></span> <span data-ttu-id="c60b7-160">**[ValueButton]** をダブルクリックします。</span><span class="sxs-lookup"><span data-stu-id="c60b7-160">Double-click **ValueButton**.</span></span>

     <span data-ttu-id="c60b7-161">**ValueButton** がフォームに表示されます。</span><span class="sxs-lookup"><span data-stu-id="c60b7-161">A **ValueButton** appears on the form.</span></span>

3. <span data-ttu-id="c60b7-162">**[ValueButton]** を右クリックし、ショートカット メニューの **[プロパティ]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="c60b7-162">Right-click the **ValueButton** and select **Properties** from the shortcut menu.</span></span>

4. <span data-ttu-id="c60b7-163">**[プロパティ]** ウィンドウで、このコントロールのプロパティを調べます。</span><span class="sxs-lookup"><span data-stu-id="c60b7-163">In the **Properties** window, examine the properties of this control.</span></span> <span data-ttu-id="c60b7-164">これらは、追加のプロパティ ButtonValue がある点を除いて、標準ボタンによって公開されるプロパティと同じであることに注意してください。</span><span class="sxs-lookup"><span data-stu-id="c60b7-164">Note that they are identical to the properties exposed by a standard button, except that there is an additional property, ButtonValue.</span></span>

5. <span data-ttu-id="c60b7-165">**Buttonvalue** プロパティを **5** に設定します。</span><span class="sxs-lookup"><span data-stu-id="c60b7-165">Set the **ButtonValue** property to **5**.</span></span>

6. <span data-ttu-id="c60b7-166">**ツールボックス** の [**すべての Windows フォーム**] タブで、[**ラベル**] をダブルクリックし <xref:System.Windows.Forms.Label> てフォームにコントロールを追加します。</span><span class="sxs-lookup"><span data-stu-id="c60b7-166">In the **All Windows Forms** tab of the **Toolbox**, double-click **Label** to add a <xref:System.Windows.Forms.Label> control to your form.</span></span>

7. <span data-ttu-id="c60b7-167">ラベルをフォームの中央に配置し直します。</span><span class="sxs-lookup"><span data-stu-id="c60b7-167">Relocate the label to the center of the form.</span></span>

8. <span data-ttu-id="c60b7-168">`valueButton1` をダブルクリックします。</span><span class="sxs-lookup"><span data-stu-id="c60b7-168">Double-click `valueButton1`.</span></span>

     <span data-ttu-id="c60b7-169">**コード エディター** が開き、`valueButton1_Click` イベントが表示されます。</span><span class="sxs-lookup"><span data-stu-id="c60b7-169">The **Code Editor** opens to the `valueButton1_Click` event.</span></span>

9. <span data-ttu-id="c60b7-170">次のコード行を挿入します。</span><span class="sxs-lookup"><span data-stu-id="c60b7-170">Insert the following line of code.</span></span>

    ```csharp
    label1.Text = valueButton1.ButtonValue.ToString();
    ```

10. <span data-ttu-id="c60b7-171">**ソリューション エクスプローラー** で、**[Test]** を右クリックし、ショートカット メニューの **[スタートアップ プロジェクトに設定]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="c60b7-171">In **Solution Explorer**, right-click **Test**, and choose **Set as Startup Project** from the shortcut menu.</span></span>

11. <span data-ttu-id="c60b7-172">**[デバッグ]** メニューの **[デバッグの開始]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="c60b7-172">From the **Debug** menu, select **Start Debugging**.</span></span>

     <span data-ttu-id="c60b7-173">`Form1` が表示されます。</span><span class="sxs-lookup"><span data-stu-id="c60b7-173">`Form1` appears.</span></span>

12. <span data-ttu-id="c60b7-174">[`valueButton1`] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="c60b7-174">Click `valueButton1`.</span></span>

     <span data-ttu-id="c60b7-175">`label1` に数字の "5" が表示されます。これは、継承されたコントロールの `ButtonValue` プロパティが、`valueButton1_Click` メソッドによって `label1` に渡されたことを示しています。</span><span class="sxs-lookup"><span data-stu-id="c60b7-175">The numeral '5' is displayed in `label1`, demonstrating that the `ButtonValue` property of your inherited control has been passed to `label1` through the `valueButton1_Click` method.</span></span> <span data-ttu-id="c60b7-176">このようにして、`ValueButton` コントロールは標準の Windows フォーム ボタンの機能をすべて継承しながら、追加のカスタム プロパティを公開します。</span><span class="sxs-lookup"><span data-stu-id="c60b7-176">Thus your `ValueButton` control inherits all the functionality of the standard Windows Forms button, but exposes an additional, custom property.</span></span>

## <a name="see-also"></a><span data-ttu-id="c60b7-177">関連項目</span><span class="sxs-lookup"><span data-stu-id="c60b7-177">See also</span></span>

- <span data-ttu-id="c60b7-178">[方法: [ツールボックス アイテムの選択] ダイアログ ボックスにコントロールを表示する](how-to-display-a-control-in-the-choose-toolbox-items-dialog-box.md)</span><span class="sxs-lookup"><span data-stu-id="c60b7-178">[How to: Display a Control in the Choose Toolbox Items Dialog Box](how-to-display-a-control-in-the-choose-toolbox-items-dialog-box.md)</span></span>
- [<span data-ttu-id="c60b7-179">チュートリアル: Visual C を使用した複合コントロールの作成#</span><span class="sxs-lookup"><span data-stu-id="c60b7-179">Walkthrough: Authoring a Composite Control with Visual C#</span></span>](walkthrough-authoring-a-composite-control-with-visual-csharp.md)
