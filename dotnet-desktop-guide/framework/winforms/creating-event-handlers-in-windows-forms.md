---
title: イベントハンドラーの作成
description: Windows フォームのイベントを複数のハンドラーに割り当てる方法と、特定のイベントを処理するメソッドを動的に変更する方法について説明します。
ms.date: 03/30/2017
helpviewer_keywords:
- event handling [Windows Forms]
- Windows Forms controls, event handling
- Windows Forms, event handling
- events [Windows Forms], event handlers
- event handlers [Windows Forms]
ms.assetid: 6514e530-c6b8-489c-a8d2-eda7b7072701
ms.openlocfilehash: e4c60c79862fb88342b4f2f7b2f1b57d15782efb
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/09/2020
ms.locfileid: "96980014"
---
# <a name="creating-event-handlers-in-windows-forms"></a><span data-ttu-id="f8b60-103">Windows フォーム内でのイベント ハンドラーの作成</span><span class="sxs-lookup"><span data-stu-id="f8b60-103">Creating Event Handlers in Windows Forms</span></span>

<span data-ttu-id="f8b60-104">イベント ハンドラーは、ユーザーがボタンをクリックする、またはメッセージ キューがメッセージを受信するなどのイベントが発生したときに実行するアクションを決定する、コード内の手順です。</span><span class="sxs-lookup"><span data-stu-id="f8b60-104">An event handler is a procedure in your code that determines what actions are performed when an event occurs, such as when the user clicks a button or a message queue receives a message.</span></span> <span data-ttu-id="f8b60-105">イベントが発生すると、そのイベントを受信した一つまたは複数のイベント ハンドラーが実行されます。</span><span class="sxs-lookup"><span data-stu-id="f8b60-105">When an event is raised, the event handler or handlers that receive the event are executed.</span></span> <span data-ttu-id="f8b60-106">イベントは複数のハンドラーに割り当てられ、特定のイベントを処理するメソッドは動的に変更できます。</span><span class="sxs-lookup"><span data-stu-id="f8b60-106">Events can be assigned to multiple handlers, and the methods that handle particular events can be changed dynamically.</span></span> <span data-ttu-id="f8b60-107">また、Visual Studio の Windows フォームデザイナーを使用して、イベントハンドラーを作成することもできます。</span><span class="sxs-lookup"><span data-stu-id="f8b60-107">You can also use the Windows Forms Designer in Visual Studio to create event handlers.</span></span>

## <a name="in-this-section"></a><span data-ttu-id="f8b60-108">このセクションの内容</span><span class="sxs-lookup"><span data-stu-id="f8b60-108">In This Section</span></span>

 <span data-ttu-id="f8b60-109">[イベントの概要](events-overview-windows-forms.md)</span><span class="sxs-lookup"><span data-stu-id="f8b60-109">[Events Overview](events-overview-windows-forms.md)</span></span>\
 <span data-ttu-id="f8b60-110">イベント モデルおよびデリゲートの役割を説明します。</span><span class="sxs-lookup"><span data-stu-id="f8b60-110">Explains the event model and the role of delegates.</span></span>

 <span data-ttu-id="f8b60-111">[イベントハンドラーの概要](event-handlers-overview-windows-forms.md)</span><span class="sxs-lookup"><span data-stu-id="f8b60-111">[Event Handlers Overview](event-handlers-overview-windows-forms.md)</span></span>\
 <span data-ttu-id="f8b60-112">イベントを処理する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="f8b60-112">Describes how to handle events.</span></span>

 <span data-ttu-id="f8b60-113">[方法: Windows フォームの実行時にイベントハンドラーを作成する](how-to-create-event-handlers-at-run-time-for-windows-forms.md)</span><span class="sxs-lookup"><span data-stu-id="f8b60-113">[How to: Create Event Handlers at Run Time for Windows Forms](how-to-create-event-handlers-at-run-time-for-windows-forms.md)</span></span>\
 <span data-ttu-id="f8b60-114">システム イベントおよびユーザー イベントへの動的な応答の手順を説明します。</span><span class="sxs-lookup"><span data-stu-id="f8b60-114">Gives directions for responding to system or user events dynamically.</span></span>

 <span data-ttu-id="f8b60-115">[方法: Windows フォームで複数のイベントを1つのイベントハンドラーに接続する](how-to-connect-multiple-events-to-a-single-event-handler-in-windows-forms.md)</span><span class="sxs-lookup"><span data-stu-id="f8b60-115">[How to: Connect Multiple Events to a Single Event Handler in Windows Forms](how-to-connect-multiple-events-to-a-single-event-handler-in-windows-forms.md)</span></span>\
 <span data-ttu-id="f8b60-116">イベントを通じて、複数のコントロールに同じ機能を割り当てる手順について説明します。</span><span class="sxs-lookup"><span data-stu-id="f8b60-116">Gives directions for assigning the same functionality to multiple controls through events.</span></span>

 <span data-ttu-id="f8b60-117">[Windows フォーム内のイベントの順序](order-of-events-in-windows-forms.md)</span><span class="sxs-lookup"><span data-stu-id="f8b60-117">[Order of Events in Windows Forms](order-of-events-in-windows-forms.md)</span></span>\
 <span data-ttu-id="f8b60-118">Windows フォーム コントロールで発生するイベントの順序について説明します。</span><span class="sxs-lookup"><span data-stu-id="f8b60-118">Describes the order in which events are raised in Windows Forms controls.</span></span>

 <span data-ttu-id="f8b60-119">[方法: デザイナーを使用してイベントハンドラーを作成する](/previous-versions/visualstudio/visual-studio-2010/zwwsdtbk(v=vs.100)) Windows フォームデザイナーを使用してイベントハンドラーを作成する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="f8b60-119">[How to: Create Event Handlers Using the Designer](/previous-versions/visualstudio/visual-studio-2010/zwwsdtbk(v=vs.100)) Describes how to use the Windows Forms Designer to create event handlers.</span></span>

## <a name="related-sections"></a><span data-ttu-id="f8b60-120">関連項目</span><span class="sxs-lookup"><span data-stu-id="f8b60-120">Related Sections</span></span>

 <span data-ttu-id="f8b60-121">[記録](/dotnet/standard/events/index)</span><span class="sxs-lookup"><span data-stu-id="f8b60-121">[Events](/dotnet/standard/events/index)</span></span>\
 <span data-ttu-id="f8b60-122">.NET Framework を使用したイベントの処理と発生に関するトピックへのリンクを示します。</span><span class="sxs-lookup"><span data-stu-id="f8b60-122">Provides links to topics on handling and raising events using the .NET Framework.</span></span>

 <span data-ttu-id="f8b60-123">[Visual Basic での継承されたイベントハンドラーのトラブルシューティング](/dotnet/visual-basic/programming-guide/language-features/events/troubleshooting-inherited-event-handlers)</span><span class="sxs-lookup"><span data-stu-id="f8b60-123">[Troubleshooting Inherited Event Handlers in Visual Basic](/dotnet/visual-basic/programming-guide/language-features/events/troubleshooting-inherited-event-handlers)</span></span>\
 <span data-ttu-id="f8b60-124">継承されたコンポーネントでイベント ハンドラーに生じる一般的な問題を一覧表示します。</span><span class="sxs-lookup"><span data-stu-id="f8b60-124">Lists common issues that occur with event handlers in inherited components.</span></span>
