---
title: グラフィックス コンテナーの使用
ms.date: 03/30/2017
helpviewer_keywords:
- graphics [Windows Forms], using containers
- graphics containers
- examples [Windows Forms], graphics containers
ms.assetid: 74632f91-cefa-4f51-ab7c-f9ac91942caf
ms.openlocfilehash: cfad7254057a31ea8268784cd4b6849850f3e2aa
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/09/2020
ms.locfileid: "96975225"
---
# <a name="using-graphics-containers"></a>グラフィックス コンテナーの使用
オブジェクトには <xref:System.Drawing.Graphics> <xref:System.Drawing.Graphics.DrawLine%2A> 、 <xref:System.Drawing.Graphics.DrawImage%2A> <xref:System.Drawing.Graphics.DrawString%2A> ベクターイメージ、ラスターイメージ、およびテキストを表示するための、、およびなどのメソッドが用意されています。 <xref:System.Drawing.Graphics>オブジェクトには、描画される項目の品質と向きに影響を与えるいくつかのプロパティもあります。 たとえば、スムージングモードプロパティは、アンチエイリアシングが線と曲線に適用されるかどうかを決定し、ワールド変換プロパティは描画される項目の位置と回転に影響します。  
  
 <xref:System.Drawing.Graphics>オブジェクトは、特定のディスプレイデバイスに関連付けられています。 オブジェクトを使用して <xref:System.Drawing.Graphics> ウィンドウに描画すると、 <xref:System.Drawing.Graphics> オブジェクトもその特定のウィンドウに関連付けられます。  
  
 オブジェクトは、 <xref:System.Drawing.Graphics> 描画に影響を与える一連のプロパティを保持し、デバイス固有の情報にリンクされるため、コンテナーと考えることができます。 既存 <xref:System.Drawing.Graphics> のオブジェクトのメソッドを呼び出すことによって、既存のオブジェクト内にセカンダリコンテナーを作成でき <xref:System.Drawing.Graphics.BeginContainer%2A> <xref:System.Drawing.Graphics> ます。  
  
## <a name="in-this-section"></a>このセクションの内容  
 [Graphics オブジェクトの状態の管理](managing-the-state-of-a-graphics-object.md)  
 オブジェクトの品質設定、クリッピング領域、および変換を管理する方法について説明し <xref:System.Drawing.Graphics> ます。  
  
 [入れ子になっているグラフィックス コンテナーの使用](using-nested-graphics-containers.md)  
 コンテナーを使用してオブジェクトの状態を制御する方法について説明し <xref:System.Drawing.Graphics> ます。
