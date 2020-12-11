---
title: データバインドの変更通知
ms.date: 03/30/2017
helpviewer_keywords:
- Windows Forms, data binding
- Windows Forms, adding change notification for data binding
ms.assetid: b5b10f90-0585-41d9-a377-409835262a92
ms.openlocfilehash: 2dffea46bf0db54d28ef55e507767d88bd29ebc2
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/09/2020
ms.locfileid: "96981132"
---
# <a name="change-notification-in-windows-forms-data-binding"></a>Windows フォーム データ バインディングの変更通知
Windows フォームデータバインディングの最も重要な概念の1つは、 *変更通知* です。 データソースとバインドされたコントロールに常に最新のデータが保持されるようにするには、データバインディングの変更通知を追加する必要があります。 具体的には、データソースに対して行われた変更をバインドされたコントロールに通知し、コントロールのバインドされたプロパティに加えられた変更がデータソースに通知されるようにします。  
  
 変更通知には、データバインディングの種類に応じて、さまざまな種類があります。  
  
- 単純なバインド。単一のコントロールプロパティがオブジェクトの1つのインスタンスにバインドされます。  
  
- リストベースのバインディング。リスト内の項目のプロパティにバインドされた単一のコントロールプロパティや、オブジェクトのリストにバインドされたコントロールプロパティを含むことができます。  
  
 また、データバインディングに使用する Windows フォームコントロールを作成する場合は、コントロールのバインドされたプロパティに対する変更がデータソースに反映されるように、 *PropertyName* Changed パターンをコントロールに適用する必要があります。  
  
## <a name="change-notification-for-simple-binding"></a>単純なバインドの変更通知  
 単純なバインドの場合、ビジネスオブジェクトは、バインドされたプロパティの値が変更されたときに変更通知を提供する必要があります。 これを行うには、ビジネスオブジェクトの各プロパティに対して *PropertyName* Changed イベントを公開し、ビジネスオブジェクトがインターフェイスを実装する、または優先メソッドを使用してビジネスオブジェクトをコントロールにバインド <xref:System.Windows.Forms.BindingSource> <xref:System.ComponentModel.INotifyPropertyChanged> し <xref:System.ComponentModel.INotifyPropertyChanged.PropertyChanged> ます。また、プロパティの値が変更されたときにイベントを発生させます。 詳細については、「 [方法: INotifyPropertyChanged インターフェイスを実装](how-to-implement-the-inotifypropertychanged-interface.md)する」を参照してください。 インターフェイスを実装するオブジェクトを使用する場合、 <xref:System.ComponentModel.INotifyPropertyChanged> オブジェクトをコントロールにバインドするためにを使用する必要はありませんが、を使用する <xref:System.Windows.Forms.BindingSource> <xref:System.Windows.Forms.BindingSource> ことをお勧めします。  
  
## <a name="change-notification-for-list-based-binding"></a>List-Based バインドの変更通知  
 Windows フォームは、バインドされたリストに依存してプロパティの変更 (リスト項目のプロパティ値の変更) を提供し、バインドされたコントロールに対して (項目が削除またはリストに追加される) リストを変更します。 したがって、データバインディングに使用されるリストでは、 <xref:System.ComponentModel.IBindingList> 両方の種類の変更通知を提供するを実装する必要があります。 は <xref:System.ComponentModel.BindingList%601> の汎用実装であり、 <xref:System.ComponentModel.IBindingList> Windows フォームデータバインディングで使用するように設計されています。 を <xref:System.ComponentModel.BindingList%601> 実装するビジネスオブジェクトの種類を含むを作成でき <xref:System.ComponentModel.INotifyPropertyChanged> ます。この一覧では、イベントがイベントに自動的に変換され <xref:System.ComponentModel.INotifyPropertyChanged.PropertyChanged> <xref:System.ComponentModel.IBindingList.ListChanged> ます。 バインドされたリストがでない場合は、 <xref:System.ComponentModel.IBindingList> コンポーネントを使用して、オブジェクトのリストを Windows フォームコントロールにバインドする必要があり <xref:System.Windows.Forms.BindingSource> ます。 <xref:System.Windows.Forms.BindingSource>コンポーネントは、のプロパティからリストへの変換を提供 <xref:System.ComponentModel.BindingList%601> します。 詳細については、「 [方法: BindingSource と INotifyPropertyChanged インターフェイスを使用して変更通知を発生させる](./controls/raise-change-notifications--bindingsource.md)」を参照してください。  
  
## <a name="change-notification-for-custom-controls"></a>カスタムコントロールの通知の変更  
 最後に、コントロール側から、データにバインドされるように設計された各プロパティの *PropertyName* Changed イベントを公開する必要があります。 次に、コントロールプロパティの変更が、バインドされたデータソースに反映されます。 詳細については、「[方法: PropertyNameChanged パターンを適用する](how-to-apply-the-propertynamechanged-pattern.md)」を参照してください。  
  
## <a name="see-also"></a>関連項目

- <xref:System.Windows.Forms.BindingSource>
- <xref:System.ComponentModel.INotifyPropertyChanged>
- <xref:System.ComponentModel.BindingList%601>
- [Windows フォームでのデータ バインディング](windows-forms-data-binding.md)
- [Windows フォームがサポートするデータ ソース](data-sources-supported-by-windows-forms.md)
- [データ連結と Windows フォーム](data-binding-and-windows-forms.md)
