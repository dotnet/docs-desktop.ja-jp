---
title: デザイン時にコントロールを開発する
ms.date: 03/30/2017
helpviewer_keywords:
- Windows Forms controls [Windows Forms]
- Windows Forms controls, creating
- controls [Windows Forms]
- controls [Windows Forms], creating
- user controls [Windows Forms]
- custom controls [Windows Forms]
ms.assetid: e5a8e088-7ec8-4fd9-bcb3-9078fd134829
ms.openlocfilehash: d5285bd4190e74a86e20d951d9ebb2256c21c544
ms.sourcegitcommit: 7f48b9ecf8a30db42c8ecea0dd4df577736631a2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/28/2021
ms.locfileid: "98956981"
---
# <a name="develop-windows-forms-controls-at-design-time"></a><span data-ttu-id="295be-102">デザイン時に Windows フォームコントロールを開発する</span><span class="sxs-lookup"><span data-stu-id="295be-102">Develop Windows Forms controls at design time</span></span>

<span data-ttu-id="295be-103">コントロールの作成者は、.NET Framework のさまざまなコントロール作成テクノロジを利用できます。</span><span class="sxs-lookup"><span data-stu-id="295be-103">For control authors, the .NET Framework provides a wealth of control authoring technology.</span></span> <span data-ttu-id="295be-104">既存のコントロールを組み合わせた複合コントロールしかデザインできないといった制約はなくなりました。</span><span class="sxs-lookup"><span data-stu-id="295be-104">Authors are no longer limited to designing composite controls that act as a collection of preexisting controls.</span></span> <span data-ttu-id="295be-105">継承により、既存の複合コントロールや既存の Windows フォーム コントロールから、独自のコントロールを作成できます。</span><span class="sxs-lookup"><span data-stu-id="295be-105">Through inheritance, you can create your own controls from preexisting composite controls or preexisting Windows Forms controls.</span></span> <span data-ttu-id="295be-106">カスタム描画を実装する独自のコントロールを設計することもできます。</span><span class="sxs-lookup"><span data-stu-id="295be-106">You can also design your own controls that implement custom painting.</span></span> <span data-ttu-id="295be-107">これらのオプションを使うと、非常に柔軟にビジュアル インターフェイスのデザインと機能を決めることができます。</span><span class="sxs-lookup"><span data-stu-id="295be-107">These options enable a great deal of flexibility to the design and functionality of the visual interface.</span></span> <span data-ttu-id="295be-108">これらの機能を利用するには、オブジェクト ベースのプログラミング概念について理解しておく必要があります。</span><span class="sxs-lookup"><span data-stu-id="295be-108">To take advantage of these features, you should be familiar with object-based programming concepts.</span></span>

> [!NOTE]
> <span data-ttu-id="295be-109">継承について十分に理解している必要はありませんが、 [継承の基本 (Visual Basic)](/dotnet/visual-basic/programming-guide/language-features/objects-and-classes/inheritance-basics)を参照すると役立つ場合があります。</span><span class="sxs-lookup"><span data-stu-id="295be-109">It is not necessary to have a thorough understanding of inheritance, but you may find it useful to refer to [Inheritance basics (Visual Basic)](/dotnet/visual-basic/programming-guide/language-features/objects-and-classes/inheritance-basics).</span></span>

<span data-ttu-id="295be-110">Web フォームで使うカスタム コントロールを作る場合は、「[カスタム ASP.NET サーバー コントロールの開発](/previous-versions/aspnet/zt27tfhy(v=vs.100))」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="295be-110">If you want to create custom controls to use on Web Forms, see [Developing Custom ASP.NET Server Controls](/previous-versions/aspnet/zt27tfhy(v=vs.100)).</span></span>

## <a name="in-this-section"></a><span data-ttu-id="295be-111">このセクションの内容</span><span class="sxs-lookup"><span data-stu-id="295be-111">In this section</span></span>

<span data-ttu-id="295be-112">[チュートリアル: 複合コントロールの作成](walkthrough-authoring-a-composite-control-with-visual-csharp.md)</span><span class="sxs-lookup"><span data-stu-id="295be-112">[Walkthrough: Authoring a Composite Control](walkthrough-authoring-a-composite-control-with-visual-csharp.md)</span></span>\
<span data-ttu-id="295be-113">C# で簡単な複合コントロールを作る方法を示します。</span><span class="sxs-lookup"><span data-stu-id="295be-113">Shows how to create a simple composite control in C#.</span></span>

