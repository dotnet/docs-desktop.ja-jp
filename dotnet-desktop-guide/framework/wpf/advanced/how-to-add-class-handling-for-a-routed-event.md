---
title: '方法: ルーティング イベントのクラス処理を追加する'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- routed events [WPF], class handlers
- task_core_add_class_handling_routed_properties [WPF]
- class handlers [WPF], routed events
ms.assetid: 15b7b06c-9112-4ee5-b30a-65d10c5c5df6
ms.openlocfilehash: 7b897954cbdab461dc0305c6290e67c1af5282c3
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/09/2020
ms.locfileid: "96982659"
---
# <a name="how-to-add-class-handling-for-a-routed-event"></a><span data-ttu-id="26813-102">方法: ルーティング イベントのクラス処理を追加する</span><span class="sxs-lookup"><span data-stu-id="26813-102">How to: Add Class Handling for a Routed Event</span></span>
<span data-ttu-id="26813-103">ルーティング イベントは、ルート内の特定のノードのクラス ハンドラーまたはインスタンス ハンドラーのいずれかによって処理されます。</span><span class="sxs-lookup"><span data-stu-id="26813-103">Routed events can be handled either by class handlers or instance handlers on any given node in the route.</span></span> <span data-ttu-id="26813-104">クラス ハンドラーを最初に呼び出し、クラス実装で使用して、インスタンス処理からのイベントを抑制したり、基底クラスによって所有されるイベントに他のイベント固有の動作を導入したりすることができます。</span><span class="sxs-lookup"><span data-stu-id="26813-104">Class handlers are invoked first, and can be used by class implementations to suppress events from instance handling or introduce other event specific behaviors on events that are owned by base classes.</span></span> <span data-ttu-id="26813-105">この例は、クラス ハンドラーを実装するための密接に関連する 2 つの手法を示しています。</span><span class="sxs-lookup"><span data-stu-id="26813-105">This example illustrates two closely related techniques for implementing class handlers.</span></span>  
  
