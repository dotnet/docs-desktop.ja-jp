---
title: コントロールによって表示されるイメージを設定する
ms.date: 08/20/2019
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- Button control [Windows Forms], images
- Windows Forms controls, images
- controls [Windows Forms], images
- images [Windows Forms], Windows Forms controls
- examples [Windows Forms], controls
ms.assetid: 9445af8f-4f62-48b0-a3f6-068058964b9f
ms.openlocfilehash: 5df0068c8462bbaab0cb0135de1dd1b91ababe06
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/09/2020
ms.locfileid: "96983044"
---
# <a name="how-to-set-the-image-displayed-by-a-windows-forms-control"></a><span data-ttu-id="175ff-102">方法: Windows フォームコントロールによって表示されるイメージを設定する</span><span class="sxs-lookup"><span data-stu-id="175ff-102">How to: Set the image displayed by a Windows Forms control</span></span>

<span data-ttu-id="175ff-103">いくつかの Windows フォームコントロールでイメージを表示できます。</span><span class="sxs-lookup"><span data-stu-id="175ff-103">Several Windows Forms controls can display images.</span></span> <span data-ttu-id="175ff-104">これらのイメージは、[保存] コマンドを示すボタン上のフロッピーディスクアイコンなど、コントロールの目的を明確にするアイコンにすることができます。</span><span class="sxs-lookup"><span data-stu-id="175ff-104">These images can be icons that clarify the purpose of the control, such as a diskette icon on a button denoting the Save command.</span></span> <span data-ttu-id="175ff-105">または、アイコンに背景画像を使用して、コントロールの外観と動作を指定することもできます。</span><span class="sxs-lookup"><span data-stu-id="175ff-105">Alternatively, the icons can be background images to give the control the appearance and behavior you want.</span></span>

## <a name="programmatic"></a><span data-ttu-id="175ff-106">プログラムによる</span><span class="sxs-lookup"><span data-stu-id="175ff-106">Programmatic</span></span>

<span data-ttu-id="175ff-107">コントロールの `Image` プロパティまたは `BackgroundImage` プロパティを、型のオブジェクトに設定 <xref:System.Drawing.Image> します。</span><span class="sxs-lookup"><span data-stu-id="175ff-107">Set the control's `Image` or `BackgroundImage` property to an object of type <xref:System.Drawing.Image>.</span></span> <span data-ttu-id="175ff-108">通常は、メソッドを使用して、ファイルからイメージを読み込みます <xref:System.Drawing.Image.FromFile%2A> 。</span><span class="sxs-lookup"><span data-stu-id="175ff-108">Generally, you'll be loading the image from a file by using the <xref:System.Drawing.Image.FromFile%2A> method.</span></span>

<span data-ttu-id="175ff-109">次のコード例では、イメージの場所に設定されているパスが **[マイピクチャ** ] フォルダーです。</span><span class="sxs-lookup"><span data-stu-id="175ff-109">In the following code example, the path set for the location of the image is the **My Pictures** folder.</span></span> <span data-ttu-id="175ff-110">Windows オペレーティングシステムを実行しているほとんどのコンピューターには、このディレクトリが含まれています。</span><span class="sxs-lookup"><span data-stu-id="175ff-110">Most computers running the Windows operating system include this directory.</span></span> <span data-ttu-id="175ff-111">これにより、最小限のシステムアクセスレベルを持つユーザーも、アプリケーションを安全に実行できます。</span><span class="sxs-lookup"><span data-stu-id="175ff-111">This also enables users with minimal system access levels to run the application safely.</span></span> <span data-ttu-id="175ff-112">次のコード例では、コントロールが追加されたフォームが既に存在している必要があり <xref:System.Windows.Forms.PictureBox> ます。</span><span class="sxs-lookup"><span data-stu-id="175ff-112">The following code example requires that you already have a form with a <xref:System.Windows.Forms.PictureBox> control added.</span></span>

```vb
' Replace the image named below with your own icon.
PictureBox1.Image = Image.FromFile _
   (System.Environment.GetFolderPath _
   (System.Environment.SpecialFolder.MyPictures) _
   & "\Image.gif")
```

```csharp
// Replace the image named below with your own icon.
// Note the escape character used (@) when specifying the path.
pictureBox1.Image = Image.FromFile
   (System.Environment.GetFolderPath
   (System.Environment.SpecialFolder.MyPictures)
   + @"\Image.gif");
```

```cpp
// Replace the image named below with your own icon.
pictureBox1->Image = Image::FromFile(String::Concat
   (System::Environment::GetFolderPath
   (System::Environment::SpecialFolder::MyPictures),
   "\\Image.gif"));
```

## <a name="designer"></a><span data-ttu-id="175ff-113">Designer</span><span class="sxs-lookup"><span data-stu-id="175ff-113">Designer</span></span>

1. <span data-ttu-id="175ff-114">Visual Studio の [ **プロパティ** ] ウィンドウで、コントロールの **Image** または **BackgroundImage** プロパティを選択し、省略記号 ( ![ visual Studio の省略記号) を選択して [リソースの ](./media/visual-studio-ellipsis-button.png) **選択** ] ダイアログボックスを表示します。</span><span class="sxs-lookup"><span data-stu-id="175ff-114">In the **Properties** window of Visual Studio, select the **Image** or **BackgroundImage** property of the control, and then select the ellipsis (![Ellipsis button in Visual Studio](./media/visual-studio-ellipsis-button.png)) to display the **Select Resource** dialog box.</span></span>

2. <span data-ttu-id="175ff-115">表示するイメージを選択します。</span><span class="sxs-lookup"><span data-stu-id="175ff-115">Select the image you want to display.</span></span>

## <a name="see-also"></a><span data-ttu-id="175ff-116">関連項目</span><span class="sxs-lookup"><span data-stu-id="175ff-116">See also</span></span>

- <xref:System.Drawing.Image.FromFile%2A>
- <xref:System.Drawing.Image>
- <xref:System.Windows.Forms.Control.BackgroundImage%2A>
