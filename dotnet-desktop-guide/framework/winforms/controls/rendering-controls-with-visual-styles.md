---
title: visual スタイルが使用されているコントロールのレンダリング
ms.date: 03/30/2017
helpviewer_keywords:
- professional appearance [Windows Forms], rendering Windows Forms controls
- themes [Windows Forms], XP visual styles in Window Forms
- custom controls [Windows Forms], rendering
- custom controls [Windows Forms], painting
- visual themes [Windows Forms], rendering Windows Forms controls
- user controls [Windows Forms], painting
- visual styles [Windows Forms], rendering Windows Forms controls
ms.assetid: a5b178ba-610e-46c4-a6c0-509c0886a744
ms.openlocfilehash: 32bcbab585c39be4a72150bf49820d4a16f1691f
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/09/2020
ms.locfileid: "96982471"
---
# <a name="rendering-controls-with-visual-styles"></a>visual スタイルが使用されているコントロールのレンダリング
.NET Framework では、コントロールやその他の Windows ユーザーインターフェイス (UI) 要素をサポートするオペレーティングシステムの visual スタイルを使用して、その要素のレンダリングをサポートしています。 このトピックでは、オペレーティングシステムの現在の視覚スタイルを使用してコントロールやその他の UI 要素をレンダリングするための、.NET Framework におけるいくつかのサポートレベルについて説明します。  
  
## <a name="rendering-classes-for-common-controls"></a>一般的なコントロールのクラスをレンダリングする  
 コントロールのレンダリングとは、コントロールのユーザー インターフェイスを描画することを意味します。 <xref:System.Windows.Forms?displayProperty=nameWithType> 名前空間は、いくつかの一般的な Windows フォーム コントロールをレンダリングするための <xref:System.Windows.Forms.ControlPaint> クラスを提供します。 ただし、このクラスは従来の Windows スタイルでコントロールを描画するため、視覚スタイルが有効になったアプリケーションでカスタム コントロールを描画する際の一貫した UI エクスペリエンスの維持が困難になる可能性があります。  
  
 .NET Framework 2.0 には、 <xref:System.Windows.Forms?displayProperty=nameWithType> visual スタイルを使用して一般的なコントロールのパーツと状態をレンダリングする名前空間のクラスが含まれています。 これらの各クラスに含まれる `static` メソッドにより、オペレーティング システムの現在の視覚スタイルを使用して、特定の状態のコントロールまたはコントロールのパーツを描画します。  
  
 これらのクラスの一部は、視覚スタイルが使用可能かどうかに関係なく関連するコントロールを描画するように設計されています。 視覚スタイルが有効になっている場合、クラス メンバーは視覚スタイルを使用して関連するコントロールを描画します。視覚スタイルが無効になっている場合、クラス メンバーは、従来の Windows スタイルでコントロールを描画します。 次のようなクラスがこれに含まれます。  
  
- <xref:System.Windows.Forms.ButtonRenderer>  
  
- <xref:System.Windows.Forms.CheckBoxRenderer>  
  
- <xref:System.Windows.Forms.GroupBoxRenderer>  
  
- <xref:System.Windows.Forms.RadioButtonRenderer>  
  
 他のクラスは、視覚スタイルが使用可能な場合にのみ関連するコントロールを描画することができ、視覚スタイルが無効になっている場合、それらのメンバーは例外をスローします。 次のようなクラスがこれに含まれます。  
  
- <xref:System.Windows.Forms.ComboBoxRenderer>  
  
- <xref:System.Windows.Forms.ProgressBarRenderer>  
  
- <xref:System.Windows.Forms.ScrollBarRenderer>  
  
- <xref:System.Windows.Forms.TabRenderer>  
  
- <xref:System.Windows.Forms.TextBoxRenderer>  
  
- <xref:System.Windows.Forms.TrackBarRenderer>  
  
 これらのクラスを使用したコントロールの描画の詳細については、「 [How to: Use a Control Rendering Class](how-to-use-a-control-rendering-class.md)」を参照してください。  
  
## <a name="visual-style-element-and-rendering-classes"></a>視覚スタイル要素とレンダリング クラス  
 <xref:System.Windows.Forms.VisualStyles?displayProperty=nameWithType> 名前空間に含まれるクラスを使用して、視覚スタイルによってサポートされる任意のコントロールまたは UI 要素を描画したり、それらに関する情報を取得したりすることができます。 サポートされるコントロールには、 <xref:System.Windows.Forms?displayProperty=nameWithType> 名前空間のレンダリング クラスを使用する一般的なコントロール (前のセクションを参照してください)、およびタブ コントロールや rebar コントロールなどの他のコントロールが含まれます。 他のサポートされる UI 要素には、 **[スタート]** メニュー、タスクバー、ウィンドウの非クライアント領域のパーツなどがあります。  
  
 <xref:System.Windows.Forms.VisualStyles?displayProperty=nameWithType> 名前空間の主要なクラスは <xref:System.Windows.Forms.VisualStyles.VisualStyleElement> と <xref:System.Windows.Forms.VisualStyles.VisualStyleRenderer>です。 <xref:System.Windows.Forms.VisualStyles.VisualStyleElement> は、視覚スタイルによってサポートされる任意のコントロールまたはユーザー インターフェイス要素を識別するための基盤クラスです。 <xref:System.Windows.Forms.VisualStyles.VisualStyleElement> 自体に加えて、 <xref:System.Windows.Forms.VisualStyles?displayProperty=nameWithType> 名前空間には、視覚スタイルによってサポートされるコントロール、コントロール パーツ、その他の UI 要素のすべての状態の <xref:System.Windows.Forms.VisualStyles.VisualStyleElement> を返す `static` プロパティを持つ <xref:System.Windows.Forms.VisualStyles.VisualStyleElement> の多くの入れ子になったクラスが含まれています。  
  
 <xref:System.Windows.Forms.VisualStyles.VisualStyleRenderer> は、オペレーティング システムの現在の視覚スタイルによって定義される各 <xref:System.Windows.Forms.VisualStyles.VisualStyleElement> を描画したり、それらに関する情報を取得したりするメソッドを提供します。 取得可能な要素に関する情報には、既定のサイズ、背景の種類、色の定義などが含まれます。 <xref:System.Windows.Forms.VisualStyles.VisualStyleRenderer> は、Windows プラットフォーム SDK の Windows シェル部分からの視覚スタイル (UxTheme) API の機能をラップします。 詳細については、「 [Visual スタイルの有効化](/windows/desktop/controls/cookbook-overview)」を参照してください。  
  
 との使用方法の詳細については <xref:System.Windows.Forms.VisualStyles.VisualStyleRenderer> <xref:System.Windows.Forms.VisualStyles.VisualStyleElement> 、「 [方法: Visual スタイル要素を表示する](how-to-render-a-visual-style-element.md)」を参照してください。  
  
