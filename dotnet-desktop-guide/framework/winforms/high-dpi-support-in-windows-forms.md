---
title: 高 DPI サポート
description: 一般的な高 DPI および動的 DPI シナリオでの Windows フォームのサポートについて説明します。 また、高 DPI サポート用に Windows フォームアプリケーションを構成する方法についても説明します。
ms.date: 05/16/2017
helpviewer_keywords:
- High DPI in Windows Forms
- Dynamic rescaling in Windows Forms
- Windows Forms layout
- Windows Forms dynamic resizing
ms.assetid: 075ea4c3-900c-4f8a-9dd2-13ea6804346b
ms.openlocfilehash: e0e61a296003343d6e5da4b8ab242995555240af
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/09/2020
ms.locfileid: "96983523"
---
# <a name="high-dpi-support-in-windows-forms"></a><span data-ttu-id="f7fe0-104">Windows フォームでの高 DPI サポート</span><span class="sxs-lookup"><span data-stu-id="f7fe0-104">High DPI support in Windows Forms</span></span>

<span data-ttu-id="f7fe0-105">.NET Framework 4.7 以降の Windows フォームには、一般的な高 DPI および動的 DPI シナリオの機能強化が含まれています。</span><span class="sxs-lookup"><span data-stu-id="f7fe0-105">Starting with the .NET Framework 4.7, Windows Forms includes enhancements for common high DPI and dynamic DPI scenarios.</span></span> <span data-ttu-id="f7fe0-106">これには以下が含まれます。</span><span class="sxs-lookup"><span data-stu-id="f7fe0-106">These include:</span></span>

- <span data-ttu-id="f7fe0-107">コントロールやコントロールなど、多数の Windows フォームコントロールのスケーリングとレイアウトの機能強化 <xref:System.Windows.Forms.MonthCalendar> <xref:System.Windows.Forms.CheckedListBox> 。</span><span class="sxs-lookup"><span data-stu-id="f7fe0-107">Improvements in the scaling and layout of a number of Windows Forms controls, such as the <xref:System.Windows.Forms.MonthCalendar> control and the <xref:System.Windows.Forms.CheckedListBox> control.</span></span>

- <span data-ttu-id="f7fe0-108">シングルパススケーリング。</span><span class="sxs-lookup"><span data-stu-id="f7fe0-108">Single-pass scaling.</span></span>  <span data-ttu-id="f7fe0-109">.NET Framework 4.6 以前のバージョンでは、複数のパスによってスケーリングが実行され、いくつかのコントロールが必要以上に拡大縮小されました。</span><span class="sxs-lookup"><span data-stu-id="f7fe0-109">In the .NET Framework 4.6 and earlier versions, scaling was performed through multiple passes, which caused some controls to be scaled more than was necessary.</span></span>

- <span data-ttu-id="f7fe0-110">Windows フォームアプリケーションの起動後にユーザーが DPI またはスケールファクターを変更する動的な DPI シナリオのサポート。</span><span class="sxs-lookup"><span data-stu-id="f7fe0-110">Support for dynamic DPI scenarios in which the user changes the DPI or scale factor after a Windows Forms application has been launched.</span></span>

<span data-ttu-id="f7fe0-111">.NET Framework 4.7 以降の .NET Framework のバージョンでは、強化された高 DPI サポートはオプトイン機能です。</span><span class="sxs-lookup"><span data-stu-id="f7fe0-111">In versions of the .NET Framework starting with the .NET Framework 4.7, enhanced high DPI support is an opt-in feature.</span></span> <span data-ttu-id="f7fe0-112">アプリケーションを利用するように構成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="f7fe0-112">You must configure your application to take advantage of it.</span></span>

## <a name="configuring-your-windows-forms-app-for-high-dpi-support"></a><span data-ttu-id="f7fe0-113">高 DPI サポート用の Windows フォームアプリの構成</span><span class="sxs-lookup"><span data-stu-id="f7fe0-113">Configuring your Windows Forms app for high DPI support</span></span>

<span data-ttu-id="f7fe0-114">高 DPI 認識をサポートする新しい Windows フォーム機能は、.NET Framework 4.7 を対象とし、Windows 10 の作成者の更新プログラム以降で Windows オペレーティングシステムで実行されているアプリケーションでのみ使用できます。</span><span class="sxs-lookup"><span data-stu-id="f7fe0-114">The new Windows Forms features that support high DPI awareness are available only in applications that target the .NET Framework 4.7 and are running on Windows operating systems starting with the Windows 10 Creators Update.</span></span>

<span data-ttu-id="f7fe0-115">さらに、Windows フォームアプリケーションで高 DPI サポートを構成するには、次の操作を行う必要があります。</span><span class="sxs-lookup"><span data-stu-id="f7fe0-115">In addition, to configure high DPI support in your Windows Forms application, you must do the following:</span></span>

