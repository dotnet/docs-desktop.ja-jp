---
title: '方法: アプリケーション設定を作成する'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- application settings [Windows Forms], Windows Forms
- application settings [Windows Forms], creating
ms.assetid: 1e7aa347-af75-41e5-89ca-f53cab704f72
ms.openlocfilehash: 1c7bcb5b9166cf8fcb01f11d701ea4ebca713ee7
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/09/2020
ms.locfileid: "96974833"
---
# <a name="how-to-create-application-settings"></a><span data-ttu-id="51ce9-102">方法: アプリケーション設定を作成する</span><span class="sxs-lookup"><span data-stu-id="51ce9-102">How to: Create Application Settings</span></span>

<span data-ttu-id="51ce9-103">マネージド コードを使用することにより、新しいアプリケーション設定を作成し、フォームまたはフォームのコントロールのプロパティにバインドして、これらの設定が実行時に自動的に読み込まれて保存されるようにすることができます。</span><span class="sxs-lookup"><span data-stu-id="51ce9-103">Using managed code, you can create new application settings and bind them to properties on your form or your form's controls, so that these settings are loaded and saved automatically at run time.</span></span>  
  
 <span data-ttu-id="51ce9-104">次の手順では、<xref:System.Configuration.ApplicationSettingsBase> から派生するラッパー クラスを手動で作成します。</span><span class="sxs-lookup"><span data-stu-id="51ce9-104">In the following procedure, you manually create a wrapper class that derives from <xref:System.Configuration.ApplicationSettingsBase>.</span></span> <span data-ttu-id="51ce9-105">このクラスには、公開する各アプリケーション設定に対して、パブリックにアクセスできるプロパティを追加します。</span><span class="sxs-lookup"><span data-stu-id="51ce9-105">To this class you add a publicly accessible property for each application setting that you want to expose.</span></span>  
  
 <span data-ttu-id="51ce9-106">また、Visual Studio デザイナーで最小限のコードを使用してこの手順を実行することもできます。</span><span class="sxs-lookup"><span data-stu-id="51ce9-106">You can also perform this procedure using minimal code in the Visual Studio designer.</span></span>  <span data-ttu-id="51ce9-107">「 [方法: デザイナーを使用してアプリケーション設定を作成する](/previous-versions/visualstudio/visual-studio-2010/wabtadw6(v=vs.100))」も参照してください。</span><span class="sxs-lookup"><span data-stu-id="51ce9-107">Also see [How to: Create Application Settings Using the Designer](/previous-versions/visualstudio/visual-studio-2010/wabtadw6(v=vs.100)).</span></span>  
  
### <a name="to-create-new-application-settings-programmatically"></a><span data-ttu-id="51ce9-108">新しいアプリケーション設定をプログラムで作成するには</span><span class="sxs-lookup"><span data-stu-id="51ce9-108">To create new Application Settings programmatically</span></span>  
  
1. <span data-ttu-id="51ce9-109">プロジェクトに新しいクラスを追加して、名前を変更します。</span><span class="sxs-lookup"><span data-stu-id="51ce9-109">Add a new class to your project, and rename it.</span></span> <span data-ttu-id="51ce9-110">この手順では、このクラスを呼び出し `MyUserSettings` ます。</span><span class="sxs-lookup"><span data-stu-id="51ce9-110">For this procedure, we will call this class `MyUserSettings`.</span></span> <span data-ttu-id="51ce9-111">クラスの派生元が <xref:System.Configuration.ApplicationSettingsBase> になるようクラス定義を変更します。</span><span class="sxs-lookup"><span data-stu-id="51ce9-111">Change the class definition so that the class derives from <xref:System.Configuration.ApplicationSettingsBase>.</span></span>  
  