## <a name="enabling-visual-styles"></a>視覚スタイルを有効にする  
 .NET Framework バージョン1.0 用に記述されたアプリケーションの visual スタイルを有効にするには、ComCtl32.dll バージョン6以降をコントロールの描画に使用することを指定するアプリケーションマニフェストをプログラマに含める必要があります。 .NET Framework バージョン1.1 以降でビルドされたアプリケーションでは、 <xref:System.Windows.Forms.Application.EnableVisualStyles%2A?displayProperty=nameWithType> クラスのメソッドを使用でき <xref:System.Windows.Forms.Application> ます。  
  
## <a name="checking-for-visual-styles-support"></a>視覚スタイルのサポートの確認  
 <xref:System.Windows.Forms.Application.RenderWithVisualStyles%2A> クラスの <xref:System.Windows.Forms.Application> プロパティは、現在のアプリケーションが視覚スタイルを使用してコントロールを描画しているかどうかを示します。 カスタム コントロールを描画するときには、 <xref:System.Windows.Forms.Application.RenderWithVisualStyles%2A> の値を確認して、コントロールのレンダリングに視覚スタイルを使用する必要があるかどうかを判断できます。 次の表に、 <xref:System.Windows.Forms.Application.RenderWithVisualStyles%2A> が `true`を返すために満たす必要がある 4 つの条件を示します。  
  
|条件|Notes|  
|---------------|-----------|  
|オペレーティング システム視覚スタイルをサポートしている。|この条件を個別に確認するには、 <xref:System.Windows.Forms.VisualStyles.VisualStyleInformation.IsSupportedByOS%2A> クラスの <xref:System.Windows.Forms.VisualStyles.VisualStyleInformation> プロパティを使用します。|  
|ユーザーがオペレーティング システムで視覚スタイルを有効にしている。|この条件を個別に確認するには、 <xref:System.Windows.Forms.VisualStyles.VisualStyleInformation.IsEnabledByUser%2A> クラスの <xref:System.Windows.Forms.VisualStyles.VisualStyleInformation> プロパティを使用します。|  
|アプリケーションで視覚スタイルが有効になっている。|アプリケーションで視覚スタイルを有効にするには、 <xref:System.Windows.Forms.Application.EnableVisualStyles%2A?displayProperty=nameWithType> メソッドを呼び出すか、ComCtl32.dll バージョン 6 以降をコントロールの描画に使用することを指定するアプリケーション マニフェストを使用します。|  
|アプリケーション ウィンドウのクライアント領域を描画するために視覚スタイルが使用されている。|この条件を個別に確認するには、 <xref:System.Windows.Forms.Application.VisualStyleState%2A> クラスの <xref:System.Windows.Forms.Application> プロパティを使用し、その値が <xref:System.Windows.Forms.VisualStyles.VisualStyleState.ClientAreaEnabled?displayProperty=nameWithType> または <xref:System.Windows.Forms.VisualStyles.VisualStyleState.ClientAndNonClientAreasEnabled?displayProperty=nameWithType>になっていることを確認します。|  
  
 ユーザーが視覚スタイルの有効と無効を切り替えたり、1 つの視覚スタイルから別の視覚スタイルに切り替えたりしたときに、それを確認するには、 <xref:Microsoft.Win32.UserPreferenceCategory.VisualStyle?displayProperty=nameWithType> または <xref:Microsoft.Win32.SystemEvents.UserPreferenceChanging?displayProperty=nameWithType> イベントのハンドラーの <xref:Microsoft.Win32.SystemEvents.UserPreferenceChanged?displayProperty=nameWithType> 値を確認します。  
  
> [!IMPORTANT]
> ユーザーが視覚スタイルを有効にしたり切り替えたりしたときに、 <xref:System.Windows.Forms.VisualStyles.VisualStyleRenderer> を使用してコントロールまたは UI 要素をレンダリングする場合は、 <xref:Microsoft.Win32.SystemEvents.UserPreferenceChanged> イベントではなく <xref:Microsoft.Win32.SystemEvents.UserPreferenceChanging> イベントを処理するときにこの処理を実行してください。 <xref:System.Windows.Forms.VisualStyles.VisualStyleRenderer> を処理するときに <xref:Microsoft.Win32.SystemEvents.UserPreferenceChanging>クラスを使用した場合は、例外がスローされます。  
  
## <a name="see-also"></a>関連項目

- [コントロールのカスタム描画およびレンダリング](custom-control-painting-and-rendering.md)
