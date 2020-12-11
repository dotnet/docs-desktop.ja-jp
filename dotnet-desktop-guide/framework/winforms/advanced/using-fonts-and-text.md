---
title: フォントとテキストの使用
ms.date: 03/30/2017
helpviewer_keywords:
- GDI [Windows Forms], drawing text [Windows Forms]
- text [Windows Forms], drawing in Windows Forms
- examples [Windows Forms], fonts and text
- fonts [Windows Forms], using in Windows Forms
- strings [Windows Forms], drawing in Windows Forms
ms.assetid: d43640f3-da94-4df2-a29d-a9d021a1c069
ms.openlocfilehash: 73a4af5fe7367e777fcb83af8c84c09be91e5b1e
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/09/2020
ms.locfileid: "96981608"
---
# <a name="using-fonts-and-text"></a>フォントとテキストの使用
Windows フォームにテキストを描画するために GDI + と GDI によって提供されるいくつかのクラスがあります。 GDI + <xref:System.Drawing.Graphics> クラスには、 <xref:System.Drawing.Graphics.DrawString%2A> 場所、外接する四角形、フォント、書式など、テキストのさまざまな機能を指定できるいくつかのメソッドがあります。 さらに、 <xref:System.Windows.Forms.TextRenderer.DrawText%2A> <xref:System.Windows.Forms.TextRenderer.MeasureText%2A> クラスによって提供される静的メソッドとメソッドを使用して、GDI を使用してテキストを描画し、測定することができ `TextRenderer` ます。 GDI メソッドでは、場所、フォント、および形式を指定することもできます。 テキストレンダリングには、GDI または GDI + を選択できます。ただし、GDI は通常、より優れたパフォーマンスとより正確なテキスト測定を提供します。 テキストレンダリングに寄与するその他のクラスには `FontFamily` 、、、 `Font` 、およびがあり <xref:System.Drawing.StringFormat> `TextFormatFlags` ます。  
  
## <a name="in-this-section"></a>このセクションの内容  
 [方法: フォント ファミリとフォントを作成する](how-to-construct-font-families-and-fonts.md)  
 オブジェクトとオブジェクトを作成する方法について説明し `Font` `FontFamily` ます。  
  
 [方法: テキストを指定の位置に描画する](how-to-draw-text-at-a-specified-location.md)  
 GDI + と GDI を使用して特定の場所にテキストを描画する方法について説明します。  
  
 [方法: 四角形内にテキストを折り返して描画する](how-to-draw-wrapped-text-in-a-rectangle.md)  
 GDI + と GDI を使用して四角形にテキストを描画する方法について説明します。  
  
 [方法: GDI を使用してテキストを描画する](how-to-draw-text-with-gdi.md)  
 GDI を使用してテキストを描画する方法を示します。  
  
 [方法: 描画テキストを配置する](how-to-align-drawn-text.md)  
 GDI + と GDI テキストの書式を設定する方法について説明します。  
  
 [方法: 垂直方向のテキストを作成する](how-to-create-vertical-text.md)  
 GDI + で垂直方向に配置されたテキストを描画する方法について説明します。  
  
 [方法: 描画されたテキストにタブ ストップを設定する](how-to-set-tab-stops-in-drawn-text.md)  
 GDI + でタブストップを使用してテキストを描画する方法について説明します。  
  
 [方法: インストールされているフォントを列挙する](how-to-enumerate-installed-fonts.md)  
 インストールされているフォントの名前を一覧表示する方法について説明します。  
  
 [方法: プライベート フォント コレクションを作成する](how-to-create-a-private-font-collection.md)  
 オブジェクトを作成する方法について説明し <xref:System.Drawing.Text.PrivateFontCollection> ます。  
  
 [方法: フォント メトリックを取得する](how-to-obtain-font-metrics.md)  
 セルのアセントや降下などのフォントメトリックを取得する方法について説明します。  
  
 [方法: テキストでのアンチエイリアシングの使用](how-to-use-antialiasing-with-text.md)  
 テキストを描画するときにアンチエイリアシングを使用する方法について説明します。  
  
## <a name="reference"></a>リファレンス  
 <xref:System.Drawing.Font>  
 このクラスについて説明し、そのすべてのメンバーへのリンクを示します。  
  
 <xref:System.Drawing.FontFamily>  
 このクラスについて説明し、そのすべてのメンバーへのリンクを示します。  
  
 <xref:System.Drawing.Text.PrivateFontCollection>  
 このクラスについて説明し、そのすべてのメンバーへのリンクを示します。  
  
 <xref:System.Windows.Forms.TextRenderer>  
 このクラスについて説明し、そのすべてのメンバーへのリンクを示します。  
  
 <xref:System.Windows.Forms.TextFormatFlags>  
 このクラスについて説明し、そのすべてのメンバーへのリンクを示します。
