---
title: 余白、余白、および AutoSize プロパティを使用してコントロールをレイアウトします
ms.date: 03/30/2017
f1_keywords:
- Margin.Bottom
- Margin.Left
- Margin.Top
- Margin.All
- Margin.Right
helpviewer_keywords:
- Margin property [Windows Forms], walkthroughs
- walkthroughs [Windows Forms], layout
- AutoSize property [Windows Forms], walkthroughs
- Padding property [Windows Forms], walkthroughs
- layout [Windows Forms], margins and padding
- Windows Forms, layout
ms.assetid: f8ae2a6b-db13-4630-8e25-d104091205c7
author: jillre
ms.author: jillfra
manager: jillfra
ms.openlocfilehash: ca7942c04434592f2541252c47ac3dd17e03dbac
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/09/2020
ms.locfileid: "96980029"
---
# <a name="walkthrough-lay-out-controls-with-padding-margins-and-the-autosize-property"></a>チュートリアル: padding、margin、および AutoSize プロパティを使用してコントロールをレイアウトする

フォーム上のコントロールを正確に配置することは、多くのアプリケーションで優先度の高い作業です。 Visual Studio の **Windows フォームデザイナー** には、これを実現するためのさまざまなレイアウトツールが用意されています。 最も重要なのは <xref:System.Windows.Forms.Control.Margin%2A> 、すべての <xref:System.Windows.Forms.Control.Padding%2A> <xref:System.Windows.Forms.Control.AutoSize%2A> Windows フォームコントロールに存在する、、、およびの各プロパティです。

<xref:System.Windows.Forms.Control.Margin%2A> プロパティは、その他のコントロールで、コントロールの枠線からの指定された距離を保持するコントロールの周囲のスペースを定義します。

<xref:System.Windows.Forms.Control.Padding%2A> プロパティは、コントロールの内容 (<xref:System.Windows.Forms.Control.Text%2A> プロパティの値など) で、コントロールの枠線からの指定した距離を保持するコントロールの内部のスペースを定義します。

次の図は、コントロールの <xref:System.Windows.Forms.Control.Padding%2A> プロパティと <xref:System.Windows.Forms.Control.Margin%2A> プロパティを示しています。

![Windows フォーム コントロールのパディングとマージン](./media/vs-winformpadmargin.gif)

プロパティは、 <xref:System.Windows.Forms.Control.AutoSize%2A> コントロールがその内容に自動的にサイズを変更するように指示します。 元のプロパティの値よりも小さいサイズになることはなく、 <xref:System.Windows.Forms.Control.Size%2A> プロパティの値が考慮され <xref:System.Windows.Forms.Control.Padding%2A> ます。

## <a name="prerequisites"></a>前提条件

このチュートリアルを完了するには、Visual Studio が必要です。

## <a name="create-the-project"></a>プロジェクトを作成する

1. Visual Studio で、という名前の **Windows アプリケーション** プロジェクトを作成 `LayoutExample` します。

2. **Windows フォームデザイナー** でフォームを選択します。

## <a name="set-margins-for-controls"></a>コントロールの余白を設定する

コントロール間の既定の距離は、プロパティを使用して設定でき <xref:System.Windows.Forms.Control.Margin%2A> ます。 コントロールを別のコントロールに移動すると、2つのコントロールの余白を示すスナップ線が表示されます。 移動するコントロールは、余白で定義されている距離にもスナップされます。

### <a name="arrange-controls-on-your-form-using-the-margin-property"></a>Margin プロパティを使用してフォーム上のコントロールを配置する

1. <xref:System.Windows.Forms.Button>**ツールボックス** からフォームに2つのコントロールをドラッグします。

2. コントロールの1つを選択し、 <xref:System.Windows.Forms.Button> ほぼタッチするまで、そのコントロールの近くに移動します。

   これらの間に表示されるスナップ線を観察します。 この距離は、2つのコントロールの値の合計です <xref:System.Windows.Forms.Control.Margin%2A> 。 移動しようとしているコントロールは、この距離にスナップされます。 詳細については、「 [チュートリアル: スナップ線を使用した Windows フォームでのコントロールの配置](walkthrough-arranging-controls-on-windows-forms-using-snaplines.md)」を参照してください。

3. [ <xref:System.Windows.Forms.Control.Margin%2A> <xref:System.Windows.Forms.Control.Margin%2A> **プロパティ**] ウィンドウでエントリを展開し、プロパティを20に設定して、いずれかのコントロールのプロパティを変更し <xref:System.Windows.Forms.Padding.All%2A> ます。 

