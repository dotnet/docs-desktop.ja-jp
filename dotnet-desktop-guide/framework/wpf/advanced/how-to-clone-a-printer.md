---
title: '方法: プリンターを複製する'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- print queues [WPF]
- cloning printers [WPF]
- printers [WPF], cloning
- print queues [WPF], cloning
- cloning print queues [WPF]
ms.assetid: dd6997c9-fe04-40f8-88a6-92e3ac0889eb
ms.openlocfilehash: e6af8d6410c4e383990bdaa27f97cc698be71719
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/09/2020
ms.locfileid: "96983387"
---
# <a name="how-to-clone-a-printer"></a><span data-ttu-id="7d184-102">方法: プリンターを複製する</span><span class="sxs-lookup"><span data-stu-id="7d184-102">How to: Clone a Printer</span></span>
<span data-ttu-id="7d184-103">ほとんどの企業は、ある時点で同じモデルのプリンターを複数購入します。</span><span class="sxs-lookup"><span data-stu-id="7d184-103">Most businesses will, at some point, buy multiple printers of the same model.</span></span> <span data-ttu-id="7d184-104">通常、これらはすべて、ほぼ同一の構成設定でインストールされます。</span><span class="sxs-lookup"><span data-stu-id="7d184-104">Typically, these are all installed with virtually identical configuration settings.</span></span> <span data-ttu-id="7d184-105">各プリンターのインストールには時間がかかり、エラーが発生しやすくなります。</span><span class="sxs-lookup"><span data-stu-id="7d184-105">Installing each printer can be time-consuming and error prone.</span></span> <span data-ttu-id="7d184-106"><xref:System.Printing.IndexedProperties?displayProperty=nameWithType> 名前空間と、Microsoft .NET Framework で公開されている <xref:System.Printing.PrintServer.InstallPrintQueue%2A> クラスを使用すると、既存の印刷キューから複製された任意の数の追加の印刷キューをすぐにインストールすることができます。</span><span class="sxs-lookup"><span data-stu-id="7d184-106">The <xref:System.Printing.IndexedProperties?displayProperty=nameWithType> namespace and the <xref:System.Printing.PrintServer.InstallPrintQueue%2A> class that are exposed with Microsoft .NET Framework makes it possible to instantly install any number of additional print queues that are cloned from an existing print queue.</span></span>  
  
## <a name="example"></a><span data-ttu-id="7d184-107">例</span><span class="sxs-lookup"><span data-stu-id="7d184-107">Example</span></span>  
 <span data-ttu-id="7d184-108">次の例では、2 番目の印刷キューが既存の印刷キューから複製されています。</span><span class="sxs-lookup"><span data-stu-id="7d184-108">In the example below, a second print queue is cloned from an existing print queue.</span></span> <span data-ttu-id="7d184-109">2 番目と最初の違いは、名前、場所、ポート、および共有状態のみです。</span><span class="sxs-lookup"><span data-stu-id="7d184-109">The second differs from the first only in its name, location, port, and shared status.</span></span> <span data-ttu-id="7d184-110">これを行うための主な手順は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="7d184-110">The major steps for doing this are as follows.</span></span>  
  
1. <span data-ttu-id="7d184-111">複製する既存のプリンターの <xref:System.Printing.PrintQueue> オブジェクトを作成します。</span><span class="sxs-lookup"><span data-stu-id="7d184-111">Create a <xref:System.Printing.PrintQueue> object for the existing printer that is going to be cloned.</span></span>  
  
