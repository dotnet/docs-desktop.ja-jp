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
# <a name="how-to-use-a-resourcedictionary-to-manage-localizable-string-resources"></a>方法: ResourceDictionary を使用してローカライズ可能な文字列リソースを管理する
この例では、を使用し <xref:System.Windows.ResourceDictionary> て Windows Presentation Foundation (WPF) アプリケーションのローカライズ可能な文字列リソースをパッケージ化する方法を示します。  
  
### <a name="to-use-a-resourcedictionary-to-manage-localizable-string-resources"></a>ResourceDictionary を使用してローカライズ可能な文字列リソースを管理するには  
  
1. <xref:System.Windows.ResourceDictionary>ローカライズする文字列を含むを作成します。 次のコードは例を示します。  
  
     [!code-xaml[StringLocalizationSample#StringResourceDictionary](~/samples/snippets/csharp/VS_Snippets_Wpf/StringLocalizationSample/CSharp/StringResources.xaml#stringresourcedictionary)]  
  
     このコードでは、mscorlib.dll の `localizedMessage` 名前空間から、型の文字列リソースを定義 <xref:System.String> <xref:System> します。  
  
2. 次の <xref:System.Windows.ResourceDictionary> コードを使用して、をアプリケーションに追加します。  
  
     [!code-xaml[StringLocalizationSample#ReferencingStringResourceDictionary](~/samples/snippets/csharp/VS_Snippets_Wpf/StringLocalizationSample/CSharp/App.xaml#referencingstringresourcedictionary)]  
  
3. 次のようにを使用して、マークアップからの文字列リソースを使用し [!INCLUDE[TLA#tla_xaml](../../../includes/tlasharptla-xaml-md.md)] ます。  
  
     [!code-xaml[StringLocalizationSample#GetLocalizedResourceFromMarkup](~/samples/snippets/csharp/VS_Snippets_Wpf/StringLocalizationSample/CSharp/MainWindow.xaml#getlocalizedresourcefrommarkup)]  
  
4. 次のようなコードを使用して、コードビハインドから文字列リソースを使用します。  
  
     [!code-csharp[StringLocalizationSample#GetLocalizedResourceFromCode](~/samples/snippets/csharp/VS_Snippets_Wpf/StringLocalizationSample/CSharp/MainWindow.xaml.cs#getlocalizedresourcefromcode)]
     [!code-vb[StringLocalizationSample#GetLocalizedResourceFromCode](~/samples/snippets/visualbasic/VS_Snippets_Wpf/StringLocalizationSample/VisualBasic/MainWindow.xaml.vb#getlocalizedresourcefromcode)]  
  
5. アプリケーションをローカライズします。 詳細については、「[アプリケーションをローカライズする](how-to-localize-an-application.md)」を参照してください。
