---
title: ヘルプシステム
ms.date: 03/30/2017
helpviewer_keywords:
- Help [Windows Forms], adding to Windows applications
- Windows applications [Windows Forms], providing Help systems
- What's This? Help
- Help [Windows Forms], Windows Forms
- HelpProvider component [Windows Forms], providing Help in Windows applications
ms.assetid: 2a96a278-432c-41fc-9e3c-5bfedf5e1267
ms.openlocfilehash: 07e13ff35de49ae3ec7591544b1c9353ba4bb378
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/09/2020
ms.locfileid: "96979783"
---
# <a name="help-systems-in-windows-forms-applications"></a>Windows フォーム アプリケーションのヘルプ システム
アプリケーションの開発者として最も重要な courtesies の1つは、ユーザーがスキルの高いヘルプシステムを提供できることです。 ここで、混乱または迷子が行われたときに、この場所が有効になります。 Windows ベースのアプリケーションでヘルプシステムを提供するには、 [HelpProvider コンポーネント](../controls/helpprovider-component-windows-forms.md)を使用します。  
  
## <a name="different-types-of-help"></a>さまざまな種類のヘルプ  
 Windows フォーム <xref:System.Windows.Forms.HelpProvider> コンポーネントは、Windows ベースのアプリケーションで HTML ヘルプ 1.x のヘルプ ファイル (HTML Help Workshop で生成された .chm ファイル、または .htm ファイル) を関連付けるために使用します。 コンポーネントを使用すると、 <xref:System.Windows.Forms.HelpProvider> Windows フォームまたは特定のコントロールのコントロールについて、状況依存のヘルプを提供できます。 また、コンポーネントでは、 <xref:System.Windows.Forms.HelpProvider> 目次のメインページ、インデックス、検索機能など、特定の領域に対してヘルプファイルを開くことができます。 コンポーネントの全般的な情報については <xref:System.Windows.Forms.HelpProvider> 、「 [HelpProvider コンポーネントの概要](../controls/helpprovider-component-overview-windows-forms.md)」を参照してください。 コンポーネントを使用して <xref:System.Windows.Forms.HelpProvider> Windows フォームのポップアップヘルプを表示する方法については、「 [方法: ポップアップヘルプを表示](how-to-display-pop-up-help.md)する」を参照してください。 コンポーネントを使用してコントロール固有のヘルプを表示する方法の詳細については <xref:System.Windows.Forms.ToolTip> 、「 [ツールヒントを使用したコントロールのヘルプ](control-help-using-tooltips.md)」を参照してください。  
  
 Html ヘルプ 1. x ファイルは、HTML ヘルプワークショップを使用して生成できます。 HTML ヘルプの詳細については、MSDN の「HTML ヘルプワークショップ」またはその他の「HTML ヘルプ」を参照してください。  
  
## <a name="see-also"></a>関連項目

- [Windows フォームでのヘルプの統合](integrating-user-help-in-windows-forms.md)
- [HelpProvider コンポーネント](../controls/helpprovider-component-windows-forms.md)
- [ToolTip コンポーネント](../controls/tooltip-component-windows-forms.md)
- [Windows フォームの概要](../windows-forms-overview.md)
- [Windows フォーム](../index.yml)
