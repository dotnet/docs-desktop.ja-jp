---
title: ユーザー入力の検証
description: Windows フォームを使用してアプリケーションのユーザー入力を検証するいくつかの方法について説明します。
ms.date: 10/26/2020
ms.topic: overview
helpviewer_keywords:
- Windows Forms, validating user input
- validation [Windows Forms], Windows Forms user input
- user input [Windows Forms], validating in Windows Forms
- validating user input [Windows Forms], Windows Forms
ms.openlocfilehash: 16db8a1048c5f342f942f88a91a764d6b2a57f35
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/09/2020
ms.locfileid: "96942163"
---
# <a name="overview-of-how-to-validate-user-input-windows-forms-net"></a>ユーザー入力を検証する方法の概要 (Windows フォーム .NET)

ユーザーがアプリケーションにデータを入力するときに、アプリケーションで使用される前にデータが有効であるかどうかを検証することが必要な場合があります。 特定のテキスト フィールドの長さがゼロでないこと、フィールドが電話番号として書式設定されていること、または文字列に無効な文字が含まれていないことを要求する場合などです。 Windows フォームには、アプリケーションの入力を検証するための方法がいくつか用意されています。

[!INCLUDE [desktop guide under construction](../../includes/desktop-guide-preview-note.md)]

## <a name="maskedtextbox-control"></a>MaskedTextBox コントロール

電話番号や部品番号など、適切に定義された形式でデータを入力するようにユーザーに要求する必要がある場合は、<xref:System.Windows.Forms.MaskedTextBox> コントロールを使用して最小限のコードで、これをすばやく完了することができます。 "*マスク*" は、マスク言語の文字で構成される文字列であり、テキスト ボックスの任意の位置に入力できる文字を指定します。 このコントロールにより、一連のプロンプトがユーザーに表示されます。 ユーザーが不正なエントリを入力した場合、たとえば、数字が必要なときにユーザーが文字を入力した場合、このコントロールにより、入力が自動的に拒否されます。

<xref:System.Windows.Forms.MaskedTextBox> で使用されるマスク言語は柔軟性があります。 必須の文字、省略可能な文字、リテラル文字 (ハイフンやかっこなど)、通貨記号、日付の区切り記号を指定できます。 このコントロールは、データ ソースにバインドされている場合にも問題なく機能します。 データ バインディングの<xref:System.Windows.Forms.Binding.Format> イベントを使用して、マスクに準拠するように受信データを再フォーマットできます。また、<xref:System.Windows.Forms.Binding.Parse> イベントを使用して、データ フィールドの仕様に準拠するように送信データを再フォーマットできます。

<!-- TODO
For more information, see [MaskedTextBox Control](./controls/maskedtextbox-control-windows-forms.md).-->

## <a name="event-driven-validation"></a>イベント ドリブン検証

検証をプログラムで完全に制御する場合、または複雑な検証チェックが必要な場合、Windows フォームに組み込まれた検証イベントを使用する必要があります。 自由形式のユーザー入力を受け入れる各コントロールには、コントロールがデータ検証を必要とするたびに <xref:System.Windows.Forms.Control.Validating> イベントが含まれます。 <xref:System.Windows.Forms.Control.Validating> イベント処理メソッドでは、いくつかの方法でユーザー入力を検証できます。 たとえば、郵便番号が含まれている必要のあるテキスト ボックスがある場合、次の方法で検証を実行できます。

- 郵便番号が特定の郵便番号グループに属している必要がある場合、入力に対して文字列比較を実行し、ユーザーが入力したデータを検証することができます。 たとえば、郵便番号が `{10001, 10002, 10003}` のセットに含まれている必要がある場合、文字列比較を使用してデータを検証できます。

- 郵便番号が特定の形式である必要がある場合、正規表現を使用して、ユーザーが入力したデータを検証できます。 たとえば、フォーム `#####` または `#####-####` を検証するには、正規表現 `^(\d{5})(-\d{4})?$` を使用できます。 フォーム `A#A #A#` を検証するには、正規表現 `[A-Z]\d[A-Z] \d[A-Z]\d` を使用できます。 正規表現の詳細については、「[.NET 正規表現](/dotnet/standard/base-types/regular-expressions)」および[正規表現の例](/dotnet/standard/base-types/regular-expression-example-scanning-for-hrefs)に関する記事を参照してください。