<span data-ttu-id="295be-114">[チュートリアル: Windows フォームコントロールからの継承](walkthrough-inheriting-from-a-windows-forms-control-with-visual-csharp.md)</span><span class="sxs-lookup"><span data-stu-id="295be-114">[Walkthrough: Inheriting from a Windows Forms Control](walkthrough-inheriting-from-a-windows-forms-control-with-visual-csharp.md)</span></span>\
<span data-ttu-id="295be-115">C# で継承を使って簡単な Windows フォーム コントロールを作る方法を示します。</span><span class="sxs-lookup"><span data-stu-id="295be-115">Shows how to create a simple Windows Forms control using inheritance in C#.</span></span>

<span data-ttu-id="295be-116">[チュートリアル: デザイン アクションを使って一般的なタスクを実行する](perform-common-tasks-design-actions.md)</span><span class="sxs-lookup"><span data-stu-id="295be-116">[Walkthrough: Perform common tasks using designer actions](perform-common-tasks-design-actions.md)</span></span>\
<span data-ttu-id="295be-117">Windows フォーム コントロールでスマート タグ機能を使う方法を示します。</span><span class="sxs-lookup"><span data-stu-id="295be-117">Shows how to use the smart tag feature on Windows Forms controls.</span></span>

<span data-ttu-id="295be-118">[チュートリアル: DesignerSerializationVisibilityAttribute を使用した標準型のコレクションのシリアル化](serializing-collections-designerserializationvisibilityattribute.md)</span><span class="sxs-lookup"><span data-stu-id="295be-118">[Walkthrough: Serializing Collections of Standard Types with the DesignerSerializationVisibilityAttribute](serializing-collections-designerserializationvisibilityattribute.md)</span></span>\
<span data-ttu-id="295be-119">属性を使用してコレクションをシリアル化する方法について説明し <xref:System.ComponentModel.DesignerSerializationVisibilityAttribute.Content?displayProperty=nameWithType> ます。</span><span class="sxs-lookup"><span data-stu-id="295be-119">Shows how to use the <xref:System.ComponentModel.DesignerSerializationVisibilityAttribute.Content?displayProperty=nameWithType> attribute to serialize a collection.</span></span>

<span data-ttu-id="295be-120">[チュートリアル: デザイン時のカスタム Windows フォームコントロールのデバッグ](walkthrough-debugging-custom-windows-forms-controls-at-design-time.md)</span><span class="sxs-lookup"><span data-stu-id="295be-120">[Walkthrough: Debugging Custom Windows Forms Controls at Design Time](walkthrough-debugging-custom-windows-forms-controls-at-design-time.md)</span></span>\
<span data-ttu-id="295be-121">Windows フォーム コントロールのデザイン時動作をデバッグする方法を示します。</span><span class="sxs-lookup"><span data-stu-id="295be-121">Shows how to debug the design-time behavior of a Windows Forms control.</span></span>

<span data-ttu-id="295be-122">[チュートリアル: Visual Studio の Design-Time 機能を利用する Windows フォームコントロールの作成](creating-a-wf-control-design-time-features.md)</span><span class="sxs-lookup"><span data-stu-id="295be-122">[Walkthrough: Creating a Windows Forms Control That Takes Advantage of Visual Studio Design-Time Features](creating-a-wf-control-design-time-features.md)</span></span>\
<span data-ttu-id="295be-123">デザイン環境に複合コントロールを緊密に統合する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="295be-123">Shows how to tightly integrate a composite control into the design environment.</span></span>

<span data-ttu-id="295be-124">[方法: Windows フォームのコントロールを作成する](how-to-author-controls-for-windows-forms.md)</span><span class="sxs-lookup"><span data-stu-id="295be-124">[How to: Author Controls for Windows Forms](how-to-author-controls-for-windows-forms.md)</span></span>\
<span data-ttu-id="295be-125">Windows フォーム コントロールの実装に関する考慮事項の概要を説明します。</span><span class="sxs-lookup"><span data-stu-id="295be-125">Provides an overview of considerations for implementing a Windows Forms control.</span></span>

<span data-ttu-id="295be-126">[方法: 複合コントロールを作成する](how-to-author-composite-controls.md)</span><span class="sxs-lookup"><span data-stu-id="295be-126">[How to: Author Composite Controls](how-to-author-composite-controls.md)</span></span>\
<span data-ttu-id="295be-127">複合コントロールから継承することでコントロールを作る方法を示します。</span><span class="sxs-lookup"><span data-stu-id="295be-127">Shows how to create a control by inheriting from a composite control.</span></span>

