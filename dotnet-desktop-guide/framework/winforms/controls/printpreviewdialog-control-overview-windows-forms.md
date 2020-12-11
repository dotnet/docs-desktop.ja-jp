---
title: PrintPreviewDialog コントロールの概要
ms.date: 01/08/2018
f1_keywords:
- PrintPreviewDialog
helpviewer_keywords:
- PrintPreviewDialog control (using designer), about PrintPreviewDialog
ms.assetid: efd4ee8d-6edd-47ec-88e4-4a4759bd2384
ms.openlocfilehash: c7576beb56cd10a691a850969c132a2d33ad8870
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/09/2020
ms.locfileid: "96974395"
---
# <a name="printpreviewdialog-control-overview-windows-forms"></a><span data-ttu-id="8590a-102">Printプレビューダイアログコントロールの概要 (Windows フォーム)</span><span class="sxs-lookup"><span data-stu-id="8590a-102">PrintPreviewDialog control overview (Windows Forms)</span></span>

<span data-ttu-id="8590a-103">Windows フォーム <xref:System.Windows.Forms.PrintPreviewDialog> コントロールは、印刷時の [PrintDocument](printdocument-component-windows-forms.md) の表示方法を表示するために事前に構成されたダイアログボックスです。</span><span class="sxs-lookup"><span data-stu-id="8590a-103">The Windows Forms <xref:System.Windows.Forms.PrintPreviewDialog> control is a pre-configured dialog box used to display how a [PrintDocument](printdocument-component-windows-forms.md) will appear when printed.</span></span> <span data-ttu-id="8590a-104">独自のダイアログボックスを構成するのではなく、単純なソリューションとして Windows ベースのアプリケーション内で使用します。</span><span class="sxs-lookup"><span data-stu-id="8590a-104">Use it within your Windows-based application as a simple solution instead of configuring your own dialog box.</span></span> <span data-ttu-id="8590a-105">このコントロールには、印刷を開始するボタン、ズーム イン用のボタン、1 ページまたは複数ページを表示するボタン、およびダイアログ ボックスを閉じるためのボタンが含まれています。</span><span class="sxs-lookup"><span data-stu-id="8590a-105">The control contains buttons for printing, zooming in, displaying one or multiple pages, and closing the dialog box.</span></span>

## <a name="key-properties-and-methods"></a><span data-ttu-id="8590a-106">キーのプロパティとメソッド</span><span class="sxs-lookup"><span data-stu-id="8590a-106">Key properties and methods</span></span>

<span data-ttu-id="8590a-107">コントロールのキープロパティは <xref:System.Windows.Forms.PrintPreviewDialog.Document%2A> であり、プレビューするドキュメントを設定します。</span><span class="sxs-lookup"><span data-stu-id="8590a-107">The control's key property is <xref:System.Windows.Forms.PrintPreviewDialog.Document%2A>, which sets the document to be previewed.</span></span> <span data-ttu-id="8590a-108">ドキュメントはオブジェクトである必要があり <xref:System.Drawing.Printing.PrintDocument> ます。</span><span class="sxs-lookup"><span data-stu-id="8590a-108">The document must be a <xref:System.Drawing.Printing.PrintDocument> object.</span></span> <span data-ttu-id="8590a-109">ダイアログボックスを表示するには、メソッドを呼び出す必要があり <xref:System.Windows.Forms.Form.ShowDialog%2A> ます。</span><span class="sxs-lookup"><span data-stu-id="8590a-109">In order to display the dialog box, you must call its <xref:System.Windows.Forms.Form.ShowDialog%2A> method.</span></span> <span data-ttu-id="8590a-110">アンチエイリアシングを使用すると、テキストを滑らかに表示できますが、表示速度が低下することもあります。これを使用するには、プロパティをに設定し <xref:System.Windows.Forms.PrintPreviewDialog.UseAntiAlias%2A> `true` ます。</span><span class="sxs-lookup"><span data-stu-id="8590a-110">Anti-aliasing can make the text appear smoother, but it can also make the display slower; to use it, set the <xref:System.Windows.Forms.PrintPreviewDialog.UseAntiAlias%2A> property to `true`.</span></span>

