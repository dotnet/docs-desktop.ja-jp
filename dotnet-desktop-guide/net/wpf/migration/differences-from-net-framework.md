---
title: .NET Framework と .NET の相違点
description: Windows Presentation Foundation (WPF) の .NET Framework の実装と .NET の WPF との相違点について説明します。 アプリを移行するときは、次の非互換性について考慮する必要があります。
author: adegeo
ms.date: 09/21/2019
ms.author: adegeo
ms.topic: conceptual
ms.openlocfilehash: e722faf2adb15966d62cb4a31efd60cf0d26b2a6
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/09/2020
ms.locfileid: "96942367"
---
# <a name="differences-in-wpf-net"></a><span data-ttu-id="2a86c-104">WPF .NET の相違点</span><span class="sxs-lookup"><span data-stu-id="2a86c-104">Differences in WPF .NET</span></span>

<span data-ttu-id="2a86c-105">この記事では、.NET Core と .NET Framework での Windows Presentation Foundation (WPF) の違いについて説明します。</span><span class="sxs-lookup"><span data-stu-id="2a86c-105">This article describes the differences between Windows Presentation Foundation (WPF) on .NET Core and .NET Framework.</span></span> <span data-ttu-id="2a86c-106">.NET Core の WPF は、.NET Framework ソース コードの元の WPF からフォークされた [オープンソース フレームワーク](https://github.com/dotnet/wpf)です。</span><span class="sxs-lookup"><span data-stu-id="2a86c-106">WPF for .NET Core is an [open-source framework](https://github.com/dotnet/wpf) forked from the original WPF for .NET Framework source code.</span></span>

<span data-ttu-id="2a86c-107">.NET Framework の機能のうち、.NET Core ではサポートされないものがいくつかあります。</span><span class="sxs-lookup"><span data-stu-id="2a86c-107">There are a few features of .NET Framework that .NET Core doesn't support.</span></span> <span data-ttu-id="2a86c-108">サポートされないテクノロジの詳細については、「[.NET Core で使用できない .NET Framework テクノロジ](/dotnet/core/porting/net-framework-tech-unavailable)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="2a86c-108">For more information on unsupported technologies, see [.NET Framework technologies unavailable on .NET Core](/dotnet/core/porting/net-framework-tech-unavailable).</span></span>

[!INCLUDE [desktop guide under construction](../../includes/desktop-guide-preview-note.md)]

## <a name="sdk-style-projects"></a><span data-ttu-id="2a86c-109">SDK スタイルのプロジェクト</span><span class="sxs-lookup"><span data-stu-id="2a86c-109">SDK-style projects</span></span>

<span data-ttu-id="2a86c-110">.NET Core では、SDK スタイルのプロジェクト ファイルが使用されます。</span><span class="sxs-lookup"><span data-stu-id="2a86c-110">.NET Core uses SDK-style project files.</span></span> <span data-ttu-id="2a86c-111">これらのプロジェクト ファイルは、Visual Studio によって管理される従来の .NET Framework プロジェクト ファイルとは異なります。</span><span class="sxs-lookup"><span data-stu-id="2a86c-111">These project files are different from the traditional .NET Framework project files managed by Visual Studio.</span></span> <span data-ttu-id="2a86c-112">.NET Framework の WPF アプリを .NET Core に移行するには、プロジェクトを変換する必要があります。</span><span class="sxs-lookup"><span data-stu-id="2a86c-112">To migrate your .NET Framework WPF apps to .NET Core, you must convert your projects.</span></span> <span data-ttu-id="2a86c-113">詳細については、「[.NET Core 3.0 への WPF アプリの移行](convert-project-from-net-framework.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="2a86c-113">For more information, see [Migrate WPF apps to .NET Core 3.0](convert-project-from-net-framework.md).</span></span>

## <a name="nuget-package-references"></a><span data-ttu-id="2a86c-114">NuGet パッケージのリファレンス</span><span class="sxs-lookup"><span data-stu-id="2a86c-114">NuGet package references</span></span>

<span data-ttu-id="2a86c-115">.NET Framework アプリで *packages.config* ファイルに NuGet の依存関係が一覧表示されている場合は、[`<PackageReference>`](/nuget/consume-packages/package-references-in-project-files) 形式に移行します。</span><span class="sxs-lookup"><span data-stu-id="2a86c-115">If your .NET Framework app lists its NuGet dependencies in a *packages.config* file, migrate to the [`<PackageReference>`](/nuget/consume-packages/package-references-in-project-files) format:</span></span>

1. <span data-ttu-id="2a86c-116">Visual Studio で、 **[ソリューション エクスプローラー]** ペインを開きます。</span><span class="sxs-lookup"><span data-stu-id="2a86c-116">In Visual Studio, open the **Solution Explorer** pane.</span></span>
1. <span data-ttu-id="2a86c-117">WPF プロジェクトで、右クリックで **[packages.config]**  >  **[packages.config を PackageReference に移行する]** と進みます。</span><span class="sxs-lookup"><span data-stu-id="2a86c-117">In your WPF project, right-click **packages.config** > **Migrate packages.config to PackageReference**.</span></span>

![PackageReference へのアップグレード](media/differences-from-net-framework/package-reference-migration.png)

<span data-ttu-id="2a86c-119">計算された最上位の NuGet 依存関係を表示し、他のどの NuGet パッケージを最上位に昇格する必要があるかを尋ねるダイアログが表示されます。</span><span class="sxs-lookup"><span data-stu-id="2a86c-119">A dialog will appear showing calculated top-level NuGet dependencies and asking which other NuGet packages should be promoted to top level.</span></span> <span data-ttu-id="2a86c-120">**[OK]** を選択すると、*packages.config* ファイルがプロジェクトから削除され、`<PackageReference>` 要素がプロジェクト ファイルに追加されます。</span><span class="sxs-lookup"><span data-stu-id="2a86c-120">Select **OK** and the *packages.config* file will be removed from the project and `<PackageReference>` elements will be added to the project file.</span></span>

<span data-ttu-id="2a86c-121">プロジェクトで `<PackageReference>` を使用する場合、パッケージは *Packages* フォルダーにローカルに保存されず、グローバルに格納されます。</span><span class="sxs-lookup"><span data-stu-id="2a86c-121">When your project uses `<PackageReference>`, packages aren't stored locally in a *Packages* folder, they're stored globally.</span></span> <span data-ttu-id="2a86c-122">プロジェクト ファイルを開き、*Packages* フォルダーを参照していた `<Analyzer>` 要素をすべて削除します。</span><span class="sxs-lookup"><span data-stu-id="2a86c-122">Open the project file and remove any `<Analyzer>` elements that referred to the *Packages* folder.</span></span> <span data-ttu-id="2a86c-123">これらのアナライザーは、NuGet パッケージの参照に自動的に含まれます。</span><span class="sxs-lookup"><span data-stu-id="2a86c-123">These analyzers are automatically included with the NuGet package references.</span></span>

## <a name="code-access-security"></a><span data-ttu-id="2a86c-124">コード アクセス セキュリティ</span><span class="sxs-lookup"><span data-stu-id="2a86c-124">Code Access Security</span></span>

<span data-ttu-id="2a86c-125">コード アクセス セキュリティ (CAS) は、.Net Core でも .NET Core の WPF でもサポートされません。</span><span class="sxs-lookup"><span data-stu-id="2a86c-125">Code Access Security (CAS) is not supported by .NET Core or WPF for .NET Core.</span></span> <span data-ttu-id="2a86c-126">CAS 関連のすべての機能は、完全な信頼の想定のもとで扱われます。</span><span class="sxs-lookup"><span data-stu-id="2a86c-126">All CAS-related functionality is treated under the assumption of full-trust.</span></span> <span data-ttu-id="2a86c-127">.NET Core の WPF では、CAS 関連のコードは削除されます。</span><span class="sxs-lookup"><span data-stu-id="2a86c-127">WPF for .NET Core removes CAS-related code.</span></span> <span data-ttu-id="2a86c-128">これらの型のパブリック API サーフェイスは、これらの型への呼び出しが成功するように引き続き存在しています。</span><span class="sxs-lookup"><span data-stu-id="2a86c-128">The public API surface of these types still exists to ensure that calls into these types succeed.</span></span>

<span data-ttu-id="2a86c-129">パブリックに定義された CAS 関連の型は、WPF アセンブリから Core .NET ライブラリ アセンブリに移動されました。</span><span class="sxs-lookup"><span data-stu-id="2a86c-129">Publicly defined CAS-related types were moved out of the WPF assemblies and into the Core .NET library assemblies.</span></span> <span data-ttu-id="2a86c-130">WPF アセンブリでは、型転送が、移動された型の新しい場所に設定されています。</span><span class="sxs-lookup"><span data-stu-id="2a86c-130">The WPF assemblies have type-forwarding set to the new location of the moved types.</span></span>

| <span data-ttu-id="2a86c-131">ソース アセンブリ</span><span class="sxs-lookup"><span data-stu-id="2a86c-131">Source assembly</span></span> | <span data-ttu-id="2a86c-132">ターゲット アセンブリ</span><span class="sxs-lookup"><span data-stu-id="2a86c-132">Target assembly</span></span> | <span data-ttu-id="2a86c-133">種類</span><span class="sxs-lookup"><span data-stu-id="2a86c-133">Type</span></span>                |
| --------------- | --------------- | ------------------- |
| <span data-ttu-id="2a86c-134">*WindowsBase.dll*</span><span class="sxs-lookup"><span data-stu-id="2a86c-134">*WindowsBase.dll*</span></span> | <span data-ttu-id="2a86c-135">*System.Security.Permissions.dll*</span><span class="sxs-lookup"><span data-stu-id="2a86c-135">*System.Security.Permissions.dll*</span></span> | <xref:System.Security.Permissions.MediaPermission> <br /> <xref:System.Security.Permissions.MediaPermissionAttribute> <br /> <xref:System.Security.Permissions.MediaPermissionAudio> <br /> <xref:System.Security.Permissions.MediaPermissionImage> <br /> <xref:System.Security.Permissions.MediaPermissionVideo> <br /> <xref:System.Security.Permissions.WebBrowserPermission> <br /> <xref:System.Security.Permissions.WebBrowserPermissionAttribute> <br /> <xref:System.Security.Permissions.WebBrowserPermissionLevel> |
| <span data-ttu-id="2a86c-136">*System.Xaml.dll*</span><span class="sxs-lookup"><span data-stu-id="2a86c-136">*System.Xaml.dll*</span></span> | <span data-ttu-id="2a86c-137">*System.Security.Permissions.dll*</span><span class="sxs-lookup"><span data-stu-id="2a86c-137">*System.Security.Permissions.dll*</span></span> | <xref:System.Xaml.Permissions.XamlLoadPermission> |
| <span data-ttu-id="2a86c-138">*System.Xaml.dll*</span><span class="sxs-lookup"><span data-stu-id="2a86c-138">*System.Xaml.dll*</span></span> | <span data-ttu-id="2a86c-139">*System.Windows.Extension.dll*</span><span class="sxs-lookup"><span data-stu-id="2a86c-139">*System.Windows.Extension.dll*</span></span>    | <xref:System.Xaml.Permissions.XamlAccessLevel><br/> |

> [!NOTE]
> <span data-ttu-id="2a86c-140">移植での問題を最小限に抑えるために、次のプロパティに関連する情報を格納および取得するための機能は、`XamlAccessLevel` 型に保持されていました。</span><span class="sxs-lookup"><span data-stu-id="2a86c-140">In order to minimize porting friction, the functionality for storing and retrieving information related to the following properties was retained in the `XamlAccessLevel` type.</span></span>
>
> - `PrivateAccessToTypeName`
> - `AssemblyNameString`

## <a name="next-steps"></a><span data-ttu-id="2a86c-141">次の手順</span><span class="sxs-lookup"><span data-stu-id="2a86c-141">Next steps</span></span>

- [<span data-ttu-id="2a86c-142">.NET Framework の WPF アプリを .NET Core に移植する方法について学びます。</span><span class="sxs-lookup"><span data-stu-id="2a86c-142">Learn how to port a .NET Framework WPF app to .NET Core.</span></span>](convert-project-from-net-framework.md)
