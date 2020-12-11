---
title: Windows フォームの WPF コントロールを選択する
titleSuffix: ''
ms.date: 03/30/2017
helpviewer_keywords:
- WPF content [Windows Forms], assigning at design time
- ElementHost control [Windows Forms], assigning WPF content at design time
- interoperability [WPF]
- Windows Forms, content assignments
- WPF user control [Windows Forms], hosting in Windows Forms
ms.assetid: b3e9ef93-7e0f-4a2f-8f1e-3437609a1eb7
author: jillre
ms.author: jillfra
manager: jillfra
ms.openlocfilehash: c1532206b467c523ffd8e4cf4f85c168a4aad80b
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/09/2020
ms.locfileid: "96981167"
---
# <a name="walkthrough-assign-wpf-content-on-windows-forms-at-design-time"></a>チュートリアル: デザイン時の Windows フォームでの WPF コンテンツの割り当て

この記事では、フォームに表示する Windows Presentation Foundation (WPF) コントロールの種類を選択する方法について説明します。 プロジェクトに含まれている WPF コントロールの種類を選択できます。

## <a name="prerequisites"></a>必須コンポーネント

このチュートリアルを完了するには Visual Studio が必要です。

## <a name="create-the-project"></a>プロジェクトを作成する

Visual Studio を開き、Visual Basic またはという名前の Visual C# で新しい Windows フォームアプリケーションプロジェクトを作成し `SelectingWpfContent` ます。

> [!NOTE]
> WPF コンテンツをホストする場合は、C# プロジェクトと Visual Basic プロジェクトのみがサポートされます。

## <a name="create-the-wpf-control-types"></a>WPF コントロール型を作成する

プロジェクトに追加した WPF コントロール型は、さまざまな <xref:System.Windows.Forms.Integration.ElementHost> コントロール内でホストできます。

1. 新しい WPF <xref:System.Windows.Controls.UserControl> プロジェクトをソリューションに追加します。 コントロール型の既定の名前である `UserControl1.xaml` を使用します。 詳細については、「 [チュートリアル: デザイン時の Windows フォームでの新しい WPF コンテンツの作成](walkthrough-creating-new-wpf-content-on-windows-forms-at-design-time.md)」を参照してください。

2. デザイン ビューで `UserControl1` が選択されていることを確認します。

3. [ **プロパティ** ] ウィンドウで、 <xref:System.Windows.FrameworkElement.Width%2A> プロパティとプロパティの値を <xref:System.Windows.FrameworkElement.Height%2A> **200** に設定します。

4. <xref:System.Windows.Controls.TextBox?displayProperty=nameWithType>にコントロールを追加 <xref:System.Windows.Controls.UserControl> し、プロパティの値 <xref:System.Windows.Controls.TextBox.Text%2A> を **ホステッドコンテンツ** に設定します。

5. WPF <xref:System.Windows.Controls.UserControl> をプロジェクトにもう 1 つ追加します。 コントロール型の既定の名前である `UserControl2.xaml` を使用します。

6. [ **プロパティ** ] ウィンドウで、 <xref:System.Windows.FrameworkElement.Width%2A> プロパティとプロパティの値を <xref:System.Windows.FrameworkElement.Height%2A> **200** に設定します。

7. <xref:System.Windows.Controls.TextBox?displayProperty=nameWithType>にコントロールを追加 <xref:System.Windows.Controls.UserControl> し、プロパティの値 <xref:System.Windows.Controls.TextBox.Text%2A> を **Hosted Content 2** に設定します。

   > [!NOTE]
   > 一般的には、もう少し高度な WPF コンテンツをホストしてください。 ここでは、説明する目的でのみ <xref:System.Windows.Controls.TextBox?displayProperty=nameWithType> コントロールを使用しています。

8. プロジェクトをビルドします。

## <a name="select-wpf-controls"></a>WPF コントロールの選択

既にコンテンツをホストしている <xref:System.Windows.Forms.Integration.ElementHost> コントロールに異なる WPF コンテンツを割り当てることができます。

1. Windows フォーム デザイナーで `Form1` を開きます。

2. **ツールボックス** で、をダブルクリックして、 `UserControl1` フォーム上にのインスタンスを作成し `UserControl1` ます。

   `UserControl1` のインスタンスは、`elementHost1` という名前の新しい <xref:System.Windows.Forms.Integration.ElementHost> コントロールでホストされます。

3. のスマートタグパネルで、 `elementHost1` **[ホスト** されているコンテンツの選択] ドロップダウンリストを開きます。

4. ドロップダウンリストボックスから [ **usercontrol2]** ] を選択します。

   これで、`elementHost1` コントロールが `UserControl2` 型のインスタンスをホストするようになりました。

5. [ **プロパティ** ] ウィンドウで、 <xref:System.Windows.Forms.Integration.ElementHost.Child%2A> プロパティが **usercontrol2]** に設定されていることを確認します。

6. [ **ツールボックス**] の [ **WPF 相互運用性** ] グループで、 <xref:System.Windows.Forms.Integration.ElementHost> コントロールをフォームにドラッグします。

   新しい名前として、このコントロールの既定である `elementHost2` を使用します。

7. のスマートタグパネルで、 `elementHost2` **[ホスト** されているコンテンツの選択] ドロップダウンリストを開きます。

8. ドロップダウンリストから [ **UserControl1** ] を選択します。

9. これで、`elementHost2` コントロールが `UserControl1` 型のインスタンスをホストするようになりました。

## <a name="see-also"></a>関連項目

- <xref:System.Windows.Forms.Integration.ElementHost>
- <xref:System.Windows.Forms.Integration.WindowsFormsHost>
- [移行と相互運用性](/dotnet/framework/wpf/advanced/migration-and-interoperability)
- [WPF コントロールの使用](using-wpf-controls.md)
- [Visual Studio で XAML をデザインする](/visualstudio/xaml-tools/designing-xaml-in-visual-studio)
