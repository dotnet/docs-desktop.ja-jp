---
title: ToolStrip コントロールの概要
ms.date: 03/30/2017
f1_keywords:
- Toolstrip
helpviewer_keywords:
- ToolStrip control [Windows Forms], about ToolStrip control
- toolbars [Windows Forms], what's new in Windows Forms
- toolbars [Windows Forms]
- what's new [Windows Forms], toolbars
ms.assetid: 81d067ed-297c-4dad-90de-1bcac15336ec
ms.openlocfilehash: 931a6a0ea09f9b684b793c05cb1c3db8ee8fb7c7
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/09/2020
ms.locfileid: "96983860"
---
# <a name="toolstrip-control-overview-windows-forms"></a>ToolStrip コントロールの概要 (Windows フォーム)
Windows フォーム <xref:System.Windows.Forms.ToolStrip> コントロールとそれに関連付けられたクラスは、ユーザーインターフェイス要素をツールバー、ステータスバー、およびメニューに結合するための共通のフレームワークを提供します。 <xref:System.Windows.Forms.ToolStrip> コントロールは、埋め込み先のアクティベーションと編集、カスタムレイアウト、およびラフティングを含む豊富なデザイン時のエクスペリエンスを提供します。これは、水平方向または垂直方向のスペースを共有するためのツールバーの機能です。  
  
 <xref:System.Windows.Forms.ToolStrip>は、以前のバージョンのコントロールに代わる機能を追加して <xref:System.Windows.Forms.ToolBar> いますが、必要に応じて、下位互換性と将来の使用の両方のために保持されています。  
  
## <a name="features-of-the-toolstrip-controls"></a>ToolStrip コントロールの機能  
 コントロールを使用して <xref:System.Windows.Forms.ToolStrip> 次の操作を行います。  
  
- コンテナー間で共通のユーザーインターフェイスを提供します。  
  
- ドッキング、ラフティング、テキストとイメージを含むボタン、ドロップダウンボタンとコントロール、オーバーフローボタン、実行時の項目の並べ替えなど、高度なユーザーインターフェイスとレイアウト機能をサポートする、簡単にカスタマイズされたツールバーを作成し <xref:System.Windows.Forms.ToolStrip> ます。  
  
- オーバーフローおよび実行時の項目の並べ替えをサポートします。 オーバーフロー機能は、に表示する領域が不足しているときに、項目をドロップダウンメニューに移動し <xref:System.Windows.Forms.ToolStrip> ます。  
  
- 共通のレンダリングモデルを使用して、オペレーティングシステムの一般的な外観と動作をサポートします。  
  
- 他のコントロールのイベントを処理するのと同じ方法で、すべてのコンテナーと含まれる項目に対して一貫したイベントを処理します。  
  
- ある項目から別の項目 <xref:System.Windows.Forms.ToolStrip> または内の項目をドラッグし <xref:System.Windows.Forms.ToolStrip> ます。  
  
- で高度なレイアウトを使用して、ドロップダウンコントロールとユーザーインターフェイスの種類のエディターを作成 <xref:System.Windows.Forms.ToolStripDropDown> します。  
  
 クラスを使用して <xref:System.Windows.Forms.ToolStripControlHost> 、の他のコントロールを使用し、そのコントロール <xref:System.Windows.Forms.ToolStrip> の機能を取得し <xref:System.Windows.Forms.ToolStrip> ます。  
  
 、、を使用して、およびの列挙体と共に機能を拡張し、外観と動作を変更することができ <xref:System.Windows.Forms.ToolStripRenderer> <xref:System.Windows.Forms.ToolStripProfessionalRenderer> <xref:System.Windows.Forms.ToolStripManager> <xref:System.Windows.Forms.ToolStripRenderMode> <xref:System.Windows.Forms.ToolStripManagerRenderMode> ます。  
  
 <xref:System.Windows.Forms.ToolStrip>コントロールは、高度な構成と拡張が可能で、外観と動作をカスタマイズするための多数のプロパティ、メソッド、およびイベントが用意されています。 注目すべきメンバーを次に示します。  
  
### <a name="important-toolstrip-members"></a>重要な ToolStrip メンバー  
  
