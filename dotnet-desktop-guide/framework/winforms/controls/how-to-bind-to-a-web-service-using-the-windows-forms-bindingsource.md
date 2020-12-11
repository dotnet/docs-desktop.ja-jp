---
title: BindingSource を使用して Web サービスにバインドする
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- Web services [Windows Forms], binding controls
- BindingSource component [Windows Forms], binding to a Web service
- examples [Windows Forms], BindingSource component
- controls [Windows Forms], binding to Web service
- BindingSource component [Windows Forms], examples
ms.assetid: ee261207-4573-4cb9-a8cb-5185037e0fba
ms.openlocfilehash: 0680c73e578577cf40158761f6c635fe30ff9f4d
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/09/2020
ms.locfileid: "96980931"
---
# <a name="how-to-bind-to-a-web-service-using-the-windows-forms-bindingsource"></a><span data-ttu-id="d282c-102">方法: Windows フォーム BindingSource を使用して Web サービスにバインドする</span><span class="sxs-lookup"><span data-stu-id="d282c-102">How to: Bind to a Web Service Using the Windows Forms BindingSource</span></span>
<span data-ttu-id="d282c-103">XML Web サービスを呼び出して取得した結果に対して Windows フォーム コントロールをバインドする場合は、<xref:System.Windows.Forms.BindingSource> コンポーネントを使用します。</span><span class="sxs-lookup"><span data-stu-id="d282c-103">If you want to bind a Windows Form control to the results obtained from calling an XML Web service, you can use a <xref:System.Windows.Forms.BindingSource> component.</span></span> <span data-ttu-id="d282c-104">この手順は、<xref:System.Windows.Forms.BindingSource> コンポーネントを型にバインディングする場合と似ています。</span><span class="sxs-lookup"><span data-stu-id="d282c-104">This procedure is similar to binding a <xref:System.Windows.Forms.BindingSource> component to a type.</span></span> <span data-ttu-id="d282c-105">Web サービスが公開するメソッドおよび型を含むクライアント側プロキシを作成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="d282c-105">You must create a client-side proxy that contains the methods and types exposed by the Web service.</span></span> <span data-ttu-id="d282c-106">クライアント側プロキシは、Web サービス (.asmx) 自体またはその Web サービス記述言語 (WSDL: Web Services Description Language) ファイルから生成できます。</span><span class="sxs-lookup"><span data-stu-id="d282c-106">You generate a client-side proxy from the Web service (.asmx) itself, or its Web Services Description Language (WSDL) file.</span></span> <span data-ttu-id="d282c-107">また、クライアント側プロキシでは Web サービスが使用する複合型のフィールドをパブリック プロパティとして公開する必要があります。</span><span class="sxs-lookup"><span data-stu-id="d282c-107">Additionally, your client-side proxy must expose the fields of complex types used by the Web service as public properties.</span></span> <span data-ttu-id="d282c-108">その後、Web サービス プロキシ内で公開された型のいずれかに <xref:System.Windows.Forms.BindingSource> をバインドします。</span><span class="sxs-lookup"><span data-stu-id="d282c-108">You then bind the <xref:System.Windows.Forms.BindingSource> to one of the types exposed in the Web service proxy.</span></span>  
  
### <a name="to-create-and-bind-to-a-client-side-proxy"></a><span data-ttu-id="d282c-109">クライアント側プロキシを作成してバインドするには</span><span class="sxs-lookup"><span data-stu-id="d282c-109">To create and bind to a client-side proxy</span></span>  
  
1. <span data-ttu-id="d282c-110">適切な名前空間を使用して、任意のディレクトリに Windows フォームを作成します。</span><span class="sxs-lookup"><span data-stu-id="d282c-110">Create a Windows Form in the directory of your choice, with an appropriate namespace.</span></span>  
  
2. <span data-ttu-id="d282c-111">フォームに <xref:System.Windows.Forms.BindingSource> コンポーネントを追加します。</span><span class="sxs-lookup"><span data-stu-id="d282c-111">Add a <xref:System.Windows.Forms.BindingSource> component to the form.</span></span>  
  
3. <span data-ttu-id="d282c-112">Windows Software Development Kit (SDK) コマンドプロンプトを開き、フォームが配置されているディレクトリに移動します。</span><span class="sxs-lookup"><span data-stu-id="d282c-112">Open the Windows Software Development Kit (SDK) command prompt, and navigate to the same directory that your form is located in.</span></span>  
  
