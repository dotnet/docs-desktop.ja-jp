---
title: '方法: ResourceDictionary を使用してローカライズ可能な文字列リソースを管理する'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- resources [WPF], packaging string resources
- packaging string resources [WPF]
- ResourceDictionary [WPF]
- localization [WPF], packaging string resources
ms.assetid: 19e7d9a5-20df-4ad3-b157-fe6515902e5e
ms.openlocfilehash: 3e7a6813497a6a4a7251b49382ed32e4a7b521da
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/09/2020
ms.locfileid: "96982068"
---
# <a name="how-to-use-a-resourcedictionary-to-manage-localizable-string-resources"></a><span data-ttu-id="6dea4-102">方法: ResourceDictionary を使用してローカライズ可能な文字列リソースを管理する</span><span class="sxs-lookup"><span data-stu-id="6dea4-102">How to: Use a ResourceDictionary to Manage Localizable String Resources</span></span>
<span data-ttu-id="6dea4-103">この例では、を使用し <xref:System.Windows.ResourceDictionary> て Windows Presentation Foundation (WPF) アプリケーションのローカライズ可能な文字列リソースをパッケージ化する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="6dea4-103">This example shows how to use a <xref:System.Windows.ResourceDictionary> to package localizable string resources for Windows Presentation Foundation (WPF) applications.</span></span>  
  
### <a name="to-use-a-resourcedictionary-to-manage-localizable-string-resources"></a><span data-ttu-id="6dea4-104">ResourceDictionary を使用してローカライズ可能な文字列リソースを管理するには</span><span class="sxs-lookup"><span data-stu-id="6dea4-104">To use a ResourceDictionary to manage localizable string resources</span></span>  
  
1. <span data-ttu-id="6dea4-105"><xref:System.Windows.ResourceDictionary>ローカライズする文字列を含むを作成します。</span><span class="sxs-lookup"><span data-stu-id="6dea4-105">Create a <xref:System.Windows.ResourceDictionary> that contains the strings you would like to localize.</span></span> <span data-ttu-id="6dea4-106">次のコードは例を示します。</span><span class="sxs-lookup"><span data-stu-id="6dea4-106">The following code shows an example.</span></span>  
  
     [!code-xaml[StringLocalizationSample#StringResourceDictionary](~/samples/snippets/csharp/VS_Snippets_Wpf/StringLocalizationSample/CSharp/StringResources.xaml#stringresourcedictionary)]  
  
     <span data-ttu-id="6dea4-107">このコードでは、mscorlib.dll の `localizedMessage` 名前空間から、型の文字列リソースを定義 <xref:System.String> <xref:System> します。</span><span class="sxs-lookup"><span data-stu-id="6dea4-107">This code defines a string resource, `localizedMessage`, of type <xref:System.String>, from the <xref:System> namespace in mscorlib.dll.</span></span>  
  
2. <span data-ttu-id="6dea4-108">次の <xref:System.Windows.ResourceDictionary> コードを使用して、をアプリケーションに追加します。</span><span class="sxs-lookup"><span data-stu-id="6dea4-108">Add the <xref:System.Windows.ResourceDictionary> to your application, using the following code.</span></span>  
  
     [!code-xaml[StringLocalizationSample#ReferencingStringResourceDictionary](~/samples/snippets/csharp/VS_Snippets_Wpf/StringLocalizationSample/CSharp/App.xaml#referencingstringresourcedictionary)]  
  
3. <span data-ttu-id="6dea4-109">次のようにを使用して、マークアップからの文字列リソースを使用し [!INCLUDE[TLA#tla_xaml](../../../includes/tlasharptla-xaml-md.md)] ます。</span><span class="sxs-lookup"><span data-stu-id="6dea4-109">Use the string resource from markup, using [!INCLUDE[TLA#tla_xaml](../../../includes/tlasharptla-xaml-md.md)] like the following.</span></span>  
  
     [!code-xaml[StringLocalizationSample#GetLocalizedResourceFromMarkup](~/samples/snippets/csharp/VS_Snippets_Wpf/StringLocalizationSample/CSharp/MainWindow.xaml#getlocalizedresourcefrommarkup)]  
  
4. <span data-ttu-id="6dea4-110">次のようなコードを使用して、コードビハインドから文字列リソースを使用します。</span><span class="sxs-lookup"><span data-stu-id="6dea4-110">Use the string resource from code-behind, using code like the following.</span></span>  
  
     [!code-csharp[StringLocalizationSample#GetLocalizedResourceFromCode](~/samples/snippets/csharp/VS_Snippets_Wpf/StringLocalizationSample/CSharp/MainWindow.xaml.cs#getlocalizedresourcefromcode)]
     [!code-vb[StringLocalizationSample#GetLocalizedResourceFromCode](~/samples/snippets/visualbasic/VS_Snippets_Wpf/StringLocalizationSample/VisualBasic/MainWindow.xaml.vb#getlocalizedresourcefromcode)]  
  
5. <span data-ttu-id="6dea4-111">アプリケーションをローカライズします。</span><span class="sxs-lookup"><span data-stu-id="6dea4-111">Localize the application.</span></span> <span data-ttu-id="6dea4-112">詳細については、「[アプリケーションをローカライズする](how-to-localize-an-application.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="6dea4-112">For more information, see [Localize an Application](how-to-localize-an-application.md).</span></span>