<span data-ttu-id="8590a-111">特定のプロパティは、に格納されているを介して使用でき <xref:System.Windows.Forms.PrintPreviewControl> <xref:System.Windows.Forms.PrintPreviewDialog> ます。</span><span class="sxs-lookup"><span data-stu-id="8590a-111">Certain properties are available through the <xref:System.Windows.Forms.PrintPreviewControl> that the <xref:System.Windows.Forms.PrintPreviewDialog> contains.</span></span> <span data-ttu-id="8590a-112">(フォームにこのを追加する必要はありません <xref:System.Windows.Forms.PrintPreviewControl> 。フォームにダイアログを追加すると、に自動的に含まれ <xref:System.Windows.Forms.PrintPreviewDialog> ます)。で使用できるプロパティの例 <xref:System.Windows.Forms.PrintPreviewControl> <xref:System.Windows.Forms.PrintPreviewControl.Columns%2A> として、プロパティとプロパティがあり <xref:System.Windows.Forms.PrintPreviewControl.Rows%2A> ます。このプロパティは、コントロールの水平方向および垂直方向に表示されるページ数を決定します。</span><span class="sxs-lookup"><span data-stu-id="8590a-112">(You do not have to add this <xref:System.Windows.Forms.PrintPreviewControl> to the form; it is automatically contained within the <xref:System.Windows.Forms.PrintPreviewDialog> when you add the dialog to your form.) Examples of properties available through the <xref:System.Windows.Forms.PrintPreviewControl> are the <xref:System.Windows.Forms.PrintPreviewControl.Columns%2A> and <xref:System.Windows.Forms.PrintPreviewControl.Rows%2A> properties, which determine the number of pages displayed horizontally and vertically on the control.</span></span> <span data-ttu-id="8590a-113">プロパティには <xref:System.Windows.Forms.PrintPreviewControl.Columns%2A> `PrintPreviewDialog1.PrintPreviewControl.Columns` 、Visual Basic、 `printPreviewDialog1.PrintPreviewControl.Columns` Visual C#、または Visual C++ でアクセスでき `printPreviewDialog1->PrintPreviewControl->Columns` ます。</span><span class="sxs-lookup"><span data-stu-id="8590a-113">You can access the <xref:System.Windows.Forms.PrintPreviewControl.Columns%2A> property as `PrintPreviewDialog1.PrintPreviewControl.Columns` in Visual Basic, `printPreviewDialog1.PrintPreviewControl.Columns` in Visual C#, or `printPreviewDialog1->PrintPreviewControl->Columns` in Visual C++.</span></span>

## <a name="printpreviewdialog-performance"></a><span data-ttu-id="8590a-114">Printプレビューダイアログのパフォーマンス</span><span class="sxs-lookup"><span data-stu-id="8590a-114">PrintPreviewDialog performance</span></span>

<span data-ttu-id="8590a-115">次の条件下では、 <xref:System.Windows.Forms.PrintPreviewDialog> コントロールの初期化が非常に遅くなります。</span><span class="sxs-lookup"><span data-stu-id="8590a-115">Under the following conditions, the <xref:System.Windows.Forms.PrintPreviewDialog> control initializes very slowly:</span></span>

- <span data-ttu-id="8590a-116">ネットワークプリンターが使用されます。</span><span class="sxs-lookup"><span data-stu-id="8590a-116">A network printer is used.</span></span>
- <span data-ttu-id="8590a-117">このプリンターのユーザー設定 (二重設定など) は変更されます。</span><span class="sxs-lookup"><span data-stu-id="8590a-117">User preferences for this printer, such as duplex settings, are modified.</span></span>

