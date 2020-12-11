---
title: デザイナーを使用してマルチペインユーザーインターフェイスを作成する
ms.date: 03/30/2017
helpviewer_keywords:
- user interface [Windows Forms], multipane
- SplitContainer control [Windows Forms], using the designer
- multipane user interface
ms.assetid: c3f9294d-a26c-4198-9242-f237f55f7573
ms.openlocfilehash: 6b41d538f1cd1633cec51c89e27adf3c5b47f9a6
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/09/2020
ms.locfileid: "96974262"
---
# <a name="how-to-create-a-multipane-user-interface-with-windows-forms-using-the-designer"></a>方法: デザイナーを使用して Windows フォームでマルチペイン ユーザー インターフェイスを作成する
次の手順では、Microsoft Outlook で使用されているものと同様のマルチペインユーザーインターフェイスを作成します。これは、 **フォルダー** リスト、 **メッセージ** ペイン、および **プレビュー** ウィンドウで使用します。 この配置は、フォームを使用してドッキングコントロールを主することで実現されます。

 コントロールをドッキングすると、コントロールが固定されている親コンテナーの端が決まります。 したがって、プロパティをに設定すると、 <xref:System.Windows.Forms.SplitContainer.Dock%2A> <xref:System.Windows.Forms.DockStyle.Right> コントロールの右端が親コントロールの右端にドッキングされます。 さらに、ドッキングしたコントロールの端は、コンテナーコントロールの端に合わせて変更されます。 プロパティの動作の詳細については <xref:System.Windows.Forms.SplitContainer.Dock%2A> 、「 [方法: Windows フォームにコントロールをドッキング](how-to-dock-controls-on-windows-forms.md)する」を参照してください。

 この手順では、 <xref:System.Windows.Forms.SplitContainer> アプリケーションが Microsoft Outlook を模倣するように機能を追加するのではなく、フォーム上のと他のコントロールを配置する方法に焦点を当てます。

 このユーザーインターフェイスを作成するには、すべてのコントロールをコントロール内に配置します。コントロールには、 <xref:System.Windows.Forms.SplitContainer> 左側のパネルにコントロールが含まれてい <xref:System.Windows.Forms.TreeView> ます。 コントロールの右側のパネルには、コントロールの <xref:System.Windows.Forms.SplitContainer> 上にコントロールを持つ2つ目のコントロールが含まれてい <xref:System.Windows.Forms.SplitContainer> <xref:System.Windows.Forms.ListView> <xref:System.Windows.Forms.RichTextBox> ます。 これらの <xref:System.Windows.Forms.SplitContainer> コントロールを使用すると、フォーム上の他のコントロールのサイズを個別に変更できます。 この手順の手法を調整して、独自のカスタムユーザーインターフェイスを作成することができます。

## <a name="to-create-an-outlook-style-user-interface-at-design-time"></a>デザイン時に Outlook スタイルのユーザーインターフェイスを作成するには

1. 新しい Windows アプリケーションプロジェクトを作成します ([**ファイル**] [  >  **新しい**  >  **プロジェクト**] [  >  **Visual C#** ] または [ **Visual Basic**  >  **クラシックデスクトップ**  >  **Windows フォームアプリケーション**])。

2. コントロールを <xref:System.Windows.Forms.SplitContainer> [ **ツールボックス** ] からフォームにドラッグします。 **[プロパティ]** ウィンドウで、 <xref:System.Windows.Forms.SplitContainer.Dock%2A> プロパティを <xref:System.Windows.Forms.DockStyle.Fill>に設定します。

3. コントロールを <xref:System.Windows.Forms.TreeView> [ **ツールボックス** ] からコントロールの左側のパネルにドラッグし <xref:System.Windows.Forms.SplitContainer> ます。 [ **プロパティ** ] ウィンドウで、 <xref:System.Windows.Forms.SplitContainer.Dock%2A> <xref:System.Windows.Forms.DockStyle.Left> 下矢印がクリックされたときに表示される値エディターで左側のパネルをクリックして、プロパティをに設定します。

4. <xref:System.Windows.Forms.SplitContainer>**ツールボックス** から別のコントロールをドラッグし、 <xref:System.Windows.Forms.SplitContainer> フォームに追加したコントロールの右側のパネルに配置します。 [ **プロパティ** ] ウィンドウで、プロパティをに設定し、 <xref:System.Windows.Forms.SplitContainer.Dock%2A> <xref:System.Windows.Forms.DockStyle.Fill> <xref:System.Windows.Forms.SplitContainer.Orientation%2A> プロパティをに設定し <xref:System.Windows.Forms.Orientation.Horizontal> ます。

5. <xref:System.Windows.Forms.ListView>フォームに追加した2つ目のコントロールの上のパネルに、**ツールボックス** からコントロールをドラッグし <xref:System.Windows.Forms.SplitContainer> ます。 <xref:System.Windows.Forms.SplitContainer.Dock%2A> プロパティの <xref:System.Windows.Forms.ListView> コントロールを <xref:System.Windows.Forms.DockStyle.Fill>に設定します。

6. <xref:System.Windows.Forms.RichTextBox>**ツールボックス** からコントロールを2番目のコントロールの下のパネルにドラッグし <xref:System.Windows.Forms.SplitContainer> ます。 <xref:System.Windows.Forms.SplitContainer.Dock%2A> プロパティの <xref:System.Windows.Forms.RichTextBox> コントロールを <xref:System.Windows.Forms.DockStyle.Fill>に設定します。

     この時点で、F5 キーを押してアプリケーションを実行すると、Microsoft Outlook のような3部構成のユーザーインターフェイスがフォームに表示されます。

    > [!NOTE]
    > コントロール内のいずれかのスプリッターの上にマウスポインターを置くと <xref:System.Windows.Forms.SplitContainer> 、内部ディメンションのサイズを変更できます。

アプリケーション開発のこの時点で、洗練されたユーザーインターフェイスを作成しました。 次の手順では、アプリケーション自体のプログラミングに進み <xref:System.Windows.Forms.TreeView> ます。たとえば、コントロールと <xref:System.Windows.Forms.ListView> コントロールを何らかの種類のデータソースに接続します。 コントロールをデータに接続する方法の詳細については、「 [データバインディングと Windows フォーム](../data-binding-and-windows-forms.md)」を参照してください。

## <a name="see-also"></a>関連項目

- <xref:System.Windows.Forms.SplitContainer>
- [SplitContainer コントロール](splitcontainer-control-windows-forms.md)