## <a name="example"></a><span data-ttu-id="26813-106">例</span><span class="sxs-lookup"><span data-stu-id="26813-106">Example</span></span>  
 <span data-ttu-id="26813-107">この例では、<xref:System.Windows.Controls.Canvas> パネルに基づくカスタム クラスを使用しています。</span><span class="sxs-lookup"><span data-stu-id="26813-107">This example uses a custom class based on the <xref:System.Windows.Controls.Canvas> panel.</span></span> <span data-ttu-id="26813-108">アプリケーションの基本的な前提は、カスタム クラスによって、その子要素に動作が導入されるということです。たとえば、子要素クラスまたはそれに対するインスタンス ハンドラーが呼び出される前に、左マウス ボタンのクリックがインターセプトされ処理済みとしてマークされることなどです。</span><span class="sxs-lookup"><span data-stu-id="26813-108">The basic premise of the application is that the custom class introduces behaviors on its child elements, including intercepting any left mouse button clicks and marking them handled, before the child element class or any instance handlers on it will be invoked.</span></span>  
  
 <span data-ttu-id="26813-109"><xref:System.Windows.UIElement> クラスによって仮想メソッドが公開され、イベントをオーバーライドするだけで、<xref:System.Windows.UIElement.PreviewMouseLeftButtonDown> イベントに対するクラス処理が可能になります。</span><span class="sxs-lookup"><span data-stu-id="26813-109">The <xref:System.Windows.UIElement> class exposes a virtual method that enables class handling on the <xref:System.Windows.UIElement.PreviewMouseLeftButtonDown> event, by simply overriding the event.</span></span> <span data-ttu-id="26813-110">クラスの階層のどこかでこのような仮想メソッドを使用できる場合、これがクラス処理を実装する最もシンプルな方法です。</span><span class="sxs-lookup"><span data-stu-id="26813-110">This is the simplest way to implement class handling if such a virtual method is available somewhere in your class' hierarchy.</span></span> <span data-ttu-id="26813-111">次のコードは、<xref:System.Windows.Controls.Canvas> から派生した "MyEditContainer" での <xref:System.Windows.UIElement.OnPreviewMouseLeftButtonDown%2A> の実装を示しています。</span><span class="sxs-lookup"><span data-stu-id="26813-111">The following code shows the <xref:System.Windows.UIElement.OnPreviewMouseLeftButtonDown%2A> implementation in the "MyEditContainer" that is derived from <xref:System.Windows.Controls.Canvas>.</span></span> <span data-ttu-id="26813-112">この実装では、引数でイベントを処理済みとマークし、ソース要素に基本的な目に見える変更を加えるコードを追加します。</span><span class="sxs-lookup"><span data-stu-id="26813-112">The implementation marks the event as handled in the arguments, and then adds some code to give the source element a basic visible change.</span></span>  
  
 [!code-csharp[ClassHandling#OnStarClassHandler](~/samples/snippets/csharp/VS_Snippets_Wpf/ClassHandling/CSharp/SDKSampleLibrary/class1.cs#onstarclasshandler)]
 [!code-vb[ClassHandling#OnStarClassHandler](~/samples/snippets/visualbasic/VS_Snippets_Wpf/ClassHandling/visualbasic/sdksamplelibrary/class1.vb#onstarclasshandler)]  
  
 <span data-ttu-id="26813-113">基底クラスまたはその特定のメソッドで使用できる仮想がない場合は、<xref:System.Windows.EventManager> クラスのユーティリティ メソッド <xref:System.Windows.EventManager.RegisterClassHandler%2A> を使用して、クラス処理を直接追加できます。</span><span class="sxs-lookup"><span data-stu-id="26813-113">If no virtual is available on base classes or for that particular method, class handling can be added directly using a utility method of the <xref:System.Windows.EventManager> class, <xref:System.Windows.EventManager.RegisterClassHandler%2A>.</span></span> <span data-ttu-id="26813-114">このメソッドは、クラス処理を追加しているクラスの静的初期化内でのみ呼び出す必要があります。</span><span class="sxs-lookup"><span data-stu-id="26813-114">This method should only be called within the static initialization of classes that are adding class handling.</span></span> <span data-ttu-id="26813-115">この例では、<xref:System.Windows.UIElement.PreviewMouseLeftButtonDown> のハンドラーをもう 1 つ追加します。この場合、登録されるクラスはカスタム クラスです。</span><span class="sxs-lookup"><span data-stu-id="26813-115">This example adds another handler for <xref:System.Windows.UIElement.PreviewMouseLeftButtonDown> , and in this case the registered class is the custom class.</span></span> <span data-ttu-id="26813-116">これに対し、仮想を使用する場合、登録されるクラスは実際には <xref:System.Windows.UIElement> 基底クラスです。</span><span class="sxs-lookup"><span data-stu-id="26813-116">In contrast, when using the virtuals, the registered class is really the <xref:System.Windows.UIElement> base class.</span></span> <span data-ttu-id="26813-117">基底クラスとサブクラスのそれぞれにクラス処理が登録される場合、サブクラス ハンドラーが最初に呼び出されます。</span><span class="sxs-lookup"><span data-stu-id="26813-117">In cases where base classes and subclass each register class handling, the subclass handlers are invoked first.</span></span> <span data-ttu-id="26813-118">アプリケーションの動作では、最初にこのハンドラーでメッセージ ボックスが表示され、次に仮想メソッドのハンドラーのビジュアルの変更が表示されます。</span><span class="sxs-lookup"><span data-stu-id="26813-118">The behavior in an application would be that first this handler would show its message box and then the visual change in the virtual method's handler would be shown.</span></span>  
  
 [!code-csharp[ClassHandling#StaticAndRegisterClassHandler](~/samples/snippets/csharp/VS_Snippets_Wpf/ClassHandling/CSharp/SDKSampleLibrary/class1.cs#staticandregisterclasshandler)]
 [!code-vb[ClassHandling#StaticAndRegisterClassHandler](~/samples/snippets/visualbasic/VS_Snippets_Wpf/ClassHandling/visualbasic/sdksamplelibrary/class1.vb#staticandregisterclasshandler)]  
  
## <a name="see-also"></a><span data-ttu-id="26813-119">関連項目</span><span class="sxs-lookup"><span data-stu-id="26813-119">See also</span></span>

- <xref:System.Windows.EventManager>
- [<span data-ttu-id="26813-120">ルーティング イベントの処理済みとしてのマーキング、およびクラス処理</span><span class="sxs-lookup"><span data-stu-id="26813-120">Marking Routed Events as Handled, and Class Handling</span></span>](marking-routed-events-as-handled-and-class-handling.md)
- [<span data-ttu-id="26813-121">ルーティング イベントを処理する</span><span class="sxs-lookup"><span data-stu-id="26813-121">Handle a Routed Event</span></span>](how-to-handle-a-routed-event.md)
- [<span data-ttu-id="26813-122">ルーティング イベントの概要</span><span class="sxs-lookup"><span data-stu-id="26813-122">Routed Events Overview</span></span>](routed-events-overview.md)