2. <span data-ttu-id="51ce9-112">必要な各アプリケーション設定のこのラッパー クラスでプロパティを定義し、設定のスコープに応じて、そのプロパティを <xref:System.Configuration.ApplicationScopedSettingAttribute> または <xref:System.Configuration.UserScopedSettingAttribute> のいずれかを使用して適用します。</span><span class="sxs-lookup"><span data-stu-id="51ce9-112">Define a property on this wrapper class for each application setting you require, and apply that property with either the <xref:System.Configuration.ApplicationScopedSettingAttribute> or <xref:System.Configuration.UserScopedSettingAttribute>, depending on the scope of the setting.</span></span> <span data-ttu-id="51ce9-113">設定スコープの詳細については、「 [アプリケーション設定の概要](application-settings-overview.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="51ce9-113">For more information about settings scope, see [Application Settings Overview](application-settings-overview.md).</span></span> <span data-ttu-id="51ce9-114">ここまでで、コードは次のようになります。</span><span class="sxs-lookup"><span data-stu-id="51ce9-114">By now, your code should look like this:</span></span>  
  
     [!code-csharp[ApplicationSettings.Create#1](~/samples/snippets/csharp/VS_Snippets_Winforms/ApplicationSettings.Create/CS/MyAppSettings.cs#1)]
     [!code-vb[ApplicationSettings.Create#1](~/samples/snippets/visualbasic/VS_Snippets_Winforms/ApplicationSettings.Create/VB/MyAppSettings.vb#1)]  
  
3. <span data-ttu-id="51ce9-115">アプリケーションでこのラッパー クラスのインスタンスを作成します。</span><span class="sxs-lookup"><span data-stu-id="51ce9-115">Create an instance of this wrapper class in your application.</span></span> <span data-ttu-id="51ce9-116">これは、一般的にはメイン フォームのプライベート メンバーです。</span><span class="sxs-lookup"><span data-stu-id="51ce9-116">It will commonly be a private member of the main form.</span></span> <span data-ttu-id="51ce9-117">クラスを定義したので、それをプロパティにバインドする必要があります。この場合は、フォームの <xref:System.Windows.Forms.Form.BackColor%2A> プロパティです。</span><span class="sxs-lookup"><span data-stu-id="51ce9-117">Now that you have defined your class, you need to bind it to a property; in this case, the <xref:System.Windows.Forms.Form.BackColor%2A> property of your form.</span></span> <span data-ttu-id="51ce9-118">これは、フォームのイベントハンドラーで実行でき `Load` ます。</span><span class="sxs-lookup"><span data-stu-id="51ce9-118">You can accomplish this in your form's `Load` event handler.</span></span>  
  
     [!code-csharp[ApplicationSettings.Create#2](~/samples/snippets/csharp/VS_Snippets_Winforms/ApplicationSettings.Create/CS/Form1.cs#2)]
     [!code-vb[ApplicationSettings.Create#2](~/samples/snippets/visualbasic/VS_Snippets_Winforms/ApplicationSettings.Create/VB/Form1.vb#2)]  
  
4. <span data-ttu-id="51ce9-119">実行時に設定を変更する方法を提供する場合は、フォームを閉じるときにユーザーの現在の設定をディスクに保存する必要があります。そうしないと、これらの変更が失われます。</span><span class="sxs-lookup"><span data-stu-id="51ce9-119">If you provide a way to change settings at run time, you will need to save the user's current settings to disk when your form closes, or else these changes will be lost.</span></span>  
  
     [!code-csharp[ApplicationSettings.Create#3](~/samples/snippets/csharp/VS_Snippets_Winforms/ApplicationSettings.Create/CS/Form1.cs#3)]
     [!code-vb[ApplicationSettings.Create#3](~/samples/snippets/visualbasic/VS_Snippets_Winforms/ApplicationSettings.Create/VB/Form1.vb#3)]  
  
     <span data-ttu-id="51ce9-120">これで、新しいアプリケーション設定を正常に作成し、指定されたプロパティにバインドしました。</span><span class="sxs-lookup"><span data-stu-id="51ce9-120">You have now successfully created a new application setting and bound it to the specified property.</span></span>  
  
## <a name="net-framework-security"></a><span data-ttu-id="51ce9-121">.NET Framework セキュリティ</span><span class="sxs-lookup"><span data-stu-id="51ce9-121">.NET Framework Security</span></span>  

 <span data-ttu-id="51ce9-122">既定の設定プロバイダーの <xref:System.Configuration.LocalFileSettingsProvider> は、情報をプレーン テキストとして構成ファイルに保存します。</span><span class="sxs-lookup"><span data-stu-id="51ce9-122">The default settings provider, <xref:System.Configuration.LocalFileSettingsProvider>, persists information to configuration files as plain text.</span></span> <span data-ttu-id="51ce9-123">これにより、セキュリティがオペレーティング システムが現在のユーザーに対して提供するファイル アクセスのセキュリティに制限されます。</span><span class="sxs-lookup"><span data-stu-id="51ce9-123">This limits security to the file access security provided by the operating system for the current user.</span></span> <span data-ttu-id="51ce9-124">このため、構成ファイルに保存される情報に注意する必要があります。</span><span class="sxs-lookup"><span data-stu-id="51ce9-124">Because of this, care must be taken with the information stored in configuration files.</span></span> <span data-ttu-id="51ce9-125">たとえば、アプリケーション設定の一般的な用途の 1 つとして、アプリケーションのデータ ストアをポイントする接続文字列を格納します。</span><span class="sxs-lookup"><span data-stu-id="51ce9-125">For example, one common use for application settings is to store connection strings that point to the application's data store.</span></span> <span data-ttu-id="51ce9-126">ただし、セキュリティの問題があるため、このような文字列にパスワードは含まれません。</span><span class="sxs-lookup"><span data-stu-id="51ce9-126">However, because of security concerns, such strings should not include passwords.</span></span> <span data-ttu-id="51ce9-127">接続文字列の詳細については、「<xref:System.Configuration.SpecialSetting>」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="51ce9-127">For more information about connection strings, see <xref:System.Configuration.SpecialSetting>.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="51ce9-128">関連項目</span><span class="sxs-lookup"><span data-stu-id="51ce9-128">See also</span></span>

- <xref:System.Configuration.SpecialSettingAttribute>
- <xref:System.Configuration.LocalFileSettingsProvider>
- [<span data-ttu-id="51ce9-129">アプリケーション設定の概要</span><span class="sxs-lookup"><span data-stu-id="51ce9-129">Application Settings Overview</span></span>](application-settings-overview.md)
- [<span data-ttu-id="51ce9-130">方法: アプリケーション設定を検証する</span><span class="sxs-lookup"><span data-stu-id="51ce9-130">How to: Validate Application Settings</span></span>](how-to-validate-application-settings.md)
