---
title: ユーザー インターフェイスを持たないコントロールを追加する
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
f1_keywords:
- NonVisualSelection
helpviewer_keywords:
- invisible controls [Windows Forms]
- Windows Forms controls, adding to form
- controls [Windows Forms], nonvisual
- Windows Forms controls, nonvisual
- nonvisual controls [Windows Forms]
ms.assetid: 52134d9c-cff6-4eed-8e2b-3d5eb3bd494e
ms.openlocfilehash: c1ab1ec848b4c7a19ed9a65b67e17679bac215cd
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/09/2020
ms.locfileid: "96982020"
---
# <a name="how-to-add-controls-without-a-user-interface-to-windows-forms"></a><span data-ttu-id="5dc4a-102">方法 : ユーザー インターフェイスを持たないコントロールを Windows フォームに追加する</span><span class="sxs-lookup"><span data-stu-id="5dc4a-102">How to: Add Controls Without a User Interface to Windows Forms</span></span>

<span data-ttu-id="5dc4a-103">非可視のコントロール (またはコンポーネント) は、アプリケーションに機能を提供します。</span><span class="sxs-lookup"><span data-stu-id="5dc4a-103">A nonvisual control (or component) provides functionality to your application.</span></span> <span data-ttu-id="5dc4a-104">他のコントロールとは異なり、コンポーネントはユーザーにユーザーインターフェイスを提供しないため、Windows フォームデザイナー画面に表示する必要はありません。</span><span class="sxs-lookup"><span data-stu-id="5dc4a-104">Unlike other controls, components do not provide a user interface to the user and thus do not need to be displayed on the Windows Forms Designer surface.</span></span> <span data-ttu-id="5dc4a-105">コンポーネントがフォームに追加されると、すべてのコンポーネントが表示されるフォームの下部に、サイズ変更可能なトレイ Windows フォームデザイナーが表示されます。</span><span class="sxs-lookup"><span data-stu-id="5dc4a-105">When a component is added to a form, the Windows Forms Designer displays a resizable tray at the bottom of the form where all components are displayed.</span></span> <span data-ttu-id="5dc4a-106">コンポーネントトレイにコントロールが追加されたら、コンポーネントを選択し、フォーム上の他のコントロールと同様にそのプロパティを設定できます。</span><span class="sxs-lookup"><span data-stu-id="5dc4a-106">Once a control has been added to the component tray, you can select the component and set its properties as you would any other control on the form.</span></span>

## <a name="add-a-component-to-a-windows-form"></a><span data-ttu-id="5dc4a-107">Windows フォームへのコンポーネントの追加</span><span class="sxs-lookup"><span data-stu-id="5dc4a-107">Add a component to a Windows Form</span></span>

1. <span data-ttu-id="5dc4a-108">Visual Studio でフォームを開きます。</span><span class="sxs-lookup"><span data-stu-id="5dc4a-108">Open the form in Visual Studio.</span></span> <span data-ttu-id="5dc4a-109">詳細については、「 [方法: デザイナーで Windows フォームを表示する](/previous-versions/visualstudio/visual-studio-2010/w5yd62ts(v=vs.100))」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="5dc4a-109">For details, see [How to: Display Windows Forms in the Designer](/previous-versions/visualstudio/visual-studio-2010/w5yd62ts(v=vs.100)).</span></span>

2. <span data-ttu-id="5dc4a-110">**ツールボックス** でコンポーネントをクリックし、フォームにドラッグします。</span><span class="sxs-lookup"><span data-stu-id="5dc4a-110">In the **Toolbox**, click a component and drag it to your form.</span></span>

     <span data-ttu-id="5dc4a-111">コンポーネントがコンポーネントトレイに表示されます。</span><span class="sxs-lookup"><span data-stu-id="5dc4a-111">Your component appears in the component tray.</span></span>

