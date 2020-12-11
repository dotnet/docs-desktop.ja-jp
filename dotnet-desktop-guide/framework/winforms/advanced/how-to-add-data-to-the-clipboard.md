---
title: '方法: クリップボードにデータを追加する'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- Clipboard [Windows Forms], copying data to
- data [Windows Forms], copying to Clipboard
ms.assetid: 25152454-0e78-40a9-8a9e-a2a5a274e517
ms.openlocfilehash: 0d9b82f01080d18353ecb91578a8005260bbe739
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/09/2020
ms.locfileid: "96974432"
---
# <a name="how-to-add-data-to-the-clipboard"></a><span data-ttu-id="68e7b-102">方法: クリップボードにデータを追加する</span><span class="sxs-lookup"><span data-stu-id="68e7b-102">How to: Add Data to the Clipboard</span></span>

<span data-ttu-id="68e7b-103">クラスには、 <xref:System.Windows.Forms.Clipboard> Windows オペレーティングシステムのクリップボード機能との対話に使用できるメソッドが用意されています。</span><span class="sxs-lookup"><span data-stu-id="68e7b-103">The <xref:System.Windows.Forms.Clipboard> class provides methods that you can use to interact with the Windows operating system Clipboard feature.</span></span> <span data-ttu-id="68e7b-104">多くのアプリケーションでは、データの一時リポジトリとしてクリップボードを使用します。</span><span class="sxs-lookup"><span data-stu-id="68e7b-104">Many applications use the Clipboard as a temporary repository for data.</span></span> <span data-ttu-id="68e7b-105">たとえば、ワードプロセッサは、切り取りと貼り付けの操作中にクリップボードを使用します。</span><span class="sxs-lookup"><span data-stu-id="68e7b-105">For example, word processors use the Clipboard during cut-and-paste operations.</span></span> <span data-ttu-id="68e7b-106">クリップボードは、あるアプリケーションから別のアプリケーションにデータを転送する場合にも役立ちます。</span><span class="sxs-lookup"><span data-stu-id="68e7b-106">The Clipboard is also useful for transferring data from one application to another.</span></span>

<span data-ttu-id="68e7b-107">クリップボードにデータを追加すると、他のアプリケーションがその形式を使用できる場合にデータを認識できるように、データ形式を指定できます。</span><span class="sxs-lookup"><span data-stu-id="68e7b-107">When you add data to the Clipboard, you can indicate the data format so that other applications can recognize the data if they can use that format.</span></span> <span data-ttu-id="68e7b-108">また、データを複数の異なる形式でクリップボードに追加して、データを使用する可能性がある他のアプリケーションの数を増やすこともできます。</span><span class="sxs-lookup"><span data-stu-id="68e7b-108">You can also add data to the Clipboard in multiple different formats to increase the number of other applications that can potentially use the data.</span></span>

<span data-ttu-id="68e7b-109">クリップボード形式は、その形式を使用するアプリケーションが関連データを取得できるように、形式を識別する文字列です。</span><span class="sxs-lookup"><span data-stu-id="68e7b-109">A Clipboard format is a string that identifies the format so that an application that uses that format can retrieve the associated data.</span></span> <span data-ttu-id="68e7b-110">クラスには、 <xref:System.Windows.Forms.DataFormats> 使用するための定義済みの形式名が用意されています。</span><span class="sxs-lookup"><span data-stu-id="68e7b-110">The <xref:System.Windows.Forms.DataFormats> class provides predefined format names for your use.</span></span> <span data-ttu-id="68e7b-111">独自の形式名を使用することも、形式としてオブジェクトの型を使用することもできます。</span><span class="sxs-lookup"><span data-stu-id="68e7b-111">You can also use your own format names or use the type of an object as its format.</span></span>

<span data-ttu-id="68e7b-112">1つまたは複数の形式でクリップボードにデータを追加するには、メソッドを使用し <xref:System.Windows.Forms.Clipboard.SetDataObject%2A> ます。</span><span class="sxs-lookup"><span data-stu-id="68e7b-112">To add data to the Clipboard in one or multiple formats, use the <xref:System.Windows.Forms.Clipboard.SetDataObject%2A> method.</span></span> <span data-ttu-id="68e7b-113">このメソッドには任意のオブジェクトを渡すことができますが、複数の形式でデータを追加するには、まず、複数の形式を使用するように設計された別のオブジェクトにデータを追加する必要があります。</span><span class="sxs-lookup"><span data-stu-id="68e7b-113">You can pass any object to this method, but to add data in multiple formats, you must first add the data to a separate object designed to work with multiple formats.</span></span> <span data-ttu-id="68e7b-114">通常は、にデータを追加します <xref:System.Windows.Forms.DataObject> が、インターフェイスを実装する任意の型を使用でき <xref:System.Windows.Forms.IDataObject> ます。</span><span class="sxs-lookup"><span data-stu-id="68e7b-114">Typically, you will add your data to a <xref:System.Windows.Forms.DataObject>, but you can use any type that implements the <xref:System.Windows.Forms.IDataObject> interface.</span></span>

