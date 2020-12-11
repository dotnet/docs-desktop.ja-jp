---
title: MenuStrip コントロールでのメニュー項目のマージ
ms.date: 03/30/2017
helpviewer_keywords:
- MenuStrip [Windows Forms], merging
- merging [Windows Forms], general concepts
ms.assetid: 95e113ba-f362-4dda-8a76-6d95ddc45cee
ms.openlocfilehash: 9fc2b40ef23d72db51853c124095b734a7646cda
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/09/2020
ms.locfileid: "96982927"
---
# <a name="merging-menu-items-in-the-windows-forms-menustrip-control"></a>Windows フォームの MenuStrip コントロールへのメニュー項目のマージ
マルチドキュメントインターフェイス (MDI) アプリケーションを使用している場合は、メニュー項目またはメニュー全体を子フォームから親フォームのメニューにマージできます。  
  
 このトピックでは、MDI アプリケーションでのメニュー項目のマージに関連する基本的な概念について説明します。  
  
## <a name="general-concepts"></a>一般的な概念  
 マージプロシージャには、ターゲットとソース管理の両方が含まれます。  
  
- ターゲットは、 <xref:System.Windows.Forms.MenuStrip> メニュー項目をマージするメインまたは MDI 親フォーム上のコントロールです。  
  
- ソースは、[ <xref:System.Windows.Forms.MenuStrip> ターゲット] メニューにマージするメニュー項目を含む MDI 子フォーム上のコントロールです。  
  
 プロパティは、 <xref:System.Windows.Forms.MenuStrip.MdiWindowListItem%2A> 現在の mdi 親フォームの mdi 子のタイトルを設定するドロップダウンリストを持つメニュー項目を識別します。 たとえば、通常は [ **ウィンドウ** ] メニューで現在開いている MDI 子を一覧表示します。  
  
 プロパティは、 <xref:System.Windows.Forms.ToolStripMenuItem.IsMdiWindowListEntry%2A> <xref:System.Windows.Forms.MenuStrip> MDI 子フォーム上のから取得されたメニュー項目を識別します。  
  
 メニュー項目は、手動または自動で結合できます。 メニュー項目は両方の方法で同じ方法でマージされますが、このトピックで後述する「手動マージ」と「自動マージ」のセクションで説明したように、マージのアクティブ化は異なります。 手動マージと自動マージの両方で、マージアクションは、次のマージアクションに影響します。  
  
 <xref:System.Windows.Forms.MenuStrip> マージ <xref:System.Windows.Forms.ToolStrip> は、の場合と同様に、メニュー項目を複製するのではなく、別のに移動し <xref:System.Windows.Forms.MainMenu> ます。  
  
## <a name="mergeaction-values"></a>MergeAction 値  
 ソースのメニュー項目に対するマージ操作は、 <xref:System.Windows.Forms.MenuStrip> プロパティを使用して設定し <xref:System.Windows.Forms.MergeAction> ます。  
  
 次の表では、使用可能なマージアクションの意味と一般的な使用方法について説明します。  
  
