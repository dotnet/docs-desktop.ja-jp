---
title: NotifyIcon コンポーネントを使用してアプリケーションアイコンをタスクバーに追加する
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
f1_keywords:
- TrayIcon
helpviewer_keywords:
- status area icons
- icons [Windows Forms], adding to taskbar
- NotifyIcon component
- taskbar [Windows Forms], adding icons
ms.assetid: d28c0fe6-aaf2-4df7-ad74-928d861a8510
ms.openlocfilehash: 46b50ecaabe75dba08fea922d7b5639031692269
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/09/2020
ms.locfileid: "96981099"
---
# <a name="how-to-add-application-icons-to-the-taskbar-with-the-windows-forms-notifyicon-component"></a><span data-ttu-id="eea8b-102">方法: Windows フォームの NotifyIcon コンポーネントによってタスクバーにアプリケーション アイコンを追加する</span><span class="sxs-lookup"><span data-stu-id="eea8b-102">How to: Add Application Icons to the TaskBar with the Windows Forms NotifyIcon Component</span></span>

<span data-ttu-id="eea8b-103">Windows フォームコンポーネントでは、 <xref:System.Windows.Forms.NotifyIcon> タスクバーの状態通知領域に1つのアイコンが表示されます。</span><span class="sxs-lookup"><span data-stu-id="eea8b-103">The Windows Forms <xref:System.Windows.Forms.NotifyIcon> component displays a single icon in the status notification area of the taskbar.</span></span> <span data-ttu-id="eea8b-104">状態領域に複数のアイコンを表示するには、 <xref:System.Windows.Forms.NotifyIcon> フォームに複数のコンポーネントが必要です。</span><span class="sxs-lookup"><span data-stu-id="eea8b-104">To display multiple icons in the status area, you must have multiple <xref:System.Windows.Forms.NotifyIcon> components on your form.</span></span> <span data-ttu-id="eea8b-105">コントロールに対して表示されるアイコンを設定するには、プロパティを使用し <xref:System.Windows.Forms.NotifyIcon.Icon%2A> ます。</span><span class="sxs-lookup"><span data-stu-id="eea8b-105">To set the icon displayed for a control, use the <xref:System.Windows.Forms.NotifyIcon.Icon%2A> property.</span></span> <span data-ttu-id="eea8b-106">また、 <xref:System.Windows.Forms.NotifyIcon.DoubleClick> ユーザーがアイコンをダブルクリックしたときに何かが発生するように、イベントハンドラーにコードを記述することもできます。</span><span class="sxs-lookup"><span data-stu-id="eea8b-106">You can also write code in the <xref:System.Windows.Forms.NotifyIcon.DoubleClick> event handler so that something happens when the user double-clicks the icon.</span></span> <span data-ttu-id="eea8b-107">たとえば、アイコンによって表されるバックグラウンドプロセスをユーザーが構成するためのダイアログボックスを表示することができます。</span><span class="sxs-lookup"><span data-stu-id="eea8b-107">For example, you could make a dialog box appear for the user to configure the background process represented by the icon.</span></span>

> [!NOTE]
> <span data-ttu-id="eea8b-108">この <xref:System.Windows.Forms.NotifyIcon> コンポーネントは、通知の目的でのみ使用され、アクションまたはイベントが発生したこと、または何らかの種類の状態が変更されたことをユーザーに警告します。</span><span class="sxs-lookup"><span data-stu-id="eea8b-108">The <xref:System.Windows.Forms.NotifyIcon> component is used for notification purposes only, to alert users that an action or event has occurred or there has been a change in status of some sort.</span></span> <span data-ttu-id="eea8b-109">アプリケーションとの標準的な対話には、メニュー、ツールバー、およびその他のユーザーインターフェイス要素を使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="eea8b-109">You should use menus, toolbars, and other user-interface elements for standard interaction with applications.</span></span>

### <a name="to-set-the-icon"></a><span data-ttu-id="eea8b-110">アイコンを設定するには</span><span class="sxs-lookup"><span data-stu-id="eea8b-110">To set the icon</span></span>

1. <span data-ttu-id="eea8b-111">プロパティに値を割り当て <xref:System.Windows.Forms.NotifyIcon.Icon%2A> ます。</span><span class="sxs-lookup"><span data-stu-id="eea8b-111">Assign a value to the <xref:System.Windows.Forms.NotifyIcon.Icon%2A> property.</span></span> <span data-ttu-id="eea8b-112">値は型である必要があり、 `System.Drawing.Icon` .ico ファイルから読み込むことができます。</span><span class="sxs-lookup"><span data-stu-id="eea8b-112">The value must be of type `System.Drawing.Icon` and can be loaded from an .ico file.</span></span> <span data-ttu-id="eea8b-113">アイコンファイルをコードで指定するか、 ![ [プロパティ] ウィンドウでプロパティの横にある省略記号ボタン ([.. プロパティウィンドウ.]) をクリックして、 ](./media/visual-studio-ellipsis-button.png) <xref:System.Windows.Forms.NotifyIcon.Icon%2A> 表示される [**開く**] ダイアログボックスでファイルを選択します。</span><span class="sxs-lookup"><span data-stu-id="eea8b-113">You can specify the icon file in code or by clicking the ellipsis button (![The Ellipsis button (...) in the Properties window of Visual Studio.](./media/visual-studio-ellipsis-button.png)) next to the <xref:System.Windows.Forms.NotifyIcon.Icon%2A> property in the **Properties** window, and then selecting the file in the **Open** dialog box that appears.</span></span>

