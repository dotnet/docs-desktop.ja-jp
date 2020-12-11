---
title: ラベルコントロールでアクセスキーを作成する
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- controls [Windows Forms], access keys
- dialog box controls [Windows Forms], mnemonics
- access keys [Windows Forms], creating for controls
- Label control [Windows Forms], creating access keys
- mnemonics [Windows Forms], adding to dialog box controls
- mnemonics
- Windows Forms controls, access keys
- UseMnemonic property [Windows Forms], Label control
- keyboard shortcuts [Windows Forms], creating for controls
- access keys [Windows Forms], Windows Forms
ms.assetid: 5ee8f823-80be-4a4f-96a4-412671e2e306
ms.openlocfilehash: 800afc03e71435e2721456b93bb9704af01f714a
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/09/2020
ms.locfileid: "96980907"
---
# <a name="how-to-create-access-keys-with-windows-forms-label-controls"></a><span data-ttu-id="3c36e-102">方法: Windows フォームの Label コントロールでアクセス キーを作成する</span><span class="sxs-lookup"><span data-stu-id="3c36e-102">How to: Create Access Keys with Windows Forms Label Controls</span></span>
<span data-ttu-id="3c36e-103">Windows フォーム <xref:System.Windows.Forms.Label> コントロールを使用して、他のコントロールのアクセスキーを定義できます。</span><span class="sxs-lookup"><span data-stu-id="3c36e-103">Windows Forms <xref:System.Windows.Forms.Label> controls can be used to define access keys for other controls.</span></span> <span data-ttu-id="3c36e-104">ラベルコントロールでアクセスキーを定義すると、ユーザーは ALT キーと指定した文字を押して、タブオーダーでその後のコントロールにフォーカスを移動できます。</span><span class="sxs-lookup"><span data-stu-id="3c36e-104">When you define an access key in a label control, the user can press the ALT key plus the character you designate to move the focus to the control that follows it in the tab order.</span></span> <span data-ttu-id="3c36e-105">ラベルはフォーカスを受け取ることができないため、フォーカスはタブオーダーの次のコントロールに自動的に移動します。</span><span class="sxs-lookup"><span data-stu-id="3c36e-105">Because labels cannot receive focus, focus automatically moves to the next control in the tab order.</span></span> <span data-ttu-id="3c36e-106">この手法を使用すると、テキストボックス、コンボボックス、リストボックス、およびデータグリッドにアクセスキーを割り当てることができます。</span><span class="sxs-lookup"><span data-stu-id="3c36e-106">Use this technique to assign access keys to text boxes, combo boxes, list boxes, and data grids.</span></span>  
  
### <a name="to-assign-an-access-key-to-a-control-with-a-label"></a><span data-ttu-id="3c36e-107">ラベルを持つコントロールにアクセスキーを割り当てるには</span><span class="sxs-lookup"><span data-stu-id="3c36e-107">To assign an access key to a control with a label</span></span>  
  
1. <span data-ttu-id="3c36e-108">まず、ラベルを描画してから、もう一方のコントロールを描画します。</span><span class="sxs-lookup"><span data-stu-id="3c36e-108">Draw the label first, and then draw the other control.</span></span>  
  
     <span data-ttu-id="3c36e-109">または</span><span class="sxs-lookup"><span data-stu-id="3c36e-109">-or-</span></span>  
  
     <span data-ttu-id="3c36e-110">コントロールを任意の順序で描画し、 <xref:System.Windows.Forms.Control.TabIndex%2A> ラベルのプロパティを他のコントロールよりも1小さい値に設定します。</span><span class="sxs-lookup"><span data-stu-id="3c36e-110">Draw the controls in any order and set the <xref:System.Windows.Forms.Control.TabIndex%2A> property of the label to one less than the other control.</span></span>  
  
2. <span data-ttu-id="3c36e-111">ラベルの <xref:System.Windows.Forms.Label.UseMnemonic%2A> プロパティをに設定し `true` ます。</span><span class="sxs-lookup"><span data-stu-id="3c36e-111">Set the label's <xref:System.Windows.Forms.Label.UseMnemonic%2A> property to `true`.</span></span>  
  
