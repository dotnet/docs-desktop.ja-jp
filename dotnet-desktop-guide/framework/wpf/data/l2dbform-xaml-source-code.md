---
title: L2DBForm.xaml ソース コード
ms.date: 10/22/2019
ms.topic: sample
ms.openlocfilehash: 290b00e136f0c49e1b27d4fa1bca7321eebe936e
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/09/2020
ms.locfileid: "96982040"
---
# <a name="l2dbformxaml-source-code"></a><span data-ttu-id="a0fe0-102">L2DBForm.xaml ソース コード</span><span class="sxs-lookup"><span data-stu-id="a0fe0-102">L2DBForm.xaml source code</span></span>

<span data-ttu-id="a0fe0-103">このページでは、「[LINQ to XML を使用した WPF のデータ バインディングの例](linq-to-xml-data-binding-sample.md)」の XAML ソース ファイルの内容と説明を示します。</span><span class="sxs-lookup"><span data-stu-id="a0fe0-103">This page contains and describes the XAML source file for the [WPF data binding using LINQ to XML example](linq-to-xml-data-binding-sample.md).</span></span>

## <a name="overall-ui-structure"></a><span data-ttu-id="a0fe0-104">UI の全体的な構造</span><span class="sxs-lookup"><span data-stu-id="a0fe0-104">Overall UI structure</span></span>

<span data-ttu-id="a0fe0-105">WPF プロジェクトでよくあるように、このファイルには親要素として <xref:System.Windows.Window> XML 要素が含まれており、この要素に `L2XDBFrom` 名前空間の派生クラス `LinqToXmlDataBinding` が関連付けられています。</span><span class="sxs-lookup"><span data-stu-id="a0fe0-105">As is typical for a WPF project, this file contains one parent element, a <xref:System.Windows.Window> XML element that's associated with the derived class `L2XDBFrom` in the `LinqToXmlDataBinding` namespace.</span></span>

<span data-ttu-id="a0fe0-106">クライアント領域は、背景が薄い青になっている <xref:System.Windows.Controls.StackPanel> に含まれています。</span><span class="sxs-lookup"><span data-stu-id="a0fe0-106">The client area is contained within a <xref:System.Windows.Controls.StackPanel> that's given a light blue background.</span></span> <span data-ttu-id="a0fe0-107">このパネルは、 <xref:System.Windows.Controls.DockPanel> バーで区切られた 4 つの <xref:System.Windows.Controls.Separator> UI セクションで構成されています。</span><span class="sxs-lookup"><span data-stu-id="a0fe0-107">This panel contains four <xref:System.Windows.Controls.DockPanel> UI sections separated by <xref:System.Windows.Controls.Separator> bars.</span></span> <span data-ttu-id="a0fe0-108">これらのセクションの目的については、[こちら](linq-to-xml-data-binding-sample.md#overview)で説明されています。</span><span class="sxs-lookup"><span data-stu-id="a0fe0-108">The purpose of these sections is described [here](linq-to-xml-data-binding-sample.md#overview).</span></span>

<span data-ttu-id="a0fe0-109">各セクションには、それぞれを識別するラベルが含まれています。</span><span class="sxs-lookup"><span data-stu-id="a0fe0-109">Each section contains a label that identifies it.</span></span> <span data-ttu-id="a0fe0-110">最初の 2 つのセクションでは、 <xref:System.Windows.FrameworkElement.LayoutTransform%2A>を使用してこのラベルを 90°回転させています。</span><span class="sxs-lookup"><span data-stu-id="a0fe0-110">In the first two sections, this label is rotated 90 degrees through the use of a <xref:System.Windows.FrameworkElement.LayoutTransform%2A>.</span></span> <span data-ttu-id="a0fe0-111">セクションの残りの部分には、そのセクションの目的に適したテキスト ブロック、テキスト ボックス、ボタンなどの UI 要素が含まれています。</span><span class="sxs-lookup"><span data-stu-id="a0fe0-111">The rest of the section contains UI elements appropriate to the purpose of that section, for example, text blocks, text boxes, and buttons.</span></span> <span data-ttu-id="a0fe0-112">これらの子コントロールの配置には、子 <xref:System.Windows.Controls.StackPanel> が使用されている場合があります。</span><span class="sxs-lookup"><span data-stu-id="a0fe0-112">Sometimes a child <xref:System.Windows.Controls.StackPanel> is used to align these child controls.</span></span>

