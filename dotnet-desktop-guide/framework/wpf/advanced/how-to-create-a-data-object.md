---
title: '方法: データ オブジェクトを作成する'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- DataObject class [WPF], creating
- data objects [WPF], creating
- drag-and-drop [WPF], creating data objects
ms.assetid: 022fa142-717d-4fea-a53c-3b52e9d91aff
ms.openlocfilehash: deae8751518d9322e8d924a1b1fcbc20e25b35ed
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/09/2020
ms.locfileid: "96984708"
---
# <a name="how-to-create-a-data-object"></a><span data-ttu-id="6ba09-102">方法: データ オブジェクトを作成する</span><span class="sxs-lookup"><span data-stu-id="6ba09-102">How to: Create a Data Object</span></span>
<span data-ttu-id="6ba09-103">次の例は、<xref:System.Windows.DataObject> クラスによって提供されるコンストラクターを使用して、データ オブジェクトを作成するさまざまな方法を示しています。</span><span class="sxs-lookup"><span data-stu-id="6ba09-103">The following examples show various ways to create a data object using the constructors provided by the <xref:System.Windows.DataObject> class.</span></span>  
  
## <a name="example"></a><span data-ttu-id="6ba09-104">例</span><span class="sxs-lookup"><span data-stu-id="6ba09-104">Example</span></span>  
  
### <a name="description"></a><span data-ttu-id="6ba09-105">説明</span><span class="sxs-lookup"><span data-stu-id="6ba09-105">Description</span></span>  
 <span data-ttu-id="6ba09-106">次のコード例では、新しいデータ オブジェクトが作成され、オーバーロードされたコンストラクター (<xref:System.Windows.DataObject.%23ctor%28System.Object%29>) の 1 つを使用して、文字列でデータ オブジェクトが初期化されます。</span><span class="sxs-lookup"><span data-stu-id="6ba09-106">The following example code creates a new data object and uses one of the overloaded constructors (<xref:System.Windows.DataObject.%23ctor%28System.Object%29>) to initialize the data object with a string.</span></span>  <span data-ttu-id="6ba09-107">この場合、格納されているデータの型に応じて適切なデータ形式が自動的に決定されます。格納されているデータの自動変換が既定で許可されています。</span><span class="sxs-lookup"><span data-stu-id="6ba09-107">In this case, an appropriate data format is determined automatically according to the stored data's type, and auto-converting of the stored data is allowed by default.</span></span>  
  
