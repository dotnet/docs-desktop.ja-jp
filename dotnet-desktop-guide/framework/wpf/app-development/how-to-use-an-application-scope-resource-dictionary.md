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
# <a name="how-to-use-an-application-scope-resource-dictionary"></a>方法: アプリケーション スコープのリソース ディクショナリを使用する

この例では、アプリケーション スコープのカスタム リソース ディクショナリを定義して、使用する方法を示します。  
  
## <a name="example"></a>例  

 <xref:System.Windows.Application> では、共有リソース用にアプリケーション スコープのストア <xref:System.Windows.Application.Resources%2A> が公開されています。 既定では、<xref:System.Windows.Application.Resources%2A> プロパティは <xref:System.Windows.ResourceDictionary> 型のインスタンスで初期化されます。 このインスタンスは、<xref:System.Windows.Application.Resources%2A> を使用してアプリケーション スコープのプロパティを取得および設定するときに使用します。 詳細については、「[方法:アプリケーション スコープのリソースを取得および設定する](/previous-versions/dotnet/netframework-4.0/aa348547(v=vs.100))」を参照してください。
  
 <xref:System.Windows.Application.Resources%2A> を使用して設定するリソースが複数ある場合には、代わりにカスタム リソース ディクショナリを使用して、これらのリソースを格納し、<xref:System.Windows.Application.Resources%2A> を設定できます。 XAML を使用してカスタム リソース ディクショナリを宣言する方法を次に示します。
  
 [!code-xaml[HOWTOResourceDictionaries#1](~/samples/snippets/csharp/VS_Snippets_Wpf/HowToResourceDictionaries/CSharp/MyResourceDictionary.xaml#1)]  
  
 <xref:System.Windows.Application.Resources%2A> を使用してリソース ディクショナリ全体を交換することで、各テーマが単一のリソース ディクショナリにカプセル化されているアプリケーション スコープのテーマをサポートできます。 <xref:System.Windows.ResourceDictionary> を設定する方法を次の例に示します。  
  
 [!code-xaml[HOWTOResourceDictionaries#2](~/samples/snippets/csharp/VS_Snippets_Wpf/HowToResourceDictionaries/CSharp/App.xaml#2)]  
  
 XAML の <xref:System.Windows.Application.Resources%2A> によって公開されたリソース ディクショナリからアプリケーション スコープのリソースを取得する方法を次に示します。  
  
 [!code-xaml[HOWTOResourceDictionaries#4](~/samples/snippets/csharp/VS_Snippets_Wpf/HowToResourceDictionaries/CSharp/MainWindow.xaml#4)]  
  
 コードでリソースも取得する方法を次に示します。  
  
 [!code-csharp[HOWTOResourceDictionaries#3](~/samples/snippets/csharp/VS_Snippets_Wpf/HowToResourceDictionaries/CSharp/MainWindow.xaml.cs#3)]
 [!code-vb[HOWTOResourceDictionaries#3](~/samples/snippets/visualbasic/VS_Snippets_Wpf/HowToResourceDictionaries/VB/MainWindow.xaml.vb#3)]  
  
 <xref:System.Windows.Application.Resources%2A> を使用するときに注意する点が 2 つあります。 1 つ目は、ディクショナリの "*キー*" はオブジェクトであるため、プロパティ値を設定および取得するときに、まったく同じオブジェクト インスタンスを使用する必要があります。 (キーに文字列を使用する場合、大文字と小文字が区別されることに注意してください)。2 つ目は、ディクショナリの "*値*" はオブジェクトであるため、プロパティ値を取得するときに、その値を目的の型に変換する必要があります。  

リソースの種類によっては、型や型などの明示的なキーとして、型によって定義されたプロパティが自動的に使用される場合があり <xref:System.Windows.Style> <xref:System.Windows.DataTemplate> ます。 これにより、値が上書きされる可能性があり `x:Key` ます。 キーが尊重されることを保証するには `x:Key` 、明示的なキープロパティの前に宣言します。 詳細については、「 [スタイル」、「DataTemplates](../advanced/xaml-resources-define.md#styles-datatemplates-and-implicit-keys)」、および「暗黙のキー」を参照してください。

## <a name="see-also"></a>関連項目

- <xref:System.Windows.ResourceDictionary>
- <xref:System.Windows.Application.Resources%2A>
- [XAML リソース](/dotnet/desktop-wpf/fundamentals/xaml-resources-define)
- [マージされたリソース ディクショナリ](../advanced/merged-resource-dictionaries.md)
