---
title: L2DBForm.xaml.cs sauce コード
ms.date: 10/22/2019
ms.topic: sample
ms.openlocfilehash: 882699a76eab3c291cd92c298287bc5d28fb08e1
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/09/2020
ms.locfileid: "96982608"
---
# <a name="l2dbformxamlcs-source-code"></a><span data-ttu-id="7b40b-102">L2DBForm.xaml.cs sauce コード</span><span class="sxs-lookup"><span data-stu-id="7b40b-102">L2DBForm.xaml.cs source code</span></span>

<span data-ttu-id="7b40b-103">このページには、*L2DBForm.xaml.cs* ファイル内の C# ソース コードの内容と説明が含まれます。</span><span class="sxs-lookup"><span data-stu-id="7b40b-103">This page contains the contents and description of the C# source code in the file *L2DBForm.xaml.cs*.</span></span> <span data-ttu-id="7b40b-104">このファイルに含まれている L2XDBForm 部分クラスは、3 つの論理的な部分、つまりデータ メンバー、`OnRemove`、`OnAddBook` ボタン クリック イベント ハンドラーに分けることができます。</span><span class="sxs-lookup"><span data-stu-id="7b40b-104">The L2XDBForm partial class contained in this file can be divided into three logical sections: data members and the `OnRemove` and `OnAddBook` button click event handlers.</span></span>

## <a name="data-members"></a><span data-ttu-id="7b40b-105">データ メンバー</span><span class="sxs-lookup"><span data-stu-id="7b40b-105">Data members</span></span>

<span data-ttu-id="7b40b-106">このクラスを *L2DBForm.xaml* で使用されているウィンドウ リソースに関連付けるために、2 つのプライベート データ メンバーが使用されています。</span><span class="sxs-lookup"><span data-stu-id="7b40b-106">Two private data members are used to associate this class to the window resources used in *L2DBForm.xaml*.</span></span>

- <span data-ttu-id="7b40b-107">名前空間変数 `myBooks` は、`"http://www.mybooks.com"` に初期化されます。</span><span class="sxs-lookup"><span data-stu-id="7b40b-107">The namespace variable `myBooks` is initialized to `"http://www.mybooks.com"`.</span></span>

- <span data-ttu-id="7b40b-108">メンバー `bookList` は、コンストラクター内で次の行を使用して *L2DBForm.xaml* 内の CDATA 文字列に初期化されます。</span><span class="sxs-lookup"><span data-stu-id="7b40b-108">The member `bookList` is initialized in the constructor to the CDATA string in *L2DBForm.xaml* with the following line:</span></span>

    ```csharp
    bookList = (XElement)((ObjectDataProvider)Resources["LoadedBooks"]).Data;
    ```

## <a name="onaddbook-event-handler"></a><span data-ttu-id="7b40b-109">OnAddBook イベント ハンドラー</span><span class="sxs-lookup"><span data-stu-id="7b40b-109">OnAddBook event handler</span></span>

<span data-ttu-id="7b40b-110">このメソッドには次の 3 つのステートメントが含まれています。</span><span class="sxs-lookup"><span data-stu-id="7b40b-110">This method contains the following three statements:</span></span>

- <span data-ttu-id="7b40b-111">最初の条件ステートメントでは、入力が検証されます。</span><span class="sxs-lookup"><span data-stu-id="7b40b-111">The first conditional statement is used for input validation.</span></span>

- <span data-ttu-id="7b40b-112">2 番目のステートメントでは、 **[Add New Book]\(新しい書籍の追加\)** ユーザー インターフェイス (UI) セクションでユーザーが入力した文字列値から新しい <xref:System.Xml.Linq.XElement> が作成されます。</span><span class="sxs-lookup"><span data-stu-id="7b40b-112">The second statement creates a new <xref:System.Xml.Linq.XElement> from the string values the user entered in the **Add New Book** user interface (UI) section.</span></span>

- <span data-ttu-id="7b40b-113">最後のステートメントでは、この新しい書籍要素が、*L2DBForm.xaml* のデータ プロバイダーに追加されます。</span><span class="sxs-lookup"><span data-stu-id="7b40b-113">The last statement adds this new book element to the data provider in *L2DBForm.xaml*.</span></span> <span data-ttu-id="7b40b-114">その結果、動的なデータ バインドによって UI がこの新しい項目で自動的に更新されます。ユーザーがコードを追加する必要はありません。</span><span class="sxs-lookup"><span data-stu-id="7b40b-114">Consequently, dynamic data binding will automatically update the UI with this new item; no extra user-supplied code is required.</span></span>

## <a name="onremove-event-handler"></a><span data-ttu-id="7b40b-115">OnRemove イベント ハンドラー</span><span class="sxs-lookup"><span data-stu-id="7b40b-115">OnRemove event handler</span></span>

