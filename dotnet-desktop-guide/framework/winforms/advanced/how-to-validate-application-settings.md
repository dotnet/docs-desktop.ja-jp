---
title: '方法: アプリケーション設定を検証する'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- validating application settings
- application settings [Windows Forms], Windows Forms
- application settings [Windows Forms], validating
ms.assetid: 9f145ada-4267-436a-aa4c-c4dcffd0afb7
ms.openlocfilehash: e2a364aacfbd1b6ac2542c5500380647a09a33ab
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/09/2020
ms.locfileid: "96981716"
---
# <a name="how-to-validate-application-settings"></a><span data-ttu-id="2e2c3-102">方法: アプリケーション設定を検証する</span><span class="sxs-lookup"><span data-stu-id="2e2c3-102">How to: Validate Application Settings</span></span>

<span data-ttu-id="2e2c3-103">このトピックでは、アプリケーション設定を永続化する前に検証する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="2e2c3-103">This topic demonstrates how to validate application settings before they are persisted.</span></span>

<span data-ttu-id="2e2c3-104">アプリケーション設定は厳密に型指定されているため、ユーザーが特定の設定に誤った型のデータを割り当てることはほとんどありません。</span><span class="sxs-lookup"><span data-stu-id="2e2c3-104">Because application settings are strongly typed, you have some confidence that users cannot assign data of an incorrect type to a given setting.</span></span> <span data-ttu-id="2e2c3-105">しかし、誕生日として未来の日付を入力するなど、ユーザーが許容範囲外の値を設定に割り当てようとする場合もあります。</span><span class="sxs-lookup"><span data-stu-id="2e2c3-105">However, a user still may attempt to assign a value to a setting that falls outside of acceptable bounds—for example, supplying a birth date that occurs in the future.</span></span> <span data-ttu-id="2e2c3-106"><xref:System.Configuration.ApplicationSettingsBase>は、すべてのアプリケーション設定クラスの親クラスであり、このような範囲チェックを有効にするために4つのイベントを公開します。</span><span class="sxs-lookup"><span data-stu-id="2e2c3-106"><xref:System.Configuration.ApplicationSettingsBase>, the parent class of all application settings classes, exposes four events to enable such bounds checking.</span></span> <span data-ttu-id="2e2c3-107">これらのイベントを処理すると、検証コードがプロジェクト全体に分散するのではなく、すべての検証コードが 1 か所に配置されます。</span><span class="sxs-lookup"><span data-stu-id="2e2c3-107">Handling these events puts all of your validation code in a single location, rather than scattering it throughout your project.</span></span>

<span data-ttu-id="2e2c3-108">次の表に示すように、使用するイベントは設定をいつ検証する必要があるかによって決まります。</span><span class="sxs-lookup"><span data-stu-id="2e2c3-108">The event you use depends upon when you need to validate your settings, as described in the following table.</span></span>

|<span data-ttu-id="2e2c3-109">Event</span><span class="sxs-lookup"><span data-stu-id="2e2c3-109">Event</span></span>|<span data-ttu-id="2e2c3-110">発生と使用</span><span class="sxs-lookup"><span data-stu-id="2e2c3-110">Occurrence and use</span></span>|
|-----------|------------------------|
|<xref:System.Configuration.ApplicationSettingsBase.SettingsLoaded>|<span data-ttu-id="2e2c3-111">設定プロパティ グループの初期読み込み後に発生します。</span><span class="sxs-lookup"><span data-stu-id="2e2c3-111">Occurs after the initial loading of a settings property group.</span></span><br /><br /> <span data-ttu-id="2e2c3-112">プロパティ グループ全体の初期値がアプリケーション内で使用される前に値を検証するには、このイベントを使用します。</span><span class="sxs-lookup"><span data-stu-id="2e2c3-112">Use this event to validate initial values for the entire property group before they are used within the application.</span></span>|
|<xref:System.Configuration.ApplicationSettingsBase.SettingChanging>|<span data-ttu-id="2e2c3-113">1 つの設定プロパティの値が変更される前に発生します。</span><span class="sxs-lookup"><span data-stu-id="2e2c3-113">Occurs before the value of a single settings property is changed.</span></span><br /><br /> <span data-ttu-id="2e2c3-114">1 つのプロパティが変更される前にプロパティを検証するには、このイベントを使用します。</span><span class="sxs-lookup"><span data-stu-id="2e2c3-114">Use this event to validate a single property before it is changed.</span></span> <span data-ttu-id="2e2c3-115">アクションと選択に関するフィードバックをユーザーにすぐに提供できます。</span><span class="sxs-lookup"><span data-stu-id="2e2c3-115">It can provide immediate feedback to users regarding their actions and choices.</span></span>|
|<xref:System.Configuration.ApplicationSettingsBase.PropertyChanged>|<span data-ttu-id="2e2c3-116">1 つの設定プロパティの値が変更された後に発生します。</span><span class="sxs-lookup"><span data-stu-id="2e2c3-116">Occurs after the value of a single settings property is changed.</span></span><br /><br /> <span data-ttu-id="2e2c3-117">1 つのプロパティが変更された後にプロパティを検証するには、このイベントを使用します。</span><span class="sxs-lookup"><span data-stu-id="2e2c3-117">Use this event to validate a single property after it is changed.</span></span> <span data-ttu-id="2e2c3-118">時間がかかる非同期の検証プロセスが必要な場合を除き、このイベントを検証に使用することはほとんどありません。</span><span class="sxs-lookup"><span data-stu-id="2e2c3-118">This event is rarely used for validation unless a lengthy, asynchronous validation process is required.</span></span>|
|<xref:System.Configuration.ApplicationSettingsBase.SettingsSaving>|<span data-ttu-id="2e2c3-119">設定プロパティ グループが保存される前に発生します。</span><span class="sxs-lookup"><span data-stu-id="2e2c3-119">Occurs before the settings property group is stored.</span></span><br /><br /> <span data-ttu-id="2e2c3-120">プロパティ グループ全体の値がディスクに永続化される前に値を検証するには、このイベントを使用します。</span><span class="sxs-lookup"><span data-stu-id="2e2c3-120">Use this event to validate values for the entire property group before they are persisted to disk.</span></span>|