- 郵便番号が有効な米国郵便番号である必要がある場合、郵便番号 Web サービスを呼び出して、ユーザーが入力したデータを検証できます。

<xref:System.Windows.Forms.Control.Validating> イベントには、型 <xref:System.ComponentModel.CancelEventArgs> のオブジェクトが提供されます。 コントロールのデータが有効ではないと判断した場合、このオブジェクトの <xref:System.ComponentModel.CancelEventArgs.Cancel%2A> プロパティを `true` に設定することによって、<xref:System.Windows.Forms.Control.Validating> イベントをキャンセルします。 <xref:System.ComponentModel.CancelEventArgs.Cancel%2A> プロパティを設定しない場合、Windows フォームによって、そのコントロールに対する検証が成功したと見なされ、<xref:System.Windows.Forms.Control.Validated> イベントが発生します。

<xref:System.Windows.Controls.TextBox> でメール アドレスを検証するコード例については、<xref:System.Windows.Forms.Control.Validating> イベントのリファレンスを参照してください。

### <a name="event-driven-validation-data-bound-controls"></a>イベントドリブン検証のデータ バインド コントロール

検証は、データベース テーブルなどのデータソースにコントロールをバインドした場合に役立ちます。 検証を使用すると、コントロールのデータがデータソースに必要な形式を満たしていること、および引用符やバックスラッシュなどの安全ではないおそれがある特殊文字が含まれていないことを確認できます。

データ バインディングを使用する場合、コントロール内のデータは、<xref:System.Windows.Forms.Control.Validating> イベントの実行時にデータ ソースと同期されます。 <xref:System.Windows.Forms.Control.Validating> イベントをキャンセルした場合、データはデータ ソースと同期されません。

> [!IMPORTANT]
> <xref:System.Windows.Forms.Control.Validating> イベントの後に実行されるカスタム検証がある場合、データ バインディングには影響しません。 たとえば、<xref:System.Windows.Forms.Control.Validated> イベントに、データ バインディングをキャンセルしようとするコードが含まれている場合でも、データ バインディングは発生します。 この場合、<xref:System.Windows.Forms.Control.Validated> イベントで検証を実行するには、コントロールの [`Binding.DataSourceUpdateMode`](xref:System.Windows.Forms.Binding.DataSourceUpdateMode) プロパティを <xref:System.Windows.Forms.DataSourceUpdateMode.OnValidation?displayProperty=nameWithType> から <xref:System.Windows.Forms.DataSourceUpdateMode.Never?displayProperty=nameWithType> に変更し、`your-control.DataBindings["field-name"].WriteValue()` を検証コードに追加します。

## <a name="implicit-and-explicit-validation"></a>暗黙的および明示的な検証

では、コントロールのデータが検証されるのはいつでしょうか? これは、開発者が決定します。 アプリケーションのニーズに応じて、暗黙的または明示的な検証を使用できます。

### <a name="implicit-validation"></a>暗黙的な検証

暗黙的な検証アプローチにより、ユーザーがデータを入力すると検証が実行されます。 キーが押されたときにキーを読み取ることによって、またはより一般的にはユーザーが入力フォーカスをコントロールから離すたびに、データが検証されます。 このアプローチは、作業中にデータに関するフィードバックをユーザーにすぐに提供したい場合に役立ちます。

コントロールに暗黙的な検証を使用する場合、そのコントロールの <xref:System.Windows.Forms.ContainerControl.AutoValidate%2A> プロパティを <xref:System.Windows.Forms.AutoValidate.EnablePreventFocusChange> または <xref:System.Windows.Forms.AutoValidate.EnableAllowFocusChange> に設定する必要があります。 <xref:System.Windows.Forms.Control.Validating> イベントをキャンセルした場合、コントロールの動作は、<xref:System.Windows.Forms.ContainerControl.AutoValidate%2A> に割り当てた値によって決まります。 <xref:System.Windows.Forms.AutoValidate.EnablePreventFocusChange>を割り当てた場合、イベントをキャンセルすると、<xref:System.Windows.Forms.Control.Validated> イベントは発生しません。 ユーザーがデータを有効な形式に変更するまで、入力フォーカスは引き続き現在のコントロール上にあります。 <xref:System.Windows.Forms.AutoValidate.EnableAllowFocusChange> を割り当てた場合、<xref:System.Windows.Forms.Control.Validated> イベントをキャンセルすると、このイベントは発生しませんが、フォーカスは次のコントロールに移ります。