## <a name="window-resource-section"></a><span data-ttu-id="a0fe0-113">ウィンドウ リソース セクション</span><span class="sxs-lookup"><span data-stu-id="a0fe0-113">Window resource section</span></span>

<span data-ttu-id="a0fe0-114">9 行目の `<Window.Resources>` 開始タグは、ウィンドウ リソース セクションの開始を示します。</span><span class="sxs-lookup"><span data-stu-id="a0fe0-114">The opening `<Window.Resources>` tag on line 9 indicates the start of the window resource section.</span></span> <span data-ttu-id="a0fe0-115">このセクションは、35 行目の終了タグで終了します。</span><span class="sxs-lookup"><span data-stu-id="a0fe0-115">It ends with the closing tag on line 35.</span></span>

<span data-ttu-id="a0fe0-116">11 ～ 25 行目にわたる `<ObjectDataProvider>` タグでは、 <xref:System.Windows.Data.ObjectDataProvider>をソースとして使用する `LoadedBooks`という名前の <xref:System.Xml.Linq.XElement> が宣言されています。</span><span class="sxs-lookup"><span data-stu-id="a0fe0-116">The `<ObjectDataProvider>` tag, which spans lines 11 through 25, declares a <xref:System.Windows.Data.ObjectDataProvider>, named `LoadedBooks`, that uses an <xref:System.Xml.Linq.XElement> as the source.</span></span> <span data-ttu-id="a0fe0-117"><xref:System.Xml.Linq.XElement> は、組み込み XML ドキュメント (`CDATA` 要素) を解析することで初期化されます。</span><span class="sxs-lookup"><span data-stu-id="a0fe0-117">The <xref:System.Xml.Linq.XElement> is initialized by parsing an embedded XML document (a `CDATA` element).</span></span> <span data-ttu-id="a0fe0-118">埋め込み XML ドキュメントの宣言時および解析時に、空白が保持されることに注意してください。</span><span class="sxs-lookup"><span data-stu-id="a0fe0-118">Notice that white space is preserved when declaring the embedded XML document and also when it's parsed.</span></span> <span data-ttu-id="a0fe0-119">空白が保持されるのは、生の XML の表示に使用されている <xref:System.Windows.Controls.TextBlock> コントロールに、特別な XML 書式設定機能がないためです。</span><span class="sxs-lookup"><span data-stu-id="a0fe0-119">White space is preserved because the <xref:System.Windows.Controls.TextBlock> control, which is used to display the raw XML, has no special XML formatting capabilities.</span></span>

<span data-ttu-id="a0fe0-120">最後に、28 ～ 34 行目で <xref:System.Windows.DataTemplate> という名前の `BookTemplate` が定義されています。</span><span class="sxs-lookup"><span data-stu-id="a0fe0-120">Lastly, a <xref:System.Windows.DataTemplate> named `BookTemplate` is defined on lines 28 through 34.</span></span> <span data-ttu-id="a0fe0-121">このテンプレートは、 **[Book List]** UI セクションにエントリを表示するために使用されます。</span><span class="sxs-lookup"><span data-stu-id="a0fe0-121">This template is used to display the entries in the **Book List** UI section.</span></span> <span data-ttu-id="a0fe0-122">ここでは、データ バインドおよび LINQ to XML の動的プロパティを使用し、次の代入を通じて書籍の ID と名前を取得します。</span><span class="sxs-lookup"><span data-stu-id="a0fe0-122">It uses data binding and LINQ to XML dynamic properties to retrieve the book ID and book name through the following assignments:</span></span>

```xaml
Text="{Binding Path=Attribute[id].Value}"Text="{Binding Path=Value}"
```

## <a name="data-binding-code"></a><span data-ttu-id="a0fe0-123">データ バインド コード</span><span class="sxs-lookup"><span data-stu-id="a0fe0-123">Data binding code</span></span>

<span data-ttu-id="a0fe0-124">このファイルでは、 <xref:System.Windows.DataTemplate> 要素に加えて、データ バインドが各所で使用されています。</span><span class="sxs-lookup"><span data-stu-id="a0fe0-124">In addition to the <xref:System.Windows.DataTemplate> element, data binding is used in a number of other places in this file.</span></span>

<span data-ttu-id="a0fe0-125">38 行目の `<StackPanel>` 開始タグでは、このパネルの <xref:System.Windows.FrameworkElement.DataContext%2A> プロパティが `LoadedBooks` データ プロバイダーに設定されています。</span><span class="sxs-lookup"><span data-stu-id="a0fe0-125">In the opening `<StackPanel>` tag on line 38, the <xref:System.Windows.FrameworkElement.DataContext%2A> property of this panel is set to the `LoadedBooks` data provider.</span></span>

