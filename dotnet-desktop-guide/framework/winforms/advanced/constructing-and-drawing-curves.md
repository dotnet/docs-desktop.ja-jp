---
title: 曲線の作成と描画
ms.date: 03/30/2017
helpviewer_keywords:
- drawing [Windows Forms], curves
- examples [Windows Forms], drawing curves
- curves [Windows Forms], drawing
ms.assetid: 76e92623-4130-4644-b867-faca58bdb3a2
ms.openlocfilehash: 4c1b0cc6c6f878569fcf0c392f1b6f9683ec8afc
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/09/2020
ms.locfileid: "96975049"
---
# <a name="constructing-and-drawing-curves"></a>曲線の作成と描画
GDI + では、楕円、円弧、カーディナルスプライン、ベジエスプラインなど、いくつかの種類の曲線がサポートされています。 楕円は、外接する四角形によって定義されます。弧は、開始角度とスイープ角度で定義された楕円の一部です。 カーディナルスプラインは、点の配列とテンションパラメーターによって定義されます。曲線は配列内の各点をスムーズに通過し、テンションパラメーターは曲線のベンド方法に影響します。 ベジエスプラインは、2つのエンドポイントと2つの制御点によって定義されています。曲線はコントロールポイントを通過しませんが、曲線があるエンドポイントから別のエンドポイントに到達すると、制御点が方向とベンドに影響します。  
  
## <a name="in-this-section"></a>このセクションの内容  
 [方法: カーディナル スプラインを描画する](how-to-draw-cardinal-splines.md)  
 カーディナルスプラインとその描画方法について説明します。  
  
 [方法: 1 本のベジエ スプラインを描画する](how-to-draw-a-single-bezier-spline.md)  
 ベジエスプラインとその描画方法について説明します。  
  
 [方法: 一連のベジエ スプラインを描画する](how-to-draw-a-sequence-of-bezier-splines.md)  
 複数のベジエスプラインを順番に描画する方法について説明します。
