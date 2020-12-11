---
title: SplitContainer コントロールの概要
ms.date: 03/30/2017
f1_keywords:
- SplitContainer
helpviewer_keywords:
- SplitContainer control [Windows Forms], about SplitContainer control
ms.assetid: 6de5a5f7-97a5-402d-be6d-7e2785483db5
ms.openlocfilehash: f697629020342d534265c633707fed8c4a460e20
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/09/2020
ms.locfileid: "96982440"
---
# <a name="splitcontainer-control-overview-windows-forms"></a>SplitContainer コントロールの概要 (Windows フォーム)

Windows フォームの <xref:System.Windows.Forms.SplitContainer> コントロールは複合と考えることができ、移動可能なバーで区切られた 2 つのパネルです。 マウス ポインターがバーの上に移動すると、ポインターの形が変わり、バーが移動可能であることを示します。  
  
> [!IMPORTANT]
> **ツールボックス** では、 <xref:System.Windows.Forms.SplitContainer> <xref:System.Windows.Forms.Splitter> 以前のバージョンの Visual Studio にあったコントロールがコントロールに置き換わることができます。 <xref:System.Windows.Forms.SplitContainer> コントロールは <xref:System.Windows.Forms.Splitter> コントロールより優先されます。 <xref:System.Windows.Forms.Splitter> クラスは、既存のアプリケーションの互換性のために .NET Framework に含まれていますが、新しいプロジェクトでは <xref:System.Windows.Forms.SplitContainer> コントロールを使用することを強くお勧めします。  
  
 コントロールを使用 <xref:System.Windows.Forms.SplitContainer> すると、複雑なユーザーインターフェイスを作成できます。多くの場合、1つのパネルで選択すると、他のパネルに表示されるオブジェクトが決まります。 この配置は、情報の表示と参照に対して非常に効果的です。 2つのパネルを使用すると、領域内の情報を集計できます。また、バーまたは "スプリッター" を使用すると、ユーザーがパネルのサイズを簡単に変更できるようになります。  
  
 複数のコントロールを入れ子にする <xref:System.Windows.Forms.SplitContainer> こともできます。2つ目の <xref:System.Windows.Forms.SplitContainer> コントロールは水平方向に並べて、上と下のパネルを作成します。  
  
 <xref:System.Windows.Forms.SplitContainer>コントロールは既定でキーボードからアクセスできることに注意してください。 <xref:System.Windows.Forms.SplitContainer.IsSplitterFixed%2A> プロパティがに設定されている場合、ユーザーは方向キーを押してスプリッターを移動できます `false` 。  
  
 コントロール <xref:System.Windows.Forms.SplitContainer.Orientation%2A> のプロパティは、 <xref:System.Windows.Forms.SplitContainer> コントロール自体ではなく、スプリッターの方向を決定します。 このため、このプロパティがに設定されている場合、 <xref:System.Windows.Forms.Orientation.Vertical> スプリッターは上から下に実行され、左右のパネルが作成されます。  
  
 また、プロパティの値は、 <xref:System.Windows.Forms.SplitContainer.SplitterRectangle%2A> プロパティの値によって異なることに注意して <xref:System.Windows.Forms.SplitContainer.Orientation%2A> ください。 詳細については、「プロパティ」を参照してください <xref:System.Windows.Forms.SplitContainer.SplitterRectangle%2A> 。  
  
 また、コントロールのサイズと移動を制限することもでき <xref:System.Windows.Forms.SplitContainer> ます。 プロパティは、 <xref:System.Windows.Forms.SplitContainer.FixedPanel%2A> コントロールのサイズが変更された後も同じサイズのパネルをどのパネルに表示するかを決定 <xref:System.Windows.Forms.SplitContainer> し、プロパティは、 <xref:System.Windows.Forms.SplitContainer.IsSplitterFixed%2A> 分割線をキーボードまたはマウスで移動できるかどうかを決定します。  
  
> [!NOTE]
> <xref:System.Windows.Forms.SplitContainer.IsSplitterFixed%2A>プロパティがに設定されている場合でも、 `true` たとえば、プロパティを使用して、スプリッターがプログラムによって移動される場合があり <xref:System.Windows.Forms.SplitContainer.SplitterDistance%2A> ます。  
  
 最後に、コントロールの各パネルに <xref:System.Windows.Forms.SplitContainer> は、個々のサイズを決定するプロパティがあります。  
  
## <a name="commonly-used-properties-methods-and-events"></a>一般的に使用されるプロパティ、メソッド、およびイベント  
  
|名前|説明|  
|----------|-----------------|  
|<xref:System.Windows.Forms.SplitContainer.FixedPanel%2A> プロパティ|コントロールのサイズを変更した後、どのパネルを同じサイズのまま維持するかを指定し <xref:System.Windows.Forms.SplitContainer> ます。|  
|<xref:System.Windows.Forms.SplitContainer.IsSplitterFixed%2A> プロパティ|キーボードまたはマウスを使用してスプリッターを移動できるかどうかを決定します。|  
|<xref:System.Windows.Forms.SplitContainer.Orientation%2A> プロパティ|分割線を垂直方向または水平方向のどちらに配置するかを決定します。|  
|<xref:System.Windows.Forms.SplitContainer.SplitterDistance%2A> プロパティ|左端または上端から移動可能スプリッターバーまでの距離をピクセル単位で決定します。|  
|<xref:System.Windows.Forms.SplitContainer.SplitterIncrement%2A> プロパティ|ユーザーがスプリッターを移動できる最小距離をピクセル単位で指定します。|  
|<xref:System.Windows.Forms.SplitContainer.SplitterWidth%2A> プロパティ|分割線の太さ (ピクセル単位) を決定します。|  
|<xref:System.Windows.Forms.SplitContainer.SplitterMoving> イベント|スプリッターの移動中に発生します。|  
|<xref:System.Windows.Forms.SplitContainer.SplitterMoved> イベント|スプリッターが移動したときに発生します。|  
  
## <a name="see-also"></a>関連項目

- <xref:System.Windows.Forms.SplitContainer>
- [SplitContainer コントロール](splitcontainer-control-windows-forms.md)
- [SplitContainer コントロールのサンプル](/previous-versions/visualstudio/visual-studio-2008/0ffz7d1b(v=vs.90))
