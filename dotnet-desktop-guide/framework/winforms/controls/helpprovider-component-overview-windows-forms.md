---
title: HelpProvider コンポーネントの概要
ms.date: 03/30/2017
f1_keywords:
- HelpProvider
helpviewer_keywords:
- HelpProvider component [Windows Forms], about HelpProvider component
- Help [Windows Forms], adding to Windows applications
- F1 Help [Windows Forms], adding to Windows Forms
- dialog boxes [Windows Forms], context-sensitive Help
- Windows Forms, context-sensitive Help
ms.assetid: 6b10c2cc-c577-4cb5-9669-e37b33416af9
ms.openlocfilehash: 74d35dfa39a605cb1e1e85cc3aeda834e1c60669
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/09/2020
ms.locfileid: "96981484"
---
# <a name="helpprovider-component-overview-windows-forms"></a>HelpProvider コンポーネントの概要 (Windows フォーム)
Windows フォーム [HelpProvider](helpprovider-component-windows-forms.md) コンポーネントは、Windows アプリケーションと共に html ヘルプ1.x ヘルプファイル (Html ヘルプワークショップで生成された .chm ファイル、または .htm ファイル) を関連付けるために使用されます。 ヘルプは、次のさまざまな方法で提供できます。  
  
- Windows フォームのコントロールについて、状況依存のヘルプを提供します。  
  
- ダイアログボックスの特定のダイアログボックスまたは特定のコントロールについて、状況依存のヘルプを提供します。  
  
- 目次のメインページ、インデックス、検索機能など、特定の領域に対してヘルプファイルを開きます。  
  
## <a name="using-the-help-provider"></a>ヘルププロバイダーの使用  
 Windows フォームにコンポーネントを追加すると、 <xref:System.Windows.Forms.HelpProvider> フォーム上の他のコントロールがコンポーネントのヘルププロパティを公開できるように <xref:System.Windows.Forms.HelpProvider> なります。 これにより、Windows フォーム上のコントロールにヘルプを提供できます。 プロパティを使用して、ヘルプファイルをコンポーネントに関連付けることができ <xref:System.Windows.Forms.HelpProvider> <xref:System.Windows.Forms.HelpProvider.HelpNamespace%2A> ます。 を呼び出し、 <xref:System.Windows.Forms.HelpProvider.SetHelpNavigator%2A> <xref:System.Windows.Forms.HelpNavigator> 指定したコントロールの列挙体の値を指定して、提供されるヘルプの種類を指定します。 ヘルプのキーワードまたはトピックは、メソッドを呼び出すことによって指定し <xref:System.Windows.Forms.HelpProvider.SetHelpKeyword%2A> ます。  
  
 必要に応じて、特定のヘルプ文字列を別のコントロールに関連付けるには、メソッドを使用し <xref:System.Windows.Forms.HelpProvider.SetHelpString%2A> ます。 コントロールにフォーカスがあるときにユーザーが F1 キーを押すと、このメソッドを使用してコントロールに関連付ける文字列がポップアップウィンドウに表示されます。  
  
 <xref:System.Windows.Forms.HelpProvider.HelpNamespace%2A>が設定されていない場合は、を使用してヘルプテキストを指定する必要があり <xref:System.Windows.Forms.HelpProvider.SetHelpString%2A> ます。 との両方のヘルプ文字列を設定している場合は <xref:System.Windows.Forms.HelpProvider.HelpNamespace%2A> 、に基づくヘルプ <xref:System.Windows.Forms.HelpProvider.HelpNamespace%2A> が優先されます。  
  
> [!NOTE]
> <xref:System.Windows.Forms.Help.ShowHelp%2A>コントロールのメソッドまたはプロパティでヘルプファイルへのパスを指定するときに、相対パスを使用すると問題が発生することがあり <xref:System.Windows.Forms.HelpProvider.HelpNamespace%2A> <xref:System.Windows.Forms.HelpProvider> ます。 そのため、絶対ファイルパスを使用してヘルプファイルを指定してください。  
  
## <a name="see-also"></a>関連項目

- [Windows フォーム アプリケーションのヘルプ システム](../advanced/help-systems-in-windows-forms-applications.md)
