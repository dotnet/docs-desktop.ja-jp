---
title: '方法: 実行時に設定を C# で読み取る'
description: プロパティオブジェクトを使用して、C# を使用して、アプリケーションスコープの設定とユーザースコープ設定の両方を実行時に読み取る方法について説明します。
ms.date: 03/30/2017
helpviewer_keywords:
- application settings [Windows Forms], reading
- application settings [Windows Forms], run time
- application settings [Windows Forms], C#
ms.assetid: dbe8bf09-5e1c-49da-9192-154033d7240b
ms.openlocfilehash: d784544e018bb693c501e35ea36fcae1946ef5eb
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/09/2020
ms.locfileid: "96981784"
---
# <a name="how-to-read-settings-at-run-time-with-c"></a><span data-ttu-id="d8070-103">方法: 実行時に C を使用して設定を読み取る\#</span><span class="sxs-lookup"><span data-stu-id="d8070-103">How To: Read Settings at Run Time With C\#</span></span>

<span data-ttu-id="d8070-104">アプリケーション スコープの設定とユーザー スコープの設定は、どちらも実行時に Properties オブジェクトを使用して読み取ることができます。</span><span class="sxs-lookup"><span data-stu-id="d8070-104">You can read both Application-scoped and User-scoped settings at run time via the Properties object.</span></span> <span data-ttu-id="d8070-105">Properties オブジェクトは、プロジェクトのすべての既定の設定を、定義されているプロジェクトの既定の名前空間にある default メンバーを介して公開します。</span><span class="sxs-lookup"><span data-stu-id="d8070-105">The Properties object exposes all of the default settings for the project via the Properties.Settings.Default member in the default namespace of the project they are defined in.</span></span>  
  
## <a name="to-read-settings-at-run-time-with-c"></a><span data-ttu-id="d8070-106">実行時に C を使用して設定を読み取るには\#</span><span class="sxs-lookup"><span data-stu-id="d8070-106">To Read Settings at Run Time with C\#</span></span>
  
<span data-ttu-id="d8070-107">Properties.Settings.Default メンバーを介して適切な設定にアクセスします。</span><span class="sxs-lookup"><span data-stu-id="d8070-107">Access the appropriate setting via the Properties.Settings.Default member.</span></span> <span data-ttu-id="d8070-108">BackColor プロパティに `myColor` という名前の設定を割り当てる方法を次の例に示します。</span><span class="sxs-lookup"><span data-stu-id="d8070-108">The following example shows how to assign a setting named `myColor` to a BackColor property.</span></span> <span data-ttu-id="d8070-109">この例を実行する前に、`myColor` という名前の `System.Drawing.Color` 型の設定を含む設定ファイルを作成しておく必要があります。</span><span class="sxs-lookup"><span data-stu-id="d8070-109">It requires you to have previously created a Settings file containing a setting named `myColor` of type `System.Drawing.Color`.</span></span> <span data-ttu-id="d8070-110">設定ファイルの作成の詳細については、「 [方法: デザイン時に新しい設定を作成](how-to-create-a-new-setting-at-design-time.md)する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="d8070-110">For information about creating a Settings file, see [How To: Create a New Setting at Design Time](how-to-create-a-new-setting-at-design-time.md).</span></span>  
  
```csharp
this.BackColor = Properties.Settings.Default.myColor;  
```  
  
## <a name="see-also"></a><span data-ttu-id="d8070-111">関連項目</span><span class="sxs-lookup"><span data-stu-id="d8070-111">See also</span></span>

- [<span data-ttu-id="d8070-112">アプリケーション設定とユーザー設定の使用</span><span class="sxs-lookup"><span data-stu-id="d8070-112">Using Application Settings and User Settings</span></span>](using-application-settings-and-user-settings.md)
- [<span data-ttu-id="d8070-113">方法: 実行時にユーザー設定を C# で書き込む</span><span class="sxs-lookup"><span data-stu-id="d8070-113">How To: Write User Settings at Run Time with C#</span></span>](how-to-write-user-settings-at-run-time-with-csharp.md)
- [<span data-ttu-id="d8070-114">アプリケーション設定の概要</span><span class="sxs-lookup"><span data-stu-id="d8070-114">Application Settings Overview</span></span>](application-settings-overview.md)