<span data-ttu-id="2e2c3-121">通常は、検証のために同じアプリケーション内でこれらのイベントをすべて使用するわけではありません。</span><span class="sxs-lookup"><span data-stu-id="2e2c3-121">Typically, you will not use all of these events within the same application for validation purposes.</span></span> <span data-ttu-id="2e2c3-122">たとえば、イベントのみを処理することで、すべての検証要件を満たすことができ <xref:System.Configuration.ApplicationSettingsBase.SettingChanging> ます。</span><span class="sxs-lookup"><span data-stu-id="2e2c3-122">For example, it is often possible to fulfill all validation requirements by handling only the <xref:System.Configuration.ApplicationSettingsBase.SettingChanging> event.</span></span>

<span data-ttu-id="2e2c3-123">イベント ハンドラーは、無効な値を検出すると、一般に次のいずれかのアクションを実行します。</span><span class="sxs-lookup"><span data-stu-id="2e2c3-123">An event handler generally performs one of the following actions when it detects an invalid value:</span></span>

- <span data-ttu-id="2e2c3-124">既定値など、正しいことがわかっている値を自動的に入力します。</span><span class="sxs-lookup"><span data-stu-id="2e2c3-124">Automatically supplies a value known to be correct, such as the default value.</span></span>

- <span data-ttu-id="2e2c3-125">サーバー コードのユーザーに情報を再度照会します。</span><span class="sxs-lookup"><span data-stu-id="2e2c3-125">Re-queries the user of server code for information.</span></span>

- <span data-ttu-id="2e2c3-126">やなど、関連するアクションの前に発生するイベントの場合、引数を使用して <xref:System.Configuration.ApplicationSettingsBase.SettingChanging> <xref:System.Configuration.ApplicationSettingsBase.SettingsSaving> 操作を <xref:System.ComponentModel.CancelEventArgs> 取り消します。</span><span class="sxs-lookup"><span data-stu-id="2e2c3-126">For events raised before their associated actions, such as <xref:System.Configuration.ApplicationSettingsBase.SettingChanging> and <xref:System.Configuration.ApplicationSettingsBase.SettingsSaving>, uses the <xref:System.ComponentModel.CancelEventArgs> argument to cancel the operation.</span></span>

