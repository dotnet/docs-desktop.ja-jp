---
title: '方法: アプリケーション スコープのリソース ディクショナリを使用する'
description: Windows Presentation Foundation (WPF) でアプリケーションスコープのカスタム リソース ディクショナリを定義して使用する方法について説明します。
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- dictionaries [WPF], resource
- resource dictionaries [WPF], application-scope
- application-scope resource dictionaries
ms.assetid: 53857682-bd2c-4f2c-8f25-1307d0b451a2
ms.openlocfilehash: 0d9c4f851c5ee03bf60dbdadc31d9fc4c6536746
ms.sourcegitcommit: 302273bd74509dfbff11126753dd210d80f1bc37
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/16/2021
ms.locfileid: "98535991"
---
# <a name="how-to-use-an-application-scope-resource-dictionary"></a><span data-ttu-id="c97c6-103">方法: アプリケーション スコープのリソース ディクショナリを使用する</span><span class="sxs-lookup"><span data-stu-id="c97c6-103">How to: Use an Application-Scope Resource Dictionary</span></span>

<span data-ttu-id="c97c6-104">この例では、アプリケーション スコープのカスタム リソース ディクショナリを定義して、使用する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="c97c6-104">This example shows how to define and use an application-scope custom resource dictionary.</span></span>  
  
