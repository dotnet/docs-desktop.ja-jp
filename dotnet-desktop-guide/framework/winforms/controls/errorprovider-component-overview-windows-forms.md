---
title: ErrorProvider コンポーネントの概要
ms.date: 03/30/2017
f1_keywords:
- ErrorProvider
helpviewer_keywords:
- errors [Windows Forms], displaying to users
- error messages [Windows Forms], displaying
- ErrorProvider component [Windows Forms], about ErrorProvider component
ms.assetid: ced189f2-b5c8-46a7-a6f1-37f5af95dc99
ms.openlocfilehash: b66e97d97d0d8c2ea4e9bdba29f8ff35e486e1f6
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/09/2020
ms.locfileid: "96981068"
---
# <a name="errorprovider-component-overview-windows-forms"></a>ErrorProvider コンポーネントの概要 (Windows フォーム)
Windows フォーム [ErrorProvider](errorprovider-component-windows-forms.md) コンポーネントは、フォームまたはコントロールのユーザー入力を検証するために使用されます。 通常は、フォームでのユーザー入力の検証、またはデータセット内のエラーの表示と組み合わせて使用されます。 エラープロバイダーは、メッセージボックスにエラーメッセージを表示するよりも適しています。これは、メッセージボックスが閉じられると、エラーメッセージが表示されなくなるためです。 コンポーネントは、 <xref:System.Windows.Forms.ErrorProvider> ![ テキストボックスなど、関連するコントロールの横にエラーアイコン (赤い丸の内側に白い感嘆符) を表示します。 ](./media/errorprovider-component-overview-windows-forms/vb-error-provider-icon.gif) ユーザーがマウスポインターをエラーアイコンの上に置くと、エラーメッセージ文字列を示すツールヒントが表示されます。  
  
## <a name="key-properties"></a>キー プロパティ  
 <xref:System.Windows.Forms.ErrorProvider>コンポーネントのキープロパティは、、、 <xref:System.Windows.Forms.ErrorProvider.DataSource%2A> <xref:System.Windows.Forms.ErrorProvider.ContainerControl%2A> および <xref:System.Windows.Forms.ErrorProvider.Icon%2A> です。 データバインドコントロールでコンポーネントを使用する場合は、 <xref:System.Windows.Forms.ErrorProvider> <xref:System.Windows.Forms.ErrorProvider.ContainerControl%2A> コンポーネントがフォームにエラーアイコンを表示するために、プロパティを適切なコンテナー (通常は Windows フォーム) に設定する必要があります。 コンポーネントがデザイナーに追加されると、 <xref:System.Windows.Forms.ErrorProvider.ContainerControl%2A> プロパティは、それを含んでいるフォームに設定されます。コントロールをコードに追加する場合は、自分で設定する必要があります。  
  
 プロパティは、 <xref:System.Windows.Forms.ErrorProvider.Icon%2A> 既定のの代わりにカスタムエラーアイコンに設定できます。 プロパティが設定されている場合、 <xref:System.Windows.Forms.ErrorProvider.DataSource%2A> <xref:System.Windows.Forms.ErrorProvider> コンポーネントはデータセットのエラーメッセージを表示できます。 コンポーネントの主要なメソッド <xref:System.Windows.Forms.ErrorProvider> は、 <xref:System.Windows.Forms.ErrorProvider.SetError%2A> エラーメッセージ文字列を指定し、エラーアイコンが表示されるメソッドです。  
  
> [!NOTE]
> <xref:System.Windows.Forms.ErrorProvider>コンポーネントには、ユーザー補助クライアントの組み込みサポートが用意されていません。 このコンポーネントを使用してアプリケーションにアクセスできるようにするには、追加のアクセス可能なフィードバックメカニズムを提供する必要があります。  
  
## <a name="see-also"></a>関連項目

- <xref:System.Windows.Forms.ErrorProvider>
- [方法: Windows フォーム ErrorProvider コンポーネントで DataSet 内にエラーを表示する](view-errors-within-a-dataset-with-wf-errorprovider-component.md)
- [方法: Windows フォーム ErrorProvider コンポーネントを使用してフォーム妥当性検査でエラー アイコンを表示する](display-error-icons-for-form-validation-with-wf-errorprovider.md)