<span data-ttu-id="5dc4a-112">また、実行時にコンポーネントをフォームに追加することもできます。</span><span class="sxs-lookup"><span data-stu-id="5dc4a-112">Furthermore, components can be added to a form at run time.</span></span> <span data-ttu-id="5dc4a-113">これは、特に、ユーザーインターフェイスを持つコントロールとは異なり、コンポーネントにはビジュアル式がないため、一般的なシナリオです。</span><span class="sxs-lookup"><span data-stu-id="5dc4a-113">This is a common scenario, especially because components do not have a visual expression, unlike controls that have a user interface.</span></span> <span data-ttu-id="5dc4a-114">次の例では、 <xref:System.Windows.Forms.Timer> コンポーネントが実行時に追加されます。</span><span class="sxs-lookup"><span data-stu-id="5dc4a-114">In the example below, a <xref:System.Windows.Forms.Timer> component is added at run time.</span></span> <span data-ttu-id="5dc4a-115">(Visual Studio にはさまざまなタイマーが含まれていることに注意してください。この場合は、Windows フォームコンポーネントを使用 <xref:System.Windows.Forms.Timer> します。</span><span class="sxs-lookup"><span data-stu-id="5dc4a-115">(Note that Visual Studio contains a number of different timers; in this case, use a Windows Forms <xref:System.Windows.Forms.Timer> component.</span></span> <span data-ttu-id="5dc4a-116">Visual Studio でのさまざまなタイマーの詳細については、「 [Server-Based タイマーの概要](/previous-versions/visualstudio/visual-studio-2008/tb9yt5e6(v=vs.90))」を参照してください)。</span><span class="sxs-lookup"><span data-stu-id="5dc4a-116">For more information about the different timers in Visual Studio, see [Introduction to Server-Based Timers](/previous-versions/visualstudio/visual-studio-2008/tb9yt5e6(v=vs.90)).)</span></span>

> [!CAUTION]
> <span data-ttu-id="5dc4a-117">コンポーネントには、多くの場合、コンポーネントを効果的に機能させるために設定する必要があるコントロール固有のプロパティがあります。</span><span class="sxs-lookup"><span data-stu-id="5dc4a-117">Components often have control-specific properties that must be set for the component to function effectively.</span></span> <span data-ttu-id="5dc4a-118">以下のコンポーネントの場合は、 <xref:System.Windows.Forms.Timer> プロパティを設定し `Interval` ます。</span><span class="sxs-lookup"><span data-stu-id="5dc4a-118">In the case of the <xref:System.Windows.Forms.Timer> component below, you set the `Interval` property.</span></span> <span data-ttu-id="5dc4a-119">コンポーネントをプロジェクトに追加するときは、そのコンポーネントに必要なプロパティを設定します。</span><span class="sxs-lookup"><span data-stu-id="5dc4a-119">Be sure, when adding components to your project, that you set the properties necessary for that component.</span></span>

## <a name="add-a-component-to-a-windows-form-programmatically"></a><span data-ttu-id="5dc4a-120">プログラムによって Windows フォームにコンポーネントを追加する</span><span class="sxs-lookup"><span data-stu-id="5dc4a-120">Add a component to a Windows Form programmatically</span></span>

1. <span data-ttu-id="5dc4a-121">コードでクラスのインスタンスを作成 <xref:System.Windows.Forms.Timer> します。</span><span class="sxs-lookup"><span data-stu-id="5dc4a-121">Create an instance of the <xref:System.Windows.Forms.Timer> class in code.</span></span>

2. <span data-ttu-id="5dc4a-122">`Interval`タイマーのタイマー刻みの間隔を決定するには、プロパティを設定します。</span><span class="sxs-lookup"><span data-stu-id="5dc4a-122">Set the `Interval` property to determine the time between ticks of the timer.</span></span>