## <a name="example"></a><span data-ttu-id="c97c6-105">例</span><span class="sxs-lookup"><span data-stu-id="c97c6-105">Example</span></span>  

 <span data-ttu-id="c97c6-106"><xref:System.Windows.Application> では、共有リソース用にアプリケーション スコープのストア <xref:System.Windows.Application.Resources%2A> が公開されています。</span><span class="sxs-lookup"><span data-stu-id="c97c6-106"><xref:System.Windows.Application> exposes an application-scope store for shared resources: <xref:System.Windows.Application.Resources%2A>.</span></span> <span data-ttu-id="c97c6-107">既定では、<xref:System.Windows.Application.Resources%2A> プロパティは <xref:System.Windows.ResourceDictionary> 型のインスタンスで初期化されます。</span><span class="sxs-lookup"><span data-stu-id="c97c6-107">By default, the <xref:System.Windows.Application.Resources%2A> property is initialized with an instance of the <xref:System.Windows.ResourceDictionary> type.</span></span> <span data-ttu-id="c97c6-108">このインスタンスは、<xref:System.Windows.Application.Resources%2A> を使用してアプリケーション スコープのプロパティを取得および設定するときに使用します。</span><span class="sxs-lookup"><span data-stu-id="c97c6-108">You use this instance when you get and set application-scope properties using <xref:System.Windows.Application.Resources%2A>.</span></span> <span data-ttu-id="c97c6-109">詳細については、「[方法:アプリケーション スコープのリソースを取得および設定する](/previous-versions/dotnet/netframework-4.0/aa348547(v=vs.100))」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="c97c6-109">For more information, see [How to: Get and Set an Application-Scope Resource](/previous-versions/dotnet/netframework-4.0/aa348547(v=vs.100)).</span></span>
  
 <span data-ttu-id="c97c6-110"><xref:System.Windows.Application.Resources%2A> を使用して設定するリソースが複数ある場合には、代わりにカスタム リソース ディクショナリを使用して、これらのリソースを格納し、<xref:System.Windows.Application.Resources%2A> を設定できます。</span><span class="sxs-lookup"><span data-stu-id="c97c6-110">If you have multiple resources that you set using <xref:System.Windows.Application.Resources%2A>, you can instead use a custom resource dictionary to store those resources and set <xref:System.Windows.Application.Resources%2A> with it instead.</span></span> <span data-ttu-id="c97c6-111">XAML を使用してカスタム リソース ディクショナリを宣言する方法を次に示します。</span><span class="sxs-lookup"><span data-stu-id="c97c6-111">The following shows how you declare a custom resource dictionary using XAML.</span></span>
  
 [!code-xaml[HOWTOResourceDictionaries#1](~/samples/snippets/csharp/VS_Snippets_Wpf/HowToResourceDictionaries/CSharp/MyResourceDictionary.xaml#1)]  
  
 <span data-ttu-id="c97c6-112"><xref:System.Windows.Application.Resources%2A> を使用してリソース ディクショナリ全体を交換することで、各テーマが単一のリソース ディクショナリにカプセル化されているアプリケーション スコープのテーマをサポートできます。</span><span class="sxs-lookup"><span data-stu-id="c97c6-112">Swapping entire resource dictionaries using <xref:System.Windows.Application.Resources%2A> allows you to support application-scope themes, where each theme is encapsulated by a single resource dictionary.</span></span> <span data-ttu-id="c97c6-113"><xref:System.Windows.ResourceDictionary> を設定する方法を次の例に示します。</span><span class="sxs-lookup"><span data-stu-id="c97c6-113">The following example shows how to set the <xref:System.Windows.ResourceDictionary>.</span></span>  
  
 [!code-xaml[HOWTOResourceDictionaries#2](~/samples/snippets/csharp/VS_Snippets_Wpf/HowToResourceDictionaries/CSharp/App.xaml#2)]  
  
 <span data-ttu-id="c97c6-114">XAML の <xref:System.Windows.Application.Resources%2A> によって公開されたリソース ディクショナリからアプリケーション スコープのリソースを取得する方法を次に示します。</span><span class="sxs-lookup"><span data-stu-id="c97c6-114">The following shows how you can get application-scope resources from the resource dictionary exposed by <xref:System.Windows.Application.Resources%2A> in XAML.</span></span>  
  
 [!code-xaml[HOWTOResourceDictionaries#4](~/samples/snippets/csharp/VS_Snippets_Wpf/HowToResourceDictionaries/CSharp/MainWindow.xaml#4)]  
  
 <span data-ttu-id="c97c6-115">コードでリソースも取得する方法を次に示します。</span><span class="sxs-lookup"><span data-stu-id="c97c6-115">The following shows how you can also get the resources in code.</span></span>  
  
 [!code-csharp[HOWTOResourceDictionaries#3](~/samples/snippets/csharp/VS_Snippets_Wpf/HowToResourceDictionaries/CSharp/MainWindow.xaml.cs#3)]
 [!code-vb[HOWTOResourceDictionaries#3](~/samples/snippets/visualbasic/VS_Snippets_Wpf/HowToResourceDictionaries/VB/MainWindow.xaml.vb#3)]  
  
 <span data-ttu-id="c97c6-116"><xref:System.Windows.Application.Resources%2A> を使用するときに注意する点が 2 つあります。</span><span class="sxs-lookup"><span data-stu-id="c97c6-116">There are two considerations to make when using <xref:System.Windows.Application.Resources%2A>.</span></span> <span data-ttu-id="c97c6-117">1 つ目は、ディクショナリの "*キー*" はオブジェクトであるため、プロパティ値を設定および取得するときに、まったく同じオブジェクト インスタンスを使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="c97c6-117">First, the dictionary *key* is an object, so you must use exactly the same object instance when both setting and getting a property value.</span></span> <span data-ttu-id="c97c6-118">(キーに文字列を使用する場合、大文字と小文字が区別されることに注意してください)。2 つ目は、ディクショナリの "*値*" はオブジェクトであるため、プロパティ値を取得するときに、その値を目的の型に変換する必要があります。</span><span class="sxs-lookup"><span data-stu-id="c97c6-118">(Note that the key is case-sensitive when using a string.) Second, the dictionary *value* is an object, so you will have to convert the value to the desired type when getting a property value.</span></span>  

<span data-ttu-id="c97c6-119">リソースの種類によっては、型や型などの明示的なキーとして、型によって定義されたプロパティが自動的に使用される場合があり <xref:System.Windows.Style> <xref:System.Windows.DataTemplate> ます。</span><span class="sxs-lookup"><span data-stu-id="c97c6-119">Some resource types may automatically use a property defined by the type as an explicit key, such as the <xref:System.Windows.Style> and <xref:System.Windows.DataTemplate> types.</span></span> <span data-ttu-id="c97c6-120">これにより、値が上書きされる可能性があり `x:Key` ます。</span><span class="sxs-lookup"><span data-stu-id="c97c6-120">This may override your `x:Key` value.</span></span> <span data-ttu-id="c97c6-121">キーが尊重されることを保証するには `x:Key` 、明示的なキープロパティの前に宣言します。</span><span class="sxs-lookup"><span data-stu-id="c97c6-121">To guarantee that your `x:Key` key is respected, declare it before the explicit key property.</span></span> <span data-ttu-id="c97c6-122">詳細については、「 [スタイル」、「DataTemplates](../advanced/xaml-resources-define.md#styles-datatemplates-and-implicit-keys)」、および「暗黙のキー」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="c97c6-122">For more information, see [Styles, DataTemplates, and implicit keys](../advanced/xaml-resources-define.md#styles-datatemplates-and-implicit-keys).</span></span>

## <a name="see-also"></a><span data-ttu-id="c97c6-123">関連項目</span><span class="sxs-lookup"><span data-stu-id="c97c6-123">See also</span></span>

- <xref:System.Windows.ResourceDictionary>
- <xref:System.Windows.Application.Resources%2A>
- [<span data-ttu-id="c97c6-124">XAML リソース</span><span class="sxs-lookup"><span data-stu-id="c97c6-124">XAML Resources</span></span>](/dotnet/desktop-wpf/fundamentals/xaml-resources-define)
- [<span data-ttu-id="c97c6-125">マージされたリソース ディクショナリ</span><span class="sxs-lookup"><span data-stu-id="c97c6-125">Merged Resource Dictionaries</span></span>](../advanced/merged-resource-dictionaries.md)
