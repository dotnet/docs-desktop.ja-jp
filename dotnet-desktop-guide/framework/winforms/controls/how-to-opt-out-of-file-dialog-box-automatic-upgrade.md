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
# <a name="how-to-opt-out-of-file-dialog-box-automatic-upgrade"></a><span data-ttu-id="7d20b-102">方法: ファイル関連のダイアログ ボックスの自動アップグレードを無効にする</span><span class="sxs-lookup"><span data-stu-id="7d20b-102">How To: Opt Out of File Dialog Box Automatic Upgrade</span></span>
<span data-ttu-id="7d20b-103"><xref:System.Windows.Forms.OpenFileDialog> <xref:System.Windows.Forms.SaveFileDialog> クラスとクラスをアプリケーションで使用する場合、その外観と動作は、アプリケーションが実行されている Windows のバージョンによって異なります。</span><span class="sxs-lookup"><span data-stu-id="7d20b-103">When the <xref:System.Windows.Forms.OpenFileDialog> and <xref:System.Windows.Forms.SaveFileDialog> classes are used in an application, their appearance and behavior depend on the version of Windows the application is running on.</span></span> <span data-ttu-id="7d20b-104">.NET Framework 2.0 以前で作成されたアプリケーションが Windows Vista に表示されると、 <xref:System.Windows.Forms.OpenFileDialog> <xref:System.Windows.Forms.SaveFileDialog> は windows vista の外観と動作で自動的に表示されます。</span><span class="sxs-lookup"><span data-stu-id="7d20b-104">When an application that was created on the .NET Framework 2.0 or earlier is displayed on Windows Vista, <xref:System.Windows.Forms.OpenFileDialog> and <xref:System.Windows.Forms.SaveFileDialog> are automatically displayed with the Windows Vista appearance and behavior.</span></span> <span data-ttu-id="7d20b-105">.NET Framework 3.0 以降では、自動アップグレードを無効にして、 <xref:System.Windows.Forms.OpenFileDialog> とを <xref:System.Windows.Forms.SaveFileDialog> Windows XP スタイルの外観と動作で表示することができます。</span><span class="sxs-lookup"><span data-stu-id="7d20b-105">Starting in the .NET Framework 3.0, you can opt out of the automatic upgrade to display the <xref:System.Windows.Forms.OpenFileDialog> and <xref:System.Windows.Forms.SaveFileDialog> with a Windows XP-style appearance and behavior.</span></span>  
  
### <a name="to-opt-out-of-file-dialog-box-automatic-upgrade"></a><span data-ttu-id="7d20b-106">ファイル関連のダイアログ ボックスの自動アップグレードを無効にするには</span><span class="sxs-lookup"><span data-stu-id="7d20b-106">To opt out of file dialog box automatic upgrade</span></span>  
  
1. <span data-ttu-id="7d20b-107"><xref:System.Windows.Forms.FileDialog.AutoUpgradeEnabled%2A> <xref:System.Windows.Forms.OpenFileDialog> ダイアログボックスを表示する前に、またはのプロパティ <xref:System.Windows.Forms.SaveFileDialog> をに設定し `false` ます。</span><span class="sxs-lookup"><span data-stu-id="7d20b-107">Set the <xref:System.Windows.Forms.FileDialog.AutoUpgradeEnabled%2A> property of <xref:System.Windows.Forms.OpenFileDialog> or <xref:System.Windows.Forms.SaveFileDialog> to `false` before you display the dialog box.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7d20b-108">関連項目</span><span class="sxs-lookup"><span data-stu-id="7d20b-108">See also</span></span>

- <xref:System.Windows.Forms.FileDialog>
