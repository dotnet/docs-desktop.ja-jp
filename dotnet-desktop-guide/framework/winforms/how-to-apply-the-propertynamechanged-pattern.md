---
title: '方法: PropertyNameChanged パターンを適用する'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- custom controls [Windows Forms], property changes (using code)
- data binding [Windows Forms], custom controls
- PropertyNameChanged pattern [Windows Forms], applying
ms.assetid: aa47ddf6-5223-40c4-833f-a78992194836
ms.openlocfilehash: 01afa713e97206ea192ba55dc2affad20163f872
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/09/2020
ms.locfileid: "96974366"
---
# <a name="how-to-apply-the-propertynamechanged-pattern"></a><span data-ttu-id="b081f-102">方法: PropertyNameChanged パターンを適用する</span><span class="sxs-lookup"><span data-stu-id="b081f-102">How to: Apply the PropertyNameChanged Pattern</span></span>
<span data-ttu-id="b081f-103">次のコード例は、 *PropertyName* Changed パターンをカスタムコントロールに適用する方法を示しています。</span><span class="sxs-lookup"><span data-stu-id="b081f-103">The following code example demonstrates how to apply the *PropertyName* Changed pattern to a custom control.</span></span> <span data-ttu-id="b081f-104">Windows フォームデータバインディングエンジンで使用されるカスタムコントロールを実装するときに、このパターンを適用します。</span><span class="sxs-lookup"><span data-stu-id="b081f-104">Apply this pattern when you implement custom controls that are used with the Windows Forms data binding engine.</span></span>  
  
## <a name="example"></a><span data-ttu-id="b081f-105">例</span><span class="sxs-lookup"><span data-stu-id="b081f-105">Example</span></span>  
 [!code-csharp[System.Windows.Forms.ChangeNotification#3](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.ChangeNotification/CS/Form1.cs#3)]
 [!code-vb[System.Windows.Forms.ChangeNotification#3](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.ChangeNotification/VB/Form1.vb#3)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="b081f-106">コードのコンパイル</span><span class="sxs-lookup"><span data-stu-id="b081f-106">Compiling the Code</span></span>  
 <span data-ttu-id="b081f-107">前のコード例をコンパイルするには、次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="b081f-107">To compile the previous code example:</span></span>  
  
- <span data-ttu-id="b081f-108">コードを空のコードファイルに貼り付けます。</span><span class="sxs-lookup"><span data-stu-id="b081f-108">Paste the code into an empty code file.</span></span> <span data-ttu-id="b081f-109">カスタムコントロールは、メソッドを含む Windows フォームで使用する必要があり `Main` ます。</span><span class="sxs-lookup"><span data-stu-id="b081f-109">You must use the custom control on a Windows Form that contains a `Main` method.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b081f-110">関連項目</span><span class="sxs-lookup"><span data-stu-id="b081f-110">See also</span></span>

- [<span data-ttu-id="b081f-111">方法: INotifyPropertyChanged インターフェイスを実装する</span><span class="sxs-lookup"><span data-stu-id="b081f-111">How to: Implement the INotifyPropertyChanged Interface</span></span>](how-to-implement-the-inotifypropertychanged-interface.md)
- [<span data-ttu-id="b081f-112">Windows フォーム データ バインディングの変更通知</span><span class="sxs-lookup"><span data-stu-id="b081f-112">Change Notification in Windows Forms Data Binding</span></span>](change-notification-in-windows-forms-data-binding.md)
- [<span data-ttu-id="b081f-113">Windows フォームでのデータ バインディング</span><span class="sxs-lookup"><span data-stu-id="b081f-113">Windows Forms Data Binding</span></span>](windows-forms-data-binding.md)