<span data-ttu-id="2e2c3-127">イベント処理の詳細については、「[イベント ハンドラーの概要](../event-handlers-overview-windows-forms.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="2e2c3-127">For more information about event handling, see [Event Handlers Overview](../event-handlers-overview-windows-forms.md).</span></span>

<span data-ttu-id="2e2c3-128">次の手順で <xref:System.Configuration.ApplicationSettingsBase.SettingChanging> は、イベントまたはイベントを使用して、有効な生年月日をテストする方法を示し <xref:System.Configuration.ApplicationSettingsBase.SettingsSaving> ます。</span><span class="sxs-lookup"><span data-stu-id="2e2c3-128">The following procedures show how to test for a valid birth date using either the <xref:System.Configuration.ApplicationSettingsBase.SettingChanging> or the <xref:System.Configuration.ApplicationSettingsBase.SettingsSaving> event.</span></span> <span data-ttu-id="2e2c3-129">これらの手順は、アプリケーション設定を既に作成していることを前提としています。この例では、`DateOfBirth` という名前の設定の範囲チェックを実行します。</span><span class="sxs-lookup"><span data-stu-id="2e2c3-129">The procedures were written under the assumption that you have already created your application settings; in this example, we will perform bounds checking on a setting named `DateOfBirth`.</span></span> <span data-ttu-id="2e2c3-130">設定を作成する方法の詳細については、「[方法 : アプリケーション設定を作成する](how-to-create-application-settings.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="2e2c3-130">For more information about creating settings, see [How to: Create Application Settings](how-to-create-application-settings.md).</span></span>

### <a name="to-obtain-the-application-settings-object"></a><span data-ttu-id="2e2c3-131">アプリケーション設定オブジェクトを取得するには</span><span class="sxs-lookup"><span data-stu-id="2e2c3-131">To obtain the application settings object</span></span>

- <span data-ttu-id="2e2c3-132">次の項目のいずれかを実行して、アプリケーション設定オブジェクト (ラッパー インスタンス) への参照を取得します。</span><span class="sxs-lookup"><span data-stu-id="2e2c3-132">Obtain a reference to the application settings object (the wrapper instance) by completing one of the following bulleted items:</span></span>

  - <span data-ttu-id="2e2c3-133">Visual Studio の **プロパティ エディター** で [アプリケーション設定] ダイアログ ボックスを使用して設定を作成した場合は、次の式によって、使用している言語用に生成された既定の設定オブジェクトを取得できます。</span><span class="sxs-lookup"><span data-stu-id="2e2c3-133">If you created your settings using the Visual Studio Application Settings dialog box in the **Property Editor**, you can retrieve the default settings object generated for your language through the following expression.</span></span>

    ```csharp
    Properties.Settings.Default
    ```

    ```vb
    MySettings.Default
    ```

    <span data-ttu-id="2e2c3-134">または</span><span class="sxs-lookup"><span data-stu-id="2e2c3-134">-or-</span></span>

  - <span data-ttu-id="2e2c3-135">Visual Basic 開発者がプロジェクト デザイナーを使用してアプリケーション設定を作成した場合は、[My.Settings オブジェクト](/dotnet/visual-basic/language-reference/objects/my-settings-object)を使用して設定を取得できます。</span><span class="sxs-lookup"><span data-stu-id="2e2c3-135">If you are a Visual Basic developer and you created your application settings using the Project Designer, you can retrieve your settings by using the [My.Settings Object](/dotnet/visual-basic/language-reference/objects/my-settings-object).</span></span>

    <span data-ttu-id="2e2c3-136">または</span><span class="sxs-lookup"><span data-stu-id="2e2c3-136">-or-</span></span>

  - <span data-ttu-id="2e2c3-137">から直接派生して設定を作成した場合は <xref:System.Configuration.ApplicationSettingsBase> 、クラスを手動でインスタンス化する必要があります。</span><span class="sxs-lookup"><span data-stu-id="2e2c3-137">If you created your settings by deriving from <xref:System.Configuration.ApplicationSettingsBase> directly, you need to instantiate your class manually.</span></span>

    ```csharp
    MyCustomSettings settings = new MyCustomSettings();
    ```

    ```vb
    Dim Settings as New MyCustomSettings()
    ```

<span data-ttu-id="2e2c3-138">以下の手順は、この手順の最後の項目を実行してアプリケーション設定オブジェクトを取得したことを前提としています。</span><span class="sxs-lookup"><span data-stu-id="2e2c3-138">The following procedures were written under the assumption that the application settings object was obtained by completing the last bulleted item in this procedure.</span></span>

### <a name="to-validate-application-settings-when-a-setting-is-changing"></a><span data-ttu-id="2e2c3-139">設定の変更時にアプリケーション設定を検証するには</span><span class="sxs-lookup"><span data-stu-id="2e2c3-139">To validate Application Settings when a setting is changing</span></span>

1. <span data-ttu-id="2e2c3-140">C# 開発者の場合は、フォームまたはコントロールのイベントで、 `Load` イベントのイベントハンドラーを追加し <xref:System.Configuration.ApplicationSettingsBase.SettingChanging> ます。</span><span class="sxs-lookup"><span data-stu-id="2e2c3-140">If you are a C# developer, in your form or control's `Load` event, add an event handler for the <xref:System.Configuration.ApplicationSettingsBase.SettingChanging> event.</span></span>

    <span data-ttu-id="2e2c3-141">または</span><span class="sxs-lookup"><span data-stu-id="2e2c3-141">-or-</span></span>

    <span data-ttu-id="2e2c3-142">Visual Basic 開発者の場合、`WithEvents` キーワードを使用して `Settings` 変数を宣言します。</span><span class="sxs-lookup"><span data-stu-id="2e2c3-142">If you are a Visual Basic developer, you should declare the `Settings` variable using the `WithEvents` keyword.</span></span>

    ```csharp
    public void Form1_Load(Object sender, EventArgs e)
    {
        settings.SettingChanging += new SettingChangingEventHandler(MyCustomSettings_SettingChanging);
    }
    ```

    ```vb
    Public Sub Form1_Load(sender as Object, e as EventArgs)
        AddHandler settings.SettingChanging, AddressOf MyCustomSettings_SettingChanging
    End Sub
    ```

2. <span data-ttu-id="2e2c3-143">イベント ハンドラーを定義し、誕生日の範囲チェックを実行するコードをイベント ハンドラー内に記述します。</span><span class="sxs-lookup"><span data-stu-id="2e2c3-143">Define the event handler, and write the code inside of it to perform bounds checking on the birth date.</span></span>

    ```csharp
    private void MyCustomSettings_SettingChanging(Object sender, SettingChangingEventArgs e)
    {
        if (e.SettingName.Equals("DateOfBirth"))
        {
            var newDate = (DateTime)e.NewValue;
            if (newDate > DateTime.Now)
            {
                e.Cancel = true;
                // Inform the user.
            }
        }
    }
    ```

    ```vb
    Private Sub MyCustomSettings_SettingChanging(sender as Object, e as SettingChangingEventArgs) Handles Settings.SettingChanging
        If (e.SettingName.Equals("DateOfBirth")) Then
            Dim NewDate as Date = CType(e.NewValue, Date)
            If (NewDate > Date.Now) Then
                e.Cancel = True
                ' Inform the user.
            End If
        End If
    End Sub
    ```

### <a name="to-validate-application-settings-when-a-save-occurs"></a><span data-ttu-id="2e2c3-144">保存時にアプリケーション設定を検証するには</span><span class="sxs-lookup"><span data-stu-id="2e2c3-144">To validate Application Settings when a Save occurs</span></span>

1. <span data-ttu-id="2e2c3-145">フォームまたはコントロールのイベントで、 `Load` イベントのイベントハンドラーを追加し <xref:System.Configuration.ApplicationSettingsBase.SettingsSaving> ます。</span><span class="sxs-lookup"><span data-stu-id="2e2c3-145">In your form or control's `Load` event, add an event handler for the <xref:System.Configuration.ApplicationSettingsBase.SettingsSaving> event.</span></span>

    ```csharp
    public void Form1_Load(Object sender, EventArgs e)
    {
        settings.SettingsSaving += new SettingsSavingEventHandler(MyCustomSettings_SettingsSaving);
    }
    ```

    ```vb
    Public Sub Form1_Load(Sender as Object, e as EventArgs)
        AddHandler settings.SettingsSaving, AddressOf MyCustomSettings_SettingsSaving
    End Sub
    ```

2. <span data-ttu-id="2e2c3-146">イベント ハンドラーを定義し、誕生日の範囲チェックを実行するコードをイベント ハンドラー内に記述します。</span><span class="sxs-lookup"><span data-stu-id="2e2c3-146">Define the event handler, and write the code inside of it to perform bounds checking on the birth date.</span></span>

    ```csharp
    private void MyCustomSettings_SettingsSaving(Object sender, SettingsSavingEventArgs e)
    {
        if (this["DateOfBirth"] > Date.Now) {
            e.Cancel = true;
        }
    }
    ```

    ```vb
    Private Sub MyCustomSettings_SettingsSaving(Sender as Object, e as SettingsSavingEventArgs)
        If (Me["DateOfBirth"] > Date.Now) Then
            e.Cancel = True
        End If
    End Sub
    ```

## <a name="see-also"></a><span data-ttu-id="2e2c3-147">関連項目</span><span class="sxs-lookup"><span data-stu-id="2e2c3-147">See also</span></span>

- [<span data-ttu-id="2e2c3-148">Windows フォーム内でのイベント ハンドラーの作成</span><span class="sxs-lookup"><span data-stu-id="2e2c3-148">Creating Event Handlers in Windows Forms</span></span>](../creating-event-handlers-in-windows-forms.md)
- [<span data-ttu-id="2e2c3-149">方法: アプリケーション設定を作成する</span><span class="sxs-lookup"><span data-stu-id="2e2c3-149">How to: Create Application Settings</span></span>](how-to-create-application-settings.md)
