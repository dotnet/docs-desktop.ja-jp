---
title: TableLayoutPanel コントロールにおける AutoSize 動作
ms.date: 03/30/2017
ms.topic: overview
helpviewer_keywords:
- AutoSize property [Windows Forms], tableLayoutPanel control
- controls [Windows Forms], sizing
- localizing forms
- layout [Windows Forms], AutoSize
- sizing [Windows Forms], automatic
- TableLayoutPanel control [Windows Forms], AutoSize behavior
- automatic sizing
- AutoSizeMode property
ms.assetid: 9233e0c3-2fa6-405e-8701-959479b1250e
ms.openlocfilehash: daeca48c4fcfaf83d6506ba07d60ec2dcfdcace7
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/09/2020
ms.locfileid: "96981095"
---
# <a name="autosize-behavior-in-the-tablelayoutpanel-control"></a>TableLayoutPanel コントロールにおける AutoSize 動作
## <a name="distinct-autosize-behaviors"></a>個別の AutoSize 動作  
 コントロールは、 <xref:System.Windows.Forms.TableLayoutPanel> 次の方法で自動サイズ変更の動作をサポートします。  
  
- プロパティを使用し <xref:System.Windows.Forms.Control.AutoSize%2A> ます。  
  
- <xref:System.Windows.Forms.TableLayoutStyle.SizeType%2A> <xref:System.Windows.Forms.TableLayoutPanel> コントロールの列と行のスタイルのプロパティを使用します。  
  
### <a name="the-autosize-property-with-row-and-column-styles"></a>行と列のスタイルを持つ AutoSize プロパティ  
 次の表では、 <xref:System.Windows.Forms.Control.AutoSize%2A> プロパティと <xref:System.Windows.Forms.TableLayoutPanel> コントロールの列と行のスタイルの相互作用について説明します。  
  
|AutoSize 設定|スタイルの相互作用|  
|----------------------|-----------------------|  
|`false`|<xref:System.Windows.Forms.TableLayoutPanel>コントロールは左から右に進み、列または行の領域または次の順序で割り当てられます。<br /><br /> 1. <xref:System.Windows.Forms.TableLayoutStyle.SizeType%2A> プロパティがに設定され <xref:System.Windows.Forms.SizeType.Absolute> ている場合、またはで指定されたピクセル数 <xref:System.Windows.Forms.ColumnStyle.Width%2A> <xref:System.Windows.Forms.RowStyle.Height%2A> が割り当てられます。<br />2. <xref:System.Windows.Forms.TableLayoutStyle.SizeType%2A> プロパティがに設定され <xref:System.Windows.Forms.SizeType.AutoSize> ている場合、子コントロールのメソッドによって返されたピクセル数 <xref:System.Windows.Forms.Control.GetPreferredSize%2A> が割り当てられます。<br />3. すべての <xref:System.Windows.Forms.SizeType.Absolute> および <xref:System.Windows.Forms.SizeType.AutoSize> 列または行の領域が割り当てられた後、がに設定されている列または行を使用して、 <xref:System.Windows.Forms.TableLayoutStyle.SizeType%2A> <xref:System.Windows.Forms.SizeType.Percent> 残りの空き領域を均等に割り当てます。|  
|`true`|前の操作と同様に、 <xref:System.Windows.Forms.SizeType.Percent> 列または行が自動サイズ変更の側面を取得するという例外があります。<br /><br /> コントロールは、列または行を拡張して <xref:System.Windows.Forms.TableLayoutPanel> 適切な空き領域を作成します。これにより、スタイルが設定された列または行がコンテンツをクリップすることはありません <xref:System.Windows.Forms.SizeType.Percent> 。 コントロールは、 <xref:System.Windows.Forms.TableLayoutPanel> プロパティまたはプロパティに従って、新しい領域を均等に割り当て <xref:System.Windows.Forms.ColumnStyle.Width%2A> <xref:System.Windows.Forms.RowStyle.Height%2A> ます。|  
  
## <a name="see-also"></a>関連項目

- <xref:System.Windows.Forms.TableLayoutPanel>
- [TableLayoutPanel コントロールの概要](tablelayoutpanel-control-overview.md)
