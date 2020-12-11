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
# <a name="how-to-change-the-value-of-a-setting-between-application-sessions"></a>方法: アプリケーション セッション間で設定値を変更する
アプリケーションをコンパイルして展開した後で、アプリケーションセッション間で設定の値を変更することが必要になる場合があります。 たとえば、適切なデータベースの場所を指すように接続文字列を変更することができます。 アプリケーションをコンパイルして配置した後は、デザイン時ツールを使用できないため、ファイルで設定値を手動で変更する必要があります。  
  
### <a name="to-change-the-value-of-a-setting-between-application-sessions"></a>アプリケーションセッション間で設定の値を変更するには  
  
1. Microsoft メモ帳などのテキストエディターまたは XML エディターを使用して、アプリケーションに関連付けられている .config ファイルを開きます。  
  
2. 変更する設定のエントリを見つけます。 次に示す例のようになります。  
  
    ```xml  
    <setting name="Setting1" serializeAs="String" >  
       <value>My Setting Value</value>  
    </setting>  
    ```  
  
3. 設定の新しい値を入力し、ファイルを保存します。  
  
## <a name="see-also"></a>関連項目

- [アプリケーション設定とユーザー設定の使用](using-application-settings-and-user-settings.md)
- [アプリケーション設定の概要](application-settings-overview.md)