|MergeAction 値|説明|一般的な用途|  
|-----------------------|-----------------|-----------------|  
|<xref:System.Windows.Forms.MergeAction.Append>|標準ソース項目をターゲット項目のコレクションの末尾に追加します。|プログラムの一部がアクティブになったときにメニューの最後にメニュー項目を追加する。|  
|<xref:System.Windows.Forms.MergeAction.Insert>|ソース項目に対して設定されたプロパティによって指定された場所で、ターゲット項目のコレクションにソース項目を追加し <xref:System.Windows.Forms.ToolStripItem.MergeIndex%2A> ます。|プログラムの一部がアクティブになったときに、メニューの中央または先頭にメニュー項目を追加します。<br /><br /> の値 <xref:System.Windows.Forms.ToolStripItem.MergeIndex%2A> が両方のメニュー項目で同じ場合は、逆順に追加されます。 <xref:System.Windows.Forms.ToolStripItem.MergeIndex%2A>元の順序を保持するために適切に設定します。|  
|<xref:System.Windows.Forms.MergeAction.Replace>|一致するテキストを検索します。または、一致する文字列が見つからない場合は値を使用し、 <xref:System.Windows.Forms.ToolStripItem.MergeIndex%2A> 一致するターゲットメニュー項目をソースメニュー項目に置き換えます。|ターゲットメニュー項目を、同じ名前のソースメニュー項目で置き換えます。|  
|<xref:System.Windows.Forms.MergeAction.MatchOnly>|テキストの一致を検索します。または、テキストの一致が見つからない場合は値を使用し、 <xref:System.Windows.Forms.ToolStripItem.MergeIndex%2A> ソースからターゲットにすべてのドロップダウン項目を追加します。|メニュー項目をサブメニューに挿入または追加したり、サブメニューからメニュー項目を削除したりするメニュー構造を構築します。 たとえば、MDI 子からメインの [ <xref:System.Windows.Forms.MenuStrip> **名前を付けて保存**] メニューにメニュー項目を追加できます。<br /><br /> <xref:System.Windows.Forms.MergeAction.MatchOnly> 操作を行わずに、メニュー構造内を移動することができます。 これにより、後続の項目を評価することができます。|  
|<xref:System.Windows.Forms.MergeAction.Remove>|テキストの一致を検索します。または、 <xref:System.Windows.Forms.ToolStripItem.MergeIndex%2A> テキストの一致が見つからない場合は値を使用して、対象から項目を削除します。|ターゲットからメニュー項目を削除 <xref:System.Windows.Forms.MenuStrip> しています。|  
  
## <a name="manual-merging"></a>手動マージ  
 <xref:System.Windows.Forms.MenuStrip>自動マージに参加するのはコントロールのみです。 コントロールやコントロールなど、他のコントロールの項目を組み合わせるには、 <xref:System.Windows.Forms.ToolStrip> <xref:System.Windows.Forms.StatusStrip> 必要に <xref:System.Windows.Forms.ToolStripManager.Merge%2A> <xref:System.Windows.Forms.ToolStripManager.RevertMerge%2A> 応じてコード内のメソッドとメソッドを呼び出すことによって、それらを手動でマージする必要があります。  
  
## <a name="automatic-merging"></a>自動マージ  
 ソースフォームをアクティブ化することで、MDI アプリケーションの自動マージを使用できます。 MDI アプリケーションでを使用するには、 <xref:System.Windows.Forms.MenuStrip> プロパティをターゲットに設定して、 <xref:System.Windows.Forms.Form.MainMenuStrip%2A> <xref:System.Windows.Forms.MenuStrip> ソースで実行されるマージアクションが <xref:System.Windows.Forms.MenuStrip> ターゲットに反映されるようにし <xref:System.Windows.Forms.MenuStrip> ます。  
  
 自動マージをトリガーするには、 <xref:System.Windows.Forms.MenuStrip> MDI ソースでをアクティブにします。 アクティブ化時に、ソース <xref:System.Windows.Forms.MenuStrip> が MDI ターゲットにマージされます。 新しいフォームがアクティブになると、最後のフォームでマージが元に戻され、新しいフォームでトリガーされます。 この動作を制御するには、 <xref:System.Windows.Forms.ToolStripItem.MergeAction%2A> 各に対して必要に応じてプロパティを設定 <xref:System.Windows.Forms.ToolStripItem> し、 <xref:System.Windows.Forms.ToolStrip.AllowMerge%2A> それぞれのプロパティを設定し <xref:System.Windows.Forms.MenuStrip> ます。  
  
## <a name="see-also"></a>関連項目

- <xref:System.Windows.Forms.ToolStripManager>
- <xref:System.Windows.Forms.MenuStrip>
- [MenuStrip コントロール](menustrip-control-windows-forms.md)
- [方法: MenuStrip を使用して MDI ウィンドウの一覧を作成する](how-to-create-an-mdi-window-list-with-menustrip-windows-forms.md)
- [方法: MDI アプリケーションでメニューの自動マージを設定する](how-to-set-up-automatic-menu-merging-for-mdi-applications.md)