2. <span data-ttu-id="7d184-112"><xref:System.Printing.PrintQueue> の <xref:System.Printing.PrintSystemObject.PropertiesCollection%2A> から <xref:System.Printing.IndexedProperties.PrintPropertyDictionary> を作成します。</span><span class="sxs-lookup"><span data-stu-id="7d184-112">Create a <xref:System.Printing.IndexedProperties.PrintPropertyDictionary> from the <xref:System.Printing.PrintSystemObject.PropertiesCollection%2A> of the <xref:System.Printing.PrintQueue>.</span></span> <span data-ttu-id="7d184-113">この辞書内の各エントリの <xref:System.Collections.DictionaryEntry.Value%2A> プロパティは、<xref:System.Printing.IndexedProperties.PrintProperty> から派生したいずれかの型のオブジェクトです。</span><span class="sxs-lookup"><span data-stu-id="7d184-113">The <xref:System.Collections.DictionaryEntry.Value%2A> property of each entry in this dictionary is an object of one of the types derived from <xref:System.Printing.IndexedProperties.PrintProperty>.</span></span> <span data-ttu-id="7d184-114">この辞書内のエントリの値を設定するには、2 つの方法があります。</span><span class="sxs-lookup"><span data-stu-id="7d184-114">There are two ways to set the value of an entry in this dictionary.</span></span>  
  
    - <span data-ttu-id="7d184-115">辞書の **Remove** と <xref:System.Printing.IndexedProperties.PrintPropertyDictionary.Add%2A> メソッドを使用してエントリを削除し、目的の値で再度追加します。</span><span class="sxs-lookup"><span data-stu-id="7d184-115">Use the dictionary's **Remove** and <xref:System.Printing.IndexedProperties.PrintPropertyDictionary.Add%2A> methods to remove the entry and then re-add it with the desired value.</span></span>  
  
    - <span data-ttu-id="7d184-116">辞書の <xref:System.Printing.IndexedProperties.PrintPropertyDictionary.SetProperty%2A> メソッドを使用します。</span><span class="sxs-lookup"><span data-stu-id="7d184-116">Use the dictionary's <xref:System.Printing.IndexedProperties.PrintPropertyDictionary.SetProperty%2A> method.</span></span>  
  
     <span data-ttu-id="7d184-117">次の例では、両方の方法を示しています。</span><span class="sxs-lookup"><span data-stu-id="7d184-117">The example below illustrates both ways.</span></span>  
  
3. <span data-ttu-id="7d184-118"><xref:System.Printing.IndexedProperties.PrintBooleanProperty> オブジェクトを作成し、その <xref:System.Printing.IndexedProperties.PrintProperty.Name%2A> を "IsShared" に、またその <xref:System.Printing.IndexedProperties.PrintBooleanProperty.Value%2A> を `true` に設定します。</span><span class="sxs-lookup"><span data-stu-id="7d184-118">Create a <xref:System.Printing.IndexedProperties.PrintBooleanProperty> object and set its <xref:System.Printing.IndexedProperties.PrintProperty.Name%2A> to "IsShared" and its <xref:System.Printing.IndexedProperties.PrintBooleanProperty.Value%2A> to `true`.</span></span>  
  
4. <span data-ttu-id="7d184-119"><xref:System.Printing.IndexedProperties.PrintBooleanProperty> オブジェクトを使用して、<xref:System.Printing.IndexedProperties.PrintPropertyDictionary> の "IsShared" エントリの値にします。</span><span class="sxs-lookup"><span data-stu-id="7d184-119">Use the <xref:System.Printing.IndexedProperties.PrintBooleanProperty> object to be the value of the <xref:System.Printing.IndexedProperties.PrintPropertyDictionary>'s "IsShared" entry.</span></span>  
  
5. <span data-ttu-id="7d184-120"><xref:System.Printing.IndexedProperties.PrintStringProperty> オブジェクトを作成し、その <xref:System.Printing.IndexedProperties.PrintProperty.Name%2A> を "ShareName" に、またその <xref:System.Printing.IndexedProperties.PrintStringProperty.Value%2A> を適切な <xref:System.String> に設定します。</span><span class="sxs-lookup"><span data-stu-id="7d184-120">Create a <xref:System.Printing.IndexedProperties.PrintStringProperty> object and set its <xref:System.Printing.IndexedProperties.PrintProperty.Name%2A> to "ShareName" and its <xref:System.Printing.IndexedProperties.PrintStringProperty.Value%2A> to an appropriate <xref:System.String>.</span></span>  
  
