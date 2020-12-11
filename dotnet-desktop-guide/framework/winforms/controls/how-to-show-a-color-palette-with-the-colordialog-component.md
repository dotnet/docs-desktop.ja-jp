---
title: '方法: ColorDialog コンポーネントを使用してカラー パレットを表示する'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- palettes [Windows Forms], showing color
- color dialog box [Windows Forms], showing color palettes
- colors [Windows Forms], allowing users to select
- color palettes [Windows Forms], dialog box
- ColorDialog component [Windows Forms], showing color palettes
- color palettes [Windows Forms], showing in ColorDialog component
- colors [Windows Forms], showing palettes
ms.assetid: ee050f61-dbc8-4436-ba22-51360981ab48
ms.openlocfilehash: 0406ef7a32678bd149c0024348a7adf1f0b72926
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/09/2020
ms.locfileid: "96982808"
---
# <a name="how-to-show-a-color-palette-with-the-colordialog-component"></a><span data-ttu-id="8bf5f-102">方法: ColorDialog コンポーネントを使用してカラー パレットを表示する</span><span class="sxs-lookup"><span data-stu-id="8bf5f-102">How to: Show a Color Palette with the ColorDialog Component</span></span>
<span data-ttu-id="8bf5f-103">[ColorDialog](colordialog-component-windows-forms.md)コンポーネントは、色のパレットを表示し、ユーザーが選択した色を含むプロパティを返します。</span><span class="sxs-lookup"><span data-stu-id="8bf5f-103">The [ColorDialog](colordialog-component-windows-forms.md) component displays a palette of colors and returns a property containing the color the user has selected.</span></span>  
  
### <a name="to-choose-a-color-using-the-colordialog-component"></a><span data-ttu-id="8bf5f-104">ColorDialog コンポーネントを使用して色を選択するには</span><span class="sxs-lookup"><span data-stu-id="8bf5f-104">To choose a color using the ColorDialog component</span></span>  
  
1. <span data-ttu-id="8bf5f-105">メソッドを使用してダイアログボックスを表示し <xref:System.Windows.Forms.CommonDialog.ShowDialog%2A> ます。</span><span class="sxs-lookup"><span data-stu-id="8bf5f-105">Display the dialog box using the <xref:System.Windows.Forms.CommonDialog.ShowDialog%2A> method.</span></span>  
  
2. <span data-ttu-id="8bf5f-106">プロパティを使用して、 <xref:System.Windows.Forms.DialogResult> ダイアログボックスがどのように閉じられたかを確認します。</span><span class="sxs-lookup"><span data-stu-id="8bf5f-106">Use the <xref:System.Windows.Forms.DialogResult> property to determine how the dialog box was closed.</span></span>  
  
3. <span data-ttu-id="8bf5f-107">コンポーネントのプロパティを使用して、 <xref:System.Windows.Forms.ColorDialog.Color%2A> <xref:System.Windows.Forms.ColorDialog> 選択した色を設定します。</span><span class="sxs-lookup"><span data-stu-id="8bf5f-107">Use the <xref:System.Windows.Forms.ColorDialog.Color%2A> property of the <xref:System.Windows.Forms.ColorDialog> component to set the chosen color.</span></span>  
  
     <span data-ttu-id="8bf5f-108">次の例では、 <xref:System.Windows.Forms.Button> コントロールの <xref:System.Windows.Forms.Control.Click> イベントハンドラーによってコンポーネントが開かれ <xref:System.Windows.Forms.ColorDialog> ます。</span><span class="sxs-lookup"><span data-stu-id="8bf5f-108">In the example below, the <xref:System.Windows.Forms.Button> control's <xref:System.Windows.Forms.Control.Click> event handler opens a <xref:System.Windows.Forms.ColorDialog> component.</span></span> <span data-ttu-id="8bf5f-109">色が選択され、ユーザーが **[OK]** をクリックすると、 <xref:System.Windows.Forms.Button> コントロールの背景色が、選択した色に設定されます。</span><span class="sxs-lookup"><span data-stu-id="8bf5f-109">When a color is chosen and the user clicks **OK**, the <xref:System.Windows.Forms.Button> control's background color is set to the chosen color.</span></span> <span data-ttu-id="8bf5f-110">この例では、フォームにコントロールとコンポーネントがあることを前提としてい <xref:System.Windows.Forms.Button> <xref:System.Windows.Forms.ColorDialog> ます。</span><span class="sxs-lookup"><span data-stu-id="8bf5f-110">The example assumes your form has a <xref:System.Windows.Forms.Button> control and a <xref:System.Windows.Forms.ColorDialog> component.</span></span>  
  
    ```vb  
    Private Sub Button1_Click(ByVal sender As System.Object, _  
    ByVal e As System.EventArgs) Handles Button1.Click  
       If ColorDialog1.ShowDialog() = DialogResult.OK Then  
          Button1.BackColor = ColorDialog1.Color  
       End If  
    End Sub  
    ```  
  
    ```csharp  
    private void button1_Click(object sender, System.EventArgs e)  
    {  
       if(colorDialog1.ShowDialog() == DialogResult.OK)  
       {  
          button1.BackColor = colorDialog1.Color;  
       }  
    }  
    ```  
  
    ```cpp  
    private:  
       void button1_Click(System::Object ^ sender,
          System::EventArgs ^ e)  
       {  
          if(colorDialog1->ShowDialog() == DialogResult::OK)  
          {  
             button1->BackColor = colorDialog1->Color;  
          }  
       }  
    ```  
  
     <span data-ttu-id="8bf5f-111">(Visual C#、Visual C++)フォームのコンストラクターに次のコードを配置して、イベントハンドラーを登録します。</span><span class="sxs-lookup"><span data-stu-id="8bf5f-111">(Visual C#, Visual C++) Place the following code in the form's constructor to register the event handler.</span></span>  
  
    ```csharp  
    this.button1.Click += new System.EventHandler(this.button1_Click);  
    ```  
  
    ```cpp  
    this->button1->Click +=
       gcnew System::EventHandler(this, &Form1::button1_Click);  
    ```  
  
## <a name="see-also"></a><span data-ttu-id="8bf5f-112">関連項目</span><span class="sxs-lookup"><span data-stu-id="8bf5f-112">See also</span></span>

- <xref:System.Windows.Forms.ColorDialog>
- [<span data-ttu-id="8bf5f-113">ColorDialog コンポーネント</span><span class="sxs-lookup"><span data-stu-id="8bf5f-113">ColorDialog Component</span></span>](colordialog-component-windows-forms.md)
