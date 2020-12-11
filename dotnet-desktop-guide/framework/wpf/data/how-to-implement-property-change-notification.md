---
title: '方法: プロパティの変更通知を実装する'
description: Windows Presentation Foundation (WPF) で、プロパティ値が変更されたときにプロパティがバインディング ソースに自動的に通知できるようにします。
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- notifications of change [WPF]
- data binding [WPF], property change notifications
- change notifications [WPF]
- properties [WPF], change notifications
ms.assetid: 30b59d9e-8c3a-4349-aa82-4be837e841cf
ms.openlocfilehash: f3cf3fe211e852fccaa605623820ebbde7e62917
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/09/2020
ms.locfileid: "96984908"
---
# <a name="how-to-implement-property-change-notification"></a><span data-ttu-id="56dd3-103">方法: プロパティの変更通知を実装する</span><span class="sxs-lookup"><span data-stu-id="56dd3-103">How to: Implement Property Change Notification</span></span>
<span data-ttu-id="56dd3-104">バインディング ターゲットのプロパティにバインディング ソースの動的変更が自動的に反映される (たとえば、ユーザーがフォームを編集するとプレビュー ペインが自動的に更新される) ようにするために、<xref:System.Windows.Data.BindingMode.OneWay> または <xref:System.Windows.Data.BindingMode.TwoWay> バインディングをサポートするには、クラスが適切なプロパティ変更通知を提供する必要があります。</span><span class="sxs-lookup"><span data-stu-id="56dd3-104">To support <xref:System.Windows.Data.BindingMode.OneWay> or <xref:System.Windows.Data.BindingMode.TwoWay> binding to enable your binding target properties to automatically reflect the dynamic changes of the binding source (for example, to have the preview pane updated automatically when the user edits a form), your class needs to provide the proper property changed notifications.</span></span> <span data-ttu-id="56dd3-105">この例では、<xref:System.ComponentModel.INotifyPropertyChanged> を実装するクラスを作成する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="56dd3-105">This example shows how to create a class that implements <xref:System.ComponentModel.INotifyPropertyChanged>.</span></span>  
  
## <a name="example"></a><span data-ttu-id="56dd3-106">例</span><span class="sxs-lookup"><span data-stu-id="56dd3-106">Example</span></span>  
 <span data-ttu-id="56dd3-107"><xref:System.ComponentModel.INotifyPropertyChanged> を実装するには、<xref:System.ComponentModel.INotifyPropertyChanged.PropertyChanged> イベントを宣言し、`OnPropertyChanged` メソッドを作成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="56dd3-107">To implement <xref:System.ComponentModel.INotifyPropertyChanged> you need to declare the <xref:System.ComponentModel.INotifyPropertyChanged.PropertyChanged> event and create the `OnPropertyChanged` method.</span></span> <span data-ttu-id="56dd3-108">次に、変更を通知する必要のある各プロパティについて、そのプロパティが更新されるたびに `OnPropertyChanged` を呼び出します。</span><span class="sxs-lookup"><span data-stu-id="56dd3-108">Then for each property you want change notifications for, you call `OnPropertyChanged` whenever the property is updated.</span></span>  
  
 [!code-csharp[SimpleBinding#PersonClass](~/samples/snippets/csharp/VS_Snippets_Wpf/SimpleBinding/CSharp/Person.cs#personclass)]
 [!code-vb[SimpleBinding#PersonClass](~/samples/snippets/visualbasic/VS_Snippets_Wpf/SimpleBinding/VisualBasic/Person.vb#personclass)]  
  
 <span data-ttu-id="56dd3-109">`Person` クラスを使用して <xref:System.Windows.Data.BindingMode.TwoWay> バインディングをサポートする例については、「[TextBox テキストでソースを更新するタイミングを制御する](how-to-control-when-the-textbox-text-updates-the-source.md)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="56dd3-109">To see an example of how the `Person` class can be used to support <xref:System.Windows.Data.BindingMode.TwoWay> binding, see [Control When the TextBox Text Updates the Source](how-to-control-when-the-textbox-text-updates-the-source.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="56dd3-110">関連項目</span><span class="sxs-lookup"><span data-stu-id="56dd3-110">See also</span></span>

- [<span data-ttu-id="56dd3-111">バインディング ソースの概要</span><span class="sxs-lookup"><span data-stu-id="56dd3-111">Binding Sources Overview</span></span>](binding-sources-overview.md)
- [<span data-ttu-id="56dd3-112">データ バインディングの概要</span><span class="sxs-lookup"><span data-stu-id="56dd3-112">Data Binding Overview</span></span>](/dotnet/desktop-wpf/data/data-binding-overview)
- [<span data-ttu-id="56dd3-113">方法トピック</span><span class="sxs-lookup"><span data-stu-id="56dd3-113">How-to Topics</span></span>](data-binding-how-to-topics.md)
