---
title: 'チュートリアル: ツールボックスへのカスタム コンポーネントの自動設定'
ms.date: 03/30/2017
helpviewer_keywords:
- IToolboxService interface
- Toolbox [Windows Forms], populating
- custom components [Windows Forms], adding to Toolbox
ms.assetid: 2fa1e3e8-6b9f-42b2-97c0-2be57444dba4
ms.openlocfilehash: 3ceebbf07c0241996479a6f7f72ab19f4cd9aa05
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/09/2020
ms.locfileid: "96982887"
---
# <a name="walkthrough-automatically-populating-the-toolbox-with-custom-components"></a>チュートリアル: ツールボックスへのカスタム コンポーネントの自動設定

現在開いているソリューションのプロジェクトによってコンポーネントが定義されている場合は、自動的に **ツールボックス** に表示され、ユーザーによる操作は必要ありません。 [[ツールボックスアイテムの選択] ダイアログボックス (Visual Studio)](/previous-versions/visualstudio/visual-studio-2010/dyca0t6t(v=vs.100))を使用してカスタムコンポーネントを **ツールボックス** に手動で設定することもできますが、**ツールボックス** では、ソリューションのビルド出力に含まれるアイテムのうち、次のすべての特性を使用します。

- を実装し <xref:System.ComponentModel.IComponent> ます。

- がに設定されていません <xref:System.ComponentModel.ToolboxItemAttribute> `false` 。

- がに設定されていません <xref:System.ComponentModel.DesignTimeVisibleAttribute> `false` 。

> [!NOTE]
> **ツールボックス** は参照チェーンに従っていないので、ソリューション内のプロジェクトでビルドされていない項目は表示されません。

このチュートリアルでは、コンポーネントがビルドされた後に、 **ツールボックス** にカスタムコンポーネントを自動的に表示する方法について説明します。 このチュートリアルでは、以下のタスクを行います。

- Windows フォームプロジェクトを作成しています。

- カスタムコンポーネントを作成しています。

- カスタムコンポーネントのインスタンスを作成する。

- カスタムコンポーネントのアンロードと再読み込み。

完了すると、作成したコンポーネントが **ツールボックス** に設定されていることがわかります。

## <a name="create-the-project"></a>プロジェクトを作成する

1. Visual Studio で、という名前の Windows ベースのアプリケーションプロジェクトを作成 `ToolboxExample` します ([**ファイル**] [  >  **新しい**  >  **プロジェクト**] [  >  **Visual C#** ] または [ **Visual Basic**  >  **クラシックデスクトップ**  >  **Windows フォームアプリケーション**])。

2. 新しいコンポーネントをプロジェクトに追加します。 このプロジェクトに `DemoComponent`という名前を付けます。

     詳細については、「 [方法: 新しいプロジェクト項目を追加する](/previous-versions/visualstudio/visual-studio-2010/w0572c5b(v=vs.100))」を参照してください。

3. プロジェクトをビルドします。

4. [ **ツール** ] メニューの [ **オプション** ] をクリックします。 **Windows フォームデザイナー** 項目の下にある [**全般**] をクリックし、 **AutoToolboxPopulate** オプションが **True** に設定されていることを確認します。

## <a name="create-an-instance-of-a-custom-component"></a>カスタムコンポーネントのインスタンスを作成する

次の手順では、フォームにカスタムコンポーネントのインスタンスを作成します。 **ツールボックス** は新しいコンポーネントのアカウントを自動的に作成するので、他のコンポーネントやコントロールを作成するのと同じように簡単です。

1. **フォームデザイナー** でプロジェクトのフォームを開きます。

2. **ツールボックス** で、[ **ToolboxExample Components**] という名前の新しいタブをクリックします。

     タブをクリックすると、 **Democomponent** が表示されます。

    > [!NOTE]
    > パフォーマンス上の理由から、 **ツールボックス** の自動設定された領域のコンポーネントにはカスタムビットマップが表示されず、 <xref:System.Drawing.ToolboxBitmapAttribute> はサポートされていません。 **ツール** ボックスにカスタムコンポーネントのアイコンを表示するには、 **[ツールボックスアイテムの選択**] ダイアログボックスを使用してコンポーネントを読み込みます。

3. コンポーネントをフォームにドラッグします。

     コンポーネントのインスタンスが作成され、 **コンポーネントトレイ** に追加されます。

## <a name="unload-and-reload-a-custom-component"></a>カスタムコンポーネントのアンロードと再読み込み

**ツールボックス** は、読み込まれた各プロジェクトのコンポーネントを考慮し、プロジェクトがアンロードされるときに、プロジェクトのコンポーネントへの参照を削除します。

1. ソリューションからプロジェクトをアンロードします。

     プロジェクトのアンロードの詳細については、「 [方法: プロジェクトのアンロードと再読み込み](/previous-versions/visualstudio/visual-studio-2010/tt479x1t(v=vs.100))」を参照してください。 保存を確認するメッセージが表示されたら、[ **はい]** を選択します。

2. 新しい **Windows アプリケーション** プロジェクトをソリューションに追加します。 **デザイナー** でフォームを開きます。

     前のプロジェクトの [ **ToolboxExample Components** ] タブが消えました。

3. プロジェクトを再度読み込み `ToolboxExample` ます。

     [ **ToolboxExample Components** ] タブが表示されるようになりました。

## <a name="next-steps"></a>次のステップ

このチュートリアルでは、 **ツールボックス** がプロジェクトのコンポーネントを考慮していることを示しますが、 **ツールボックス** もコントロールを考慮します。 ソリューションからコントロールプロジェクトを追加したり削除したりして、独自のカスタムコントロールを試してみてください。

## <a name="see-also"></a>関連項目

- [[全般] ([オプション] ダイアログ ボックス - [Windows フォーム デザイナー])](/previous-versions/visualstudio/visual-studio-2010/5aazxs78(v=vs.100))
- [方法: [ツールボックス] タブの操作](/previous-versions/visualstudio/visual-studio-2010/66kwe227(v=vs.100))
- [[ツールボックス アイテムの選択] ダイアログ ボックス (Visual Studio)](/previous-versions/visualstudio/visual-studio-2010/dyca0t6t(v=vs.100))
- [Windows フォームへのコントロールの追加](putting-controls-on-windows-forms.md)
