---
title: システム情報
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- domain names [Windows Forms], retrieving
- SystemInformation class [Windows Forms]
- user names [Windows Forms], retrieving
- system information [Windows Forms]
ms.assetid: 30cf43a3-8cb2-4ff3-862b-6c34576616a8
ms.openlocfilehash: a91e2fd8db0ef338ce30f89f11869f1b6698af3b
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/09/2020
ms.locfileid: "96981643"
---
# <a name="system-information-and-windows-forms"></a><span data-ttu-id="31003-102">システム情報と Windows フォーム</span><span class="sxs-lookup"><span data-stu-id="31003-102">System Information and Windows Forms</span></span>
<span data-ttu-id="31003-103">場合によっては、コードを決定するために、アプリケーションが実行されているコンピューターに関する情報を収集する必要があります。</span><span class="sxs-lookup"><span data-stu-id="31003-103">Sometimes it is necessary to gather information about the computer that your application is running on in order to make decisions in your code.</span></span> <span data-ttu-id="31003-104">たとえば、特定のネットワークドメインに接続されている場合にのみ適用される関数があるとします。この場合、ドメインを特定し、ドメインが存在しない場合は関数を無効にする方法が必要になります。</span><span class="sxs-lookup"><span data-stu-id="31003-104">For example, you might have a function that is only applicable when connected to a particular network domain; in this case you would need a way to determine the domain and disable the function if the domain is not present.</span></span>  
  
 <span data-ttu-id="31003-105">Windows フォームアプリケーションは、クラスを使用し <xref:System.Windows.Forms.SystemInformation> て、実行時にコンピューターに関するさまざまなことを確認できます。</span><span class="sxs-lookup"><span data-stu-id="31003-105">Windows Forms applications can use the <xref:System.Windows.Forms.SystemInformation> class to determine a number of things about a computer at run time.</span></span> <span data-ttu-id="31003-106">クラスを使用してとを取得する例を次に示し <xref:System.Windows.Forms.SystemInformation> <xref:System.Windows.Forms.SystemInformation.UserName%2A> <xref:System.Windows.Forms.SystemInformation.UserDomainName%2A> ます。</span><span class="sxs-lookup"><span data-stu-id="31003-106">The following example demonstrates using the <xref:System.Windows.Forms.SystemInformation> class to retrieve the <xref:System.Windows.Forms.SystemInformation.UserName%2A> and <xref:System.Windows.Forms.SystemInformation.UserDomainName%2A>:</span></span>  
  
```vb  
Dim User As String = Windows.Forms.SystemInformation.UserName  
Dim Domain As String = Windows.Forms.SystemInformation.UserDomainName  
  
MessageBox.Show("Good morning " & User & ". You are connected to " _  
& Domain)  
```  
  
```csharp  
string User = SystemInformation.UserName;  
string Domain = SystemInformation.UserDomainName;  
  
MessageBox.Show("Good morning " + User + ". You are connected to "
+ Domain);
```  
  
 <span data-ttu-id="31003-107">クラスのすべてのメンバー <xref:System.Windows.Forms.SystemInformation> は読み取り専用です。ユーザーの設定を変更することはできません。</span><span class="sxs-lookup"><span data-stu-id="31003-107">All members of the <xref:System.Windows.Forms.SystemInformation> class are read-only; you cannot modify a user's settings.</span></span> <span data-ttu-id="31003-108">クラスには100を超えるメンバーがあり、コンピューターに接続されているモニターの数 () から <xref:System.Windows.Forms.SystemInformation.MonitorCount%2A> Windows エクスプローラー (および) のアイコンの間隔までのすべての情報が返され <xref:System.Windows.Forms.SystemInformation.IconHorizontalSpacing%2A> <xref:System.Windows.Forms.SystemInformation.IconVerticalSpacing%2A> ます。</span><span class="sxs-lookup"><span data-stu-id="31003-108">There are over 100 members of the class, returning information on everything from the number of monitors attached to the computer (<xref:System.Windows.Forms.SystemInformation.MonitorCount%2A>) to the spacing of icons in Windows Explorer (<xref:System.Windows.Forms.SystemInformation.IconHorizontalSpacing%2A> and <xref:System.Windows.Forms.SystemInformation.IconVerticalSpacing%2A>).</span></span>  
  
 <span data-ttu-id="31003-109">クラスの便利なメンバーには <xref:System.Windows.Forms.SystemInformation> 、、、 <xref:System.Windows.Forms.SystemInformation.ComputerName%2A> 、およびがあり <xref:System.Windows.Forms.SystemInformation.DbcsEnabled%2A> <xref:System.Windows.Forms.SystemInformation.PowerStatus%2A> <xref:System.Windows.Forms.SystemInformation.TerminalServerSession%2A> ます。</span><span class="sxs-lookup"><span data-stu-id="31003-109">Some of the more useful members of the <xref:System.Windows.Forms.SystemInformation> class include <xref:System.Windows.Forms.SystemInformation.ComputerName%2A>, <xref:System.Windows.Forms.SystemInformation.DbcsEnabled%2A>, <xref:System.Windows.Forms.SystemInformation.PowerStatus%2A>, and <xref:System.Windows.Forms.SystemInformation.TerminalServerSession%2A>.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="31003-110">関連項目</span><span class="sxs-lookup"><span data-stu-id="31003-110">See also</span></span>

- <xref:System.Windows.Forms.SystemInformation>
- [<span data-ttu-id="31003-111">Windows フォームでの電源管理</span><span class="sxs-lookup"><span data-stu-id="31003-111">Power Management in Windows Forms</span></span>](power-management-in-windows-forms.md)
