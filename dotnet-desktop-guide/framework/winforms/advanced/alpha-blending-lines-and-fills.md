---
title: アルファ ブレンドの直線と塗りつぶし
ms.date: 03/30/2017
helpviewer_keywords:
- lines [Windows Forms], adding transparency
- examples [Windows Forms], alpha blending
- alpha blending [Windows Forms], using with lines
- alpha blending
- lines [Windows Forms], alpha blending
- fills [Windows Forms], alpha blending
- alpha blending [Windows Forms], using with fills
- shapes [Windows Forms], adding transparency
ms.assetid: 5440f48c-3ac9-44c3-b170-c1c110bdbab8
ms.openlocfilehash: 66061341ee6539e2172c537a0b2a6ec9ff87565c
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/09/2020
ms.locfileid: "96974910"
---
# <a name="alpha-blending-lines-and-fills"></a>アルファ ブレンドの直線と塗りつぶし
GDI + では、色はそれぞれアルファ、赤、緑、および青の8ビットを持つ32ビット値です。 アルファ値は、色の透明度 (色を背景色とブレンドする範囲) を示します。 アルファ値は 0 ~ 255 の範囲です。0は完全に透明な色を表し、255は完全に不透明な色を表します。  
  
 アルファブレンドは、ソースと背景のカラーデータのピクセル単位のブレンドです。 特定のソース色の3つの各コンポーネント (赤、緑、青) は、次の式に従って、背景色の対応する要素とブレンドされます。  
  
 displayColor = sourceColor × alpha/255 + backgroundColor × (255 – alpha)/255  
  
 たとえば、ソースの色の赤の部分が150で、背景色の赤の要素が100であるとします。 アルファ値が200の場合、結果の色の赤の成分は次のように計算されます。  
  
 150 × 200 / 255 + 100 × (255 – 200) / 255 = 139  
  
## <a name="in-this-section"></a>このセクションの内容  
 [方法: 不透明な直線および半透明な直線を描画する](how-to-draw-opaque-and-semitransparent-lines.md)  
 アルファブレンドされた直線を描画する方法を示します。  
  
 [方法: 不透明ブラシおよび半透明ブラシを使用して描画する](how-to-draw-with-opaque-and-semitransparent-brushes.md)  
 ブラシを使用してアルファブレンドを行う方法について説明します。  
  
 [方法: 複合モードを使用してアルファ ブレンドを制御する](how-to-use-compositing-mode-to-control-alpha-blending.md)  
 を使用してアルファブレンドを制御する方法について説明し <xref:System.Drawing.Drawing2D.CompositingMode> ます。  
  
 [方法: カラー行列を使用してイメージのアルファ値を設定する](how-to-use-a-color-matrix-to-set-alpha-values-in-images.md)  
 オブジェクトを使用してアルファブレンドを制御する方法について説明 <xref:System.Drawing.Imaging.ColorMatrix> します。
