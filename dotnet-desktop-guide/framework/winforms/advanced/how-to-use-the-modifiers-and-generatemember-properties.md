---
title: '方法: Modifiers プロパティおよび GenerateMember プロパティを使用する'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
f1_keywords:
- Designer_GenerateMember
- Designer_Modifiers
helpviewer_keywords:
- base forms
- inheritance [Windows Forms], forms
- inherited forms [Windows Forms], Windows Forms
- inherited forms
- form inheritance
- Windows Forms, inheritance
ms.assetid: 3381a5e4-e1a3-44e2-a765-a0b758937b85
ms.openlocfilehash: 3fbaaae53aa60f6356c3a8daa0513de86ef2dacb
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/09/2020
ms.locfileid: "96981224"
---
# <a name="how-to-use-the-modifiers-and-generatemember-properties"></a>方法: Modifiers プロパティおよび GenerateMember プロパティを使用する

コンポーネントを Windows フォームに配置すると、デザイン環境によって、との2つのプロパティが提供されます。 `GenerateMember` `Modifiers` `GenerateMember`プロパティは、Windows フォームデザイナーがコンポーネントのメンバー変数を生成するタイミングを指定します。 プロパティは、 `Modifiers` そのメンバー変数に割り当てられたアクセス修飾子です。 プロパティの値がの場合、 `GenerateMember` `false` プロパティの値は `Modifiers` 無効です。

## <a name="specify-whether-a-component-is-a-member-of-the-form"></a>コンポーネントがフォームのメンバーであるかどうかを指定する

1. Visual Studio の Windows フォームデザイナーで、フォームを開きます。

2. **ツールボックス** を開き、フォームで3つのコントロールを配置し <xref:System.Windows.Forms.Button> ます。

3. 次の `GenerateMember` `Modifiers` 表に従って、各コントロールのプロパティとプロパティを設定し <xref:System.Windows.Forms.Button> ます。

    |ボタン名|GenerateMember 値|修飾子の値|
    |-----------------|--------------------------|---------------------|
    |`button1`|`true`|`private`|
    |`button2`|`true`|`protected`|
    |`button3`|`false`|変更なし|

4. ソリューションをビルドします。

5. **ソリューション エクスプローラー** で、 **[すべてのファイルを表示]** ボタンをクリックします。

6. **Form1** ノードを開き、**コードエディター** で、 **form1.vb** または **Form1.Designer.cs** ファイルを開きます。 このファイルには、Windows フォームデザイナーによって出力されるコードが含まれています。

7. 3つのボタンの宣言を見つけます。 次のコード例は、プロパティとプロパティによって指定された違いを示して `GenerateMember` `Modifiers` います。

     [!code-csharp[System.Windows.Forms.GenerateMember#3](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.GenerateMember/CS/Form1.cs#3)]
     [!code-vb[System.Windows.Forms.GenerateMember#3](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.GenerateMember/VB/Form1.vb#3)]

     [!code-csharp[System.Windows.Forms.GenerateMember#2](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.GenerateMember/CS/Form1.cs#2)]
     [!code-vb[System.Windows.Forms.GenerateMember#2](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.GenerateMember/VB/Form1.vb#2)]

> [!NOTE]
> 既定では、Windows フォームデザイナーは、 `private` の `Friend` ようなコンテナーコントロールに (Visual Basic) 修飾子を割り当て <xref:System.Windows.Forms.Panel> ます。 ベース <xref:System.Windows.Forms.UserControl> または <xref:System.Windows.Forms.Form> コンテナーコントロールがある場合は、継承されたコントロールおよびフォームで新しい子を受け取ることはできません。 この問題を解決するには、基本コンテナーコントロールの修飾子をまたはに変更し `protected` `public` ます。

## <a name="see-also"></a>関連項目

- <xref:System.Windows.Forms.Button>
- [Windows フォームのビジュアルの継承](windows-forms-visual-inheritance.md)
- [チュートリアル: ビジュアル継承のデモンストレーション](walkthrough-demonstrating-visual-inheritance.md)
- [方法: Windows フォームを継承する](how-to-inherit-windows-forms.md)