### <a name="code"></a><span data-ttu-id="6ba09-108">コード</span><span class="sxs-lookup"><span data-stu-id="6ba09-108">Code</span></span>  
 [!code-csharp[DragDrop_DragDropMiscCode#_DragDrop_CreateDataObject_Simple](~/samples/snippets/csharp/VS_Snippets_Wpf/DragDrop_DragDropMiscCode/CSharp/Window1.xaml.cs#_dragdrop_createdataobject_simple)]
 [!code-vb[DragDrop_DragDropMiscCode#_DragDrop_CreateDataObject_Simple](~/samples/snippets/visualbasic/VS_Snippets_Wpf/DragDrop_DragDropMiscCode/visualbasic/window1.xaml.vb#_dragdrop_createdataobject_simple)]  
  
### <a name="description"></a><span data-ttu-id="6ba09-109">説明</span><span class="sxs-lookup"><span data-stu-id="6ba09-109">Description</span></span>  
 <span data-ttu-id="6ba09-110">次のコード例は、上記のコードの短縮版です。</span><span class="sxs-lookup"><span data-stu-id="6ba09-110">The following example code is a condensed version of the code shown above.</span></span>  
  
### <a name="code"></a><span data-ttu-id="6ba09-111">コード</span><span class="sxs-lookup"><span data-stu-id="6ba09-111">Code</span></span>  
 [!code-csharp[DragDrop_DragDropMiscCode#_DragDrop_CreateDataObject_Simple_Condensed](~/samples/snippets/csharp/VS_Snippets_Wpf/DragDrop_DragDropMiscCode/CSharp/Window1.xaml.cs#_dragdrop_createdataobject_simple_condensed)]
 [!code-vb[DragDrop_DragDropMiscCode#_DragDrop_CreateDataObject_Simple_Condensed](~/samples/snippets/visualbasic/VS_Snippets_Wpf/DragDrop_DragDropMiscCode/visualbasic/window1.xaml.vb#_dragdrop_createdataobject_simple_condensed)]  
  
## <a name="example"></a><span data-ttu-id="6ba09-112">例</span><span class="sxs-lookup"><span data-stu-id="6ba09-112">Example</span></span>  
  
### <a name="description"></a><span data-ttu-id="6ba09-113">説明</span><span class="sxs-lookup"><span data-stu-id="6ba09-113">Description</span></span>  
 <span data-ttu-id="6ba09-114">次のコード例では、新しいデータ オブジェクトが作成され、オーバーロードされたコンストラクター (<xref:System.Windows.DataObject.%23ctor%28System.String%2CSystem.Object%29>) の 1 つを使用して、文字列と指定されたデータ形式でデータ オブジェクトが初期化されます。</span><span class="sxs-lookup"><span data-stu-id="6ba09-114">The following example code creates a new data object and uses one of the overloaded constructors (<xref:System.Windows.DataObject.%23ctor%28System.String%2CSystem.Object%29>) to initialize the data object with a string and a specified data format.</span></span>  <span data-ttu-id="6ba09-115">この場合、データ形式は文字列で指定されます。<xref:System.Windows.DataFormats> クラスによって、事前に定義済みの型の文字列のセットが提供されます。</span><span class="sxs-lookup"><span data-stu-id="6ba09-115">In this case the data format is specified by a string; the <xref:System.Windows.DataFormats> class provides a set of pre-defined type strings.</span></span> <span data-ttu-id="6ba09-116">既定で、格納されているデータの自動変換が許可されています。</span><span class="sxs-lookup"><span data-stu-id="6ba09-116">Auto-converting of the stored data is allowed by default.</span></span>  
  
### <a name="code"></a><span data-ttu-id="6ba09-117">コード</span><span class="sxs-lookup"><span data-stu-id="6ba09-117">Code</span></span>  
 [!code-csharp[DragDrop_DragDropMiscCode#_DragDrop_CreateDataObject_TypeString](~/samples/snippets/csharp/VS_Snippets_Wpf/DragDrop_DragDropMiscCode/CSharp/Window1.xaml.cs#_dragdrop_createdataobject_typestring)]
 [!code-vb[DragDrop_DragDropMiscCode#_DragDrop_CreateDataObject_TypeString](~/samples/snippets/visualbasic/VS_Snippets_Wpf/DragDrop_DragDropMiscCode/visualbasic/window1.xaml.vb#_dragdrop_createdataobject_typestring)]  
  
### <a name="description"></a><span data-ttu-id="6ba09-118">説明</span><span class="sxs-lookup"><span data-stu-id="6ba09-118">Description</span></span>  
 <span data-ttu-id="6ba09-119">次のコード例は、上記のコードの短縮版です。</span><span class="sxs-lookup"><span data-stu-id="6ba09-119">The following example code is a condensed version of the code shown above.</span></span>  
  
### <a name="code"></a><span data-ttu-id="6ba09-120">コード</span><span class="sxs-lookup"><span data-stu-id="6ba09-120">Code</span></span>  
 [!code-csharp[DragDrop_DragDropMiscCode#_DragDrop_CreateDataObject_TypeString_Condensed](~/samples/snippets/csharp/VS_Snippets_Wpf/DragDrop_DragDropMiscCode/CSharp/Window1.xaml.cs#_dragdrop_createdataobject_typestring_condensed)]
 [!code-vb[DragDrop_DragDropMiscCode#_DragDrop_CreateDataObject_TypeString_Condensed](~/samples/snippets/visualbasic/VS_Snippets_Wpf/DragDrop_DragDropMiscCode/visualbasic/window1.xaml.vb#_dragdrop_createdataobject_typestring_condensed)]  
  
## <a name="example"></a><span data-ttu-id="6ba09-121">例</span><span class="sxs-lookup"><span data-stu-id="6ba09-121">Example</span></span>  
  
### <a name="description"></a><span data-ttu-id="6ba09-122">説明</span><span class="sxs-lookup"><span data-stu-id="6ba09-122">Description</span></span>  
 <span data-ttu-id="6ba09-123">次のコード例では、新しいデータ オブジェクトが作成され、オーバーロードされたコンストラクター (<xref:System.Windows.DataObject.%23ctor%2A>) の 1 つを使用して、文字列と指定されたデータ形式でデータ オブジェクトが初期化されます。</span><span class="sxs-lookup"><span data-stu-id="6ba09-123">The following example code creates a new data object and uses one of the overloaded constructors (<xref:System.Windows.DataObject.%23ctor%2A>) to initialize the data object with a string and a specified data format.</span></span>  <span data-ttu-id="6ba09-124">この場合、データ形式は <xref:System.Type> パラメーターによって指定されます。</span><span class="sxs-lookup"><span data-stu-id="6ba09-124">In this case the data format is specified by a <xref:System.Type> parameter.</span></span>  <span data-ttu-id="6ba09-125">既定で、格納されているデータの自動変換が許可されています。</span><span class="sxs-lookup"><span data-stu-id="6ba09-125">Auto-converting of the stored data is allowed by default.</span></span>  
  
### <a name="code"></a><span data-ttu-id="6ba09-126">コード</span><span class="sxs-lookup"><span data-stu-id="6ba09-126">Code</span></span>  
 [!code-csharp[DragDrop_DragDropMiscCode#_DragDrop_CreateDataObject_Type](~/samples/snippets/csharp/VS_Snippets_Wpf/DragDrop_DragDropMiscCode/CSharp/Window1.xaml.cs#_dragdrop_createdataobject_type)]
 [!code-vb[DragDrop_DragDropMiscCode#_DragDrop_CreateDataObject_Type](~/samples/snippets/visualbasic/VS_Snippets_Wpf/DragDrop_DragDropMiscCode/visualbasic/window1.xaml.vb#_dragdrop_createdataobject_type)]  
  
### <a name="description"></a><span data-ttu-id="6ba09-127">説明</span><span class="sxs-lookup"><span data-stu-id="6ba09-127">Description</span></span>  
 <span data-ttu-id="6ba09-128">次のコード例は、上記のコードの短縮版です。</span><span class="sxs-lookup"><span data-stu-id="6ba09-128">The following example code is a condensed version of the code shown above.</span></span>  
  
### <a name="code"></a><span data-ttu-id="6ba09-129">コード</span><span class="sxs-lookup"><span data-stu-id="6ba09-129">Code</span></span>  
 [!code-csharp[DragDrop_DragDropMiscCode#_DragDrop_CreateDataObject_Type_Condensed](~/samples/snippets/csharp/VS_Snippets_Wpf/DragDrop_DragDropMiscCode/CSharp/Window1.xaml.cs#_dragdrop_createdataobject_type_condensed)]
 [!code-vb[DragDrop_DragDropMiscCode#_DragDrop_CreateDataObject_Type_Condensed](~/samples/snippets/visualbasic/VS_Snippets_Wpf/DragDrop_DragDropMiscCode/visualbasic/window1.xaml.vb#_dragdrop_createdataobject_type_condensed)]  
  
## <a name="example"></a><span data-ttu-id="6ba09-130">例</span><span class="sxs-lookup"><span data-stu-id="6ba09-130">Example</span></span>  
  
### <a name="description"></a><span data-ttu-id="6ba09-131">説明</span><span class="sxs-lookup"><span data-stu-id="6ba09-131">Description</span></span>  
 <span data-ttu-id="6ba09-132">次のコード例では、新しいデータ オブジェクトが作成され、オーバーロードされたコンストラクター (<xref:System.Windows.DataObject.%23ctor%28System.String%2CSystem.Object%2CSystem.Boolean%29>) の 1 つを使用して、文字列と指定されたデータ形式でデータ オブジェクトが初期化されます。</span><span class="sxs-lookup"><span data-stu-id="6ba09-132">The following example code creates a new data object and uses one of the overloaded constructors (<xref:System.Windows.DataObject.%23ctor%28System.String%2CSystem.Object%2CSystem.Boolean%29>) to initialize the data object with a string and a specified data format.</span></span>  <span data-ttu-id="6ba09-133">この場合、データ形式は文字列で指定されます。<xref:System.Windows.DataFormats> クラスによって、事前に定義済みの型の文字列のセットが提供されます。</span><span class="sxs-lookup"><span data-stu-id="6ba09-133">In this case the data format is specified by a string; the <xref:System.Windows.DataFormats> class provides a set of pre-defined type strings.</span></span> <span data-ttu-id="6ba09-134">この特定のコンストラクターのオーバーロードによって、呼び出し元で自動変換が許可されるかどうかを指定できるようになります。</span><span class="sxs-lookup"><span data-stu-id="6ba09-134">This particular constructor overload enables the caller to specify whether auto-converting is allowed.</span></span>  
  
### <a name="code"></a><span data-ttu-id="6ba09-135">コード</span><span class="sxs-lookup"><span data-stu-id="6ba09-135">Code</span></span>  
 [!code-csharp[DragDrop_DragDropMiscCode#_DragDrop_CreateDataObject_AutoConvert](~/samples/snippets/csharp/VS_Snippets_Wpf/DragDrop_DragDropMiscCode/CSharp/Window1.xaml.cs#_dragdrop_createdataobject_autoconvert)]
 [!code-vb[DragDrop_DragDropMiscCode#_DragDrop_CreateDataObject_AutoConvert](~/samples/snippets/visualbasic/VS_Snippets_Wpf/DragDrop_DragDropMiscCode/visualbasic/window1.xaml.vb#_dragdrop_createdataobject_autoconvert)]  
  
### <a name="description"></a><span data-ttu-id="6ba09-136">説明</span><span class="sxs-lookup"><span data-stu-id="6ba09-136">Description</span></span>  
 <span data-ttu-id="6ba09-137">次のコード例は、上記のコードの短縮版です。</span><span class="sxs-lookup"><span data-stu-id="6ba09-137">The following example code is a condensed version of the code shown above.</span></span>  
  
### <a name="code"></a><span data-ttu-id="6ba09-138">コード</span><span class="sxs-lookup"><span data-stu-id="6ba09-138">Code</span></span>  
 [!code-csharp[DragDrop_DragDropMiscCode#_DragDrop_CreateDataObject_AutoConvert_Condensed](~/samples/snippets/csharp/VS_Snippets_Wpf/DragDrop_DragDropMiscCode/CSharp/Window1.xaml.cs#_dragdrop_createdataobject_autoconvert_condensed)]
 [!code-vb[DragDrop_DragDropMiscCode#_DragDrop_CreateDataObject_AutoConvert_Condensed](~/samples/snippets/visualbasic/VS_Snippets_Wpf/DragDrop_DragDropMiscCode/visualbasic/window1.xaml.vb#_dragdrop_createdataobject_autoconvert_condensed)]  
  
## <a name="see-also"></a><span data-ttu-id="6ba09-139">関連項目</span><span class="sxs-lookup"><span data-stu-id="6ba09-139">See also</span></span>

- <xref:System.Windows.IDataObject>