4. <span data-ttu-id="d282c-113">WSDL ツールを使用して、`wsdl`、および Web サービスの .asmx ファイルまたは WSDL ファイルの URL を入力し、次にアプリケーションの名前空間を入力し、使用している言語 (これはオプション) を入力します。</span><span class="sxs-lookup"><span data-stu-id="d282c-113">Using the WSDL tool, enter `wsdl` and the URL for the .asmx or WSDL file for the Web service, followed by the namespace of your application, and optionally the language you are working in.</span></span>  
  
     <span data-ttu-id="d282c-114">次のコード例では、にある Web サービスを使用し `http://webservices.eraserver.net/zipcoderesolver/zipcoderesolver.asmx` ます。</span><span class="sxs-lookup"><span data-stu-id="d282c-114">The following code example uses the Web service located at `http://webservices.eraserver.net/zipcoderesolver/zipcoderesolver.asmx`.</span></span> <span data-ttu-id="d282c-115">たとえば、C# の型の場合は `wsdl http://webservices.eraserver.net.zipcoderesolver/zipcoderesolver.asmx /n:BindToWebService`、Visual Basic の型の場合は `wsdl http://webservices.eraserver.net.zipcoderesolver/zipcoderesolver.asmx /n:BindToWebService /language:VB` です。</span><span class="sxs-lookup"><span data-stu-id="d282c-115">For example, for C# type `wsdl http://webservices.eraserver.net.zipcoderesolver/zipcoderesolver.asmx /n:BindToWebService`, or for Visual Basic type `wsdl http://webservices.eraserver.net.zipcoderesolver/zipcoderesolver.asmx /n:BindToWebService /language:VB`.</span></span> <span data-ttu-id="d282c-116">パスを引数として WSDL ツールに渡すことで、指定した言語で、アプリケーションと同じディレクトリおよび名前空間にクライアント側プロキシが生成されます。</span><span class="sxs-lookup"><span data-stu-id="d282c-116">Passing the path as an argument to the WSDL tool will generate a client-side proxy in the same directory and namespace as your application, in the specified language.</span></span> <span data-ttu-id="d282c-117">Visual Studio を使用している場合は、ファイルをプロジェクトに追加します。</span><span class="sxs-lookup"><span data-stu-id="d282c-117">If you are using Visual Studio, add the file to your project.</span></span>  
  