```xaml
DataContext="{Binding Source={StaticResource LoadedBooks}}
```

<span data-ttu-id="a0fe0-126">データ コンテキストを設定することにより、このデータ プロバイダーの `Xml` プロパティにバインドして、`tbRawXml` という名前の <xref:System.Windows.Controls.TextBlock> に生の XML を表示できるようになります (46 行目)。</span><span class="sxs-lookup"><span data-stu-id="a0fe0-126">Setting the data context makes it possible (on line 46) for the <xref:System.Windows.Controls.TextBlock> named `tbRawXml` to display the raw XML by binding to this data provider's `Xml` property:</span></span>

```xaml
Text="{Binding Path=Xml}"
```

<span data-ttu-id="a0fe0-127">58 ～ 62 行目では、 <xref:System.Windows.Controls.ListBox> [Book List] **UI セクションの** が、その表示項目のテンプレートをウィンドウ リソース セクションで定義された `BookTemplate` に設定しています。</span><span class="sxs-lookup"><span data-stu-id="a0fe0-127">The <xref:System.Windows.Controls.ListBox> in the **Book List** UI section, on lines 58 through 62, sets the template for its display items to the `BookTemplate` defined in the window resource section:</span></span>

```xaml
ItemTemplate ="{StaticResource BookTemplate}"
```

<span data-ttu-id="a0fe0-128">59 ～ 62 行目では、書籍の実際の値がこのリスト ボックスにバインドされています。</span><span class="sxs-lookup"><span data-stu-id="a0fe0-128">Then, on lines 59 through 62, the actual values of the books are bound to this list box:</span></span>

```xaml
<ListBox.ItemsSource>
    <Binding Path="Elements[{http://www.mybooks.com}book]"/>
</ListBox.ItemsSource>
```

<span data-ttu-id="a0fe0-129">3 番目の UI セクション **[Edit Selected Book]** では、まず親 <xref:System.Windows.FrameworkElement.DataContext%2A> の <xref:System.Windows.Controls.StackPanel> が、 **[Book List]** UI セクション (82 行目) で現在選択されている項目にバインドされています。</span><span class="sxs-lookup"><span data-stu-id="a0fe0-129">The third UI section, **Edit Selected Book**, first binds the <xref:System.Windows.FrameworkElement.DataContext%2A> of the parent <xref:System.Windows.Controls.StackPanel> to the currently selected item in from the **Book List** UI section (line 82):</span></span>

```xaml
DataContext="{Binding ElementName=lbBooks, Path=SelectedItem}"
```

<span data-ttu-id="a0fe0-130">次に、双方向データ バインドを使用して、書籍要素の現在の値がこのパネルの 2 つのテキスト ボックスに表示され、そこで更新されるようにしています。</span><span class="sxs-lookup"><span data-stu-id="a0fe0-130">It then uses two-way data binding, so that the current values of the book elements are displayed to, and updated from, the two text boxes in this panel.</span></span> <span data-ttu-id="a0fe0-131">動的プロパティへのデータ バインドは、`BookTemplate` データ テンプレートで使用されるデータ バインドと似ています。</span><span class="sxs-lookup"><span data-stu-id="a0fe0-131">Data binding to dynamic properties is similar to the data binding used in the `BookTemplate` data template:</span></span>

```xaml
Text="{Binding Path=Attribute[id].Value}"...Text="{Binding Path=Value}"
```

<span data-ttu-id="a0fe0-132">最後の UI セクション **[Add New Book]** では、XAML コード内でデータ バインドが使用されません。</span><span class="sxs-lookup"><span data-stu-id="a0fe0-132">The last UI section, **Add New Book**, doesn't use data binding in its XAML code.</span></span> <span data-ttu-id="a0fe0-133">代わりに、データ バインドは *L2DBForm.xaml.cs* ファイルのイベント処理コード内にあります。</span><span class="sxs-lookup"><span data-stu-id="a0fe0-133">Instead, data binding is in its event handling code in the file *L2DBForm.xaml.cs*.</span></span>

## <a name="example"></a><span data-ttu-id="a0fe0-134">例</span><span class="sxs-lookup"><span data-stu-id="a0fe0-134">Example</span></span>

