---
title: '方法: アプリケーション セッション間で設定値を変更する'
ms.date: 03/30/2017
helpviewer_keywords:
- application settings [Windows Forms], changing
- application settings [Windows Forms], between application sessions
ms.assetid: 1a85911f-97b2-476c-930b-83379edd890c
ms.openlocfilehash: 95e613cb280813cd75d887d3cf147d7c897bc2e6
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/09/2020
ms.locfileid: "96975014"
---
# <a name="how-to-change-the-value-of-a-setting-between-application-sessions"></a><span data-ttu-id="f1a2b-102">方法: アプリケーション セッション間で設定値を変更する</span><span class="sxs-lookup"><span data-stu-id="f1a2b-102">How To: Change the Value of a Setting Between Application Sessions</span></span>
<span data-ttu-id="f1a2b-103">アプリケーションをコンパイルして展開した後で、アプリケーションセッション間で設定の値を変更することが必要になる場合があります。</span><span class="sxs-lookup"><span data-stu-id="f1a2b-103">At times, you might want to change the value of a setting between application sessions after the application has been compiled and deployed.</span></span> <span data-ttu-id="f1a2b-104">たとえば、適切なデータベースの場所を指すように接続文字列を変更することができます。</span><span class="sxs-lookup"><span data-stu-id="f1a2b-104">For example, you might want to change a connection string to point to the correct database location.</span></span> <span data-ttu-id="f1a2b-105">アプリケーションをコンパイルして配置した後は、デザイン時ツールを使用できないため、ファイルで設定値を手動で変更する必要があります。</span><span class="sxs-lookup"><span data-stu-id="f1a2b-105">Since design-time tools are not available after the application has been compiled and deployed, you must change the setting value manually in the file.</span></span>  
  
### <a name="to-change-the-value-of-a-setting-between-application-sessions"></a><span data-ttu-id="f1a2b-106">アプリケーションセッション間で設定の値を変更するには</span><span class="sxs-lookup"><span data-stu-id="f1a2b-106">To Change the Value of a Setting Between Application Sessions</span></span>  
  
1. <span data-ttu-id="f1a2b-107">Microsoft メモ帳などのテキストエディターまたは XML エディターを使用して、アプリケーションに関連付けられている .config ファイルを開きます。</span><span class="sxs-lookup"><span data-stu-id="f1a2b-107">Using Microsoft Notepad or some other text or XML editor, open the .config file associated with your application.</span></span>  
  
2. <span data-ttu-id="f1a2b-108">変更する設定のエントリを見つけます。</span><span class="sxs-lookup"><span data-stu-id="f1a2b-108">Locate the entry for the setting you want to change.</span></span> <span data-ttu-id="f1a2b-109">次に示す例のようになります。</span><span class="sxs-lookup"><span data-stu-id="f1a2b-109">It should look similar to the example presented below.</span></span>  
  
    ```xml  
    <setting name="Setting1" serializeAs="String" >  
       <value>My Setting Value</value>  
    </setting>  
    ```  
  
3. <span data-ttu-id="f1a2b-110">設定の新しい値を入力し、ファイルを保存します。</span><span class="sxs-lookup"><span data-stu-id="f1a2b-110">Type a new value for your setting and save the file.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f1a2b-111">関連項目</span><span class="sxs-lookup"><span data-stu-id="f1a2b-111">See also</span></span>

- [<span data-ttu-id="f1a2b-112">アプリケーション設定とユーザー設定の使用</span><span class="sxs-lookup"><span data-stu-id="f1a2b-112">Using Application Settings and User Settings</span></span>](using-application-settings-and-user-settings.md)
- [<span data-ttu-id="f1a2b-113">アプリケーション設定の概要</span><span class="sxs-lookup"><span data-stu-id="f1a2b-113">Application Settings Overview</span></span>](application-settings-overview.md)
