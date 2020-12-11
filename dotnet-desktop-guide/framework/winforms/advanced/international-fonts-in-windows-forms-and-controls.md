---
title: フォームとコントロールの国際対応フォント
ms.date: 03/30/2017
helpviewer_keywords:
- fonts [Windows Forms], international
- international applications [Windows Forms], character display
- fonts [Windows Forms], globalization considerations
- localization [Windows Forms], fonts
- Windows Forms controls, labels
- font fallback in Windows Forms
- globalization [Windows Forms], character sets
dev_langs:
- csharp
- vb
ms.assetid: 2c3066df-9bac-479a-82b2-79e484b346a3
ms.openlocfilehash: 59dde6bb384d644321a8ff5674d735f8e6d36fd0
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/09/2020
ms.locfileid: "96981211"
---
# <a name="international-fonts-in-windows-forms-and-controls"></a><span data-ttu-id="0a7c0-102">Windows フォームとコントロールの国際対応フォント</span><span class="sxs-lookup"><span data-stu-id="0a7c0-102">International fonts in Windows Forms and controls</span></span>

<span data-ttu-id="0a7c0-103">国際対応のアプリケーションでは、可能な限りフォントフォールバックを使用することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="0a7c0-103">In International applications, the recommended method of selecting fonts is to use font fallback wherever possible.</span></span> <span data-ttu-id="0a7c0-104">フォントフォールバックとは、文字が属するスクリプトをシステムが決定することを意味します。</span><span class="sxs-lookup"><span data-stu-id="0a7c0-104">Font fallback means that the system determines what script the character belongs to.</span></span>

## <a name="using-font-fallback"></a><span data-ttu-id="0a7c0-105">フォントフォールバックの使用</span><span class="sxs-lookup"><span data-stu-id="0a7c0-105">Using font fallback</span></span>

<span data-ttu-id="0a7c0-106">この機能を利用するに <xref:System.Drawing.Font> は、フォームまたは他の要素のプロパティを設定しないでください。</span><span class="sxs-lookup"><span data-stu-id="0a7c0-106">To take advantage of this feature, don't set the <xref:System.Drawing.Font> property for your form or any other element.</span></span> <span data-ttu-id="0a7c0-107">アプリケーションは、オペレーティングシステムのローカライズされた言語とは異なる既定のシステムフォントを自動的に使用します。</span><span class="sxs-lookup"><span data-stu-id="0a7c0-107">The application will automatically use the default system font, which differs from one localized language of the operating system to another.</span></span> <span data-ttu-id="0a7c0-108">アプリケーションを実行すると、オペレーティングシステムで選択されているカルチャに対応する正しいフォントがシステムによって自動的に提供されます。</span><span class="sxs-lookup"><span data-stu-id="0a7c0-108">When the application runs, the system will automatically provide the correct font for the culture selected in the operating system.</span></span>

<span data-ttu-id="0a7c0-109">フォントを設定しないという規則には例外があります。これは、フォントスタイルを変更するためのものです。</span><span class="sxs-lookup"><span data-stu-id="0a7c0-109">There's an exception to the rule of not setting the font, which is for changing the font style.</span></span> <span data-ttu-id="0a7c0-110">これは、ユーザーがボタンをクリックしてテキストボックス内のテキストを太字で表示するアプリケーションにとって重要な場合があります。</span><span class="sxs-lookup"><span data-stu-id="0a7c0-110">This might be important for an application in which the user clicks a button to make text in a text box appear in boldface.</span></span> <span data-ttu-id="0a7c0-111">これを行うには、フォームのフォントの内容に基づいて、テキストボックスのフォントスタイルを太字に変更する関数を記述します。</span><span class="sxs-lookup"><span data-stu-id="0a7c0-111">To do that, you would write a function to change the text box's font style to bold, based on whatever the form's font is.</span></span> <span data-ttu-id="0a7c0-112">この関数は、ボタンの <xref:System.Windows.Forms.Control.Click> イベントハンドラーとイベントハンドラーの2か所で呼び出すことが重要です <xref:System.Windows.Forms.Control.FontChanged> 。</span><span class="sxs-lookup"><span data-stu-id="0a7c0-112">It's important to call this function in two places: in the button's <xref:System.Windows.Forms.Control.Click> event handler and in the <xref:System.Windows.Forms.Control.FontChanged> event handler.</span></span> <span data-ttu-id="0a7c0-113">関数がイベントハンドラーでのみ呼び出され、 <xref:System.Windows.Forms.Control.Click> 他の一部のコードがフォーム全体のフォントファミリを変更した場合、テキストボックスはフォームの他の部分では変更されません。</span><span class="sxs-lookup"><span data-stu-id="0a7c0-113">If the function is called only in the <xref:System.Windows.Forms.Control.Click> event handler and some other piece of code changes the font family of the entire form, the text box doesn't change with the rest of the form.</span></span>

