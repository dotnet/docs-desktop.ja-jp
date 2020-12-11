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
# <a name="more-secure-printing-in-windows-forms"></a>Windows フォームでのより安全な印刷
Windows フォームアプリケーションには、多くの場合、印刷機能が含まれます。 .NET Framework は、クラスを使用して <xref:System.Drawing.Printing.PrintingPermission> 印刷機能へのアクセスを制御し、関連する列挙値を使用して <xref:System.Drawing.Printing.PrintingPermissionLevel> アクセスのレベルを示します。 既定では、印刷は、ローカルのイントラネットゾーンとインターネットゾーンでは既定で有効になっています。ただし、アクセスのレベルは両方のゾーンで制限されます。 アプリケーションで印刷できるか、ユーザーの操作を必要とするか、または印刷できないかは、アプリケーションに与えられたアクセス許可値によって異なります。 既定では、ローカルイントラネットゾーンは <xref:System.Drawing.Printing.PrintingPermissionLevel.DefaultPrinting> アクセスを受け取り、イントラネットゾーンはアクセスを受け取り <xref:System.Drawing.Printing.PrintingPermissionLevel.SafePrinting> ます。  
  
 次の表は、各印刷アクセス許可レベルで使用できる機能を示しています。  
  
|増刷レベル|説明|  
|-----------------------------|-----------------|  
|<xref:System.Drawing.Printing.PrintingPermissionLevel.AllPrinting>|インストールされているすべてのプリンターへのフルアクセスを提供します。|  
|<xref:System.Drawing.Printing.PrintingPermissionLevel.DefaultPrinting>|既定のプリンターへのプログラムによる印刷、および [制限付き印刷] ダイアログボックスを使用した印刷の安全性を有効にします。 <xref:System.Drawing.Printing.PrintingPermissionLevel.DefaultPrinting> は <xref:System.Drawing.Printing.PrintingPermissionLevel.AllPrinting> のサブセットです。|  
|<xref:System.Drawing.Printing.PrintingPermissionLevel.SafePrinting>|は、より制限されたダイアログボックスからのみ印刷を提供します。 <xref:System.Drawing.Printing.PrintingPermissionLevel.SafePrinting> は <xref:System.Drawing.Printing.PrintingPermissionLevel.DefaultPrinting> のサブセットです。|  
|<xref:System.Drawing.Printing.PrintingPermissionLevel.NoPrinting>|プリンターへのアクセスを防止します。 <xref:System.Drawing.Printing.PrintingPermissionLevel.NoPrinting> は <xref:System.Drawing.Printing.PrintingPermissionLevel.SafePrinting> のサブセットです。|  
  
## <a name="see-also"></a>関連項目

- [Windows フォームにおけるファイルおよびデータへのより安全なアクセス](more-secure-file-and-data-access-in-windows-forms.md)
- [Windows フォームのセキュリティに関するその他の考慮事項](additional-security-considerations-in-windows-forms.md)
- [Windows フォームのセキュリティの概要](security-in-windows-forms-overview.md)
- [Windows フォームのセキュリティ](windows-forms-security.md)