### <a name="description"></a><span data-ttu-id="a0fe0-135">説明</span><span class="sxs-lookup"><span data-stu-id="a0fe0-135">Description</span></span>

> [!NOTE]
> <span data-ttu-id="a0fe0-136">行番号を追跡しやすいように、次のコードを Visual Studio の C# ソース コード エディターなどのコード エディターにコピーすることをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="a0fe0-136">We recommend that you copy the following code below into a code editor, such as the C# source code editor in Visual Studio, so that line numbers will be easier to track.</span></span>

### <a name="code"></a><span data-ttu-id="a0fe0-137">コード</span><span class="sxs-lookup"><span data-stu-id="a0fe0-137">Code</span></span>

```xml
<Window x:Class="LinqToXmlDataBinding.L2XDBForm"
    xmlns="http://schemas.microsoft.com/winfx/2006/xaml/presentation"
    xmlns:x="http://schemas.microsoft.com/winfx/2006/xaml"
    xmlns:system="clr-namespace:System;assembly=mscorlib"
    xmlns:xlinq="clr-namespace:System.Xml.Linq;assembly=System.Xml.Linq"
    xmlns:local="clr-namespace:LinqToXmlDataBinding"
    Title="WPF Data Binding using LINQ-to-XML" Height="665" Width="500" ResizeMode="NoResize">

    <Window.Resources>
        <!-- Books provider and inline data -->
        <ObjectDataProvider x:Key="LoadedBooks" ObjectType="{x:Type xlinq:XElement}" MethodName="Parse">
            <ObjectDataProvider.MethodParameters>
                <system:String xml:space="preserve">
<![CDATA[
<books xmlns="http://www.mybooks.com">
  <book id="0">book zero</book>
  <book id="1">book one</book>
  <book id="2">book two</book>
  <book id="3">book three</book>
</books>
]]>
                </system:String>
                <xlinq:LoadOptions>PreserveWhitespace</xlinq:LoadOptions>
            </ObjectDataProvider.MethodParameters>
        </ObjectDataProvider>

        <!-- Template for use in Books List listbox. -->
        <DataTemplate x:Key="BookTemplate">
            <StackPanel Orientation="Horizontal">
                <TextBlock Margin="3" Text="{Binding Path=Attribute[id].Value}"/>
                <TextBlock Margin="3" Text="-"/>
                <TextBlock Margin="3" Text="{Binding Path=Value}"/>
            </StackPanel>
        </DataTemplate>
    </Window.Resources>

    <!-- Main visual content container -->
    <StackPanel Background="lightblue" DataContext="{Binding Source={StaticResource LoadedBooks}}">
        <!-- Raw XML display section -->
        <DockPanel Margin="5">
            <Label  Background="Gray" FontSize="12" BorderBrush="Black" BorderThickness="1" FontWeight="Bold">XML
            <Label.LayoutTransform>
                <RotateTransform Angle="90"/>
            </Label.LayoutTransform>
            </Label>
            <TextBlock Name="tbRawXml" Height="200" Background="LightGray" Text="{Binding Path=Xml}" TextTrimming="CharacterEllipsis" />
        </DockPanel>

        <Separator Height="4" Margin="5" />

        <!-- List box to display all books section -->
        <DockPanel Margin="5">
            <Label  Background="Gray" FontSize="12" BorderBrush="Black" BorderThickness="1" FontWeight="Bold">Book List
                <Label.LayoutTransform>
                    <RotateTransform Angle="90"/>
                </Label.LayoutTransform>
            </Label>
            <ListBox Name="lbBooks" Height="200" Width="415" ItemTemplate ="{StaticResource BookTemplate}">
                <ListBox.ItemsSource>
                    <Binding Path="Elements[{http://www.mybooks.com}book]"/>
                </ListBox.ItemsSource>
            </ListBox>
            <Button Margin="5" DockPanel.Dock="Right" Height="30" Width ="130" Content="Remove Selected Book" Click="OnRemoveBook">
            <Button.LayoutTransform>
                <RotateTransform Angle="90"/>
            </Button.LayoutTransform>
            </Button>
        </DockPanel>

        <Separator Height="4" Margin="5" />

        <!-- Edit current selection section -->
        <DockPanel Margin="5">
            <TextBlock Margin="5" Height="30" Width="65" DockPanel.Dock="Right" Background="LightGray" TextWrapping="Wrap" TextAlignment="Center">
                    Changes are live!
                <TextBlock.LayoutTransform>
                    <RotateTransform Angle="90"/>
                </TextBlock.LayoutTransform>
            </TextBlock>
            <StackPanel>
                <Label Width="450" Background="Gray" FontSize="12" BorderBrush="Black" BorderThickness="1" HorizontalAlignment="Left" FontWeight="Bold">Edit Selected Book</Label>
                <StackPanel Margin="1" DataContext="{Binding ElementName=lbBooks, Path=SelectedItem}">
                    <StackPanel Orientation="Horizontal">
                        <Label Width="40">ID:</Label>
                        <TextBox Name="editAttributeTextBox" Width="410" Text="{Binding Path=Attribute[id].Value}">
                            <TextBox.ToolTip>
                                <TextBlock FontWeight="Bold" TextAlignment="Center">
                                    <Label>Edit the selected book ID and see it changed.</Label>
                                </TextBlock>
                            </TextBox.ToolTip>
                        </TextBox>
                    </StackPanel>
                    <StackPanel Orientation="Horizontal">
                        <Label Width="40">Value:</Label>
                        <TextBox Name="editValueTextBox" Width="410" Text="{Binding Path=Value}" Height="25">
                            <TextBox.ToolTip>
                                <TextBlock FontWeight="Bold" TextAlignment="Center">
                                    <Label>Edit the selected book Value and see it changed.</Label>
                                </TextBlock>
                            </TextBox.ToolTip>
                        </TextBox>
                    </StackPanel>
                </StackPanel>
            </StackPanel>
        </DockPanel>

        <Separator Height="4" Margin="5" />

        <!-- Add new book section -->
        <DockPanel Margin="5">
            <Button Margin="5" Height="30" DockPanel.Dock="Right" Click ="OnAddBook">Add Book
                <Button.LayoutTransform>
                    <RotateTransform Angle="90"/>
                </Button.LayoutTransform>
            </Button>
            <StackPanel>
                <Label Width="450" Background="Gray" FontSize="12" BorderBrush="Black" BorderThickness="1" HorizontalAlignment="Left" FontWeight="Bold">Add New Book</Label>
                <StackPanel Margin="1">
                    <StackPanel Orientation="Horizontal">
                        <Label Width="40">ID:</Label>
                        <TextBox Name="tbAddID" Width="410">
                            <TextBox.ToolTip>
                                <TextBlock FontWeight="Bold" TextAlignment="Center">
                                    <Label>Enter a book ID and Value pair, then click Add Book.</Label>
                                </TextBlock>
                            </TextBox.ToolTip>
                        </TextBox>
                    </StackPanel>
                    <StackPanel Orientation="Horizontal">
                        <Label Width="40">Value:</Label>
                        <TextBox Name="tbAddValue" Width="410" Height="25">
                            <TextBox.ToolTip>
                                <TextBlock FontWeight="UltraBold" TextAlignment="Center">
                                    <Label>Enter a book ID and Value pair, then click Add Book.</Label>
                                </TextBlock>
                            </TextBox.ToolTip>
                        </TextBox>
                    </StackPanel>
                </StackPanel>
            </StackPanel>
        </DockPanel>
    </StackPanel>
</Window>
```

### <a name="comments"></a><span data-ttu-id="a0fe0-138">コメント</span><span class="sxs-lookup"><span data-stu-id="a0fe0-138">Comments</span></span>

<span data-ttu-id="a0fe0-139">WPF UI 要素に関連付けられているイベント ハンドラーの C# ソース コードについては、「[L2DBForm.xaml.cs Source Code](l2dbform-xaml-cs-source-code.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="a0fe0-139">For the C# source code for the event handlers associated with the WPF UI elements, see [L2DBForm.xaml.cs source code](l2dbform-xaml-cs-source-code.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="a0fe0-140">関連項目</span><span class="sxs-lookup"><span data-stu-id="a0fe0-140">See also</span></span>

- [<span data-ttu-id="a0fe0-141">チュートリアル: LinqToXmlDataBinding の例</span><span class="sxs-lookup"><span data-stu-id="a0fe0-141">Walkthrough: LinqToXmlDataBinding example</span></span>](linq-to-xml-data-binding-sample.md)
- [<span data-ttu-id="a0fe0-142">L2DBForm.xaml.cs sauce コード</span><span class="sxs-lookup"><span data-stu-id="a0fe0-142">L2DBForm.xaml.cs source code</span></span>](l2dbform-xaml-cs-source-code.md)