```vb
Private Sub MakeBold()
   ' Change the TextBox to a bold version of the form font
   TextBox1.Font = New Font(Me.Font, FontStyle.Bold)
End Sub

Private Sub Button1_Click(ByVal sender As System.Object, ByVal e As System.EventArgs) Handles Button1.Click
   ' Clicking this button makes the TextBox bold
   MakeBold()
End Sub

Private Sub Form1_FontChanged(ByVal sender As Object, ByVal e As System.EventArgs) Handles MyBase.FontChanged
   ' If the TextBox is already bold and the form's font changes,
   ' change the TextBox to a bold version of the new form font
   If (TextBox1.Font.Style = FontStyle.Bold) Then
      MakeBold()
   End If
End Sub
```

```csharp
private void button1_Click(object sender, System.EventArgs e)
{
   // Clicking this button makes the TextBox bold
   MakeBold();
}

private void MakeBold()
{
   // Change the TextBox to a bold version of the form's font
   textBox1.Font = new Font(this.Font, FontStyle.Bold);
}

private void Form1_FontChanged(object sender, System.EventArgs e)
{
   // If the TextBox is already bold and the form's font changes,
   // change the TextBox to a bold version of the new form font
   if (textBox1.Font.Style == FontStyle.Bold)
   {
      MakeBold();
   }
}
```

<span data-ttu-id="0a7c0-114">ただし、アプリケーションをローカライズするときに、特定の言語で太字のフォントが正しく表示されない場合があります。</span><span class="sxs-lookup"><span data-stu-id="0a7c0-114">However, when you localize your application, the bold font may display poorly for certain languages.</span></span> <span data-ttu-id="0a7c0-115">この問題が懸念される場合は、フォントを太字から標準テキストに切り替えるオプションをローカライザーに与えることをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="0a7c0-115">If this is a concern, you want the localizers to have the option of switching the font from bold to regular text.</span></span> <span data-ttu-id="0a7c0-116">ローカライザーは通常開発者ではなく、ソースコードにアクセスできないため、リソースファイルにのみアクセスできます。このオプションはリソースファイルで設定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="0a7c0-116">Since localizers are typically not developers and don't have access to source code, only to resource files, this option needs to be set in the resource files.</span></span> <span data-ttu-id="0a7c0-117">これを行うには、プロパティを <xref:System.Drawing.Font.Bold%2A> に設定し `true` ます。</span><span class="sxs-lookup"><span data-stu-id="0a7c0-117">To do this, you would set the <xref:System.Drawing.Font.Bold%2A> property to `true`.</span></span> <span data-ttu-id="0a7c0-118">これにより、ローカライズ可能なリソースファイルにフォント設定が書き込まれます。</span><span class="sxs-lookup"><span data-stu-id="0a7c0-118">This results in the font setting being written out to the resource files, where localizers can edit it.</span></span> <span data-ttu-id="0a7c0-119">次に、メソッドの後にコードを記述し `InitializeComponent` て、フォームのフォントに基づいてフォントをリセットします。ただし、リソースファイルに指定されているフォントスタイルを使用します。</span><span class="sxs-lookup"><span data-stu-id="0a7c0-119">You then write code after the `InitializeComponent` method to reset the font based on whatever the form's font is, but using the font style specified in the resource file.</span></span>

```vb
TextBox1.Font = New System.Drawing.Font(Me.Font, TextBox1.Font.Style)
```

```csharp
textBox1.Font = new System.Drawing.Font(this.Font, textBox1.Font.Style);
```
  
## <a name="see-also"></a><span data-ttu-id="0a7c0-120">関連項目</span><span class="sxs-lookup"><span data-stu-id="0a7c0-120">See also</span></span>

- [<span data-ttu-id="0a7c0-121">フォントとテキストの使用</span><span class="sxs-lookup"><span data-stu-id="0a7c0-121">Using Fonts and Text</span></span>](using-fonts-and-text.md)
