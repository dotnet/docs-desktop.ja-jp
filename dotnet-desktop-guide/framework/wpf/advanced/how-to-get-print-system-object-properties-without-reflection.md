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
# <a name="how-to-get-print-system-object-properties-without-reflection"></a><span data-ttu-id="aa3a0-102">方法 : リフレクションを使用せずに印刷システム オブジェクトのプロパティを取得する</span><span class="sxs-lookup"><span data-stu-id="aa3a0-102">How to: Get Print System Object Properties Without Reflection</span></span>
<span data-ttu-id="aa3a0-103">リフレクションを使用してオブジェクトのプロパティ (およびそれらのプロパティの型) を処理すると、アプリケーションのパフォーマンスが低下する可能性があります。</span><span class="sxs-lookup"><span data-stu-id="aa3a0-103">Using reflection to itemize the properties (and the types of those properties) on an object can slow application performance.</span></span> <span data-ttu-id="aa3a0-104"><xref:System.Printing.IndexedProperties>名前空間は、リフレクションを使用してこの情報を取得するための手段を提供します。</span><span class="sxs-lookup"><span data-stu-id="aa3a0-104">The <xref:System.Printing.IndexedProperties> namespace provides a means to getting this information with using reflection.</span></span>  
  
## <a name="example"></a><span data-ttu-id="aa3a0-105">例</span><span class="sxs-lookup"><span data-stu-id="aa3a0-105">Example</span></span>  
 <span data-ttu-id="aa3a0-106">これを行う手順は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="aa3a0-106">The steps for doing this are as follows.</span></span>  
  
1. <span data-ttu-id="aa3a0-107">型のインスタンスを作成します。</span><span class="sxs-lookup"><span data-stu-id="aa3a0-107">Create an instance of the type.</span></span> <span data-ttu-id="aa3a0-108">次の例では、型は <xref:System.Printing.PrintQueue> Microsoft .NET Framework に付属する型ですが、ほぼ同一のコードは、派生元の型に対して機能し <xref:System.Printing.PrintSystemObject> ます。</span><span class="sxs-lookup"><span data-stu-id="aa3a0-108">In the example below, the type is the <xref:System.Printing.PrintQueue> type that ships with Microsoft .NET Framework, but nearly identical code should work for types that you derive from <xref:System.Printing.PrintSystemObject>.</span></span>  
  
2. <span data-ttu-id="aa3a0-109"><xref:System.Printing.IndexedProperties.PrintPropertyDictionary>型のからを作成し <xref:System.Printing.PrintSystemObject.PropertiesCollection%2A> ます。</span><span class="sxs-lookup"><span data-stu-id="aa3a0-109">Create a <xref:System.Printing.IndexedProperties.PrintPropertyDictionary> from the type's <xref:System.Printing.PrintSystemObject.PropertiesCollection%2A>.</span></span> <span data-ttu-id="aa3a0-110">この辞書内の各エントリの <xref:System.Collections.DictionaryEntry.Value%2A> プロパティは、<xref:System.Printing.IndexedProperties.PrintProperty> から派生したいずれかの型のオブジェクトです。</span><span class="sxs-lookup"><span data-stu-id="aa3a0-110">The <xref:System.Collections.DictionaryEntry.Value%2A> property of each entry in this dictionary is an object of one of the types derived from <xref:System.Printing.IndexedProperties.PrintProperty>.</span></span>  
  
3. <span data-ttu-id="aa3a0-111">辞書のメンバーを列挙します。</span><span class="sxs-lookup"><span data-stu-id="aa3a0-111">Enumerate the members of the dictionary.</span></span> <span data-ttu-id="aa3a0-112">それぞれについて、次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="aa3a0-112">For each of them, do the following.</span></span>  
  
4. <span data-ttu-id="aa3a0-113">各エントリの値をにアップキャスト <xref:System.Printing.IndexedProperties.PrintProperty> し、それを使用してオブジェクトを作成し <xref:System.Printing.IndexedProperties.PrintProperty> ます。</span><span class="sxs-lookup"><span data-stu-id="aa3a0-113">Up-cast the value of each entry to <xref:System.Printing.IndexedProperties.PrintProperty> and use it to create a <xref:System.Printing.IndexedProperties.PrintProperty> object.</span></span>  
  
5. <span data-ttu-id="aa3a0-114">各オブジェクトのの型を取得し <xref:System.Printing.IndexedProperties.PrintProperty.Value%2A> <xref:System.Printing.IndexedProperties.PrintProperty> ます。</span><span class="sxs-lookup"><span data-stu-id="aa3a0-114">Get the type of the <xref:System.Printing.IndexedProperties.PrintProperty.Value%2A> of each of the <xref:System.Printing.IndexedProperties.PrintProperty> object.</span></span>  
  
 [!code-csharp[GetPrintObjectPropertyTypesWithoutReflection#ShowPropertyTypesWithoutReflection](~/samples/snippets/csharp/VS_Snippets_Wpf/GetPrintObjectPropertyTypesWithoutReflection/CSharp/Program.cs#showpropertytypeswithoutreflection)]
 [!code-vb[GetPrintObjectPropertyTypesWithoutReflection#ShowPropertyTypesWithoutReflection](~/samples/snippets/visualbasic/VS_Snippets_Wpf/GetPrintObjectPropertyTypesWithoutReflection/visualbasic/program.vb#showpropertytypeswithoutreflection)]  
  
## <a name="see-also"></a><span data-ttu-id="aa3a0-115">関連項目</span><span class="sxs-lookup"><span data-stu-id="aa3a0-115">See also</span></span>

- <xref:System.Printing.IndexedProperties.PrintProperty>
- <xref:System.Printing.PrintSystemObject>
- <xref:System.Printing.IndexedProperties>
- <xref:System.Printing.IndexedProperties.PrintPropertyDictionary>
- <xref:System.Printing.LocalPrintServer>
- <xref:System.Printing.PrintQueue>
- <xref:System.Collections.DictionaryEntry>
- [<span data-ttu-id="aa3a0-116">WPF のドキュメント</span><span class="sxs-lookup"><span data-stu-id="aa3a0-116">Documents in WPF</span></span>](documents-in-wpf.md)
- [<span data-ttu-id="aa3a0-117">印刷の概要</span><span class="sxs-lookup"><span data-stu-id="aa3a0-117">Printing Overview</span></span>](printing-overview.md)