4. コントロールの1つを選択し、その <xref:System.Windows.Forms.Button> コントロールの近くに移動します。

   余白の値の合計を定義するスナップ線が長くなり、コントロールが他のコントロールから離れた距離にスナップされます。

5. <xref:System.Windows.Forms.Control.Margin%2A> <xref:System.Windows.Forms.Control.Margin%2A> [**プロパティ**] ウィンドウでエントリを展開し、プロパティを5に設定して、選択したコントロールのプロパティを変更し <xref:System.Windows.Forms.Padding.Top%2A> ます。 

6. 選択したコントロールを他のコントロールの下に移動し、スナップ線が短くなっていることを確認します。 選択したコントロールを他のコントロールの左側に移動し、スナップ線が手順 4. で観察した値を保持していることを確認します。

7. プロパティ、、、、の各側面を異なる値に設定することも、 <xref:System.Windows.Forms.Control.Margin%2A> <xref:System.Windows.Forms.Padding.Left%2A> プロパティを使用し <xref:System.Windows.Forms.Padding.Top%2A> <xref:System.Windows.Forms.Padding.Right%2A> <xref:System.Windows.Forms.Padding.Bottom%2A> てすべて同じ値に設定 <xref:System.Windows.Forms.Padding.All%2A> することもできます。

## <a name="set-padding-for-controls"></a>コントロールの埋め込みを設定する

アプリケーションに必要な正確なレイアウトを実現するために、コントロールには多くの場合、子コントロールが含まれます。 親コントロールの境界線に対する子コントロールの境界線の距離を指定する場合は、子コントロールのプロパティと共に親コントロールのプロパティを使用し <xref:System.Windows.Forms.Control.Padding%2A> <xref:System.Windows.Forms.Control.Margin%2A> ます。 <xref:System.Windows.Forms.Control.Padding%2A>プロパティは、コントロールのコンテンツ ( <xref:System.Windows.Forms.Button> コントロールのプロパティなど) の境界への近接を制御するためにも使用され <xref:System.Windows.Forms.Control.Text%2A> ます。

### <a name="arrange-controls-on-your-form-using-padding"></a>パディングを使用してフォームにコントロールを配置する

1. <xref:System.Windows.Forms.Button> ツールボックス **から** コントロールをフォームにドラッグします。

2. <xref:System.Windows.Forms.Button>コントロールのプロパティの値 <xref:System.Windows.Forms.Control.AutoSize%2A> を **true** に変更します。

3. プロパティを変更 <xref:System.Windows.Forms.Control.Padding%2A> するには <xref:System.Windows.Forms.Control.Padding%2A> 、[ **プロパティ** ] ウィンドウでエントリを展開し、 <xref:System.Windows.Forms.Padding.All%2A> プロパティを **5** に設定します。

   コントロールが拡張され、新しい埋め込み用の領域が提供されます。

4. <xref:System.Windows.Forms.GroupBox> ツールボックス **から** コントロールをフォームにドラッグします。 コントロールを [ <xref:System.Windows.Forms.Button> **ツールボックス** ] からコントロールにドラッグし <xref:System.Windows.Forms.GroupBox> ます。 コントロールを <xref:System.Windows.Forms.Button> コントロールの右下隅になるように配置し <xref:System.Windows.Forms.GroupBox> ます。

   コントロールとして表示されるスナップ線が、 <xref:System.Windows.Forms.Button> コントロールの下と右の境界線に近づいていることを確認し <xref:System.Windows.Forms.GroupBox> ます。 これらのスナップ線 <xref:System.Windows.Forms.Control.Margin%2A> は、のプロパティに対応して <xref:System.Windows.Forms.Button> います。

5. <xref:System.Windows.Forms.GroupBox> <xref:System.Windows.Forms.Control.Padding%2A> <xref:System.Windows.Forms.Control.Padding%2A> [**プロパティ**] ウィンドウでエントリを展開し、プロパティを20に設定して、コントロールのプロパティを変更し <xref:System.Windows.Forms.Padding.All%2A> ます。 

6. コントロール内のコントロールを選択し <xref:System.Windows.Forms.Button> <xref:System.Windows.Forms.GroupBox> 、の中央に移動し <xref:System.Windows.Forms.GroupBox> ます。

   スナップ線は、コントロールの境界から離れた位置に表示され <xref:System.Windows.Forms.GroupBox> ます。 この距離は、 <xref:System.Windows.Forms.Button> コントロールの <xref:System.Windows.Forms.Control.Margin%2A> プロパティと <xref:System.Windows.Forms.GroupBox> コントロールのプロパティの合計です <xref:System.Windows.Forms.Control.Padding%2A> 。

