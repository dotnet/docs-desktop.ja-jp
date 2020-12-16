---
title: イベントの概要
description: .NET Windows フォームのイベントの簡単な概要です。
ms.date: 10/26/2020
ms.topic: overview
helpviewer_keywords:
- Windows Forms, event handling
- events [Windows Forms], about events
- delegates [Windows Forms], multicast
- delegates [Windows Forms], events and
- multicast event delegates
- Windows Forms controls, events
ms.openlocfilehash: aed33b7b856da210855a5b06ccf53610a6551b47
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/09/2020
ms.locfileid: "96942331"
---
# <a name="events-overview-windows-forms-net"></a>イベントの概要 (Windows フォーム .NET)

イベントとは、コード内の応答可能な、つまり "処理" 可能なアクションです。 イベントは、マウスのクリックやキーの押下などのユーザー アクション、プログラム コードまたはシステムで生成できます。

[!INCLUDE [desktop guide under construction](../../includes/desktop-guide-preview-note.md)]

イベント ドリブン アプリケーションでは、イベントに応答してコードが実行されます。 各フォームおよびコントロールは、定義済みのイベント セットを公開しており、プログラマはそれらに対応するプログラムを作成できます。 これらのイベントの 1 つが発生したときに、関連するイベント ハンドラーにコードがある場合は、そのコードが呼び出されます。

オブジェクトが発生させるイベントにはさまざまな種類がありますが、その多くがほとんどのコントロールで共通です。 たとえば、<xref:System.Windows.Forms.Control.Click> イベントは、ほとんどのオブジェクトで処理されます。 ユーザーがフォームをクリックすると、フォームの <xref:System.Windows.Forms.Control.Click> イベント ハンドラー内のコードが実行されます。

> [!NOTE]
> イベントの多くは、他のイベントと共に発生します。 たとえば、<xref:System.Windows.Forms.Control.DoubleClick> イベントが発生する場合は、<xref:System.Windows.Forms.Control.MouseDown>、<xref:System.Windows.Forms.Control.MouseUp>、および <xref:System.Windows.Forms.Control.Click> の各イベントが発生します。

イベントを発生させて処理する方法については、「[イベントの処理と発生](/dotnet/standard/events/index)」を参照してください。

## <a name="delegates-and-their-role"></a>デリゲートとその役割

デリゲートは、イベントを処理する仕組みを構築するために .NET 内で一般に使用されるクラスです。 デリゲートは、Visual C++ やその他のオブジェクト指向言語で一般的に使用されている関数ポインターに大体似ています。 ただし、関数ポインターとは異なり、デリゲートはオブジェクト指向で、タイプ セーフで、安全です。 また、関数ポインターには特定の関数への参照のみを含みますが、デリゲートはオブジェクトへの参照、およびそのオブジェクト内の 1 つ以上のメソッドへの参照で構成されています。

このイベント モデルでは、*デリゲート* を使用してそれらの処理に使用するメソッドにイベントを関連付けています。 デリゲートを使用すると、ハンドラーのメソッドを指定することにより、イベント通知のための他のクラスを登録できます。 イベントが発生すると、デリゲートは関連付けられたメソッドを呼び出します。 デリゲートを定義する方法の詳細については、「[イベントの処理と発生](/dotnet/standard/events/index)」を参照してください。

デリゲートは、単一のメソッドまたは複数のメソッドに関連付けることができます。後者は、マルチキャストと呼ばれます。 イベントに対しデリゲートを作成する場合、通常はマルチキャスト イベントを作成します。 まれな例外は、イベントごとに論理的に複数回繰り返されることがない (ダイアログ ボックスを表示するなどの) 特定のプロシージャを実行するイベントです。 マルチキャスト デリゲートを作成する方法については、「[デリゲートを結合する方法 (マルチキャスト デリゲート)](/dotnet/csharp/programming-guide/delegates/how-to-combine-delegates-multicast-delegates)」を参照してください。

マルチキャスト デリゲートは、それが関連付けられているメソッドの呼び出しリストを保持しています。 マルチキャスト デリゲートでは、呼び出しリストにメソッドを追加する <xref:System.Delegate.Combine%2A> メソッド、およびリストからメソッドを削除する <xref:System.Delegate.Remove%2A> メソッドがサポートされています。

アプリケーションによってイベントが記録されると、コントロールは、そのイベント用のデリゲートを呼び出すことによってイベントを発生させます。 次に、デリゲートによって、関連付けられたメソッドが呼び出されます。 最も一般的なケース (マルチキャスト デリゲート) では、デリゲートが呼び出しリストにある関連付けられている各メソッドを順番に呼び出し、一対多の通知を行います。 この戦略では、すべての登録と通知はデリゲートが処理するため、コントロールでは、イベント通知の対象となるオブジェクトのリストを保持する必要がありません。

デリゲートでは、複数のイベントを同じメソッドに関連付けし、多対一通知を実行することもできます。 たとえば、ボタンとメニューコマンドのクリック イベントで、同じデリゲートを呼び出すことができます。呼び出されたデリゲートによって単一のメソッドが呼び出されるので、どちらのイベントも同じように処理されます。

デリゲートで使用される関連付けの仕組みは動的です。デリゲートは、イベント ハンドラーのシグネチャと一致するすべてのメソッドに実行時に関連付けできます。 この機能によって、状況に応じて関連付けるメソッドを設定または変更したり、イベント ハンドラをコントロールに動的に関連付けることができます。

## <a name="see-also"></a>関連項目

- [イベントの処理と発生](/dotnet/standard/events/index)

<!-- TODO
- [Creating Event Handlers in Windows Forms](creating-event-handlers-in-windows-forms.md)
- [Event Handlers Overview](event-handlers-overview-windows-forms.md)-->