<span data-ttu-id="7b40b-116">`OnRemove` ハンドラーは、2 つの理由で `OnAddBook` ハンドラーよりも複雑です。</span><span class="sxs-lookup"><span data-stu-id="7b40b-116">The `OnRemove` handler is more complicated than the `OnAddBook` handler for two reasons.</span></span> <span data-ttu-id="7b40b-117">1 つは、生の XML に保持された空白が含まれているために、一致する改行を書籍エントリと共に削除する必要があることです。</span><span class="sxs-lookup"><span data-stu-id="7b40b-117">First, because the raw XML contains preserved white space, matching newlines must also be removed with the book entry.</span></span> <span data-ttu-id="7b40b-118">もう 1 つは、削除された項目に設定されていた選択が、便宜上、一覧の前の項目にリセットされることです。</span><span class="sxs-lookup"><span data-stu-id="7b40b-118">Second, as a convenience, the selection, which was on the deleted item, is reset to the previous one in the list.</span></span>

<span data-ttu-id="7b40b-119">ただし、選択された書籍項目を削除するための中心的な作業は、2 つのステートメントだけで完了します。</span><span class="sxs-lookup"><span data-stu-id="7b40b-119">However, the core work of removing the selected book item is accomplished by only two statements:</span></span>

- <span data-ttu-id="7b40b-120">まず、リスト ボックスで現在選択されている項目に関連する書籍要素が取得されます。</span><span class="sxs-lookup"><span data-stu-id="7b40b-120">First, the book element associated with the currently selected item in the list box is retrieved:</span></span>

    ```csharp
    XElement selBook = (XElement)lbBooks.SelectedItem;
    ```

- <span data-ttu-id="7b40b-121">次に、この要素がデータ プロバイダーから削除されます。</span><span class="sxs-lookup"><span data-stu-id="7b40b-121">Then, this element is deleted from the data provider:</span></span>

    ```csharp
    selBook.Remove();
    ```

<span data-ttu-id="7b40b-122">この場合も、動的なデータ バインドによってプログラムの UI が自動的に更新されます。</span><span class="sxs-lookup"><span data-stu-id="7b40b-122">Again, dynamic data binding assures that the program's UI is automatically updated.</span></span>

## <a name="example"></a><span data-ttu-id="7b40b-123">例</span><span class="sxs-lookup"><span data-stu-id="7b40b-123">Example</span></span>

### <a name="code"></a><span data-ttu-id="7b40b-124">コード</span><span class="sxs-lookup"><span data-stu-id="7b40b-124">Code</span></span>

```csharp
using System;
using System.Linq;
using System.Collections;
using System.Collections.Generic;
using System.Diagnostics;
using System.Text;
using System.Windows;
using System.Windows.Controls;
using System.Windows.Data;
using System.Windows.Input;
using System.Xml;
using System.Xml.Linq;

namespace LinqToXmlDataBinding {
    /// <summary>
    /// Interaction logic for L2XDBForm.xaml
    /// </summary>

    public partial class L2XDBForm : System.Windows.Window
    {
        XNamespace mybooks = "http://www.mybooks.com";
        XElement bookList;

        public L2XDBForm()
        {
            InitializeComponent();
            bookList = (XElement)((ObjectDataProvider)Resources["LoadedBooks"]).Data;
        }

        void OnRemoveBook(object sender, EventArgs e)
        {
            int index = lbBooks.SelectedIndex;
            if (index < 0) return;

            XElement selBook = (XElement)lbBooks.SelectedItem;
            //Get next node before removing element.
            XNode nextNode = selBook.NextNode;
            selBook.Remove();

            //Remove any matching newline node.
            if (nextNode != null && nextNode.ToString().Trim().Equals(""))
            { nextNode.Remove(); }

            //Set selected item.
            if (lbBooks.Items.Count > 0)
            {  lbBooks.SelectedItem = lbBooks.Items[index > 0 ? index - 1 : 0]; }
        }

        void OnAddBook(object sender, EventArgs e)
        {
            if (String.IsNullOrEmpty(tbAddID.Text) ||
                String.IsNullOrEmpty(tbAddValue.Text))
            {
                MessageBox.Show("Please supply both a Book ID and a Value!", "Entry Error!");
                return;
            }
            XElement newBook = new XElement(
                                mybooks + "book",
                                new XAttribute("id", tbAddID.Text),
                                tbAddValue.Text);
            bookList.Add("  ", newBook, "\r\n");
        }
    }
}
```

### <a name="comments"></a><span data-ttu-id="7b40b-125">コメント</span><span class="sxs-lookup"><span data-stu-id="7b40b-125">Comments</span></span>

<span data-ttu-id="7b40b-126">これらのハンドラーに関連する XAML ソースについては、「[L2DBForm.xaml ソース コード](l2dbform-xaml-source-code.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="7b40b-126">For the associated XAML source for these handlers, see [L2DBForm.xaml source code](l2dbform-xaml-source-code.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="7b40b-127">関連項目</span><span class="sxs-lookup"><span data-stu-id="7b40b-127">See also</span></span>

- [<span data-ttu-id="7b40b-128">チュートリアル: LinqToXmlDataBinding の例</span><span class="sxs-lookup"><span data-stu-id="7b40b-128">Walkthrough: LinqToXmlDataBinding example</span></span>](linq-to-xml-data-binding-sample.md)
- [<span data-ttu-id="7b40b-129">L2DBForm.xaml ソース コード</span><span class="sxs-lookup"><span data-stu-id="7b40b-129">L2DBForm.xaml source code</span></span>](l2dbform-xaml-source-code.md)
