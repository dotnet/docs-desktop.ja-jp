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
# <a name="system-information-and-windows-forms"></a>システム情報と Windows フォーム
場合によっては、コードを決定するために、アプリケーションが実行されているコンピューターに関する情報を収集する必要があります。 たとえば、特定のネットワークドメインに接続されている場合にのみ適用される関数があるとします。この場合、ドメインを特定し、ドメインが存在しない場合は関数を無効にする方法が必要になります。  
  
 Windows フォームアプリケーションは、クラスを使用し <xref:System.Windows.Forms.SystemInformation> て、実行時にコンピューターに関するさまざまなことを確認できます。 クラスを使用してとを取得する例を次に示し <xref:System.Windows.Forms.SystemInformation> <xref:System.Windows.Forms.SystemInformation.UserName%2A> <xref:System.Windows.Forms.SystemInformation.UserDomainName%2A> ます。  
  
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
  
 クラスのすべてのメンバー <xref:System.Windows.Forms.SystemInformation> は読み取り専用です。ユーザーの設定を変更することはできません。 クラスには100を超えるメンバーがあり、コンピューターに接続されているモニターの数 () から <xref:System.Windows.Forms.SystemInformation.MonitorCount%2A> Windows エクスプローラー (および) のアイコンの間隔までのすべての情報が返され <xref:System.Windows.Forms.SystemInformation.IconHorizontalSpacing%2A> <xref:System.Windows.Forms.SystemInformation.IconVerticalSpacing%2A> ます。  
  
 クラスの便利なメンバーには <xref:System.Windows.Forms.SystemInformation> 、、、 <xref:System.Windows.Forms.SystemInformation.ComputerName%2A> 、およびがあり <xref:System.Windows.Forms.SystemInformation.DbcsEnabled%2A> <xref:System.Windows.Forms.SystemInformation.PowerStatus%2A> <xref:System.Windows.Forms.SystemInformation.TerminalServerSession%2A> ます。  
  
## <a name="see-also"></a>関連項目

- <xref:System.Windows.Forms.SystemInformation>
- [Windows フォームでの電源管理](power-management-in-windows-forms.md)