<span data-ttu-id="295be-128">[方法: UserControl クラスを継承する](how-to-inherit-from-the-usercontrol-class.md)</span><span class="sxs-lookup"><span data-stu-id="295be-128">[How to: Inherit from the UserControl Class](how-to-inherit-from-the-usercontrol-class.md)</span></span>\
<span data-ttu-id="295be-129">複合コントロール作成手順の概要を説明します。</span><span class="sxs-lookup"><span data-stu-id="295be-129">Provides an overview of the procedure for creating a composite control.</span></span>

<span data-ttu-id="295be-130">[方法: 既存の Windows フォームコントロールを継承する](how-to-inherit-from-existing-windows-forms-controls.md)</span><span class="sxs-lookup"><span data-stu-id="295be-130">[How to: Inherit from Existing Windows Forms Controls](how-to-inherit-from-existing-windows-forms-controls.md)</span></span>\
<span data-ttu-id="295be-131">コントロールクラスから継承することによって拡張コントロールを作成する方法について説明し <xref:System.Windows.Forms.Button> ます。</span><span class="sxs-lookup"><span data-stu-id="295be-131">Shows how to create an extended control by inheriting from the <xref:System.Windows.Forms.Button> control class.</span></span>

<span data-ttu-id="295be-132">[方法: コントロールクラスを継承する](how-to-inherit-from-the-control-class.md)</span><span class="sxs-lookup"><span data-stu-id="295be-132">[How to: Inherit from the Control Class](how-to-inherit-from-the-control-class.md)</span></span>\
<span data-ttu-id="295be-133">拡張コントロールの作成の概要を説明します。</span><span class="sxs-lookup"><span data-stu-id="295be-133">Provides an overview of creating an extended control.</span></span>

<span data-ttu-id="295be-134">[方法: デザイン時にフォームの端に合わせてコントロールを配置する](how-to-align-a-control-to-the-edges-of-forms-at-design-time.md)</span><span class="sxs-lookup"><span data-stu-id="295be-134">[How to: Align a Control to the Edges of Forms at Design Time](how-to-align-a-control-to-the-edges-of-forms-at-design-time.md)</span></span>\
<span data-ttu-id="295be-135">プロパティを使用し <xref:System.Windows.Forms.Control.Dock%2A> て、コントロールをフォームの端に揃える方法を示します。</span><span class="sxs-lookup"><span data-stu-id="295be-135">Shows how to use the <xref:System.Windows.Forms.Control.Dock%2A> property to align your control to the edge of the form it occupies.</span></span>

<span data-ttu-id="295be-136">[方法: [ツールボックスアイテムの選択] ダイアログボックスにコントロールを表示する](how-to-display-a-control-in-the-choose-toolbox-items-dialog-box.md)</span><span class="sxs-lookup"><span data-stu-id="295be-136">[How to: Display a Control in the Choose Toolbox Items Dialog Box](how-to-display-a-control-in-the-choose-toolbox-items-dialog-box.md)</span></span>\
<span data-ttu-id="295be-137">**ツールボックスのカスタマイズ** ダイアログ ボックスに表示されるようにコントロールをインストールする手順を示します。</span><span class="sxs-lookup"><span data-stu-id="295be-137">Shows the procedure for installing your control so that it appears in the **Customize Toolbox** dialog box.</span></span>

<span data-ttu-id="295be-138">[方法: コントロールのツールボックスビットマップを指定する](how-to-provide-a-toolbox-bitmap-for-a-control.md)</span><span class="sxs-lookup"><span data-stu-id="295be-138">[How to: Provide a Toolbox Bitmap for a Control](how-to-provide-a-toolbox-bitmap-for-a-control.md)</span></span>\
<span data-ttu-id="295be-139">を使用して、 <xref:System.Drawing.ToolboxBitmapAttribute> **ツールボックス** のカスタムコントロールの横にアイコンを表示する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="295be-139">Shows how to use the <xref:System.Drawing.ToolboxBitmapAttribute> to display an icon next to your custom control in the **Toolbox**.</span></span>

<span data-ttu-id="295be-140">[方法: UserControl の Run-Time 動作をテストする](how-to-test-the-run-time-behavior-of-a-usercontrol.md)</span><span class="sxs-lookup"><span data-stu-id="295be-140">[How to: Test the Run-Time Behavior of a UserControl](how-to-test-the-run-time-behavior-of-a-usercontrol.md)</span></span>\
<span data-ttu-id="295be-141">**UserControl テスト コンテナー** を使って複合コントロールの動作をテストする方法を示します。</span><span class="sxs-lookup"><span data-stu-id="295be-141">Shows how to use the **UserControl Test Container** to test the behavior of a composite control.</span></span>

