---
title: アプリケーション設定とユーザー設定の使用
ms.date: 03/30/2017
description: アプリケーション設定とユーザー設定を使用して、アプリケーション実行セッション間で保持される値を作成およびアクセスする方法について説明します。
helpviewer_keywords:
- user settings [Windows Forms]
- application settings [Windows Forms], how-to topics
ms.assetid: 54682d3b-1cbf-4683-9351-012b8b4286b5
ms.openlocfilehash: a30fd354986265eca002fce57bccf5b3bb2adc15
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/09/2020
ms.locfileid: "96981612"
---
# <a name="using-application-settings-and-user-settings"></a><span data-ttu-id="7589b-103">アプリケーション設定とユーザー設定の使用</span><span class="sxs-lookup"><span data-stu-id="7589b-103">Using Application Settings and User Settings</span></span>
<span data-ttu-id="7589b-104">.NET Framework 2.0 から、アプリケーション実行セッション間で保持される値を作成してアクセスできます。</span><span class="sxs-lookup"><span data-stu-id="7589b-104">Starting with the .NET Framework 2.0, you can create and access values that are persisted between application execution sessions.</span></span> <span data-ttu-id="7589b-105">これらの値は *設定* と呼ばれます。</span><span class="sxs-lookup"><span data-stu-id="7589b-105">These values are called *settings*.</span></span> <span data-ttu-id="7589b-106">設定は、ユーザー設定、またはアプリケーションで使用する必要がある重要な情報を表すことができます。</span><span class="sxs-lookup"><span data-stu-id="7589b-106">Settings can represent user preferences, or valuable information the application needs to use.</span></span> <span data-ttu-id="7589b-107">たとえば、アプリケーションの配色のユーザー設定を保存する一連の設定を作成できます。</span><span class="sxs-lookup"><span data-stu-id="7589b-107">For example, you might create a series of settings that store user preferences for the color scheme of an application.</span></span> <span data-ttu-id="7589b-108">または、アプリケーションで使用するデータベースを指定する接続文字列を格納することもできます。</span><span class="sxs-lookup"><span data-stu-id="7589b-108">Or you might store the connection string that specifies a database that your application uses.</span></span> <span data-ttu-id="7589b-109">設定を使用すると、アプリケーションにとって重要な情報をコードの外部に保持したり、個々のユーザーの設定を格納するプロファイルを作成したりすることができます。</span><span class="sxs-lookup"><span data-stu-id="7589b-109">Settings allow you to both persist information that is critical to the application outside the code, and to create profiles that store the preferences of individual users.</span></span>  
  
 <span data-ttu-id="7589b-110">このセクションのトピックでは、デザイン時および実行時に設定を使用する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="7589b-110">The topics in this section describe how to use settings at design time and run time.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="7589b-111">このセクションの内容</span><span class="sxs-lookup"><span data-stu-id="7589b-111">In This Section</span></span>  
 [<span data-ttu-id="7589b-112">方法: 設計時に新しい設定を作成する</span><span class="sxs-lookup"><span data-stu-id="7589b-112">How To: Create a New Setting at Design Time</span></span>](how-to-create-a-new-setting-at-design-time.md)  
  
 <span data-ttu-id="7589b-113">Visual Studio を使用して、アプリケーションの新しい設定を作成する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="7589b-113">Explains how to use Visual Studio to create a new setting for an application.</span></span>  
  
 [<span data-ttu-id="7589b-114">方法: 設計時に既存の設定の値を変更する</span><span class="sxs-lookup"><span data-stu-id="7589b-114">How To: Change the Value of an Existing Setting at Design Time</span></span>](how-to-change-the-value-of-an-existing-setting-at-design-time.md)  
  
 <span data-ttu-id="7589b-115">Visual Studio を使用して、既存の設定の値を変更する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="7589b-115">Describes how to use Visual Studio to change the value of an existing setting.</span></span>  
  
 [<span data-ttu-id="7589b-116">方法: アプリケーション セッション間で設定値を変更する</span><span class="sxs-lookup"><span data-stu-id="7589b-116">How To: Change the Value of a Setting Between Application Sessions</span></span>](how-to-change-the-value-of-a-setting-between-application-sessions.md)  
  
 <span data-ttu-id="7589b-117">アプリケーションセッション間でコンパイル済みアプリケーションの設定値を変更する方法について詳しく説明します。</span><span class="sxs-lookup"><span data-stu-id="7589b-117">Details how to change the value of a setting in a compiled application between application sessions.</span></span>  
  
 [<span data-ttu-id="7589b-118">方法: 実行時に設定を C# で読み取る</span><span class="sxs-lookup"><span data-stu-id="7589b-118">How To: Read Settings at Run Time With C#</span></span>](how-to-read-settings-at-run-time-with-csharp.md)  
  
 <span data-ttu-id="7589b-119">コードを使用して C# で設定を読み取る方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="7589b-119">Describes how to use code to read settings with C#.</span></span>  
  
 [<span data-ttu-id="7589b-120">方法: 実行時にユーザー設定を C# で書き込む</span><span class="sxs-lookup"><span data-stu-id="7589b-120">How To: Write User Settings at Run Time with C#</span></span>](how-to-write-user-settings-at-run-time-with-csharp.md)  
  
 <span data-ttu-id="7589b-121">コードを使用して、C# でユーザー設定の値を書き込んで保存する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="7589b-121">Explains how to use code to write and save the values of user settings with C#.</span></span>  
  
 [<span data-ttu-id="7589b-122">方法: C# のアプリケーションに複数の設定セットを追加する</span><span class="sxs-lookup"><span data-stu-id="7589b-122">How To: Add Multiple Sets of Settings To Your Application in C#</span></span>](how-to-add-multiple-sets-of-settings-to-your-application-in-csharp.md)  
  
 <span data-ttu-id="7589b-123">C# を使用して、アプリケーションに複数の設定セットを追加する方法について詳しく説明します。</span><span class="sxs-lookup"><span data-stu-id="7589b-123">Details how to add multiple sets of settings to an application with C#.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7589b-124">関連項目</span><span class="sxs-lookup"><span data-stu-id="7589b-124">See also</span></span>

- [<span data-ttu-id="7589b-125">Windows フォームのアプリケーション設定</span><span class="sxs-lookup"><span data-stu-id="7589b-125">Application Settings for Windows Forms</span></span>](application-settings-for-windows-forms.md)