<span data-ttu-id="68e7b-115">.NET Framework 2.0 では、基本的なクリップボードタスクを簡単にするために設計された新しいメソッドを使用して、クリップボードに直接データを追加できます。</span><span class="sxs-lookup"><span data-stu-id="68e7b-115">In .NET Framework 2.0, you can add data directly to the Clipboard by using new methods designed to make basic Clipboard tasks easier.</span></span> <span data-ttu-id="68e7b-116">テキストなどの1つの一般的な形式でデータを操作する場合は、これらのメソッドを使用します。</span><span class="sxs-lookup"><span data-stu-id="68e7b-116">Use these methods when you work with data in a single, common format such as text.</span></span>

> [!NOTE]
> <span data-ttu-id="68e7b-117">すべての Windows ベースのアプリケーションは、クリップボードを共有します。</span><span class="sxs-lookup"><span data-stu-id="68e7b-117">All Windows-based applications share the Clipboard.</span></span> <span data-ttu-id="68e7b-118">そのため、別のアプリケーションに切り替えると、コンテンツが変更される可能性があります。</span><span class="sxs-lookup"><span data-stu-id="68e7b-118">Therefore, the contents are subject to change when you switch to another application.</span></span>
>
> <span data-ttu-id="68e7b-119">クラスは、 <xref:System.Windows.Forms.Clipboard> シングルスレッドアパートメント (STA) モードに設定されているスレッドでのみ使用できます。</span><span class="sxs-lookup"><span data-stu-id="68e7b-119">The <xref:System.Windows.Forms.Clipboard> class can only be used in threads set to single thread apartment (STA) mode.</span></span> <span data-ttu-id="68e7b-120">このクラスを使用するには、 `Main` メソッドが属性でマークされていることを確認し <xref:System.STAThreadAttribute> ます。</span><span class="sxs-lookup"><span data-stu-id="68e7b-120">To use this class, ensure that your `Main` method is marked with the <xref:System.STAThreadAttribute> attribute.</span></span>
>
> <span data-ttu-id="68e7b-121">オブジェクトをクリップボードに格納するには、オブジェクトをシリアル化できる必要があります。</span><span class="sxs-lookup"><span data-stu-id="68e7b-121">An object must be serializable for it to be put on the Clipboard.</span></span> <span data-ttu-id="68e7b-122">型をシリアル化できるようにするには、属性を使用してマークし <xref:System.SerializableAttribute> ます。</span><span class="sxs-lookup"><span data-stu-id="68e7b-122">To make a type serializable, mark it with the <xref:System.SerializableAttribute> attribute.</span></span> <span data-ttu-id="68e7b-123">シリアル化できないオブジェクトをクリップボードメソッドに渡すと、メソッドは例外をスローせずに失敗します。</span><span class="sxs-lookup"><span data-stu-id="68e7b-123">If you pass a non-serializable object to a Clipboard method, the method will fail without throwing an exception.</span></span> <span data-ttu-id="68e7b-124">シリアル化の詳細については、「<xref:System.Runtime.Serialization>」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="68e7b-124">For more information about serialization, see <xref:System.Runtime.Serialization>.</span></span>

### <a name="to-add-data-to-the-clipboard-in-a-single-common-format"></a><span data-ttu-id="68e7b-125">1つの一般的な形式でクリップボードにデータを追加するには</span><span class="sxs-lookup"><span data-stu-id="68e7b-125">To add data to the Clipboard in a single, common format</span></span>

