---
title: 座標
ms.date: 03/30/2017
helpviewer_keywords:
- Windows Forms coordinates
- screen coordinates
- client coordinates
- coordinates [Windows Forms], Windows Forms
ms.assetid: cc06e61f-43b6-4408-a676-2542dcfcd96e
ms.openlocfilehash: c95888f31bfc867e9c028d53072ab3d710256708
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/09/2020
ms.locfileid: "96974709"
---
# <a name="windows-forms-coordinates"></a>Windows フォームの座標
Windows フォームの座標系はデバイス座標に基づいており、Windows フォームで描画するときの基本的な測定単位はデバイス単位 (通常はピクセル) です。 画面上の点は、x 座標と y 座標のペアで表されます。 x 座標は右に上がり、y 座標は上から下に増加します。 画面を基準とした原点の位置は、画面またはクライアントの座標を指定するかどうかによって異なります。  
  
## <a name="screen-coordinates"></a>画面座標  
 Windows フォームアプリケーションでは、画面上のウィンドウの位置を画面座標で指定します。 画面座標の場合、原点は画面の左上隅になります。 ウィンドウの完全な位置は、 <xref:System.Drawing.Rectangle> ウィンドウの左上隅と右下隅を定義する2つの点の画面座標を含む構造体によって記述されることがよくあります。  
  
## <a name="client-coordinates"></a>クライアント座標  
 Windows フォームアプリケーションは、クライアント座標を使用して、フォームまたはコントロール内の点の位置を指定します。 クライアント座標の原点は、コントロールまたはフォームのクライアント領域の左上隅です。 クライアント座標は、画面上のフォームまたはコントロールの位置に関係なく、フォームまたはコントロールに描画するときに、アプリケーションが一貫した座標値を使用できるようにします。  
  
 クライアント領域のサイズは、その <xref:System.Drawing.Rectangle> 領域のクライアント座標を含む構造体によっても記述されます。 いずれの場合も、四角形の左上の座標はクライアント領域に含まれ、右下の座標は除外されます。 グラフィックス操作には、クライアント領域の右端と下端は含まれません。 たとえば、メソッドは、 <xref:System.Drawing.Graphics.FillRectangle%2A> 指定された四角形の右端と下端までを格納しますが、これらの端は含まれません。  
  
## <a name="mapping-from-one-type-of-coordinate-to-another"></a>ある種類の座標から別の型へのマッピング  
 場合によっては、画面座標からクライアント座標にマップする必要があります。 これは、 <xref:System.Windows.Forms.Control.PointToClient%2A> <xref:System.Windows.Forms.Control.PointToScreen%2A> クラスで使用可能なメソッドとメソッドを使用して簡単に実行でき <xref:System.Windows.Forms.Control> ます。 たとえば、 <xref:System.Windows.Forms.Control.MousePosition%2A> のプロパティ <xref:System.Windows.Forms.Control> は画面座標で報告されますが、これらをクライアント座標に変換することができます。  
  
## <a name="see-also"></a>関連項目

- <xref:System.Windows.Forms.Control.PointToClient%2A>
- <xref:System.Windows.Forms.Control.PointToScreen%2A>
