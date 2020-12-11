---
title: StatusStrip コントロールの概要
ms.date: 03/30/2017
f1_keywords:
- StatusStrip
helpviewer_keywords:
- StatusStrip control [Windows Forms], about StatusStrip control
- status bars [Windows Forms], about status bars
ms.assetid: c0d9bcbb-f8b8-46ef-bae2-4146b8c8ce99
ms.openlocfilehash: 9f2426220e8fe0f13d2098de8975be2ad2e43845
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/09/2020
ms.locfileid: "96982431"
---
# <a name="statusstrip-control-overview"></a>StatusStrip コントロールの概要

<xref:System.Windows.Forms.StatusStrip> コントロールには、<xref:System.Windows.Forms.Form> に表示されているオブジェクト、そのオブジェクトのコンポーネント、またはそのオブジェクトのアプリケーション内での操作に関連するコンテキストについての情報を表示します。 通常、<xref:System.Windows.Forms.StatusStrip> コントロールは <xref:System.Windows.Forms.ToolStripStatusLabel> オブジェクトで構成され、それら各オブジェクトに、テキスト、アイコン、またはその両方が表示されます。 <xref:System.Windows.Forms.StatusStrip> には、<xref:System.Windows.Forms.ToolStripDropDownButton>、<xref:System.Windows.Forms.ToolStripSplitButton>、および <xref:System.Windows.Forms.ToolStripProgressBar> の各コントロールを組み込むこともできます。  
  
 既定の <xref:System.Windows.Forms.StatusStrip> にはパネルがありません。 <xref:System.Windows.Forms.StatusStrip> にパネルを追加するには、<xref:System.Windows.Forms.ToolStripItemCollection.AddRange%2A?displayProperty=nameWithType> メソッドを使用します。  
  
 <xref:System.Windows.Forms.StatusStrip> 項目と一般的なコマンドの処理に対しては、Visual Studio に広範なサポートが用意されています。  
  
 「 [StatusStrip Items Collection Editor](/previous-versions/visualstudio/visual-studio-2010/ms233631(v=vs.100)) And [StatusStrip Tasks」](/previous-versions/visualstudio/visual-studio-2010/ms233642(v=vs.100))も参照してください。  
  
 <xref:System.Windows.Forms.StatusStrip> コントロールは、以前のバージョンの <xref:System.Windows.Forms.StatusBar> コントロールに代わると共に追加の機能を提供します。ただし、<xref:System.Windows.Forms.StatusBar> コントロールも、下位互換性を保つ目的および必要に応じて将来使用する目的で保持されます。  
  
### <a name="important-statusstrip-members"></a>StatusStrip の重要なメンバー  
  
|名前|説明|  
|----------|-----------------|  
|<xref:System.Windows.Forms.StatusStrip.CanOverflow%2A>|<xref:System.Windows.Forms.StatusStrip> がオーバーフロー機能をサポートするかどうかを示す値を取得または設定します。|  
|<xref:System.Windows.Forms.StatusStrip.Stretch%2A>|<xref:System.Windows.Forms.StatusStrip> を <xref:System.Windows.Forms.ToolStripContainer> 内で端から端まで拡大するかどうかを示す値を取得または設定します。|  
  
### <a name="important-statusstrip-companion-classes"></a>StatusStrip の重要なコンパニオン クラス  
  
|名前|説明|  
|----------|-----------------|  
|<xref:System.Windows.Forms.ToolStripStatusLabel>|<xref:System.Windows.Forms.StatusStrip> コントロールのパネルを表します。|  
|<xref:System.Windows.Forms.ToolStripDropDownButton>|関連付けられた <xref:System.Windows.Forms.ToolStripDropDown> を表示します。そこからユーザーは、単一の項目を選択できます。|  
|<xref:System.Windows.Forms.ToolStripSplitButton>|標準のボタンとドロップダウン メニューという 2 つの部分から成るコントロールを表します。|  
|<xref:System.Windows.Forms.ToolStripProgressBar>|処理の完了状態を表示します。|  
  
## <a name="see-also"></a>関連項目

- <xref:System.Windows.Forms.StatusStrip>
- <xref:System.Windows.Forms.ToolStripStatusLabel>
- <xref:System.Windows.Forms.ToolStripStatusLabel.Spring%2A>
