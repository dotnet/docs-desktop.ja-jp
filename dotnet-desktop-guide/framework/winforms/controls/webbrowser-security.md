---
title: WebBrowser セキュリティ
ms.date: 03/30/2017
helpviewer_keywords:
- WebBrowser control [Windows Forms], security
- security [Windows Forms], WebBrowser control
ms.assetid: 0968846e-48ee-485a-9797-65b5b9a622f8
ms.openlocfilehash: 3412a775cd62723bb1d7ab8548b8a89ea05ad7f6
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/09/2020
ms.locfileid: "96982680"
---
# <a name="webbrowser-security"></a><span data-ttu-id="f8cc1-102">WebBrowser セキュリティ</span><span class="sxs-lookup"><span data-stu-id="f8cc1-102">WebBrowser Security</span></span>

<span data-ttu-id="f8cc1-103"><xref:System.Windows.Forms.WebBrowser>コントロールは、完全な信頼のみで動作するように設計されています。</span><span class="sxs-lookup"><span data-stu-id="f8cc1-103">The <xref:System.Windows.Forms.WebBrowser> control is designed to work in full trust only.</span></span> <span data-ttu-id="f8cc1-104">コントロールに表示される HTML コンテンツは、外部 Web サーバーから取得でき、スクリプトまたは Web コントロールの形式でアンマネージコードを含むことができます。</span><span class="sxs-lookup"><span data-stu-id="f8cc1-104">The HTML content displayed in the control can come from external Web servers and may contain unmanaged code in the form of scripts or Web controls.</span></span> <span data-ttu-id="f8cc1-105">このような場合にコントロールを使用すると、 <xref:System.Windows.Forms.WebBrowser> コントロールは Internet Explorer の場合より安全ではなくなりますが、マネージコントロールは、この <xref:System.Windows.Forms.WebBrowser> ようなアンマネージコードの実行を防止できません。</span><span class="sxs-lookup"><span data-stu-id="f8cc1-105">If you use the <xref:System.Windows.Forms.WebBrowser> control in this situation, the control is no less secure than Internet Explorer would be, but the managed <xref:System.Windows.Forms.WebBrowser> control does not prevent such unmanaged code from running.</span></span>  
  
 <span data-ttu-id="f8cc1-106">基になる ActiveX コントロールに関連するセキュリティの問題の詳細については `WebBrowser` 、「 [WebBrowser コントロール](/previous-versions/windows/internet-explorer/ie-developer/platform-apis/aa752040(v=vs.85))」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="f8cc1-106">For more information about security issues relating to the underlying ActiveX `WebBrowser` control, see [WebBrowser Control](/previous-versions/windows/internet-explorer/ie-developer/platform-apis/aa752040(v=vs.85)).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f8cc1-107">関連項目</span><span class="sxs-lookup"><span data-stu-id="f8cc1-107">See also</span></span>

- <xref:System.Windows.Forms.WebBrowser>
- [<span data-ttu-id="f8cc1-108">WebBrowser コントロールの概要</span><span class="sxs-lookup"><span data-stu-id="f8cc1-108">WebBrowser Control Overview</span></span>](webbrowser-control-overview.md)
- <span data-ttu-id="f8cc1-109">[WebBrowser コントロール](/previous-versions/windows/internet-explorer/ie-developer/platform-apis/aa752040(v=vs.85))</span><span class="sxs-lookup"><span data-stu-id="f8cc1-109">[WebBrowser Control](/previous-versions/windows/internet-explorer/ie-developer/platform-apis/aa752040(v=vs.85))</span></span>