<span data-ttu-id="8590a-118">.NET Framework 4.5.2 で実行されているアプリでは、構成ファイルのセクションに次のキーを追加して、 \<appSettings> コントロールの初期化のパフォーマンスを向上させることができ <xref:System.Windows.Forms.PrintPreviewDialog> ます。</span><span class="sxs-lookup"><span data-stu-id="8590a-118">For apps running on the .NET Framework 4.5.2, you can add the following key to the \<appSettings> section of your configuration file to improve the performance of <xref:System.Windows.Forms.PrintPreviewDialog> control initialization:</span></span>

```xml
<appSettings>
   <add key="EnablePrintPreviewOptimization" value="true" />
</appSettings>
```

<span data-ttu-id="8590a-119">`EnablePrintPreviewOptimization`キーが他の値に設定されている場合、またはキーが存在しない場合は、最適化は適用されません。</span><span class="sxs-lookup"><span data-stu-id="8590a-119">If the `EnablePrintPreviewOptimization` key is set to any other value, or if the key is not present, the optimization is not applied.</span></span>

<span data-ttu-id="8590a-120">.NET Framework 4.6 以降のバージョンで実行されているアプリでは、 [\<AppContextSwitchOverrides>](/dotnet/framework/configure-apps/file-schema/runtime/appcontextswitchoverrides-element) [\<runtime>](/dotnet/framework/configure-apps/file-schema/runtime/index) アプリ構成ファイルのセクションで次のスイッチを要素に追加できます。</span><span class="sxs-lookup"><span data-stu-id="8590a-120">For apps running on the .NET Framework 4.6 or later versions, you can add the following switch to the [\<AppContextSwitchOverrides>](/dotnet/framework/configure-apps/file-schema/runtime/appcontextswitchoverrides-element) element in the [\<runtime>](/dotnet/framework/configure-apps/file-schema/runtime/index) section of your app config file:</span></span>

```xml
<runtime >
   <!-- AppContextSwitchOverrides values are in the form of 'key1=true|false;key2=true|false -->
   <AppContextSwitchOverrides value = "Switch.System.Drawing.Printing.OptimizePrintPreview=true" />
</runtime >
```

<span data-ttu-id="8590a-121">スイッチが存在しない場合、または他の値に設定されている場合、最適化は適用されません。</span><span class="sxs-lookup"><span data-stu-id="8590a-121">If the switch is not present or if it is set to any other value, the optimization is not applied.</span></span>

<span data-ttu-id="8590a-122">イベントを使用して <xref:System.Drawing.Printing.PrintDocument.QueryPageSettings> プリンターの設定を変更した場合、 <xref:System.Windows.Forms.PrintPreviewDialog> 最適化構成スイッチが設定されていても、コントロールのパフォーマンスは向上しません。</span><span class="sxs-lookup"><span data-stu-id="8590a-122">If you use the <xref:System.Drawing.Printing.PrintDocument.QueryPageSettings> event to modify printer settings, the performance of the <xref:System.Windows.Forms.PrintPreviewDialog> control will not improve even if an optimization configuration switch is set.</span></span>

## <a name="see-also"></a><span data-ttu-id="8590a-123">関連項目</span><span class="sxs-lookup"><span data-stu-id="8590a-123">See also</span></span>

- <xref:System.Windows.Forms.PrintPreviewDialog>
- [<span data-ttu-id="8590a-124">PrintPreviewControl コントロールの概要</span><span class="sxs-lookup"><span data-stu-id="8590a-124">PrintPreviewControl Control Overview</span></span>](printpreviewcontrol-control-overview-windows-forms.md)
- [<span data-ttu-id="8590a-125">PrintPreviewDialog コントロール</span><span class="sxs-lookup"><span data-stu-id="8590a-125">PrintPreviewDialog Control</span></span>](printpreviewdialog-control-windows-forms.md)
- [<span data-ttu-id="8590a-126">ダイアログ ボックス コントロールおよびコンポーネント</span><span class="sxs-lookup"><span data-stu-id="8590a-126">Dialog-Box Controls and Components</span></span>](dialog-box-controls-and-components-windows-forms.md)
