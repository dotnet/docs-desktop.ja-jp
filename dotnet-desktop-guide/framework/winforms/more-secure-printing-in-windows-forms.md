---
title: より安全な印刷
ms.date: 03/30/2017
helpviewer_keywords:
- Windows Forms, printing
- PrintingPermission class [Windows Forms], Windows Forms security
- printing [Windows Forms], security
- security [Windows Forms], printing
ms.assetid: 48fd36ac-872f-4de0-902a-e52969cd4367
ms.openlocfilehash: 6285b76d01660bfa761ea606421f264bdc0c0af5
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/09/2020
ms.locfileid: "96983168"
---
# <a name="more-secure-printing-in-windows-forms"></a><span data-ttu-id="37e75-102">Windows フォームでのより安全な印刷</span><span class="sxs-lookup"><span data-stu-id="37e75-102">More Secure Printing in Windows Forms</span></span>
<span data-ttu-id="37e75-103">Windows フォームアプリケーションには、多くの場合、印刷機能が含まれます。</span><span class="sxs-lookup"><span data-stu-id="37e75-103">Windows Forms applications frequently include printing abilities.</span></span> <span data-ttu-id="37e75-104">.NET Framework は、クラスを使用して <xref:System.Drawing.Printing.PrintingPermission> 印刷機能へのアクセスを制御し、関連する列挙値を使用して <xref:System.Drawing.Printing.PrintingPermissionLevel> アクセスのレベルを示します。</span><span class="sxs-lookup"><span data-stu-id="37e75-104">The .NET Framework uses the <xref:System.Drawing.Printing.PrintingPermission> class to control access to printing capabilities and the associated <xref:System.Drawing.Printing.PrintingPermissionLevel> enumeration value to indicate the level of access.</span></span> <span data-ttu-id="37e75-105">既定では、印刷は、ローカルのイントラネットゾーンとインターネットゾーンでは既定で有効になっています。ただし、アクセスのレベルは両方のゾーンで制限されます。</span><span class="sxs-lookup"><span data-stu-id="37e75-105">By default, printing is enabled by default in the Local Intranet and Internet zones; however, the level of access is restricted in both zones.</span></span> <span data-ttu-id="37e75-106">アプリケーションで印刷できるか、ユーザーの操作を必要とするか、または印刷できないかは、アプリケーションに与えられたアクセス許可値によって異なります。</span><span class="sxs-lookup"><span data-stu-id="37e75-106">Whether your application can print, requires user interaction, or cannot print depends upon the permission value granted to the application.</span></span> <span data-ttu-id="37e75-107">既定では、ローカルイントラネットゾーンは <xref:System.Drawing.Printing.PrintingPermissionLevel.DefaultPrinting> アクセスを受け取り、イントラネットゾーンはアクセスを受け取り <xref:System.Drawing.Printing.PrintingPermissionLevel.SafePrinting> ます。</span><span class="sxs-lookup"><span data-stu-id="37e75-107">By default, the Local Intranet zone receives <xref:System.Drawing.Printing.PrintingPermissionLevel.DefaultPrinting> access and the Intranet zone receives <xref:System.Drawing.Printing.PrintingPermissionLevel.SafePrinting> access.</span></span>  
  
 <span data-ttu-id="37e75-108">次の表は、各印刷アクセス許可レベルで使用できる機能を示しています。</span><span class="sxs-lookup"><span data-stu-id="37e75-108">The following table shows the functionality available at each printing permission level.</span></span>  
  