## <a name="size-controls-automatically"></a>コントロールを自動的にサイズ変更する

アプリケーションによっては、デザイン時と同じように、実行時にコントロールのサイズが同じになることはありません。 <xref:System.Windows.Forms.Button>たとえば、コントロールのテキストはデータベースから取得され、その長さは事前にわからない場合があります。

<xref:System.Windows.Forms.Control.AutoSize%2A>プロパティがに設定されている場合 `true` 、コントロールはその内容に合わせてサイズを変更します。 詳細については、「[AutoSize プロパティの概要](autosize-property-overview.md)」を参照してください。

### <a name="arrange-controls-on-your-form-using-the-autosize-property"></a>AutoSize プロパティを使用してフォーム上のコントロールを配置する

1. <xref:System.Windows.Forms.Button> ツールボックス **から** コントロールをフォームにドラッグします。

2. <xref:System.Windows.Forms.Button>コントロールのプロパティの値 <xref:System.Windows.Forms.Control.AutoSize%2A> を **true** に変更します。

3. <xref:System.Windows.Forms.Button>コントロールのプロパティを <xref:System.Windows.Forms.Control.Text%2A> このボタンに変更すると、**その Text プロパティに長い文字列が** 表示されます。

   変更をコミットすると、 <xref:System.Windows.Forms.Button> 新しいテキストに合わせてコントロールのサイズが変更されます。

4. <xref:System.Windows.Forms.Button>**ツールボックス** から別のコントロールをフォームにドラッグします。

5. <xref:System.Windows.Forms.Button>コントロールの <xref:System.Windows.Forms.Control.Text%2A> プロパティを "**このボタンには、テキストプロパティの長い文字列が含まれています**" に変更します。

   変更をコミットすると、コントロールのサイズが変更 <xref:System.Windows.Forms.Button> されず、テキストがコントロールの右端でクリップされます。

6. プロパティを変更 <xref:System.Windows.Forms.Control.Padding%2A> するには <xref:System.Windows.Forms.Control.Padding%2A> 、[ **プロパティ** ] ウィンドウでエントリを展開し、 <xref:System.Windows.Forms.Padding.All%2A> プロパティを **5** に設定します。

   コントロールの内部のテキストは、4辺すべてにクリップされます。

7. <xref:System.Windows.Forms.Button>コントロールの <xref:System.Windows.Forms.Control.AutoSize%2A> プロパティを **true** に変更します。

   コントロールは、 <xref:System.Windows.Forms.Button> 文字列全体をカバーするようにサイズを変更します。 また、テキストの周囲に埋め込みが追加されている <xref:System.Windows.Forms.Button> ため、コントロールが4つの方向に広がります。

8. <xref:System.Windows.Forms.Button> ツールボックス **から** コントロールをフォームにドラッグします。 フォームの右下隅近くに配置します。

9. <xref:System.Windows.Forms.Button>コントロールのプロパティの値 <xref:System.Windows.Forms.Control.AutoSize%2A> を **true** に変更します。

10. <xref:System.Windows.Forms.Button>コントロールのプロパティを <xref:System.Windows.Forms.Control.Anchor%2A> 、に設定し <xref:System.Windows.Forms.AnchorStyles.Right> <xref:System.Windows.Forms.AnchorStyles.Bottom> ます。

11. <xref:System.Windows.Forms.Button>コントロールの <xref:System.Windows.Forms.Control.Text%2A> プロパティを "**このボタンには、テキストプロパティの長い文字列が含まれています**" に変更します。

   変更をコミットすると、コントロールは左に向かってサイズが変更され <xref:System.Windows.Forms.Button> ます。 一般に、自動サイズ変更では、プロパティ設定とは逆の方向にコントロールのサイズが増加し <xref:System.Windows.Forms.Control.Anchor%2A> ます。

## <a name="autosize-and-autosizemode-properties"></a>AutoSize および System.windows.forms.datagridviewcolumn.autosizemode プロパティ

 一部のコントロールでは、プロパティをサポートして `AutoSizeMode` います。これにより、コントロールの自動サイズ変更動作をより細かく制御できます。

### <a name="use-the-autosizemode-property"></a>System.windows.forms.datagridviewcolumn.autosizemode プロパティを使用する

1. <xref:System.Windows.Forms.Panel> ツールボックス **から** コントロールをフォームにドラッグします。

2. <xref:System.Windows.Forms.Panel>コントロールのプロパティの値 <xref:System.Windows.Forms.Control.AutoSize%2A> を **true** に設定します。

