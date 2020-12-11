---
title: '方法: 2 つのコントロールのプロパティをバインドする'
ms.date: 03/30/2017
helpviewer_keywords:
- data binding [WPF], binding properties of two controls
- binding properties of two controls [WPF]
- controls [WPF], binding properties of
ms.assetid: 06318fac-6afd-4c7d-a277-6d7ef50f47bc
ms.openlocfilehash: 28b5f65a57fc210f3d405020daa0d75c28b934c8
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/09/2020
ms.locfileid: "96974496"
---
# <a name="how-to-bind-the-properties-of-two-controls"></a>方法: 2 つのコントロールのプロパティをバインドする

この例では、<xref:System.Windows.Data.Binding.ElementName%2A> プロパティを使用して、インスタンス化された 1 つのコントロールのプロパティを別のコントロールのプロパティにバインドする方法を示します。

## <a name="example"></a>例

次の例では、<xref:System.Windows.Controls.Canvas> の <xref:System.Windows.Controls.Panel.Background%2A> プロパティを <xref:System.Windows.Controls.ComboBox> の [SelectedItem.Content](xref:System.Windows.Controls.ContentControl.Content%2A) プロパティにバインドする方法を示します。

[!code-xaml[BindDptoDp#1](~/samples/snippets/csharp/VS_Snippets_Wpf/BindDPtoDP/CS/Window1.xaml#1)]

この例をレンダリングすると、次のようになります。

![値 Green が選択され、緑色の四角形が表示されているコンボ ボックスのスクリーンショット。](./media/how-to-bind-the-properties-of-two-controls/data-binding-bind-background-canvas.png)

> [!NOTE]
> バインディング ターゲット プロパティ (この例では <xref:System.Windows.Controls.Panel.Background%2A> プロパティ) は、依存関係プロパティである必要があります。 詳しくは、「[データ バインディングの概要](/dotnet/desktop-wpf/data/data-binding-overview)」をご覧ください。

## <a name="see-also"></a>関連項目

- [バインディング ソースを指定する](how-to-specify-the-binding-source.md)
- [方法トピック](data-binding-how-to-topics.md)
