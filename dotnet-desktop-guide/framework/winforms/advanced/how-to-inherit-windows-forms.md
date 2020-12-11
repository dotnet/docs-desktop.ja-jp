---
title: フォームの継承
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- inherited forms [Windows Forms], creating at run-time
- inheritance [Windows Forms], forms
- Windows Forms, inheritance
ms.assetid: cb3e1c0f-3d2a-4cdc-b0d1-c92eae567ffb
ms.openlocfilehash: d016eb52802a729ef3b41a1140cae3d64022d403
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/09/2020
ms.locfileid: "96981331"
---
# <a name="how-to-inherit-windows-forms"></a><span data-ttu-id="b1cc2-102">方法: Windows フォームを継承する</span><span class="sxs-lookup"><span data-stu-id="b1cc2-102">How to: Inherit Windows Forms</span></span>

<span data-ttu-id="b1cc2-103">新規の Windows フォームは、基本フォームから継承して簡単に複製できます。フォームが必要になるたびに、最初から作成し直す必要はありません。</span><span class="sxs-lookup"><span data-stu-id="b1cc2-103">Creating new Windows Forms by inheriting from base forms is a handy way to duplicate your best efforts without going through the process of entirely recreating a form every time you require it.</span></span>

<span data-ttu-id="b1cc2-104">デザイン時に **[継承ピッカー]** ダイアログ ボックスを使用してフォームを継承する方法、および継承されるコントロールのセキュリティ レベルを視覚的に区別する方法の詳細については、「[方法: [継承ピッカー] ダイアログ ボックスを使用してフォームを継承する](how-to-inherit-forms-using-the-inheritance-picker-dialog-box.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="b1cc2-104">For more information about inheriting forms at design time using the **Inheritance Picker** dialog box and how to visually distinguish between security levels of inherited controls, see [How to: Inherit Forms Using the Inheritance Picker Dialog Box](how-to-inherit-forms-using-the-inheritance-picker-dialog-box.md).</span></span>

> [!NOTE]
> <span data-ttu-id="b1cc2-105">フォームを継承するには、そのフォームを含むファイルまたは名前空間が、実行可能ファイルまたは DLL に組み込まれている必要があります。</span><span class="sxs-lookup"><span data-stu-id="b1cc2-105">In order to inherit from a form, the file or namespace containing that form must have been built into an executable file or DLL.</span></span> <span data-ttu-id="b1cc2-106">プロジェクトをビルドするには、**[ビルド]** メニューの **[ビルド]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="b1cc2-106">To build the project, choose **Build** from the **Build** menu.</span></span> <span data-ttu-id="b1cc2-107">また、フォームの継承先となるクラスに、名前空間への参照を追加する必要があります。</span><span class="sxs-lookup"><span data-stu-id="b1cc2-107">Also, a reference to the namespace must be added to the class inheriting the form.</span></span>

## <a name="inherit-a-form-programmatically"></a><span data-ttu-id="b1cc2-108">プログラムによるフォームの継承</span><span class="sxs-lookup"><span data-stu-id="b1cc2-108">Inherit a form programmatically</span></span>

1. <span data-ttu-id="b1cc2-109">クラスに、継承元のフォームを含む名前空間への参照を追加します。</span><span class="sxs-lookup"><span data-stu-id="b1cc2-109">In your class, add a reference to the namespace containing the form you wish to inherit from.</span></span>

2. <span data-ttu-id="b1cc2-110">クラス定義に、継承元のフォームへの参照を追加します。</span><span class="sxs-lookup"><span data-stu-id="b1cc2-110">In the class definition, add a reference to the form to inherit from.</span></span> <span data-ttu-id="b1cc2-111">参照では、フォームを含んでいる名前空間を指定し、その後にピリオド、続いて基本フォーム自体の名前を指定します。</span><span class="sxs-lookup"><span data-stu-id="b1cc2-111">The reference should include the namespace that contains the form, followed by a period, then the name of the base form itself.</span></span>

    ```vb
    Public Class Form2
        Inherits Namespace1.Form1
    ```

    ```csharp
    public class Form2 : Namespace1.Form1
    ```

 <span data-ttu-id="b1cc2-112">フォームを継承する場合は、イベント ハンドラーが 2 回呼び出されることで問題が発生する可能性があることに注意してください。これは、各イベントが基底クラスと継承クラスの両方によって処理されるためです。</span><span class="sxs-lookup"><span data-stu-id="b1cc2-112">When inheriting forms, keep in mind that issues may arise with regard to event handlers being called twice, because each event is being handled by both the base class and the inherited class.</span></span> <span data-ttu-id="b1cc2-113">この問題を回避する方法の詳細については、「[Visual Basic で継承されたイベント ハンドラーのトラブルシューティング](/dotnet/visual-basic/programming-guide/language-features/events/troubleshooting-inherited-event-handlers)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="b1cc2-113">For more information on how to avoid this problem, see [Troubleshooting Inherited Event Handlers in Visual Basic](/dotnet/visual-basic/programming-guide/language-features/events/troubleshooting-inherited-event-handlers).</span></span>

## <a name="see-also"></a><span data-ttu-id="b1cc2-114">関連項目</span><span class="sxs-lookup"><span data-stu-id="b1cc2-114">See also</span></span>

- [<span data-ttu-id="b1cc2-115">Inherits ステートメント</span><span class="sxs-lookup"><span data-stu-id="b1cc2-115">Inherits Statement</span></span>](/dotnet/visual-basic/language-reference/statements/inherits-statement)
- [<span data-ttu-id="b1cc2-116">Imports ステートメント (.NET 名前空間および型)</span><span class="sxs-lookup"><span data-stu-id="b1cc2-116">Imports Statement (.NET Namespace and Type)</span></span>](/dotnet/visual-basic/language-reference/statements/imports-statement-net-namespace-and-type)
- [<span data-ttu-id="b1cc2-117">using</span><span class="sxs-lookup"><span data-stu-id="b1cc2-117">using</span></span>](/dotnet/csharp/language-reference/keywords/using)
- [<span data-ttu-id="b1cc2-118">基本フォームの外観を変更した場合の影響</span><span class="sxs-lookup"><span data-stu-id="b1cc2-118">Effects of Modifying a Base Form's Appearance</span></span>](effects-of-modifying-base-form-appearance.md)
- [<span data-ttu-id="b1cc2-119">Windows フォームのビジュアルの継承</span><span class="sxs-lookup"><span data-stu-id="b1cc2-119">Windows Forms Visual Inheritance</span></span>](windows-forms-visual-inheritance.md)