- <span data-ttu-id="f7fe0-116">Windows 10 との互換性を宣言します。</span><span class="sxs-lookup"><span data-stu-id="f7fe0-116">Declare compatibility with Windows 10.</span></span>

  <span data-ttu-id="f7fe0-117">これを行うには、マニフェストファイルに次のを追加します。</span><span class="sxs-lookup"><span data-stu-id="f7fe0-117">To do this, add the following to your manifest file:</span></span>

  ```xml
  <compatibility xmlns="urn:schemas-microsoft-com:compatibility.v1">
    <application>
      <!-- Windows 10 compatibility -->
      <supportedOS Id="{8e0f7a12-bfb3-4fe8-b9a5-48fd50a15a9a}" />
    </application>
  </compatibility>
  ```

- <span data-ttu-id="f7fe0-118">*app.config* ファイルでモニターごとの DPI 認識を有効にします。</span><span class="sxs-lookup"><span data-stu-id="f7fe0-118">Enable per-monitor DPI awareness in the *app.config* file.</span></span>

  <span data-ttu-id="f7fe0-119">Windows フォーム [`<System.Windows.Forms.ApplicationConfigurationSection>`](/dotnet/framework/configure-apps/file-schema/winforms/index) では、.NET Framework 4.7 以降に追加された新しい機能とカスタマイズをサポートする新しい要素が導入されています。</span><span class="sxs-lookup"><span data-stu-id="f7fe0-119">Windows Forms introduces a new [`<System.Windows.Forms.ApplicationConfigurationSection>`](/dotnet/framework/configure-apps/file-schema/winforms/index) element to support new features and customizations added starting with the .NET Framework 4.7.</span></span> <span data-ttu-id="f7fe0-120">高 DPI をサポートする新機能を利用するには、アプリケーション構成ファイルに次の内容を追加します。</span><span class="sxs-lookup"><span data-stu-id="f7fe0-120">To take advantage of the new features that support high DPI, add the following to your application configuration file.</span></span>

  ```xml
  <System.Windows.Forms.ApplicationConfigurationSection>
    <add key="DpiAwareness" value="PerMonitorV2" />
  </System.Windows.Forms.ApplicationConfigurationSection>
  ```

  > [!IMPORTANT]
  > <span data-ttu-id="f7fe0-121">以前のバージョンの .NET Framework では、マニフェストを使用して高 DPI サポートを追加していました。</span><span class="sxs-lookup"><span data-stu-id="f7fe0-121">In previous versions of the .NET Framework, you used the manifest to add high DPI support.</span></span> <span data-ttu-id="f7fe0-122">app.config ファイルで定義されている設定を上書きするため、この方法は推奨されなくなりました。</span><span class="sxs-lookup"><span data-stu-id="f7fe0-122">This approach is no longer recommended, since it overrides settings defined on the app.config file.</span></span>

- <span data-ttu-id="f7fe0-123">静的メソッドを呼び出し <xref:System.Windows.Forms.Application.EnableVisualStyles%2A> ます。</span><span class="sxs-lookup"><span data-stu-id="f7fe0-123">Call the static <xref:System.Windows.Forms.Application.EnableVisualStyles%2A> method.</span></span>

  <span data-ttu-id="f7fe0-124">これは、アプリケーションのエントリポイントの最初のメソッド呼び出しである必要があります。</span><span class="sxs-lookup"><span data-stu-id="f7fe0-124">This should be the first method call in your application entry point.</span></span> <span data-ttu-id="f7fe0-125">次に例を示します。</span><span class="sxs-lookup"><span data-stu-id="f7fe0-125">For example:</span></span>

  ```csharp
  static void Main()
  {
      Application.EnableVisualStyles();
      Application.SetCompatibleTextRenderingDefault(false);
      Application.Run(new Form2());
  }
  ```

## <a name="opting-out-of-individual-high-dpi-features"></a><span data-ttu-id="f7fe0-126">個々の高 DPI 機能のオプトアウト</span><span class="sxs-lookup"><span data-stu-id="f7fe0-126">Opting out of individual high DPI features</span></span>

