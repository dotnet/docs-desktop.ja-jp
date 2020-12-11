---
title: '方法: ShowDialog メソッドで Windows フォームを表示して COM 相互運用機能をサポートする'
ms.date: 03/30/2017
helpviewer_keywords:
- COM [Windows Forms]
- Windows Forms, unmanaged
- COM interop [Windows Forms], calling methods
- ActiveX controls [Windows Forms], COM interop
- Windows Forms, interop
ms.assetid: 87aac8ad-3c04-43b3-9b0c-d0b00df9ee74
ms.openlocfilehash: a4b86616fab5603e08fe9efa1213edaa633deeb9
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/09/2020
ms.locfileid: "96974448"
---
# <a name="how-to-support-com-interop-by-displaying-a-windows-form-with-the-showdialog-method"></a>方法: ShowDialog メソッドで Windows フォームを表示して COM 相互運用機能をサポートする

メソッドを使用して作成された .NET Framework メッセージループで Windows フォームを表示することで、コンポーネントオブジェクトモデル (COM) の相互運用性の問題を解決できます <xref:System.Windows.Forms.Application.Run%2A?displayProperty=nameWithType> 。  
  
 フォームが COM クライアント アプリケーションから正しく動作するには、Windows フォームのメッセージ ループ上で実行する必要があります。 そのためには、次の方法のいずれかを使用します。  
  
- <xref:System.Windows.Forms.Form.ShowDialog%2A?displayProperty=nameWithType> メソッドを使用して、Windows フォームを表示します。  
  
- 各 Windows フォームを別のスレッドで表示します。 詳細については、「[方法 : 独自のスレッドで各 Windows フォームを表示して COM 相互運用機能をサポートする](how-to-support-com-interop-by-displaying-each-windows-form-on-its-own-thread.md)」を参照してください。  
  
## <a name="procedure"></a>手順  

 メソッドを使用すると、 <xref:System.Windows.Forms.Form.ShowDialog%2A?displayProperty=nameWithType> .NET Framework メッセージループでフォームを表示する最も簡単な方法になります。これは、すべての方法で、実装するコードを最小限にする必要があるためです。  
  
 <xref:System.Windows.Forms.Form.ShowDialog%2A?displayProperty=nameWithType> メソッドは、管理されていないアプリケーションのメッセージ ループを一時停止し、フォームをダイアログ ボックスとして表示します。 ホストアプリケーションのメッセージループが中断されているため、メソッドは、 <xref:System.Windows.Forms.Form.ShowDialog%2A?displayProperty=nameWithType> フォームのメッセージを処理するための新しい .NET Framework メッセージループを作成します。  
  
 <xref:System.Windows.Forms.Form.ShowDialog%2A?displayProperty=nameWithType> メソッドを使用する場合の欠点は、フォームがモーダル ダイアログ ボックスとして開かれることです。 この動作により、Windows フォームが開かれている間は呼び出し元のアプリケーションですべてのユーザー インターフェイス (UI) がブロックされます。 ユーザーがフォームを終了すると、.NET Framework メッセージループが閉じ、以前のアプリケーションのメッセージループの実行が再び開始されます。  
  
 フォームを表示するためのメソッドが含まれるクラス ライブラリを Windows フォームで作成し、その後で COM 相互運用機能のクラス ライブラリをビルドすることができます。 Visual Basic 6.0 または Microsoft Foundation Classes (MFC) からこの DLL ファイルを使用し、これらのいずれかの環境から <xref:System.Windows.Forms.Form.ShowDialog%2A?displayProperty=nameWithType> メソッドを呼び出してフォームを表示することができます。  
  
#### <a name="to-support-com-interop-by-displaying-a-windows-form-with-the-showdialog-method"></a>ShowDialog メソッドで Windows フォームを表示して COM 相互運用機能をサポートする方法  
  
- メソッドのすべての呼び出しを、 <xref:System.Windows.Forms.Form.Show%2A?displayProperty=nameWithType> <xref:System.Windows.Forms.Form.ShowDialog%2A?displayProperty=nameWithType> .NET Framework コンポーネントのメソッドの呼び出しに置き換えます。  
  
## <a name="see-also"></a>関連項目

- [COM への .NET Framework コンポーネントの公開](/dotnet/framework/interop/exposing-dotnet-components-to-co)
- [方法: 独自のスレッドで各 Windows フォームを表示して COM 相互運用機能をサポートする](how-to-support-com-interop-by-displaying-each-windows-form-on-its-own-thread.md)
- [Windows Forms and Unmanaged Applications](windows-forms-and-unmanaged-applications.md)
