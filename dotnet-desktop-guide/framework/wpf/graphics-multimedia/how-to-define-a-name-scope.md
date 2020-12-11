---
title: '方法: 名前のスコープを定義する'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- name scope [WPF], defining
- Storyboards [WPF], animating in procedural code
- animation [WPF], Storyboards [WPF], in procedural code
ms.assetid: 4f361925-6a08-40dc-8231-a61111c6b28b
ms.openlocfilehash: a03f477dd31909e8cb9dde9cd29da6f38d665758
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/09/2020
ms.locfileid: "96974472"
---
# <a name="how-to-define-a-name-scope"></a><span data-ttu-id="b1644-102">方法: 名前のスコープを定義する</span><span class="sxs-lookup"><span data-stu-id="b1644-102">How to: Define a Name Scope</span></span>
<span data-ttu-id="b1644-103">コードで <xref:System.Windows.Media.Animation.Storyboard> を使用してアニメーション化を行うには、<xref:System.Windows.NameScope> を作成し、その名前のスコープを所有する要素にターゲット オブジェクトの名前を登録する必要があります。</span><span class="sxs-lookup"><span data-stu-id="b1644-103">To animate with <xref:System.Windows.Media.Animation.Storyboard> in code, you must create a <xref:System.Windows.NameScope> and register the target objects' names with the element that owns that name scope.</span></span> <span data-ttu-id="b1644-104">次の例では、`myMainPanel` に <xref:System.Windows.NameScope> が作成されています。</span><span class="sxs-lookup"><span data-stu-id="b1644-104">In the following example, a <xref:System.Windows.NameScope> is created for `myMainPanel`.</span></span> <span data-ttu-id="b1644-105">パネルには、`button1` と `button2` の 2 つのボタンが追加され、その名前が登録されています。</span><span class="sxs-lookup"><span data-stu-id="b1644-105">Two buttons, `button1` and `button2`, are added to the panel, and their names registered.</span></span> <span data-ttu-id="b1644-106">いくつかのアニメーションと <xref:System.Windows.Media.Animation.Storyboard> が作成されています。</span><span class="sxs-lookup"><span data-stu-id="b1644-106">Several animations and a <xref:System.Windows.Media.Animation.Storyboard> are created.</span></span> <span data-ttu-id="b1644-107">アニメーションの開始には、ストーリーボードの <xref:System.Windows.Media.Animation.Storyboard.Begin%2A> メソッドが使用されています。</span><span class="sxs-lookup"><span data-stu-id="b1644-107">The storyboard's <xref:System.Windows.Media.Animation.Storyboard.Begin%2A> method is used to start the animations.</span></span>  
  
 <span data-ttu-id="b1644-108">`button1`、`button2`、および `myMainPanel` の名前のスコープは同じであるため、そのいずれかと <xref:System.Windows.Media.Animation.Storyboard><xref:System.Windows.Media.Animation.Storyboard.Begin%2A> メソッドを使用して、アニメーションを開始できます。</span><span class="sxs-lookup"><span data-stu-id="b1644-108">Because `button1`, `button2`, and `myMainPanel` all share the same name scope, any one of them can be used with the <xref:System.Windows.Media.Animation.Storyboard> <xref:System.Windows.Media.Animation.Storyboard.Begin%2A> method to start the animations.</span></span>  
  
## <a name="example"></a><span data-ttu-id="b1644-109">例</span><span class="sxs-lookup"><span data-stu-id="b1644-109">Example</span></span>  
 [!code-csharp[StoryboardBeginAnimation_procedural_snip#NameScopeExample](~/samples/snippets/csharp/VS_Snippets_Wpf/StoryboardBeginAnimation_procedural_snip/CSharp/ScopeExample.cs#namescopeexample)]
 [!code-vb[StoryboardBeginAnimation_procedural_snip#NameScopeExample](~/samples/snippets/visualbasic/VS_Snippets_Wpf/StoryboardBeginAnimation_procedural_snip/visualbasic/scopeexample.vb#namescopeexample)]  
  
## <a name="see-also"></a><span data-ttu-id="b1644-110">関連項目</span><span class="sxs-lookup"><span data-stu-id="b1644-110">See also</span></span>

- [<span data-ttu-id="b1644-111">ストーリーボードを使ってプロパティをアニメーション化する</span><span class="sxs-lookup"><span data-stu-id="b1644-111">Animate a Property by Using a Storyboard</span></span>](how-to-animate-a-property-by-using-a-storyboard.md)
- [<span data-ttu-id="b1644-112">アニメーションの概要</span><span class="sxs-lookup"><span data-stu-id="b1644-112">Animation Overview</span></span>](animation-overview.md)
