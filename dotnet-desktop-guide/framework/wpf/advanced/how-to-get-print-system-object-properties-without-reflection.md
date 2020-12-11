---
title: '方法 : リフレクションを使用せずに印刷システム オブジェクトのプロパティを取得する'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- PrintSystemObject [WPF], getting properties
ms.assetid: 43560f28-183d-41c1-b9d1-de7c2552273e
ms.openlocfilehash: bb906dafd98e75708764b5f0f009900719f6a475
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/09/2020
ms.locfileid: "96982095"
---
# <a name="how-to-get-print-system-object-properties-without-reflection"></a>方法 : リフレクションを使用せずに印刷システム オブジェクトのプロパティを取得する
リフレクションを使用してオブジェクトのプロパティ (およびそれらのプロパティの型) を処理すると、アプリケーションのパフォーマンスが低下する可能性があります。 <xref:System.Printing.IndexedProperties>名前空間は、リフレクションを使用してこの情報を取得するための手段を提供します。  
  
## <a name="example"></a>例  
 これを行う手順は次のとおりです。  
  
1. 型のインスタンスを作成します。 次の例では、型は <xref:System.Printing.PrintQueue> Microsoft .NET Framework に付属する型ですが、ほぼ同一のコードは、派生元の型に対して機能し <xref:System.Printing.PrintSystemObject> ます。  
  
2. <xref:System.Printing.IndexedProperties.PrintPropertyDictionary>型のからを作成し <xref:System.Printing.PrintSystemObject.PropertiesCollection%2A> ます。 この辞書内の各エントリの <xref:System.Collections.DictionaryEntry.Value%2A> プロパティは、<xref:System.Printing.IndexedProperties.PrintProperty> から派生したいずれかの型のオブジェクトです。  
  
3. 辞書のメンバーを列挙します。 それぞれについて、次の手順を実行します。  
  
4. 各エントリの値をにアップキャスト <xref:System.Printing.IndexedProperties.PrintProperty> し、それを使用してオブジェクトを作成し <xref:System.Printing.IndexedProperties.PrintProperty> ます。  
  
5. 各オブジェクトのの型を取得し <xref:System.Printing.IndexedProperties.PrintProperty.Value%2A> <xref:System.Printing.IndexedProperties.PrintProperty> ます。  
  
 [!code-csharp[GetPrintObjectPropertyTypesWithoutReflection#ShowPropertyTypesWithoutReflection](~/samples/snippets/csharp/VS_Snippets_Wpf/GetPrintObjectPropertyTypesWithoutReflection/CSharp/Program.cs#showpropertytypeswithoutreflection)]
 [!code-vb[GetPrintObjectPropertyTypesWithoutReflection#ShowPropertyTypesWithoutReflection](~/samples/snippets/visualbasic/VS_Snippets_Wpf/GetPrintObjectPropertyTypesWithoutReflection/visualbasic/program.vb#showpropertytypeswithoutreflection)]  
  
## <a name="see-also"></a>関連項目

- <xref:System.Printing.IndexedProperties.PrintProperty>
- <xref:System.Printing.PrintSystemObject>
- <xref:System.Printing.IndexedProperties>
- <xref:System.Printing.IndexedProperties.PrintPropertyDictionary>
- <xref:System.Printing.LocalPrintServer>
- <xref:System.Printing.PrintQueue>
- <xref:System.Collections.DictionaryEntry>
- [WPF のドキュメント](documents-in-wpf.md)
- [印刷の概要](printing-overview.md)