2. <span data-ttu-id="eea8b-114"><xref:System.Windows.Forms.NotifyIcon.Visible%2A> プロパティを `true`に設定します。</span><span class="sxs-lookup"><span data-stu-id="eea8b-114">Set the <xref:System.Windows.Forms.NotifyIcon.Visible%2A> property to `true`.</span></span>

3. <span data-ttu-id="eea8b-115"><xref:System.Windows.Forms.NotifyIcon.Text%2A>プロパティを適切なツールヒント文字列に設定します。</span><span class="sxs-lookup"><span data-stu-id="eea8b-115">Set the <xref:System.Windows.Forms.NotifyIcon.Text%2A> property to an appropriate ToolTip string.</span></span>

     <span data-ttu-id="eea8b-116">次のコード例では、アイコンの場所に設定されているパスが **[マイドキュメント** ] フォルダーです。</span><span class="sxs-lookup"><span data-stu-id="eea8b-116">In the following code example, the path set for the location of the icon is the **My Documents** folder.</span></span> <span data-ttu-id="eea8b-117">この場所は、Windows オペレーティングシステムを実行しているほとんどのコンピューターにこのフォルダーを含めることを前提としているために使用されます。</span><span class="sxs-lookup"><span data-stu-id="eea8b-117">This location is used because you can assume that most computers running the Windows operating system will include this folder.</span></span> <span data-ttu-id="eea8b-118">また、この場所を選択すると、最小限のシステムアクセスレベルのユーザーがアプリケーションを安全に実行できるようになります。</span><span class="sxs-lookup"><span data-stu-id="eea8b-118">Choosing this location also enables users with minimal system access levels to safely run the application.</span></span> <span data-ttu-id="eea8b-119">次の例では、コントロールが <xref:System.Windows.Forms.NotifyIcon> 既に追加されているフォームが必要です。</span><span class="sxs-lookup"><span data-stu-id="eea8b-119">The following example requires a form with a <xref:System.Windows.Forms.NotifyIcon> control already added.</span></span> <span data-ttu-id="eea8b-120">また、という名前のアイコンファイルも必要です `Icon.ico` 。</span><span class="sxs-lookup"><span data-stu-id="eea8b-120">It also requires an icon file named `Icon.ico`.</span></span>

    ```vb
    ' You should replace the bold icon in the sample below
    ' with an icon of your own choosing.
    NotifyIcon1.Icon = New _
       System.Drawing.Icon(System.Environment.GetFolderPath _
       (System.Environment.SpecialFolder.Personal) _
       & "\Icon.ico")
    NotifyIcon1.Visible = True
    NotifyIcon1.Text = "Antivirus program"
    ```

    ```csharp
    // You should replace the bold icon in the sample below
    // with an icon of your own choosing.
    // Note the escape character used (@) when specifying the path.
    notifyIcon1.Icon =
       new System.Drawing.Icon (System.Environment.GetFolderPath
       (System.Environment.SpecialFolder.Personal)
       + @"\Icon.ico");
    notifyIcon1.Visible = true;
    notifyIcon1.Text = "Antivirus program";
    ```

    ```cpp
    // You should replace the bold icon in the sample below
    // with an icon of your own choosing.
    notifyIcon1->Icon = gcnew
       System::Drawing::Icon(String::Concat
       (System::Environment::GetFolderPath
       (System::Environment::SpecialFolder::Personal),
       "\\Icon.ico"));
    notifyIcon1->Visible = true;
    notifyIcon1->Text = "Antivirus program";
    ```

## <a name="see-also"></a><span data-ttu-id="eea8b-121">関連項目</span><span class="sxs-lookup"><span data-stu-id="eea8b-121">See also</span></span>

- <xref:System.Windows.Forms.NotifyIcon>
- <xref:System.Windows.Forms.NotifyIcon.Icon%2A>
- [<span data-ttu-id="eea8b-122">方法: ショートカット メニューを Windows フォーム NotifyIcon コンポーネントに関連付ける</span><span class="sxs-lookup"><span data-stu-id="eea8b-122">How to: Associate a Shortcut Menu with a Windows Forms NotifyIcon Component</span></span>](how-to-associate-a-shortcut-menu-with-a-windows-forms-notifyicon-component.md)
- [<span data-ttu-id="eea8b-123">NotifyIcon コンポーネント</span><span class="sxs-lookup"><span data-stu-id="eea8b-123">NotifyIcon Component</span></span>](notifyicon-component-windows-forms.md)
- [<span data-ttu-id="eea8b-124">NotifyIcon コンポーネントの概要</span><span class="sxs-lookup"><span data-stu-id="eea8b-124">NotifyIcon Component Overview</span></span>](notifyicon-component-overview-windows-forms.md)