5. <span data-ttu-id="d282c-118">バインド先のクライアント側プロキシの型を選択します。</span><span class="sxs-lookup"><span data-stu-id="d282c-118">Select a type in the client-side proxy to bind to.</span></span>  
  
     <span data-ttu-id="d282c-119">これは、通常、Web サービスによって提供されるメソッドが返す型です。</span><span class="sxs-lookup"><span data-stu-id="d282c-119">This is typically a type returned by a method offered by the Web service.</span></span> <span data-ttu-id="d282c-120">選択した型のフィールドは、バインド用にパブリック プロパティとして公開する必要があります。</span><span class="sxs-lookup"><span data-stu-id="d282c-120">The fields of the chosen type must be exposed as public properties for binding purposes.</span></span>  
  
     [!code-cpp[System.Windows.Forms.DataConnectorWebService#4](~/samples/snippets/cpp/VS_Snippets_Winforms/System.Windows.Forms.DataConnectorWebService/CPP/form1.cpp#4)]
     [!code-csharp[System.Windows.Forms.DataConnectorWebService#4](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataConnectorWebService/CS/form1.cs#4)]
     [!code-vb[System.Windows.Forms.DataConnectorWebService#4](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataConnectorWebService/VB/form1.vb#4)]  
  
6. <span data-ttu-id="d282c-121"><xref:System.Windows.Forms.BindingSource> の <xref:System.Windows.Forms.BindingSource.DataSource%2A> プロパティに、Web サービスのクライアント側プロキシに含まれる任意の型を設定します。</span><span class="sxs-lookup"><span data-stu-id="d282c-121">Set the <xref:System.Windows.Forms.BindingSource.DataSource%2A> property of the <xref:System.Windows.Forms.BindingSource> to the type you want that is contained in the Web service client-side proxy.</span></span>  
  
     [!code-cpp[System.Windows.Forms.DataConnectorWebService#2](~/samples/snippets/cpp/VS_Snippets_Winforms/System.Windows.Forms.DataConnectorWebService/CPP/form1.cpp#2)]
     [!code-csharp[System.Windows.Forms.DataConnectorWebService#2](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataConnectorWebService/CS/form1.cs#2)]
     [!code-vb[System.Windows.Forms.DataConnectorWebService#2](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataConnectorWebService/VB/form1.vb#2)]  
  
### <a name="to-bind-controls-to-the-bindingsource-that-is-bound-to-a-web-service"></a><span data-ttu-id="d282c-122">Web サービスにバインドされた BindingSource にコントロールをバインドするには</span><span class="sxs-lookup"><span data-stu-id="d282c-122">To bind controls to the BindingSource that is bound to a Web service</span></span>  
  
- <span data-ttu-id="d282c-123">コントロールを <xref:System.Windows.Forms.BindingSource> にバインドし、Web サービスの任意の型のパブリック プロパティをパラメーターとして渡します。</span><span class="sxs-lookup"><span data-stu-id="d282c-123">Bind controls to the <xref:System.Windows.Forms.BindingSource>, passing the public property of the Web service type that you want as a parameter.</span></span>  
  
     [!code-cpp[System.Windows.Forms.DataConnectorWebService#3](~/samples/snippets/cpp/VS_Snippets_Winforms/System.Windows.Forms.DataConnectorWebService/CPP/form1.cpp#3)]
     [!code-csharp[System.Windows.Forms.DataConnectorWebService#3](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataConnectorWebService/CS/form1.cs#3)]
     [!code-vb[System.Windows.Forms.DataConnectorWebService#3](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataConnectorWebService/VB/form1.vb#3)]  
  
## <a name="example"></a><span data-ttu-id="d282c-124">例</span><span class="sxs-lookup"><span data-stu-id="d282c-124">Example</span></span>  
 <span data-ttu-id="d282c-125"><xref:System.Windows.Forms.BindingSource> コンポーネントを Web サービスにバインドし、テキスト ボックスを <xref:System.Windows.Forms.BindingSource> コンポーネントにバインドするコード例を次に示します。</span><span class="sxs-lookup"><span data-stu-id="d282c-125">The following code example demonstrates how to bind a <xref:System.Windows.Forms.BindingSource> component to a Web service, and then how to bind a text box to the <xref:System.Windows.Forms.BindingSource> component.</span></span> <span data-ttu-id="d282c-126">ボタンをクリックすると、Web サービス メソッドが呼び出され、結果が `textbox1` に表示されます。</span><span class="sxs-lookup"><span data-stu-id="d282c-126">When you click the button, a Web service method is called and the results will appear in `textbox1`.</span></span>  
  
 [!code-cpp[System.Windows.Forms.DataConnectorWebService#1](~/samples/snippets/cpp/VS_Snippets_Winforms/System.Windows.Forms.DataConnectorWebService/CPP/form1.cpp#1)]
 [!code-csharp[System.Windows.Forms.DataConnectorWebService#1](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataConnectorWebService/CS/form1.cs#1)]
 [!code-vb[System.Windows.Forms.DataConnectorWebService#1](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataConnectorWebService/VB/form1.vb#1)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="d282c-127">コードのコンパイル</span><span class="sxs-lookup"><span data-stu-id="d282c-127">Compiling the Code</span></span>  
 <span data-ttu-id="d282c-128">これは、`Main` メソッドを含む完全な例であり、クライアント側プロキシのコードを短縮したバージョンです。</span><span class="sxs-lookup"><span data-stu-id="d282c-128">This is a complete example that includes a `Main` method, and a shortened version of client-side proxy code.</span></span>  
  
 <span data-ttu-id="d282c-129">この例で必要な要素は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="d282c-129">This example requires:</span></span>  
  
- <span data-ttu-id="d282c-130">System、System.Drawing、System.Web.Services、System.Windows.Forms、および System.Xml の各アセンブリへの参照。</span><span class="sxs-lookup"><span data-stu-id="d282c-130">References to the System, System.Drawing, System.Web.Services, System.Windows.Forms and System.Xml assemblies.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d282c-131">関連項目</span><span class="sxs-lookup"><span data-stu-id="d282c-131">See also</span></span>

- [<span data-ttu-id="d282c-132">BindingSource コンポーネント</span><span class="sxs-lookup"><span data-stu-id="d282c-132">BindingSource Component</span></span>](bindingsource-component.md)
- [<span data-ttu-id="d282c-133">方法: Windows フォーム コントロールを型にバインドする</span><span class="sxs-lookup"><span data-stu-id="d282c-133">How to: Bind a Windows Forms Control to a Type</span></span>](how-to-bind-a-windows-forms-control-to-a-type.md)
