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
# <a name="webbrowser-security"></a>WebBrowser セキュリティ

<xref:System.Windows.Forms.WebBrowser>コントロールは、完全な信頼のみで動作するように設計されています。 コントロールに表示される HTML コンテンツは、外部 Web サーバーから取得でき、スクリプトまたは Web コントロールの形式でアンマネージコードを含むことができます。 このような場合にコントロールを使用すると、 <xref:System.Windows.Forms.WebBrowser> コントロールは Internet Explorer の場合より安全ではなくなりますが、マネージコントロールは、この <xref:System.Windows.Forms.WebBrowser> ようなアンマネージコードの実行を防止できません。  
  
 基になる ActiveX コントロールに関連するセキュリティの問題の詳細については `WebBrowser` 、「 [WebBrowser コントロール](/previous-versions/windows/internet-explorer/ie-developer/platform-apis/aa752040(v=vs.85))」を参照してください。  
  
## <a name="see-also"></a>関連項目

- <xref:System.Windows.Forms.WebBrowser>
- [WebBrowser コントロールの概要](webbrowser-control-overview.md)
- [WebBrowser コントロール](/previous-versions/windows/internet-explorer/ie-developer/platform-apis/aa752040(v=vs.85))
