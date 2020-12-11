---
title: '方法: C# のアプリケーションに複数の設定セットを追加する'
description: Visual Studio を使用して、C# のアプリケーションに複数の Windows フォーム設定のセットを追加する方法について説明します。
ms.date: 03/30/2017
helpviewer_keywords:
- application settings [Windows Forms], multiple sets
- application settings [Windows Forms], C#
ms.assetid: 45007ac6-cf07-4be7-bc38-3f0ef962faf9
ms.openlocfilehash: 579374ff101758b3224bc122c46b891280ed2609
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/09/2020
ms.locfileid: "96979780"
---
# <a name="how-to-add-multiple-sets-of-settings-to-your-application-in-c"></a><span data-ttu-id="c28ce-103">方法: C でアプリケーションに複数の設定セットを追加する\#</span><span class="sxs-lookup"><span data-stu-id="c28ce-103">How To: Add Multiple Sets of Settings To Your Application in C\#</span></span>

<span data-ttu-id="c28ce-104">場合によっては、アプリケーションに複数の設定セットを含めることが必要になることがあります。</span><span class="sxs-lookup"><span data-stu-id="c28ce-104">In some cases, you might want to have multiple sets of settings in an application.</span></span> <span data-ttu-id="c28ce-105">たとえば、特定の設定グループが頻繁に変更されることが予想されるアプリケーションを開発する場合は、ファイルをすべて1つのファイルに分割して、他の設定が影響を受けないようにすることをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="c28ce-105">For example, if you are developing an application where a particular group of settings is expected to change frequently, it might be wise to separate them all into a single file so that the file can be replaced wholesale, leaving other settings unaffected.</span></span> <span data-ttu-id="c28ce-106">Visual Studio では、プロジェクトに複数の設定セットを追加できます。</span><span class="sxs-lookup"><span data-stu-id="c28ce-106">Visual Studio allows you to add multiple sets of settings to your project.</span></span> <span data-ttu-id="c28ce-107">その他の設定セットは、オブジェクトを使用してアクセスでき `Properties.Settings` ます。</span><span class="sxs-lookup"><span data-stu-id="c28ce-107">Additional sets of settings can be accessed via the `Properties.Settings` object.</span></span>

## <a name="add-an-additional-set-of-settings"></a><span data-ttu-id="c28ce-108">追加の設定セットを追加する</span><span class="sxs-lookup"><span data-stu-id="c28ce-108">Add an Additional Set of Settings</span></span>

1. <span data-ttu-id="c28ce-109">Visual Studio で、[ **プロジェクト** ] メニューの [ **新しい項目の追加**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="c28ce-109">In Visual Studio, from the **Project** menu, choose **Add New Item**.</span></span>

   <span data-ttu-id="c28ce-110">**[新しい項目の追加]** ダイアログ ボックスが開きます。</span><span class="sxs-lookup"><span data-stu-id="c28ce-110">The **Add New Item** dialog box opens.</span></span>

2. <span data-ttu-id="c28ce-111">[ **新しい項目の追加** ] ダイアログボックスで、[ **設定ファイル**] を選択し、ファイルの名前を入力して [ **追加** ] をクリックし、ソリューションに新しい設定ファイルを追加します。</span><span class="sxs-lookup"><span data-stu-id="c28ce-111">In the **Add New Item** dialog box, select **Settings File**, enter a name for the file, and click **Add** to add a new settings file to your solution.</span></span>

3. <span data-ttu-id="c28ce-112">**ソリューションエクスプローラー** で、新しい設定ファイルを **Properties** フォルダーにドラッグします。</span><span class="sxs-lookup"><span data-stu-id="c28ce-112">In **Solution Explorer**, drag the new Settings file into the **Properties** folder.</span></span> <span data-ttu-id="c28ce-113">これにより、新しい設定をコードで使用できるようになります。</span><span class="sxs-lookup"><span data-stu-id="c28ce-113">This allows your new settings to be available in code.</span></span>

4. <span data-ttu-id="c28ce-114">他の設定ファイルと同様に、このファイルに設定を追加して使用します。</span><span class="sxs-lookup"><span data-stu-id="c28ce-114">Add and use settings in this file as you would any other settings file.</span></span> <span data-ttu-id="c28ce-115">この設定のグループには、オブジェクトを介してアクセスでき `Properties.Settings` ます。</span><span class="sxs-lookup"><span data-stu-id="c28ce-115">You can access this group of settings via the `Properties.Settings` object.</span></span>

## <a name="see-also"></a><span data-ttu-id="c28ce-116">関連項目</span><span class="sxs-lookup"><span data-stu-id="c28ce-116">See also</span></span>

- [<span data-ttu-id="c28ce-117">アプリケーション設定とユーザー設定の使用</span><span class="sxs-lookup"><span data-stu-id="c28ce-117">Using Application Settings and User Settings</span></span>](using-application-settings-and-user-settings.md)
- [<span data-ttu-id="c28ce-118">アプリケーション設定の概要</span><span class="sxs-lookup"><span data-stu-id="c28ce-118">Application Settings Overview</span></span>](application-settings-overview.md)