<span data-ttu-id="295be-142">[Windows フォームデザイナーのデザイン時エラー](design-time-errors-in-the-windows-forms-designer.md)</span><span class="sxs-lookup"><span data-stu-id="295be-142">[Design-Time Errors in the Windows Forms Designer](design-time-errors-in-the-windows-forms-designer.md)</span></span>\
<span data-ttu-id="295be-143">Windows フォーム デザイナーで読み込みに失敗したときに Microsoft Visual Studio に表示されるデザイン時エラー リストの意味と使用法について説明します。</span><span class="sxs-lookup"><span data-stu-id="295be-143">Explains the meaning and use of the Design-Time Error List that appears in Microsoft Visual Studio when the Windows Forms designer fails to load.</span></span>

<span data-ttu-id="295be-144">[コントロールとコンポーネントの作成に関するトラブルシューティング](troubleshooting-control-and-component-authoring.md)</span><span class="sxs-lookup"><span data-stu-id="295be-144">[Troubleshooting Control and Component Authoring](troubleshooting-control-and-component-authoring.md)</span></span>\
<span data-ttu-id="295be-145">カスタム コンポーネントやコントロールを作るときに発生する可能性がある一般的な問題を診断して解決する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="295be-145">Shows how to diagnose and fix common issues that can occur when you author a custom component or control.</span></span>

## <a name="reference"></a><span data-ttu-id="295be-146">関連項目</span><span class="sxs-lookup"><span data-stu-id="295be-146">Reference</span></span>

- <xref:System.Windows.Forms.Control?displayProperty=nameWithType>

- <xref:System.Windows.Forms.UserControl?displayProperty=nameWithType>

## <a name="related-sections"></a><span data-ttu-id="295be-147">関連項目</span><span class="sxs-lookup"><span data-stu-id="295be-147">Related sections</span></span>

<span data-ttu-id="295be-148">[.NET Framework を使用したカスタム Windows フォーム コントロールの開発](developing-custom-windows-forms-controls.md)</span><span class="sxs-lookup"><span data-stu-id="295be-148">[Developing Custom Windows Forms Controls with the .NET Framework](developing-custom-windows-forms-controls.md)</span></span>\
<span data-ttu-id="295be-149">.NET Framework で独自のカスタム コントロールを作る方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="295be-149">Discusses how to create your own custom controls with the .NET Framework.</span></span>

<span data-ttu-id="295be-150">[言語への非依存性と Language-Independent コンポーネント](/dotnet/standard/language-independence-and-language-independent-components)</span><span class="sxs-lookup"><span data-stu-id="295be-150">[Language Independence and Language-Independent Components](/dotnet/standard/language-independence-and-language-independent-components)</span></span>\
<span data-ttu-id="295be-151">コンポーネントの作成と使用を簡略化するように設計されている共通言語ランタイムの概要について説明します。</span><span class="sxs-lookup"><span data-stu-id="295be-151">Introduces the common language runtime, which is designed to simplify the creation and use of components.</span></span> <span data-ttu-id="295be-152">この簡略化の重要な側面は、さまざまなプログラミング言語で記述されたコンポーネント間の相互運用性の拡張です。</span><span class="sxs-lookup"><span data-stu-id="295be-152">An important aspect of this simplification is enhanced interoperability between components written using different programming languages.</span></span> <span data-ttu-id="295be-153">共通言語仕様 (CLS) を使うと、複数のプログラミング言語で動作するツールやコンポーネントを作ることができます。</span><span class="sxs-lookup"><span data-stu-id="295be-153">The Common Language Specification (CLS) makes it possible to create tools and components that work with multiple programming languages.</span></span>

<span data-ttu-id="295be-154">[チュートリアル: ツールボックスへのカスタムコンポーネントの自動設定](walkthrough-automatically-populating-the-toolbox-with-custom-components.md)</span><span class="sxs-lookup"><span data-stu-id="295be-154">[Walkthrough: Automatically Populating the Toolbox with Custom Components](walkthrough-automatically-populating-the-toolbox-with-custom-components.md)</span></span>\
<span data-ttu-id="295be-155">コンポーネントやコントロールを **ツールボックスのカスタマイズ** ダイアログ ボックスに表示できるようにする方法を説明します。</span><span class="sxs-lookup"><span data-stu-id="295be-155">Describes how to enable your component or control to be displayed in the **Customize Toolbox** dialog box.</span></span>
