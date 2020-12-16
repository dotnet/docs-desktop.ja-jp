---
title: コントロールにイメージを表示する
description: Windows フォーム コントロールにイメージを表示する方法について説明します。 PictureBox などの多くのコントロールでは、イメージを表示することができます。
ms.date: 10/26/2020
dev_langs:
- csharp
- vb
helpviewer_keywords:
- Button control [Windows Forms], images
- Windows Forms controls, images
- controls [Windows Forms], images
- images [Windows Forms], Windows Forms contr ols
- examples [Windows Forms], controls
ms.openlocfilehash: a0b95d51f852df4c9ddc190903369faa41f7deae
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/09/2020
ms.locfileid: "96942238"
---
# <a name="how-to-display-an-image-on-a-control-windows-forms-net"></a><span data-ttu-id="9b211-104">コントロールにイメージを表示する方法 (Windows フォーム .NET)</span><span class="sxs-lookup"><span data-stu-id="9b211-104">How to display an image on a control (Windows Forms .NET)</span></span>

<span data-ttu-id="9b211-105">いくつかの Windows フォーム コントロールでは、イメージを表示することができます。</span><span class="sxs-lookup"><span data-stu-id="9b211-105">Several Windows Forms controls can display images.</span></span> <span data-ttu-id="9b211-106">これらのイメージは、Save コマンドを示すボタンのフロッピー ディスク アイコンなど、コントロールの目的を明確化するアイコンである場合があります。</span><span class="sxs-lookup"><span data-stu-id="9b211-106">These images can be icons that clarify the purpose of the control, such as a diskette icon on a button denoting the Save command.</span></span> <span data-ttu-id="9b211-107">または、コントロールの外観と動作を表す背景イメージである場合があります。</span><span class="sxs-lookup"><span data-stu-id="9b211-107">Alternatively, the icons can be background images to give the control the appearance and behavior you want.</span></span>

[!INCLUDE [desktop guide under construction](../../includes/desktop-guide-preview-note.md)]

## <a name="designer"></a><span data-ttu-id="9b211-108">Designer</span><span class="sxs-lookup"><span data-stu-id="9b211-108">Designer</span></span>

<span data-ttu-id="9b211-109">Visual Studio の **[プロパティ]** ウィンドウで、コントロールの **Image** プロパティまたは **BackgroundImage** プロパティを選択し、省略記号 (![Visual Studio の省略記号ボタン](../media/visual-studio-ellipsis-button.png)) を選択して **[リソースの選択]** ダイアログ ボックスを表示し、表示するイメージを選択します。</span><span class="sxs-lookup"><span data-stu-id="9b211-109">In the **Properties** window of Visual Studio, select the **Image** or **BackgroundImage** property of the control, and then select the ellipsis (![Ellipsis button in Visual Studio](../media/visual-studio-ellipsis-button.png)) to display the **Select Resource** dialog box and then select the image you want to display.</span></span>

:::image type="content" source="media/how-to-add-a-picture-to-a-control/properties-image.png" alt-text="image プロパティが選択されたプロパティ ダイアログ":::

## <a name="programmatic"></a><span data-ttu-id="9b211-111">プログラムによる</span><span class="sxs-lookup"><span data-stu-id="9b211-111">Programmatic</span></span>

<span data-ttu-id="9b211-112">コントロールの `Image` プロパティまたは `BackgroundImage` プロパティを <xref:System.Drawing.Image> 型のオブジェクトに設定します。</span><span class="sxs-lookup"><span data-stu-id="9b211-112">Set the control's `Image` or `BackgroundImage` property to an object of type <xref:System.Drawing.Image>.</span></span> <span data-ttu-id="9b211-113">通常は、<xref:System.Drawing.Image.FromFile%2A> メソッドを使用して、ファイルからイメージを読み込みます。</span><span class="sxs-lookup"><span data-stu-id="9b211-113">Generally, you'll be loading the image from a file by using the <xref:System.Drawing.Image.FromFile%2A> method.</span></span>

<span data-ttu-id="9b211-114">次のコード例でイメージの場所として設定されているパスは、 **"マイ ピクチャ"** フォルダーです。</span><span class="sxs-lookup"><span data-stu-id="9b211-114">In the following code example, the path set for the location of the image is the **My Pictures** folder.</span></span> <span data-ttu-id="9b211-115">Windows オペレーティング システムが実行されているほとんどのコンピューターには、このディレクトリが含まれています。</span><span class="sxs-lookup"><span data-stu-id="9b211-115">Most computers running the Windows operating system include this directory.</span></span> <span data-ttu-id="9b211-116">これにより、システム アクセス レベルが最小限に設定されているユーザーも、アプリケーションを安全に実行できます。</span><span class="sxs-lookup"><span data-stu-id="9b211-116">This also enables users with minimal system access levels to run the application safely.</span></span> <span data-ttu-id="9b211-117">次のコード例では、<xref:System.Windows.Forms.PictureBox> コントロールが追加済みのフォームが必要です。</span><span class="sxs-lookup"><span data-stu-id="9b211-117">The following code example requires that you already have a form with a <xref:System.Windows.Forms.PictureBox> control added.</span></span>

```csharp
// Replace the image named below with your own icon.
// Note the escape character used (@) when specifying the path.
pictureBox1.Image = Image.FromFile
   (System.Environment.GetFolderPath
   (System.Environment.SpecialFolder.MyPictures)
   + @"\Image.gif");
```

```vb
' Replace the image named below with your own icon.
PictureBox1.Image = Image.FromFile _
   (System.Environment.GetFolderPath _
   (System.Environment.SpecialFolder.MyPictures) _
   & "\Image.gif")
```

## <a name="see-also"></a><span data-ttu-id="9b211-118">関連項目</span><span class="sxs-lookup"><span data-stu-id="9b211-118">See also</span></span>

- <xref:System.Drawing.Image.FromFile%2A>
- <xref:System.Drawing.Image>
- <xref:System.Windows.Forms.Control.BackgroundImage%2A>
