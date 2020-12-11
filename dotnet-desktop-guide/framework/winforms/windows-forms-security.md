---
title: セキュリティ
ms.date: 03/30/2017
helpviewer_keywords:
- designer access security [Windows Forms]
- permissions [Windows Forms], Windows Forms
- Windows Forms, security
- security [Windows Forms]
- access control [Windows Forms], Windows Forms
- security policy [Windows Forms], Windows Forms
ms.assetid: 932d438a-5285-46d8-a958-8c93d0ad6cae
ms.openlocfilehash: 2ead74987769649e8defd69ceb929ca685baa51e
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/09/2020
ms.locfileid: "96974698"
---
# <a name="windows-forms-security"></a><span data-ttu-id="032d6-102">Windows フォームのセキュリティ</span><span class="sxs-lookup"><span data-stu-id="032d6-102">Windows Forms Security</span></span>

<span data-ttu-id="032d6-103">Windows フォームには、コードベースのセキュリティモデル (コードを実行しているユーザーに関係なく、コードに対してセキュリティレベルが設定されます) が用意されています。</span><span class="sxs-lookup"><span data-stu-id="032d6-103">Windows Forms features a security model that is code-based (security levels are set for code, regardless of the user running the code).</span></span> <span data-ttu-id="032d6-104">これは、コンピューターシステムに既に配置されている可能性のあるセキュリティスキーマに追加されます。</span><span class="sxs-lookup"><span data-stu-id="032d6-104">This is in addition to any security schemas that may be in place already on your computer system.</span></span> <span data-ttu-id="032d6-105">これらの情報には、ブラウザー (Internet Explorer で使用可能なゾーンベースのセキュリティなど) やオペレーティングシステム (Windows NT の資格情報ベースのセキュリティなど) が含まれます。</span><span class="sxs-lookup"><span data-stu-id="032d6-105">These can include those in the browser (such as the zone-based security available in Internet Explorer) or the operating system (such as the credential-based security of Windows NT).</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="032d6-106">このセクションの内容</span><span class="sxs-lookup"><span data-stu-id="032d6-106">In This Section</span></span>  

 [<span data-ttu-id="032d6-107">Windows フォームのセキュリティの概要</span><span class="sxs-lookup"><span data-stu-id="032d6-107">Security in Windows Forms Overview</span></span>](security-in-windows-forms-overview.md)  
 <span data-ttu-id="032d6-108">.NET Framework セキュリティモデルと、アプリケーションの Windows フォームを確実にセキュリティで保護するために必要な基本手順について簡単に説明します。</span><span class="sxs-lookup"><span data-stu-id="032d6-108">Briefly explains the .NET Framework security model and the basic steps necessary to ensure the Windows Forms in your application are secure.</span></span>  
  
 [<span data-ttu-id="032d6-109">Windows フォームにおけるファイルおよびデータへのより安全なアクセス</span><span class="sxs-lookup"><span data-stu-id="032d6-109">More Secure File and Data Access in Windows Forms</span></span>](more-secure-file-and-data-access-in-windows-forms.md)  
 <span data-ttu-id="032d6-110">信頼度の低い環境でファイルとデータにアクセスする方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="032d6-110">Describes how to access files and data in a semi-trusted environment.</span></span>  
  
 [<span data-ttu-id="032d6-111">Windows フォームでのより安全な印刷</span><span class="sxs-lookup"><span data-stu-id="032d6-111">More Secure Printing in Windows Forms</span></span>](more-secure-printing-in-windows-forms.md)  
 <span data-ttu-id="032d6-112">信頼性の低い環境で印刷機能にアクセスする方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="032d6-112">Describes how to access printing features in a semi-trusted environment.</span></span>  
  
 [<span data-ttu-id="032d6-113">Windows フォームのセキュリティに関するその他の考慮事項</span><span class="sxs-lookup"><span data-stu-id="032d6-113">Additional Security Considerations in Windows Forms</span></span>](additional-security-considerations-in-windows-forms.md)  
 <span data-ttu-id="032d6-114">ウィンドウの操作の実行、クリップボードの使用、および、信頼されていない環境でのアンマネージコードへの呼び出しについて説明します。</span><span class="sxs-lookup"><span data-stu-id="032d6-114">Describes performing window manipulation, using the Clipboard, and making calls to unmanaged code in a semi-trusted environment.</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="032d6-115">関連項目</span><span class="sxs-lookup"><span data-stu-id="032d6-115">Related Sections</span></span>  

 <span data-ttu-id="032d6-116">[既定のセキュリティポリシー](/previous-versions/dotnet/netframework-4.0/03kwzyfc(v=vs.100))</span><span class="sxs-lookup"><span data-stu-id="032d6-116">[Default Security Policy](/previous-versions/dotnet/netframework-4.0/03kwzyfc(v=vs.100))</span></span>  
 <span data-ttu-id="032d6-117">完全信頼、ローカルイントラネット、およびインターネットのアクセス許可セットに付与されている既定のアクセス許可を一覧表示します。</span><span class="sxs-lookup"><span data-stu-id="032d6-117">Lists the default permissions granted in the Full Trust, Local Intranet, and Internet permission sets.</span></span>  
  
 <span data-ttu-id="032d6-118">[セキュリティポリシーの全般管理](/previous-versions/dotnet/netframework-4.0/ed5htz45(v=vs.100))</span><span class="sxs-lookup"><span data-stu-id="032d6-118">[General Security Policy Administration](/previous-versions/dotnet/netframework-4.0/ed5htz45(v=vs.100))</span></span>  
 <span data-ttu-id="032d6-119">.NET Framework セキュリティポリシーの管理とアクセス許可の昇格に関する情報を提供します。</span><span class="sxs-lookup"><span data-stu-id="032d6-119">Gives information about the administering the .NET Framework security policy and elevating permissions.</span></span>  
  
 [<span data-ttu-id="032d6-120">危険なアクセス許可とポリシー管理</span><span class="sxs-lookup"><span data-stu-id="032d6-120">Dangerous Permissions and Policy Administration</span></span>](/dotnet/framework/misc/dangerous-permissions-and-policy-administration)  
 <span data-ttu-id="032d6-121">セキュリティシステムを回避できる可能性がある the.NET Framework のアクセス許可について説明します。</span><span class="sxs-lookup"><span data-stu-id="032d6-121">Discusses some of the.NET Framework permissions that can potentially allow the security system to be circumvented.</span></span>  
  
 [<span data-ttu-id="032d6-122">安全なコーディングのガイドライン</span><span class="sxs-lookup"><span data-stu-id="032d6-122">Secure Coding Guidelines</span></span>](/dotnet/standard/security/secure-coding-guidelines)  
 <span data-ttu-id="032d6-123">.NET Framework に対してコードを安全に記述するためのベストプラクティスについて説明するトピックへのリンクです。</span><span class="sxs-lookup"><span data-stu-id="032d6-123">Links to topics that explain the best practices for securely writing code against the .NET Framework.</span></span>  
  
 <span data-ttu-id="032d6-124">[権限の要求](/previous-versions/dotnet/netframework-4.0/yd267cce(v=vs.100))</span><span class="sxs-lookup"><span data-stu-id="032d6-124">[Requesting Permissions](/previous-versions/dotnet/netframework-4.0/yd267cce(v=vs.100))</span></span>  
 <span data-ttu-id="032d6-125">属性を使用して、コードで実行する必要があるアクセス許可をランタイムに認識させる方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="032d6-125">Discusses the use of attributes to let the runtime know what permissions your code needs to run.</span></span>  
  
 [<span data-ttu-id="032d6-126">セキュリティの基本概念</span><span class="sxs-lookup"><span data-stu-id="032d6-126">Key Security Concepts</span></span>](/dotnet/standard/security/key-security-concepts)  
 <span data-ttu-id="032d6-127">コードセキュリティの基本的な側面について説明するトピックへのリンクです。</span><span class="sxs-lookup"><span data-stu-id="032d6-127">Links to topics that cover the basic aspects of code security.</span></span>  
  
 [<span data-ttu-id="032d6-128">コード アクセス セキュリティの基礎</span><span class="sxs-lookup"><span data-stu-id="032d6-128">Code Access Security Basics</span></span>](/dotnet/framework/misc/code-access-security-basics)  
 <span data-ttu-id="032d6-129">.NET Framework の実行時セキュリティポリシーの使用に関する基本事項について説明します。</span><span class="sxs-lookup"><span data-stu-id="032d6-129">Discusses the basics of working with the .NET Framework run time security policy.</span></span>  
  
 <span data-ttu-id="032d6-130">[セキュリティポリシーを変更する場合の判断](/previous-versions/dotnet/netframework-4.0/xky659fc(v=vs.100))</span><span class="sxs-lookup"><span data-stu-id="032d6-130">[Determining When to Modify Security Policy](/previous-versions/dotnet/netframework-4.0/xky659fc(v=vs.100))</span></span>  
 <span data-ttu-id="032d6-131">既定のセキュリティポリシーからアプリケーションを分岐する必要があるかどうかを判断する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="032d6-131">Explains how to determine when your applications need to diverge from the default security policy.</span></span>  
  
 <span data-ttu-id="032d6-132">[セキュリティポリシーの展開](/previous-versions/dotnet/netframework-4.0/13wcxx6y(v=vs.100))</span><span class="sxs-lookup"><span data-stu-id="032d6-132">[Deploying Security Policy](/previous-versions/dotnet/netframework-4.0/13wcxx6y(v=vs.100))</span></span>  
 <span data-ttu-id="032d6-133">セキュリティポリシーの変更を展開するための最適な方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="032d6-133">Discusses the best manner for deploying security policy changes.</span></span>