3. <span data-ttu-id="3c36e-112">ラベルのプロパティにアンパサンド (&) を使用して、 <xref:System.Windows.Forms.Label.Text%2A> ラベルのアクセスキーを割り当てます。</span><span class="sxs-lookup"><span data-stu-id="3c36e-112">Use an ampersand (&) in the label's <xref:System.Windows.Forms.Label.Text%2A> property to assign the access key for the label.</span></span> <span data-ttu-id="3c36e-113">詳細については、「 [Windows フォームコントロールのアクセスキーの作成](how-to-create-access-keys-for-windows-forms-controls.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="3c36e-113">For more information, see [Creating Access Keys for Windows Forms Controls](how-to-create-access-keys-for-windows-forms-controls.md).</span></span>  
  
    > [!NOTE]
    > <span data-ttu-id="3c36e-114">アンパサンドは、アクセスキーの作成に使用するのではなく、ラベルコントロールに表示することができます。</span><span class="sxs-lookup"><span data-stu-id="3c36e-114">You may want to display ampersands in a label control, rather than use them to create access keys.</span></span> <span data-ttu-id="3c36e-115">これは、データにアンパサンドが含まれているレコードセット内のフィールドにラベルコントロールをバインドした場合に発生する可能性があります。</span><span class="sxs-lookup"><span data-stu-id="3c36e-115">This may occur if you bind a label control to a field in a recordset where the data includes ampersands.</span></span> <span data-ttu-id="3c36e-116">ラベルコントロールにアンパサンドを表示するには、 <xref:System.Windows.Forms.Label.UseMnemonic%2A> プロパティをに設定し `false` ます。</span><span class="sxs-lookup"><span data-stu-id="3c36e-116">To display ampersands in a label control, set the <xref:System.Windows.Forms.Label.UseMnemonic%2A> property to `false`.</span></span> <span data-ttu-id="3c36e-117">アンパサンドを表示し、アクセスキーも持っている場合は、 <xref:System.Windows.Forms.Label.UseMnemonic%2A> プロパティをに設定 `true` し、1つのアンパサンド (&) とアンパサンドを2つのアンパサンドで表示するようにアクセスキーを指定します。</span><span class="sxs-lookup"><span data-stu-id="3c36e-117">If you wish to display ampersands and also have an access key, set the <xref:System.Windows.Forms.Label.UseMnemonic%2A> property to `true` and indicate the access key with one ampersand (&) and the ampersand to display with two ampersands.</span></span>  
  
    ```vb  
    Label1.UseMnemonic = True  
    Label1.Text = "&Print"  
    Label2.UseMnemonic = True  
    Label2.Text = "&Copy && Paste"  
    ```  
  
    ```csharp  
    label1.UseMnemonic = true;  
    label1.Text = "&Print";  
    label2.UseMnemonic = true;  
    label2.Text = "&Copy && Paste";  
    ```  
  
    ```cpp  
    label1->UseMnemonic = true;  
    label1->Text = "&Print";  
    label2->UseMnemonic = true;  
    label2->Text = "&Copy && Paste";  
    ```  
  
## <a name="see-also"></a><span data-ttu-id="3c36e-118">関連項目</span><span class="sxs-lookup"><span data-stu-id="3c36e-118">See also</span></span>

- [<span data-ttu-id="3c36e-119">方法: Windows フォーム Label コントロールのサイズを内容に合わせて変更する</span><span class="sxs-lookup"><span data-stu-id="3c36e-119">How to: Size a Windows Forms Label Control to Fit Its Contents</span></span>](how-to-size-a-windows-forms-label-control-to-fit-its-contents.md)
- [<span data-ttu-id="3c36e-120">Label コントロールの概要</span><span class="sxs-lookup"><span data-stu-id="3c36e-120">Label Control Overview</span></span>](label-control-overview-windows-forms.md)
- [<span data-ttu-id="3c36e-121">Label コントロール</span><span class="sxs-lookup"><span data-stu-id="3c36e-121">Label Control</span></span>](label-control-windows-forms.md)