<xref:System.Windows.Forms.AutoValidate.Disable> を <xref:System.Windows.Forms.ContainerControl.AutoValidate%2A> プロパティに割り当てると、暗黙的な検証も行われなくなります。 コントロールを検証するには、明示的な検証を使用する必要があります。

### <a name="explicit-validation"></a>明示的な検証

明示的な検証アプローチでは、データが一度に検証されます。 **[保存]** ボタンや **[次へ]** リンクのクリックなど、ユーザー操作に応答してデータを検証できます。 ユーザー操作が発生すると、次のいずれかの方法で明示的な検証をトリガーできます。

- <xref:System.Windows.Forms.ContainerControl.Validate%2A> を呼び出して、最後にフォーカスを失ったコントロールを検証する。
- <xref:System.Windows.Forms.ContainerControl.ValidateChildren%2A> を呼び出して、フォームまたはコンテナー コントロール内のすべての子コントロールを検証する。
- カスタム メソッドを呼び出して、コントロール内のデータを手動で検証する。

### <a name="default-implicit-validation-behavior-for-controls"></a>コントロールの暗黙的な検証の既定の動作

Windows フォームのコントロールが異なれば、その <xref:System.Windows.Forms.ContainerControl.AutoValidate%2A> プロパティの既定値も異なります。 次の表は、最も一般的なコントロールとその既定値を示しています。

| コントロール                                        | 既定の検証動作                                     |
|------------------------------------------------|-----------------------------------------------------------------|
| <xref:System.Windows.Forms.ContainerControl>   | <xref:System.Windows.Forms.AutoValidate.Inherit>                |
| <xref:System.Windows.Forms.Form>               | <xref:System.Windows.Forms.AutoValidate.EnableAllowFocusChange> |
| <xref:System.Windows.Forms.PropertyGrid>       | プロパティは Visual Studio で公開されない                           |
| <xref:System.Windows.Forms.ToolStripContainer> | プロパティは Visual Studio で公開されない                           |
| <xref:System.Windows.Forms.SplitContainer>     | <xref:System.Windows.Forms.AutoValidate.Inherit>                |
| <xref:System.Windows.Forms.UserControl>        | <xref:System.Windows.Forms.AutoValidate.EnableAllowFocusChange> |

## <a name="closing-the-form-and-overriding-validation"></a>フォームを閉じて検証をオーバーライドする

含まれるデータが無効であるためにコントロールがフォーカスを維持している場合、次の通常の方法のいずれかでも親フォームを閉じることはできません。

- **[閉じる]** ボタンをクリックする。
- **[システム]**  >  **[閉じる]** メニューを選択する。
- プログラムで <xref:System.Windows.Forms.Form.Close%2A> メソッドを呼び出す。

しかし、場合によっては、コントロールの値が有効かどうかに関係なく、ユーザーにフォームを閉じさせることが必要なことがあります。 フォームの <xref:System.Windows.Forms.Form.FormClosing> イベントのハンドラーを作成することにより、検証をオーバーライドして、無効なデータが含まれたままのフォームを閉じることができます。 この場合、<xref:System.ComponentModel.CancelEventArgs.Cancel%2A> プロパティを `false` に設定します。 これにより、フォームが強制的に閉じられます。 使用例を含む詳細については、「<xref:System.Windows.Forms.Form.FormClosing?displayProperty=nameWithType>」を参照してください。

> [!NOTE]
> この方法でフォームを強制的に閉じる場合、フォームのコントロール内にある、まだ保存されていないデータはすべて失われます。 さらに、モーダル フォームでは、コントロールが閉じられたときにその内容は検証されません。 その場合もコントロールの検証を使用してフォーカスをコントロールにロックすることはできますが、フォームを閉じることに伴う動作について心配する必要はありません。

## <a name="see-also"></a>関連項目

- [キーボード イベントの使用 (Windows フォーム .NET)](events.md)
- <xref:System.Windows.Forms.Control.Validating?displayProperty=nameWithType>
- <xref:System.Windows.Forms.Form.FormClosing?displayProperty=nameWithType>
- <xref:System.Windows.Forms.FormClosingEventArgs?displayProperty=nameWithType>