3. コントロールを [ <xref:System.Windows.Forms.Button> **ツールボックス** ] からコントロールにドラッグし <xref:System.Windows.Forms.Panel> ます。

4. コントロール <xref:System.Windows.Forms.Button> の右下隅の近くにコントロールを配置 <xref:System.Windows.Forms.Panel> します。

5. コントロールを選択 <xref:System.Windows.Forms.Panel> し、右下のサイズ変更ハンドルを取得します。 コントロールのサイズを <xref:System.Windows.Forms.Panel> 大きくしたり小さくしたりします。

   > [!NOTE]
   > コントロールのサイズは自由 <xref:System.Windows.Forms.Panel> に変更できますが、 <xref:System.Windows.Forms.Button> コントロールの右下隅の位置よりもサイズを小さくすることはできません。 この動作は、プロパティの既定値であるによって指定され `AutoSizeMode` <xref:System.Windows.Forms.AutoSizeMode.GrowOnly> ます。

6. <xref:System.Windows.Forms.Panel>コントロールのプロパティの値 `AutoSizeMode` をに設定し <xref:System.Windows.Forms.AutoSizeMode.GrowAndShrink> ます。

   コントロールは、コントロールを <xref:System.Windows.Forms.Panel> 囲むようにサイズを調整し <xref:System.Windows.Forms.Button> ます。 コントロールのサイズを変更することはできません <xref:System.Windows.Forms.Panel> 。

7. コントロール <xref:System.Windows.Forms.Button> の左上隅にコントロールをドラッグし <xref:System.Windows.Forms.Panel> ます。

   コントロールは、 <xref:System.Windows.Forms.Panel> コントロールの新しい位置にサイズ変更され <xref:System.Windows.Forms.Button> ます。

## <a name="next-steps"></a>次のステップ

Windows フォームアプリケーションにコントロールを配置するためのレイアウト機能は他にも多数あります。 いくつかの組み合わせを次に示します。

- コントロールを使用してフォームを作成 <xref:System.Windows.Forms.TableLayoutPanel> します。 詳細については、「 [チュートリアル: TableLayoutPanel を使用した Windows フォームでのコントロールの配置](walkthrough-arranging-controls-on-windows-forms-using-a-tablelayoutpanel.md)」を参照してください。 コントロールのプロパティの値、 <xref:System.Windows.Forms.TableLayoutPanel> <xref:System.Windows.Forms.Control.Padding%2A> および子コントロールのプロパティを変更してみてください <xref:System.Windows.Forms.Control.Margin%2A> 。

- コントロールを使用して同じ実験を試してみてください <xref:System.Windows.Forms.FlowLayoutPanel> 。 詳細については、「 [チュートリアル: FlowLayoutPanel を使用した Windows フォームでのコントロールの配置](walkthrough-arranging-controls-on-windows-forms-using-a-flowlayoutpanel.md)」を参照してください。

- コントロールにドッキングされた子コントロールを試してみて <xref:System.Windows.Forms.Panel> ください。 プロパティは、プロパティのより一般的な実現方法であり、子コントロールを <xref:System.Windows.Forms.Control.Padding%2A> <xref:System.Windows.Forms.ScrollableControl.DockPadding%2A> コントロールに配置 <xref:System.Windows.Forms.Panel> し、子コントロールの <xref:System.Windows.Forms.Control.Dock%2A> プロパティをに設定することによって、このことを満たすことができます <xref:System.Windows.Forms.DockStyle.Fill> 。 <xref:System.Windows.Forms.Panel>コントロールの <xref:System.Windows.Forms.Control.Padding%2A> プロパティをさまざまな値に設定し、効果を確認します。

## <a name="see-also"></a>関連項目

- <xref:System.Windows.Forms.Control.AutoSize%2A>
- <xref:System.Windows.Forms.ScrollableControl.DockPadding%2A>
- <xref:System.Windows.Forms.Control.Margin%2A>
- <xref:System.Windows.Forms.Control.Padding%2A>
- [AutoSize プロパティの概要](autosize-property-overview.md)
- [チュートリアル: TableLayoutPanel を使用した Windows フォーム上のコントロールの配置](walkthrough-arranging-controls-on-windows-forms-using-a-tablelayoutpanel.md)
- [チュートリアル: FlowLayoutPanel を使用した Windows フォーム上のコントロールの配置](walkthrough-arranging-controls-on-windows-forms-using-a-flowlayoutpanel.md)
- [チュートリアル : スナップ線を使用した Windows フォーム上のコントロールの配置](walkthrough-arranging-controls-on-windows-forms-using-snaplines.md)
