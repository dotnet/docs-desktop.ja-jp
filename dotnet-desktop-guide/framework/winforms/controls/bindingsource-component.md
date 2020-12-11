---
title: BindingSource コンポーネント
ms.date: 03/30/2017
helpviewer_keywords:
- data binding [Windows Forms], Windows Forms
- Windows Forms, data binding control
- BindingSource component [Windows Forms]
ms.assetid: 3e2faf4c-f5b8-4fa6-9fbc-f59c37ec2fb9
ms.openlocfilehash: 54639edb512a8bc6c5909282d5e4c210439e2a6e
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/09/2020
ms.locfileid: "96975114"
---
# <a name="bindingsource-component"></a>BindingSource コンポーネント
コントロールにバインドするためにデータ ソースをカプセル化します。  
  
 <xref:System.Windows.Forms.BindingSource> コンポーネントは 2 つの目的で利用できます。 1 つ目は、フォームのコントロールをデータにバインドするときに、間接レイヤーの役割を果たします。 <xref:System.Windows.Forms.BindingSource> コンポーネントをデータ ソースにバインドして、フォームのコントロールを <xref:System.Windows.Forms.BindingSource> コンポーネントにバインドすることで、これを実行できます。 データとのそれ以上の対話 (移動、並べ替え、フィルタ処理、更新など) はすべて、<xref:System.Windows.Forms.BindingSource> コンポーネントを呼び出すことによって実行します。  
  
 2 つ目は、<xref:System.Windows.Forms.BindingSource> コンポーネントが、厳密に型指定されたデータ ソースとして機能することができます。 <xref:System.Windows.Forms.BindingSource.Add%2A> メソッドを持つ <xref:System.Windows.Forms.BindingSource> コンポーネントに型を追加すると、その型の一覧が作成されます。  
  
## <a name="in-this-section"></a>このセクションの内容  
 [BindingSource コンポーネントの概要](bindingsource-component-overview.md)  
 <xref:System.Windows.Forms.BindingSource> コンポーネントの一般的な概念を導入し、データ ソースをコントロールにバインドすることができます。  
  
 [方法: Windows フォーム コントロールを DBNull データベース値にバインドする](how-to-bind-windows-forms-controls-to-dbnull-database-values.md)  
 <xref:System.Windows.Forms.BindingSource> コンポーネントを使用して、<xref:System.DBNull> の値をデータ ソースから処理する方法を示しています。  
  
 [方法: Windows フォーム BindingSource コンポーネントで ADO.NET データを並べ替える/フィルター処理する](sort-and-filter-ado-net-data-with-wf-bindingsource-component.md)  
 <xref:System.Windows.Forms.BindingSource> コンポーネントを使用して、表示されるデータに並べ替えとフィルター処理を適用する方法を示します。  
  
 [方法: Windows フォーム BindingSource を使用して Web サービスにバインドする](how-to-bind-to-a-web-service-using-the-windows-forms-bindingsource.md)  
 <xref:System.Windows.Forms.BindingSource> コンポーネントを使用して、Web サービスにバインドする方法を示します。  
  
 [方法: データ バインドで発生するエラーと例外を処理する](how-to-handle-errors-and-exceptions-that-occur-with-databinding.md)  
 <xref:System.Windows.Forms.BindingSource> コンポーネントを使用して、データ バインド操作で発生するエラーを適切に処理する方法を示します。  
  
 [方法: Windows フォーム コントロールを型にバインドする](how-to-bind-a-windows-forms-control-to-a-type.md)  
 <xref:System.Windows.Forms.BindingSource> コンポーネントを使用して、型にバインドする方法を示します。  
  
 [方法: Windows フォーム コントロールをファクトリ オブジェクトにバインドする](how-to-bind-a-windows-forms-control-to-a-factory-object.md)  
 <xref:System.Windows.Forms.BindingSource> コンポーネントを使用して、ファクトリ オブジェクトやメソッドにバインドする方法を示します。  
  
 [方法: Windows フォーム BindingSource を使用して項目の追加をカスタマイズする](how-to-customize-item-addition-with-the-windows-forms-bindingsource.md)  
 <xref:System.Windows.Forms.BindingSource> コンポーネントを使用して、新しい項目を作成し、データ ソースに追加する方法を示します。  
  
 [方法: BindingSource ResetItem メソッドを使用して変更通知を発生させる](how-to-raise-change-notifications-using-the-bindingsource-resetitem-method.md)  
 <xref:System.Windows.Forms.BindingSource> コンポーネントを使用して、変更通知をサポートしないデータ ソースに対して変更通知イベントを発生させる方法を示します。  
  
 [方法: BindingSource と INotifyPropertyChanged の各インターフェイスを使用して変更通知を発生させる](raise-change-notifications--bindingsource.md)  
 <xref:System.Windows.Forms.BindingSource> コントロールを使用して <xref:System.ComponentModel.INotifyPropertyChanged> から継承する型を使用する方法を示します。  
  
 [方法: BindingSource を使用して Windows フォーム コントロール内にデータ ソースの更新を反映させる](reflect-data-source-updates-in-a-wf-control-with-the-bindingsource.md)  
 <xref:System.Windows.Forms.BindingSource> コンポーネントを使用して、データ ソースの変更に応答する方法を示します。  
  
 [方法: BindingSource コンポーネントを使用してフォーム間でバインド データを共有する](how-to-share-bound-data-across-forms-using-the-bindingsource-component.md)  
 <xref:System.Windows.Forms.BindingSource> を使用して、同じデータ ソースに複数のフォームをバインドする方法を示します。  
  
## <a name="reference"></a>リファレンス  
 <xref:System.Windows.Forms.BindingSource>  
 <xref:System.Windows.Forms.BindingSource> コンポーネントのリファレンス ドキュメントを提供します。  
  
 <xref:System.Windows.Forms.BindingNavigator>  
 <xref:System.Windows.Forms.BindingNavigator> コントロールのリファレンス ドキュメントを提供します。  
  
## <a name="related-sections"></a>関連項目  
 [Windows フォームでのデータ バインディング](../windows-forms-data-binding.md)  
 Windows フォームのデータ バインディング アーキテクチャについて説明するトピックへのリンクが含まれます。  
  
 「[Visual Studio でのデータへのコントロールのバインド](/visualstudio/data-tools/bind-controls-to-data-in-visual-studio)」も参照してください。
