---
title: '方法: MDI アプリケーションでメニューの自動マージを設定する'
ms.date: 03/30/2017
helpviewer_keywords:
- MenuStrip [Windows Forms], merging
- Merging [Windows Forms], automatic menu
ms.assetid: 55e32cad-1141-4a56-aa33-d9543ca3d393
ms.openlocfilehash: 33e07bb655d81c6a802ebdce871a2fed845a5c96
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/09/2020
ms.locfileid: "96982807"
---
# <a name="how-to-set-up-automatic-menu-merging-for-mdi-applications"></a>方法: MDI アプリケーションでメニューの自動マージを設定する
次の手順では、マルチドキュメントインターフェイス (MDI) アプリケーションでを使用して自動マージを設定するための基本的な手順を示し <xref:System.Windows.Forms.MenuStrip> ます。  
  
### <a name="to-set-up-automatic-menu-merging"></a>メニューの自動マージを設定するには  
  
1. MDI 親フォームを作成するには、その <xref:System.Windows.Forms.Form.IsMdiContainer%2A> プロパティをに設定し `true` ます。  
  
2. を <xref:System.Windows.Forms.MenuStrip> MDI 親に追加し、その <xref:System.Windows.Forms.Form.MainMenuStrip%2A> プロパティをそれに設定 <xref:System.Windows.Forms.MenuStrip> します。  
  
3. MDI 子フォームを作成し、その <xref:System.Windows.Forms.Form.MdiParent%2A> プロパティを親フォームの名前に設定します。  
  
4. を <xref:System.Windows.Forms.MenuStrip> MDI 子フォームに追加します。  
  
5. 子フォームで、 <xref:System.Windows.Forms.ToolStripItem.Visible%2A> のプロパティ <xref:System.Windows.Forms.MenuStrip> をに設定 `false` します。  
  
6. <xref:System.Windows.Forms.MenuStrip>子フォームがアクティブになったときに親フォームにマージする子フォームに、メニュー項目を追加し <xref:System.Windows.Forms.MenuStrip> ます。  
  
7. <xref:System.Windows.Forms.ToolStripItem.MergeAction%2A>子フォームのメニュー項目のプロパティを使用して、 <xref:System.Windows.Forms.MenuStrip> 親フォームへのマージ方法を制御します。  
  
## <a name="see-also"></a>関連項目

- <xref:System.Windows.Forms.MenuStrip>
- <xref:System.Windows.Forms.ToolStripMenuItem>
- [MenuStrip コントロールの概要](menustrip-control-overview-windows-forms.md)
