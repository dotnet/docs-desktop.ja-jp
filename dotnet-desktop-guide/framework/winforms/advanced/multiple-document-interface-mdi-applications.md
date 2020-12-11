---
title: マルチ ドキュメント インターフェイス (MDI) アプリケーション
description: マルチドキュメントインターフェイス (MDI) アプリケーションを使用して複数のドキュメントを同時に表示する Windows フォーム方法について説明します。各ドキュメントは、それぞれのウィンドウに表示されます。
ms.date: 03/30/2017
helpviewer_keywords:
- forms [Windows Forms], MDI
- windows [Windows Forms], mDI
- Windows Forms, MDI applications
- MDI
ms.assetid: 599faf75-13cf-49cc-ad3c-255545e5cb97
ms.openlocfilehash: 0912a989ac1710d72c9db1cceb0e695f0ca85dee
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/09/2020
ms.locfileid: "96981675"
---
# <a name="multiple-document-interface-mdi-applications"></a><span data-ttu-id="3f092-103">マルチ ドキュメント インターフェイス (MDI) アプリケーション</span><span class="sxs-lookup"><span data-stu-id="3f092-103">Multiple-Document Interface (MDI) Applications</span></span>
<span data-ttu-id="3f092-104">マルチドキュメントインターフェイス (MDI) アプリケーションを使用すると、複数のドキュメントを同時に表示することができ、各ドキュメントは独自のウィンドウに表示されます。</span><span class="sxs-lookup"><span data-stu-id="3f092-104">Multiple-document interface (MDI) applications enable you to display multiple documents at the same time, with each document displayed in its own window.</span></span> <span data-ttu-id="3f092-105">MDI アプリケーションには、多くの場合、ウィンドウまたはドキュメントを切り替えるためのサブメニューを含む [ウィンドウ] メニュー項目があります。</span><span class="sxs-lookup"><span data-stu-id="3f092-105">MDI applications often have a Window menu item with submenus for switching between windows or documents.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="3f092-106">Windows フォームの MDI フォームとシングルドキュメントインターフェイス (SDI) ウィンドウには、いくつかの動作の違いがあります。</span><span class="sxs-lookup"><span data-stu-id="3f092-106">There are some behavior differences between MDI forms and single-document interface (SDI) windows in Windows Forms.</span></span> <span data-ttu-id="3f092-107">プロパティは、 `Opacity` MDI 子フォームの外観には影響しません。</span><span class="sxs-lookup"><span data-stu-id="3f092-107">The `Opacity` property does not affect the appearance of MDI child forms.</span></span> <span data-ttu-id="3f092-108">また、メソッドは、 <xref:System.Windows.Forms.Form.CenterToParent%2A> MDI 子フォームの動作には影響しません。</span><span class="sxs-lookup"><span data-stu-id="3f092-108">Additionally, the <xref:System.Windows.Forms.Form.CenterToParent%2A> method does not affect the behavior of MDI child forms.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="3f092-109">このセクションの内容</span><span class="sxs-lookup"><span data-stu-id="3f092-109">In This Section</span></span>  
 [<span data-ttu-id="3f092-110">方法: MDI 親フォームを作成する</span><span class="sxs-lookup"><span data-stu-id="3f092-110">How to: Create MDI Parent Forms</span></span>](how-to-create-mdi-parent-forms.md)  
 <span data-ttu-id="3f092-111">MDI アプリケーション内の複数のドキュメントのコンテナーを作成する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="3f092-111">Gives directions for creating the container for the multiple documents within an MDI application.</span></span>  
  
 [<span data-ttu-id="3f092-112">方法: MDI 子フォームを作成する</span><span class="sxs-lookup"><span data-stu-id="3f092-112">How to: Create MDI Child Forms</span></span>](how-to-create-mdi-child-forms.md)  
 <span data-ttu-id="3f092-113">MDI 親フォーム内で動作する1つまたは複数のウィンドウを作成する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="3f092-113">Gives directions for creating one or more windows that operate within an MDI parent form.</span></span>  
  
 [<span data-ttu-id="3f092-114">方法: アクティブな MDI 子フォームを特定する</span><span class="sxs-lookup"><span data-stu-id="3f092-114">How to: Determine the Active MDI Child</span></span>](how-to-determine-the-active-mdi-child.md)  
 <span data-ttu-id="3f092-115">フォーカスのある子ウィンドウを確認し、その内容をクリップボードに送信する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="3f092-115">Gives directions for verifying the child window that has focus (and sending its contents to the Clipboard).</span></span>  
  
 [<span data-ttu-id="3f092-116">方法: アクティブな MDI 子フォームにデータを送信する</span><span class="sxs-lookup"><span data-stu-id="3f092-116">How to: Send Data to the Active MDI Child</span></span>](how-to-send-data-to-the-active-mdi-child.md)  
 <span data-ttu-id="3f092-117">アクティブな子ウィンドウに情報を転送する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="3f092-117">Gives directions for transporting information to the active child window.</span></span>  
  
 [<span data-ttu-id="3f092-118">方法: MDI 子フォームを配置する</span><span class="sxs-lookup"><span data-stu-id="3f092-118">How to: Arrange MDI Child Forms</span></span>](how-to-arrange-mdi-child-forms.md)  
 <span data-ttu-id="3f092-119">MDI アプリケーションの子ウィンドウを並べて配置したり、整列したりするための手順を示します。</span><span class="sxs-lookup"><span data-stu-id="3f092-119">Gives directions for tiling, cascading, or arranging the child windows of an MDI application.</span></span>
