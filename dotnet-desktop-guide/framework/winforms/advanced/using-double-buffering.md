---
title: ダブル バッファリングの使用
ms.date: 03/30/2017
helpviewer_keywords:
- graphics [Windows Forms], double buffering
- double buffering
- flicker [Windows Forms], reducing in Windows Forms
- buffering [Windows Forms], double buffering
ms.assetid: dc484e33-7101-4e4b-ada5-d3c96155fbcd
ms.openlocfilehash: 5b22336221c7bdda3c9dd7adf23308a2b0bad450
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/09/2020
ms.locfileid: "96975233"
---
# <a name="using-double-buffering"></a>ダブル バッファリングの使用
ダブルバッファリングされたグラフィックスを使用すると、複雑な描画操作を含むアプリケーションのちらつきを減らすことができます。 .NET Framework には、ダブルバッファリングの組み込みサポートが含まれています。また、グラフィックスを手動で管理して表示することもできます。  
  
## <a name="in-this-section"></a>このセクションの内容  
 [ダブル バッファリングされたグラフィックス](double-buffered-graphics.md)  
 ダブルバッファリングの概念と、.NET Framework サポートの概要について説明します。  
  
 [方法: フォームとコントロールのダブル バッファリングを行うことによってグラフィックスのちらつきを軽減する](how-to-reduce-graphics-flicker-with-double-buffering-for-forms-and-controls.md)  
 .NET Framework で既定のダブルバッファリングサポートを使用する方法を示します。  
  
 [方法: バッファリングされたグラフィックスを手動で管理する](how-to-manually-manage-buffered-graphics.md)  
 アプリケーションでダブルバッファリングを管理する方法を示します。  
  
 [方法: バッファリングされたグラフィックスを手動で描画する](how-to-manually-render-buffered-graphics.md)  
 ダブルバッファリングされたグラフィックスを表示する方法を示します。  
  
## <a name="reference"></a>リファレンス  
 <xref:System.Windows.Forms.Control.SetStyle%2A> ダブルバッファリングを有効にする制御メソッド。  
  
 <xref:System.Drawing.BufferedGraphicsContext> グラフィックスバッファーを作成するためのメソッドを提供します。  
  
 <xref:System.Drawing.BufferedGraphicsManager>  
 アプリケーションドメインのバッファーされたグラフィックスコンテキストへのアクセスを提供します。
