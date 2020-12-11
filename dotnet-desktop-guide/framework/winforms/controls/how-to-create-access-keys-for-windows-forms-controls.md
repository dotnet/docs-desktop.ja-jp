---
title: コントロールのアクセスキーを作成する
ms.date: 08/20/2019
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- controls [Windows Forms], access keys
- Button control [Windows Forms], access keys
- dialog box controls [Windows Forms], mnemonics
- access keys [Windows Forms], creating for controls
- mnemonics [Windows Forms], adding to dialog box controls
- mnemonics
- ampersand character in shortcut key
- Windows Forms controls, access keys
- examples [Windows Forms], controls
- Text property [Windows Forms], specifying access keys for controls
- keyboard shortcuts [Windows Forms], creating for controls
- access keys [Windows Forms], Windows Forms
- ALT key
ms.assetid: 4faa0991-28ec-4eca-91db-51dc2cd6a7ac
ms.openlocfilehash: 7f6b0a5838cacfc1189fba819a54b3423d567ea0
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/09/2020
ms.locfileid: "96982556"
---
# <a name="how-to-create-access-keys-for-windows-forms-controls"></a><span data-ttu-id="594a7-102">方法: Windows フォームコントロールのアクセスキーを作成する</span><span class="sxs-lookup"><span data-stu-id="594a7-102">How to: Create access keys for Windows Forms controls</span></span>

<span data-ttu-id="594a7-103">*アクセスキー* は、メニュー、メニュー項目、またはボタンなどのコントロールのラベルのテキスト内の下線付きの文字です。</span><span class="sxs-lookup"><span data-stu-id="594a7-103">An *access key* is an underlined character in the text of a menu, menu item, or the label of a control such as a button.</span></span> <span data-ttu-id="594a7-104">ユーザーは、アクセスキーを使用して、Alt キーを定義済みのアクセスキーと組み合わせて押すことで、ボタンを "クリック" できます。</span><span class="sxs-lookup"><span data-stu-id="594a7-104">With an access key, the user can "click" a button by pressing the Alt key in combination with the predefined access key.</span></span> <span data-ttu-id="594a7-105">たとえば、ボタンがフォームを印刷するためのプロシージャを実行し、その `Text` プロパティが "print" に設定されている場合、文字 "p" の前にアンパサンドを追加すると、実行時にボタンテキストに文字 "p" が下線付きで表示されます。</span><span class="sxs-lookup"><span data-stu-id="594a7-105">For example, if a button runs a procedure to print a form, and therefore its `Text` property is set to "Print," adding an ampersand before the letter "P" causes the letter "P" to be underlined in the button text at run time.</span></span> <span data-ttu-id="594a7-106">ユーザーは、Alt + P キーを押して、ボタンに関連付けられているコマンドを実行できます。</span><span class="sxs-lookup"><span data-stu-id="594a7-106">The user can run the command associated with the button by pressing Alt+P.</span></span>

<span data-ttu-id="594a7-107">フォーカスを受け取ることができないコントロールは、アクセスキーを持つことができません。</span><span class="sxs-lookup"><span data-stu-id="594a7-107">Controls that cannot receive focus can't have access keys.</span></span>

## <a name="programmatic"></a><span data-ttu-id="594a7-108">プログラムによる</span><span class="sxs-lookup"><span data-stu-id="594a7-108">Programmatic</span></span>

<span data-ttu-id="594a7-109">プロパティを、 `Text` ショートカットにする文字の前にアンパサンド (&) を含む文字列に設定します。</span><span class="sxs-lookup"><span data-stu-id="594a7-109">Set the `Text` property to a string that includes an ampersand (&) before the letter that will be the shortcut.</span></span>

```vb
' Set the letter "P" as an access key.
Button1.Text = "&Print"
```

```csharp
// Set the letter "P" as an access key.
button1.Text = "&Print";
```

```cpp
// Set the letter "P" as an access key.
button1->Text = "&Print";
```

> [!NOTE]
> <span data-ttu-id="594a7-110">アクセスキーを作成せずにキャプションにアンパサンドを使用するには、2つのアンパサンド (&&) を含めます。</span><span class="sxs-lookup"><span data-stu-id="594a7-110">To use an ampersand in a caption without creating an access key, include two ampersands (&&).</span></span> <span data-ttu-id="594a7-111">キャプションにはアンパサンドが1つ表示され、下線付きの文字はありません。</span><span class="sxs-lookup"><span data-stu-id="594a7-111">A single ampersand is displayed in the caption and no characters are underlined.</span></span>

## <a name="designer"></a><span data-ttu-id="594a7-112">Designer</span><span class="sxs-lookup"><span data-stu-id="594a7-112">Designer</span></span>

<span data-ttu-id="594a7-113">Visual Studio の [ **プロパティ** ] ウィンドウで、[ **Text** ] プロパティを、アクセスキーにする文字の前にアンパサンド (' & ') を含む文字列に設定します。</span><span class="sxs-lookup"><span data-stu-id="594a7-113">In the **Properties** window of Visual Studio, set the **Text** property to a string that includes an ampersand ('&') before the letter that will be the access key.</span></span> <span data-ttu-id="594a7-114">たとえば、文字 "P" をアクセスキーとして設定するには、「 **&Print**」と入力します。</span><span class="sxs-lookup"><span data-stu-id="594a7-114">For example, to set the letter "P" as the access key, enter **&Print**.</span></span>

## <a name="see-also"></a><span data-ttu-id="594a7-115">関連項目</span><span class="sxs-lookup"><span data-stu-id="594a7-115">See also</span></span>

- <xref:System.Windows.Forms.Button>
- [<span data-ttu-id="594a7-116">方法 : Windows フォームのボタンのクリックに応答する</span><span class="sxs-lookup"><span data-stu-id="594a7-116">How to: Respond to Windows Forms Button Clicks</span></span>](how-to-respond-to-windows-forms-button-clicks.md)
- [<span data-ttu-id="594a7-117">方法 : Windows フォーム コントロールによって表示されるテキストを設定する</span><span class="sxs-lookup"><span data-stu-id="594a7-117">How to: Set the Text Displayed by a Windows Forms Control</span></span>](how-to-set-the-text-displayed-by-a-windows-forms-control.md)
- [<span data-ttu-id="594a7-118">各 Windows フォーム コントロールのラベル設定とショートカットの作成</span><span class="sxs-lookup"><span data-stu-id="594a7-118">Labeling Individual Windows Forms Controls and Providing Shortcuts to Them</span></span>](labeling-individual-windows-forms-controls-and-providing-shortcuts-to-them.md)