<span data-ttu-id="f7fe0-127">`DpiAwareness`値をに設定 `PerMonitorV2` すると、.NET Framework 4.7 以降の .NET Framework バージョンでサポートされているすべての高 DPI 認識機能が有効になります。</span><span class="sxs-lookup"><span data-stu-id="f7fe0-127">Setting the `DpiAwareness` value to `PerMonitorV2` enables all high DPI awareness features supported by .NET Framework versions starting with the .NET Framework 4.7.</span></span> <span data-ttu-id="f7fe0-128">通常、これはほとんどの Windows フォームアプリケーションに適しています。</span><span class="sxs-lookup"><span data-stu-id="f7fe0-128">Typically, this is adequate for most Windows Forms applications.</span></span> <span data-ttu-id="f7fe0-129">ただし、1つまたは複数の個別の機能を無効にすることもできます。</span><span class="sxs-lookup"><span data-stu-id="f7fe0-129">However, you may want to opt out of one or more individual features.</span></span> <span data-ttu-id="f7fe0-130">これを行う最も重要な理由は、既存のアプリケーションコードで既にその機能が処理されていることです。</span><span class="sxs-lookup"><span data-stu-id="f7fe0-130">The most important reason for doing this is that your existing application code already handles that feature.</span></span>  <span data-ttu-id="f7fe0-131">たとえば、アプリケーションで自動スケーリングを処理する場合は、次のように自動サイズ変更機能を無効にすることをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="f7fe0-131">For example, if your application handles auto scaling, you might want to disable the auto-resizing feature as follows:</span></span>

```xml
<System.Windows.Forms.ApplicationConfigurationSection>
  <add key="DpiAwareness" value="PerMonitorV2" />
  <add key="EnableWindowsFormsHighDpiAutoResizing" value="false" />
</System.Windows.Forms.ApplicationConfigurationSection>
```

<span data-ttu-id="f7fe0-132">個々のキーとその値の一覧については、「 [Windows フォーム Add Configuration 要素](/dotnet/framework/configure-apps/file-schema/winforms/windows-forms-add-configuration-element)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="f7fe0-132">For a list of individual keys and their values, see [Windows Forms Add Configuration Element](/dotnet/framework/configure-apps/file-schema/winforms/windows-forms-add-configuration-element).</span></span>

## <a name="new-dpi-change-events"></a><span data-ttu-id="f7fe0-133">新しい DPI 変更イベント</span><span class="sxs-lookup"><span data-stu-id="f7fe0-133">New DPI change events</span></span>

<span data-ttu-id="f7fe0-134">.NET Framework 4.7 以降では、次の3つの新しいイベントを使用して、動的な DPI 変更をプログラムで処理できます。</span><span class="sxs-lookup"><span data-stu-id="f7fe0-134">Starting with the .NET Framework 4.7, three new events allow you to programmatically handle dynamic DPI changes:</span></span>

- <span data-ttu-id="f7fe0-135"><xref:System.Windows.Forms.Control.DpiChangedAfterParent>。親コントロールまたはフォームの DPI 変更イベントが発生した後に、コントロールの DPI 設定がプログラムによって変更されたときに発生します。</span><span class="sxs-lookup"><span data-stu-id="f7fe0-135"><xref:System.Windows.Forms.Control.DpiChangedAfterParent>, which is fired when the DPI setting for a control is changed programmatically after a DPI change event for it's parent control or form has occurred.</span></span>
- <span data-ttu-id="f7fe0-136"><xref:System.Windows.Forms.Control.DpiChangedBeforeParent>。親コントロールまたはフォームの DPI 変更イベントが発生する前に、コントロールの DPI 設定がプログラムによって変更されたときに発生します。</span><span class="sxs-lookup"><span data-stu-id="f7fe0-136"><xref:System.Windows.Forms.Control.DpiChangedBeforeParent>, which is fired when the DPI setting for a control is changed programmatically before a DPI change event for its parent control or form has occurred.</span></span>
- <span data-ttu-id="f7fe0-137"><xref:System.Windows.Forms.Form.DpiChanged>。フォームが現在表示されているディスプレイデバイスで DPI 設定が変更されたときに発生します。</span><span class="sxs-lookup"><span data-stu-id="f7fe0-137"><xref:System.Windows.Forms.Form.DpiChanged>, which is fired when the DPI setting changes on the display device where the form is currently displayed.</span></span>

## <a name="new-helper-methods-and-properties"></a><span data-ttu-id="f7fe0-138">新しいヘルパーメソッドとプロパティ</span><span class="sxs-lookup"><span data-stu-id="f7fe0-138">New helper methods and properties</span></span>

<span data-ttu-id="f7fe0-139">また、.NET Framework 4.7 では、DPI スケーリングに関する情報を提供し、DPI スケーリングを実行できる新しいヘルパーメソッドとプロパティが多数追加されています。</span><span class="sxs-lookup"><span data-stu-id="f7fe0-139">The .NET Framework 4.7 also adds a number of new helper methods and properties that provide information about DPI scaling and allow you to perform DPI scaling.</span></span> <span data-ttu-id="f7fe0-140">これには以下が含まれます。</span><span class="sxs-lookup"><span data-stu-id="f7fe0-140">These include:</span></span>

- <span data-ttu-id="f7fe0-141"><xref:System.Windows.Forms.Control.LogicalToDeviceUnits%2A>。値を論理ピクセルからデバイスピクセルに変換します。</span><span class="sxs-lookup"><span data-stu-id="f7fe0-141"><xref:System.Windows.Forms.Control.LogicalToDeviceUnits%2A>, which converts a value from logical to device pixels.</span></span>