|<span data-ttu-id="37e75-109">増刷レベル</span><span class="sxs-lookup"><span data-stu-id="37e75-109">PrintingPermissionLevel</span></span>|<span data-ttu-id="37e75-110">説明</span><span class="sxs-lookup"><span data-stu-id="37e75-110">Description</span></span>|  
|-----------------------------|-----------------|  
|<xref:System.Drawing.Printing.PrintingPermissionLevel.AllPrinting>|<span data-ttu-id="37e75-111">インストールされているすべてのプリンターへのフルアクセスを提供します。</span><span class="sxs-lookup"><span data-stu-id="37e75-111">Provides full access to all installed printers.</span></span>|  
|<xref:System.Drawing.Printing.PrintingPermissionLevel.DefaultPrinting>|<span data-ttu-id="37e75-112">既定のプリンターへのプログラムによる印刷、および [制限付き印刷] ダイアログボックスを使用した印刷の安全性を有効にします。</span><span class="sxs-lookup"><span data-stu-id="37e75-112">Enables programmatic printing to the default printer and safer printing through a restrictive printing dialog box.</span></span> <span data-ttu-id="37e75-113"><xref:System.Drawing.Printing.PrintingPermissionLevel.DefaultPrinting> は <xref:System.Drawing.Printing.PrintingPermissionLevel.AllPrinting> のサブセットです。</span><span class="sxs-lookup"><span data-stu-id="37e75-113"><xref:System.Drawing.Printing.PrintingPermissionLevel.DefaultPrinting> is a subset of <xref:System.Drawing.Printing.PrintingPermissionLevel.AllPrinting>.</span></span>|  
|<xref:System.Drawing.Printing.PrintingPermissionLevel.SafePrinting>|<span data-ttu-id="37e75-114">は、より制限されたダイアログボックスからのみ印刷を提供します。</span><span class="sxs-lookup"><span data-stu-id="37e75-114">Provides printing only from a more-restricted dialog box.</span></span> <span data-ttu-id="37e75-115"><xref:System.Drawing.Printing.PrintingPermissionLevel.SafePrinting> は <xref:System.Drawing.Printing.PrintingPermissionLevel.DefaultPrinting> のサブセットです。</span><span class="sxs-lookup"><span data-stu-id="37e75-115"><xref:System.Drawing.Printing.PrintingPermissionLevel.SafePrinting> is a subset of <xref:System.Drawing.Printing.PrintingPermissionLevel.DefaultPrinting>.</span></span>|  
|<xref:System.Drawing.Printing.PrintingPermissionLevel.NoPrinting>|<span data-ttu-id="37e75-116">プリンターへのアクセスを防止します。</span><span class="sxs-lookup"><span data-stu-id="37e75-116">Prevents access to printers.</span></span> <span data-ttu-id="37e75-117"><xref:System.Drawing.Printing.PrintingPermissionLevel.NoPrinting> は <xref:System.Drawing.Printing.PrintingPermissionLevel.SafePrinting> のサブセットです。</span><span class="sxs-lookup"><span data-stu-id="37e75-117"><xref:System.Drawing.Printing.PrintingPermissionLevel.NoPrinting> is a subset of <xref:System.Drawing.Printing.PrintingPermissionLevel.SafePrinting>.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="37e75-118">関連項目</span><span class="sxs-lookup"><span data-stu-id="37e75-118">See also</span></span>

- [<span data-ttu-id="37e75-119">Windows フォームにおけるファイルおよびデータへのより安全なアクセス</span><span class="sxs-lookup"><span data-stu-id="37e75-119">More Secure File and Data Access in Windows Forms</span></span>](more-secure-file-and-data-access-in-windows-forms.md)
- [<span data-ttu-id="37e75-120">Windows フォームのセキュリティに関するその他の考慮事項</span><span class="sxs-lookup"><span data-stu-id="37e75-120">Additional Security Considerations in Windows Forms</span></span>](additional-security-considerations-in-windows-forms.md)
- [<span data-ttu-id="37e75-121">Windows フォームのセキュリティの概要</span><span class="sxs-lookup"><span data-stu-id="37e75-121">Security in Windows Forms Overview</span></span>](security-in-windows-forms-overview.md)
- [<span data-ttu-id="37e75-122">Windows フォームのセキュリティ</span><span class="sxs-lookup"><span data-stu-id="37e75-122">Windows Forms Security</span></span>](windows-forms-security.md)