3. <span data-ttu-id="5dc4a-123">コンポーネントに必要なその他のプロパティを構成します。</span><span class="sxs-lookup"><span data-stu-id="5dc4a-123">Configure any other necessary properties for your component.</span></span>

     <span data-ttu-id="5dc4a-124">次のコードは、プロパティセットを使用したの作成を示して <xref:System.Windows.Forms.Timer> `Interval` います。</span><span class="sxs-lookup"><span data-stu-id="5dc4a-124">The following code shows the creation of a <xref:System.Windows.Forms.Timer> with its `Interval` property set.</span></span>

    ```vb
    Public Sub CreateTimer()
       Dim timerKeepTrack As New System.Windows.Forms.Timer
       timerKeepTrack.Interval = 1000
    End Sub
    ```

    ```csharp
    public void createTimer()
    {
       System.Windows.Forms.Timer timerKeepTrack = new
           System.Windows.Forms.Timer();
       timerKeepTrack.Interval = 1000;
    }
    ```

    ```cpp
    public:
       void createTimer()
       {
          System::Windows::Forms::Timer^ timerKeepTrack = gcnew
             System::Windows::Forms::Timer();
          timerKeepTrack->Interval = 1000;
       }
    ```

    > [!IMPORTANT]
    > <span data-ttu-id="5dc4a-125">悪意のある UserControl を参照することにより、ネットワーク経由でローカルコンピューターをセキュリティ上のリスクにさらすことがあります。</span><span class="sxs-lookup"><span data-stu-id="5dc4a-125">You might expose your local computer to a security risk through the network by referencing a malicious UserControl.</span></span> <span data-ttu-id="5dc4a-126">これは、悪意のあるユーザーが有害なカスタムコントロールを作成した後、誤ってプロジェクトに追加した場合にのみ問題になります。</span><span class="sxs-lookup"><span data-stu-id="5dc4a-126">This would only be a concern in the case of a malicious person creating a damaging custom control, followed by you mistakenly adding it to your project.</span></span>

## <a name="see-also"></a><span data-ttu-id="5dc4a-127">関連項目</span><span class="sxs-lookup"><span data-stu-id="5dc4a-127">See also</span></span>

- [<span data-ttu-id="5dc4a-128">Windows フォームコントロール</span><span class="sxs-lookup"><span data-stu-id="5dc4a-128">Windows Forms Controls</span></span>](index.md)
- [<span data-ttu-id="5dc4a-129">方法: Windows フォームにコントロールを追加する</span><span class="sxs-lookup"><span data-stu-id="5dc4a-129">How to: Add Controls to Windows Forms</span></span>](how-to-add-controls-to-windows-forms.md)
- [<span data-ttu-id="5dc4a-130">方法: Windows フォームに ActiveX コントロールを追加する</span><span class="sxs-lookup"><span data-stu-id="5dc4a-130">How to: Add ActiveX Controls to Windows Forms</span></span>](how-to-add-activex-controls-to-windows-forms.md)
- [<span data-ttu-id="5dc4a-131">Windows フォームへのコントロールの追加</span><span class="sxs-lookup"><span data-stu-id="5dc4a-131">Putting Controls on Windows Forms</span></span>](putting-controls-on-windows-forms.md)
- [<span data-ttu-id="5dc4a-132">各 Windows フォーム コントロールのラベル設定とショートカットの作成</span><span class="sxs-lookup"><span data-stu-id="5dc4a-132">Labeling Individual Windows Forms Controls and Providing Shortcuts to Them</span></span>](labeling-individual-windows-forms-controls-and-providing-shortcuts-to-them.md)
- [<span data-ttu-id="5dc4a-133">Windows フォームで使用するコントロール</span><span class="sxs-lookup"><span data-stu-id="5dc4a-133">Controls to Use on Windows Forms</span></span>](controls-to-use-on-windows-forms.md)
- [<span data-ttu-id="5dc4a-134">Windows フォーム コントロールの機能別一覧</span><span class="sxs-lookup"><span data-stu-id="5dc4a-134">Windows Forms Controls by Function</span></span>](windows-forms-controls-by-function.md)