- <span data-ttu-id="f7fe0-142"><xref:System.Windows.Forms.Control.ScaleBitmapLogicalToDevice%2A>。ビットマップイメージをデバイスの論理 DPI にスケーリングします。</span><span class="sxs-lookup"><span data-stu-id="f7fe0-142"><xref:System.Windows.Forms.Control.ScaleBitmapLogicalToDevice%2A>, which scales a bitmap image to the logical DPI for a device.</span></span>

- <span data-ttu-id="f7fe0-143"><xref:System.Windows.Forms.Control.DeviceDpi%2A>。現在のデバイスの DPI を返します。</span><span class="sxs-lookup"><span data-stu-id="f7fe0-143"><xref:System.Windows.Forms.Control.DeviceDpi%2A>, which returns the DPI for the current device.</span></span>

## <a name="versioning-considerations"></a><span data-ttu-id="f7fe0-144">バージョン管理に関する考慮事項</span><span class="sxs-lookup"><span data-stu-id="f7fe0-144">Versioning considerations</span></span>

<span data-ttu-id="f7fe0-145">.NET Framework 4.7 と Windows 10 の作成者の更新プログラムで実行するだけでなく、アプリケーションも高 DPI の機能強化と互換性のない環境で実行される場合があります。</span><span class="sxs-lookup"><span data-stu-id="f7fe0-145">In addition to running on .NET Framework 4.7 and Windows 10 Creators Update, your application may also run in an environment in which it isn't compatible with high DPI improvements.</span></span> <span data-ttu-id="f7fe0-146">この場合、アプリケーションのフォールバックを開発する必要があります。</span><span class="sxs-lookup"><span data-stu-id="f7fe0-146">In this case, you'll need to develop a fallback for your application.</span></span> <span data-ttu-id="f7fe0-147">これを行うと、スケーリングを処理する [カスタム描画](./controls/user-drawn-controls.md) を実行できます。</span><span class="sxs-lookup"><span data-stu-id="f7fe0-147">You can do this to perform [custom drawing](./controls/user-drawn-controls.md) to handle scaling.</span></span>

<span data-ttu-id="f7fe0-148">これを行うには、アプリが実行されているオペレーティングシステムを特定する必要もあります。</span><span class="sxs-lookup"><span data-stu-id="f7fe0-148">To do this, you also need to determine the operating system on which your app is running.</span></span> <span data-ttu-id="f7fe0-149">そのためには、次のようなコードを使用します。</span><span class="sxs-lookup"><span data-stu-id="f7fe0-149">You can do that with code like the following:</span></span>

```csharp
// Create a reference to the OS version of Windows 10 Creators Update.
Version OsMinVersion = new Version(10, 0, 15063, 0);

// Access the platform/version of the current OS.
Console.WriteLine(Environment.OSVersion.Platform.ToString());
Console.WriteLine(Environment.OSVersion.VersionString);

// Compare the current version to the minimum required version.
Console.WriteLine(Environment.OSVersion.Version.CompareTo(OsMinVersion));
```

<span data-ttu-id="f7fe0-150">アプリケーションマニフェストでサポートされているオペレーティングシステムとして表示されていない場合、アプリケーションが Windows 10 を正常に検出できないことに注意してください。</span><span class="sxs-lookup"><span data-stu-id="f7fe0-150">Note that your application won't successfully detect Windows 10 if it wasn't listed as a supported operating system in the application manifest.</span></span>

<span data-ttu-id="f7fe0-151">また、アプリケーションがビルドされた .NET Framework のバージョンを確認することもできます。</span><span class="sxs-lookup"><span data-stu-id="f7fe0-151">You can also check the version of the .NET Framework that the application was built against:</span></span>

```csharp
Console.WriteLine(AppDomain.CurrentDomain.SetupInformation.TargetFrameworkName);
```

## <a name="see-also"></a><span data-ttu-id="f7fe0-152">関連項目</span><span class="sxs-lookup"><span data-stu-id="f7fe0-152">See also</span></span>

- [<span data-ttu-id="f7fe0-153">構成要素の追加 Windows フォーム</span><span class="sxs-lookup"><span data-stu-id="f7fe0-153">Windows Forms Add Configuration Element</span></span>](/dotnet/framework/configure-apps/file-schema/winforms/windows-forms-add-configuration-element)
- [<span data-ttu-id="f7fe0-154">Windows フォームのサイズとスケールを調整する</span><span class="sxs-lookup"><span data-stu-id="f7fe0-154">Adjusting the Size and Scale of Windows Forms</span></span>](adjusting-the-size-and-scale-of-windows-forms.md)
