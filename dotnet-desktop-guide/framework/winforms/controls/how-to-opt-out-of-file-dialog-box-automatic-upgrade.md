---
title: '方法: ファイル関連のダイアログ ボックスの自動アップグレードを無効にする'
ms.date: 03/30/2017
helpviewer_keywords:
- OpenFileDialog [Windows Forms], opt out of automatic upgrade
- file dialog box [Windows Forms], opt out of automatic upgrade
- Windows Vista file dialog box [Windows Forms], opt out of automatic upgrade
- SaveFileDialog [Windows Forms], opt out of automatic upgrade
- AutoUpgradeEnabled property
ms.assetid: 522e482e-cc01-48b1-8d59-9617dc2c4ac1
ms.openlocfilehash: 154953680426f98a9506feb0b8f4de25c873b795
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/09/2020
ms.locfileid: "96982847"
---
# <a name="how-to-opt-out-of-file-dialog-box-automatic-upgrade"></a>方法: ファイル関連のダイアログ ボックスの自動アップグレードを無効にする
<xref:System.Windows.Forms.OpenFileDialog> <xref:System.Windows.Forms.SaveFileDialog> クラスとクラスをアプリケーションで使用する場合、その外観と動作は、アプリケーションが実行されている Windows のバージョンによって異なります。 .NET Framework 2.0 以前で作成されたアプリケーションが Windows Vista に表示されると、 <xref:System.Windows.Forms.OpenFileDialog> <xref:System.Windows.Forms.SaveFileDialog> は windows vista の外観と動作で自動的に表示されます。 .NET Framework 3.0 以降では、自動アップグレードを無効にして、 <xref:System.Windows.Forms.OpenFileDialog> とを <xref:System.Windows.Forms.SaveFileDialog> Windows XP スタイルの外観と動作で表示することができます。  
  
### <a name="to-opt-out-of-file-dialog-box-automatic-upgrade"></a>ファイル関連のダイアログ ボックスの自動アップグレードを無効にするには  
  
1. <xref:System.Windows.Forms.FileDialog.AutoUpgradeEnabled%2A> <xref:System.Windows.Forms.OpenFileDialog> ダイアログボックスを表示する前に、またはのプロパティ <xref:System.Windows.Forms.SaveFileDialog> をに設定し `false` ます。  
  
## <a name="see-also"></a>関連項目

- <xref:System.Windows.Forms.FileDialog>