6. <span data-ttu-id="7d184-121"><xref:System.Printing.IndexedProperties.PrintStringProperty> オブジェクトを使用して、<xref:System.Printing.IndexedProperties.PrintPropertyDictionary> の "ShareName" エントリの値にします。</span><span class="sxs-lookup"><span data-stu-id="7d184-121">Use the <xref:System.Printing.IndexedProperties.PrintStringProperty> object to be the value of the <xref:System.Printing.IndexedProperties.PrintPropertyDictionary>'s "ShareName" entry.</span></span>  
  
7. <span data-ttu-id="7d184-122">別の <xref:System.Printing.IndexedProperties.PrintStringProperty> オブジェクトを作成し、その <xref:System.Printing.IndexedProperties.PrintProperty.Name%2A> を "Location" に、またその <xref:System.Printing.IndexedProperties.PrintStringProperty.Value%2A> を適切な <xref:System.String> に設定します。</span><span class="sxs-lookup"><span data-stu-id="7d184-122">Create another <xref:System.Printing.IndexedProperties.PrintStringProperty> object and set its <xref:System.Printing.IndexedProperties.PrintProperty.Name%2A> to "Location" and its <xref:System.Printing.IndexedProperties.PrintStringProperty.Value%2A> to an appropriate <xref:System.String>.</span></span>  
  
8. <span data-ttu-id="7d184-123">2 番目の <xref:System.Printing.IndexedProperties.PrintStringProperty> オブジェクトを使用して、<xref:System.Printing.IndexedProperties.PrintPropertyDictionary> の "Location" エントリの値にします。</span><span class="sxs-lookup"><span data-stu-id="7d184-123">Use the second <xref:System.Printing.IndexedProperties.PrintStringProperty> object to be the value of the <xref:System.Printing.IndexedProperties.PrintPropertyDictionary>'s "Location" entry.</span></span>  
  
9. <span data-ttu-id="7d184-124"><xref:System.String> の配列を作成します。</span><span class="sxs-lookup"><span data-stu-id="7d184-124">Create an array of <xref:System.String>s.</span></span> <span data-ttu-id="7d184-125">各項目は、サーバー上のポートの名前です。</span><span class="sxs-lookup"><span data-stu-id="7d184-125">Each item is the name of a port on the server.</span></span>  
  
10. <span data-ttu-id="7d184-126"><xref:System.Printing.PrintServer.InstallPrintQueue%2A> を使用して、新しいプリンターを新しい値を使用してインストールします。</span><span class="sxs-lookup"><span data-stu-id="7d184-126">Use <xref:System.Printing.PrintServer.InstallPrintQueue%2A> to install the new printer with the new values.</span></span>  
  
 <span data-ttu-id="7d184-127">次に例を示します。</span><span class="sxs-lookup"><span data-stu-id="7d184-127">An example is below.</span></span>  
  
 [!code-csharp[ClonePrinter#ClonePrinter](~/samples/snippets/csharp/VS_Snippets_Wpf/ClonePrinter/CSharp/Program.cs#cloneprinter)]
 [!code-vb[ClonePrinter#ClonePrinter](~/samples/snippets/visualbasic/VS_Snippets_Wpf/ClonePrinter/visualbasic/program.vb#cloneprinter)]  
  
## <a name="see-also"></a><span data-ttu-id="7d184-128">関連項目</span><span class="sxs-lookup"><span data-stu-id="7d184-128">See also</span></span>

- <xref:System.Printing.IndexedProperties>
- <xref:System.Printing.IndexedProperties.PrintPropertyDictionary>
- <xref:System.Printing.LocalPrintServer>
- <xref:System.Printing.PrintQueue>
- <xref:System.Collections.DictionaryEntry>
- [<span data-ttu-id="7d184-129">WPF のドキュメント</span><span class="sxs-lookup"><span data-stu-id="7d184-129">Documents in WPF</span></span>](documents-in-wpf.md)
- [<span data-ttu-id="7d184-130">印刷の概要</span><span class="sxs-lookup"><span data-stu-id="7d184-130">Printing Overview</span></span>](printing-overview.md)