1. <span data-ttu-id="68e7b-126">、、 <xref:System.Windows.Forms.Clipboard.SetAudio%2A> <xref:System.Windows.Forms.Clipboard.SetFileDropList%2A> <xref:System.Windows.Forms.Clipboard.SetImage%2A> 、またはメソッドを使用し <xref:System.Windows.Forms.Clipboard.SetText%2A> ます。</span><span class="sxs-lookup"><span data-stu-id="68e7b-126">Use the <xref:System.Windows.Forms.Clipboard.SetAudio%2A>, <xref:System.Windows.Forms.Clipboard.SetFileDropList%2A>, <xref:System.Windows.Forms.Clipboard.SetImage%2A>, or <xref:System.Windows.Forms.Clipboard.SetText%2A> method.</span></span> <span data-ttu-id="68e7b-127">これらのメソッドは、.NET Framework 2.0 でのみ使用できます。</span><span class="sxs-lookup"><span data-stu-id="68e7b-127">These methods are available only in .NET Framework 2.0.</span></span>

    [!code-csharp[System.Windows.Forms.Clipboard#2](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Clipboard/CS/form1.cs#2)]
    [!code-vb[System.Windows.Forms.Clipboard#2](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Clipboard/vb/form1.vb#2)]

### <a name="to-add-data-to-the-clipboard-in-a-custom-format"></a><span data-ttu-id="68e7b-128">カスタム形式でクリップボードにデータを追加するには</span><span class="sxs-lookup"><span data-stu-id="68e7b-128">To add data to the Clipboard in a custom format</span></span>

1. <span data-ttu-id="68e7b-129"><xref:System.Windows.Forms.Clipboard.SetData%2A>カスタム書式名を使用して、メソッドを使用します。</span><span class="sxs-lookup"><span data-stu-id="68e7b-129">Use the <xref:System.Windows.Forms.Clipboard.SetData%2A> method with a custom format name.</span></span> <span data-ttu-id="68e7b-130">このメソッドは、.NET Framework 2.0 でのみ使用できます。</span><span class="sxs-lookup"><span data-stu-id="68e7b-130">This method is available only in .NET Framework 2.0.</span></span>

    <span data-ttu-id="68e7b-131">メソッドでは、定義済みの書式名を使用することもでき <xref:System.Windows.Forms.Clipboard.SetData%2A> ます。</span><span class="sxs-lookup"><span data-stu-id="68e7b-131">You can also use predefined format names with the <xref:System.Windows.Forms.Clipboard.SetData%2A> method.</span></span> <span data-ttu-id="68e7b-132">詳細については、「<xref:System.Windows.Forms.DataFormats>」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="68e7b-132">For more information, see <xref:System.Windows.Forms.DataFormats>.</span></span>

    [!code-csharp[System.Windows.Forms.Clipboard#3](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Clipboard/CS/form1.cs#3)]
    [!code-vb[System.Windows.Forms.Clipboard#3](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Clipboard/vb/form1.vb#3)]
    [!code-csharp[System.Windows.Forms.Clipboard#100](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Clipboard/CS/form1.cs#100)]
    [!code-vb[System.Windows.Forms.Clipboard#100](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Clipboard/vb/form1.vb#100)]

### <a name="to-add-data-to-the-clipboard-in-multiple-formats"></a><span data-ttu-id="68e7b-133">複数の形式でクリップボードにデータを追加するには</span><span class="sxs-lookup"><span data-stu-id="68e7b-133">To add data to the Clipboard in multiple formats</span></span>

1. <span data-ttu-id="68e7b-134">メソッドを使用 <xref:System.Windows.Forms.Clipboard.SetDataObject%2A?displayProperty=nameWithType> し、 <xref:System.Windows.Forms.DataObject> データが格納されているを渡します。</span><span class="sxs-lookup"><span data-stu-id="68e7b-134">Use the <xref:System.Windows.Forms.Clipboard.SetDataObject%2A?displayProperty=nameWithType> method and pass in a <xref:System.Windows.Forms.DataObject> that contains your data.</span></span> <span data-ttu-id="68e7b-135">.NET Framework 2.0 より前のバージョンのクリップボードにデータを追加するには、このメソッドを使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="68e7b-135">You must use this method to add data to the Clipboard on versions earlier than .NET Framework 2.0.</span></span>

    [!code-csharp[System.Windows.Forms.Clipboard#4](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Clipboard/CS/form1.cs#4)]
    [!code-vb[System.Windows.Forms.Clipboard#4](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Clipboard/vb/form1.vb#4)]
    [!code-csharp[System.Windows.Forms.Clipboard#100](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Clipboard/CS/form1.cs#100)]
    [!code-vb[System.Windows.Forms.Clipboard#100](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Clipboard/vb/form1.vb#100)]

## <a name="see-also"></a><span data-ttu-id="68e7b-136">関連項目</span><span class="sxs-lookup"><span data-stu-id="68e7b-136">See also</span></span>

- [<span data-ttu-id="68e7b-137">ドラッグ アンド ドロップ操作とクリップボードのサポート</span><span class="sxs-lookup"><span data-stu-id="68e7b-137">Drag-and-Drop Operations and Clipboard Support</span></span>](drag-and-drop-operations-and-clipboard-support.md)
- [<span data-ttu-id="68e7b-138">方法: クリップボードからデータを取得する</span><span class="sxs-lookup"><span data-stu-id="68e7b-138">How to: Retrieve Data from the Clipboard</span></span>](how-to-retrieve-data-from-the-clipboard.md)