|名前|説明|  
|----------|-----------------|  
|<xref:System.Windows.Forms.ToolStrip.Dock%2A>|がドッキングされている親コンテナーの端を取得または設定し <xref:System.Windows.Forms.ToolStrip> ます。|  
|<xref:System.Windows.Forms.ToolStrip.AllowItemReorder%2A>|<xref:System.Windows.Forms.ToolStrip> クラスがドラッグ アンド ドロップおよび項目の並べ替えをプライベートで処理するかどうかを示す値を取得または設定します。|  
|<xref:System.Windows.Forms.ToolStrip.LayoutStyle%2A>|が項目をレイアウトする方法を示す値を取得または設定し <xref:System.Windows.Forms.ToolStrip> ます。|  
|<xref:System.Windows.Forms.ToolStripItem.Overflow%2A>|がにアタッチされているかどうか、また <xref:System.Windows.Forms.ToolStripItem> <xref:System.Windows.Forms.ToolStrip> はこの <xref:System.Windows.Forms.ToolStripOverflowButton> 2 つの間で浮動小数点演算が可能かどうかを取得または設定します|  
|<xref:System.Windows.Forms.ToolStrip.IsDropDown%2A>|<xref:System.Windows.Forms.ToolStripItem>がクリックされたときに、ドロップダウンリストに他の項目を表示するかどうかを示す値を取得し <xref:System.Windows.Forms.ToolStripItem> ます。|  
|<xref:System.Windows.Forms.ToolStrip.OverflowButton%2A>|オーバーフローが有効な <xref:System.Windows.Forms.ToolStripItem> のオーバーフロー ボタンである <xref:System.Windows.Forms.ToolStrip> を取得します。|  
|<xref:System.Windows.Forms.ToolStrip.Renderer%2A>|<xref:System.Windows.Forms.ToolStripRenderer>の外観と動作 (ルックアンドフィール) をカスタマイズするために使用するを取得または設定し <xref:System.Windows.Forms.ToolStrip> ます。|  
|<xref:System.Windows.Forms.ToolStrip.RenderMode%2A>|<xref:System.Windows.Forms.ToolStrip> に適用される描画スタイルを取得または設定します。|  
|<xref:System.Windows.Forms.ToolStrip.RendererChanged>|<xref:System.Windows.Forms.ToolStrip.Renderer%2A> プロパティが変更されたときに発生します。|  
  
 <xref:System.Windows.Forms.ToolStrip>コントロールの柔軟性は、多数のコンパニオンクラスを使用することによって実現されます。 次に、最も注目すべき点をいくつか示します。  
  
### <a name="important-toolstrip-companion-classes"></a>重要な ToolStrip コンパニオンクラス  
  
|名前|説明|  
|----------|-----------------|  
|<xref:System.Windows.Forms.MenuStrip>|を置き換えて、機能をクラスに追加し <xref:System.Windows.Forms.MainMenu> ます。|  
|<xref:System.Windows.Forms.StatusStrip>|を置き換えて、機能をクラスに追加し <xref:System.Windows.Forms.StatusBar> ます。|  
|<xref:System.Windows.Forms.ContextMenuStrip>|を置き換えて、機能をクラスに追加し <xref:System.Windows.Forms.ContextMenu> ます。|  
|<xref:System.Windows.Forms.ToolStripItem>|<xref:System.Windows.Forms.ToolStrip>、 <xref:System.Windows.Forms.ToolStripControlHost> 、またはに格納できるすべての要素のイベントとレイアウトを管理する抽象基本クラス <xref:System.Windows.Forms.ToolStripDropDown> 。|  
|<xref:System.Windows.Forms.ToolStripContainer>|さまざまな方法でコントロールを配置できるように、フォームの各辺にパネルを備えたコンテナーを提供します。|  
|<xref:System.Windows.Forms.ToolStripRenderer>|<xref:System.Windows.Forms.ToolStrip> オブジェクトの描画機能を処理します。|  
|<xref:System.Windows.Forms.ToolStripProfessionalRenderer>|Microsoft Office スタイルの外観を提供します。|  
|<xref:System.Windows.Forms.ToolStripManager>|<xref:System.Windows.Forms.ToolStrip> のレンダリングとラフティング、および <xref:System.Windows.Forms.MenuStrip>、<xref:System.Windows.Forms.ToolStripDropDownMenu>、<xref:System.Windows.Forms.ToolStripMenuItem> の各オブジェクトのマージを制御します。|  
|<xref:System.Windows.Forms.ToolStripManagerRenderMode>|フォームに含まれる複数のオブジェクトに適用される描画スタイル (カスタム、Windows XP、または Microsoft Office Professional) を指定し <xref:System.Windows.Forms.ToolStrip> ます。|  
|<xref:System.Windows.Forms.ToolStripRenderMode>|フォームに含まれる1つのオブジェクトに適用される描画スタイル (カスタム、Windows XP、または Microsoft Office Professional) を指定し <xref:System.Windows.Forms.ToolStrip> ます。|  
|<xref:System.Windows.Forms.ToolStripControlHost>|特に制御していないが、機能を必要とする他のコントロールをホスト <xref:System.Windows.Forms.ToolStrip> <xref:System.Windows.Forms.ToolStrip> します。|  
|<xref:System.Windows.Forms.ToolStripItemPlacement>|をメインに配置するか、オーバーフローするか <xref:System.Windows.Forms.ToolStripItem> 、またはそのどちらでレイアウトするかを指定し <xref:System.Windows.Forms.ToolStrip> <xref:System.Windows.Forms.ToolStrip> ます。|  
  
 詳細については、「 [Toolstrip テクノロジの概要](toolstrip-technology-summary.md) 」と「 [toolstrip コントロールアーキテクチャ](toolstrip-control-architecture.md)」を参照してください。  
  
## <a name="see-also"></a>関連項目

- <xref:System.Windows.Forms.ToolStrip>
- <xref:System.Windows.Forms.MenuStrip>
- <xref:System.Windows.Forms.ContextMenuStrip>
- <xref:System.Windows.Forms.StatusStrip>
- <xref:System.Windows.Forms.ToolStripItem>
- <xref:System.Windows.Forms.ToolStripDropDown>
