---
title: '方法: 印刷ダイアログ ボックスを呼び出す'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- invoking print dialogs [WPF]
- print dialogs [WPF], invoking
ms.assetid: e3a2c84c-74fe-45a4-8501-5813f9dbfed2
ms.openlocfilehash: f6e85afc40d5736de94ff7851d1db2c8007720d0
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/09/2020
ms.locfileid: "96980011"
---
# <a name="how-to-invoke-a-print-dialog"></a><span data-ttu-id="3a095-102">方法: 印刷ダイアログ ボックスを呼び出す</span><span class="sxs-lookup"><span data-stu-id="3a095-102">How to: Invoke a Print Dialog</span></span>
<span data-ttu-id="3a095-103">アプリケーションから印刷する機能を提供するには、<xref:System.Windows.Controls.PrintDialog> オブジェクトを作成して開くだけで済みます。</span><span class="sxs-lookup"><span data-stu-id="3a095-103">To provide the ability to print from you application, you can simply create and open a <xref:System.Windows.Controls.PrintDialog> object.</span></span>  
  
## <a name="example"></a><span data-ttu-id="3a095-104">例</span><span class="sxs-lookup"><span data-stu-id="3a095-104">Example</span></span>  
 <span data-ttu-id="3a095-105"><xref:System.Windows.Controls.PrintDialog> コントロールには、[!INCLUDE[TLA2#tla_ui](../../../includes/tla2sharptla-ui-md.md)]、構成、および XPS ジョブの送信用に 1 つのエントリ ポイントが用意されています。</span><span class="sxs-lookup"><span data-stu-id="3a095-105">The <xref:System.Windows.Controls.PrintDialog> control provides a single entry point for [!INCLUDE[TLA2#tla_ui](../../../includes/tla2sharptla-ui-md.md)], configuration, and XPS job submission.</span></span> <span data-ttu-id="3a095-106">このコントロールは使いやすく、[!INCLUDE[TLA#tla_xaml](../../../includes/tlasharptla-xaml-md.md)] マークアップまたはコードを使用してインスタンス化できます。</span><span class="sxs-lookup"><span data-stu-id="3a095-106">The control is easy to use and can be instantiated by using [!INCLUDE[TLA#tla_xaml](../../../includes/tlasharptla-xaml-md.md)] markup or code.</span></span> <span data-ttu-id="3a095-107">コードでコントロールをインスタンス化して開く方法と、そこから印刷する方法の例を次に示します。</span><span class="sxs-lookup"><span data-stu-id="3a095-107">The following example demonstrates how to instantiate and open the control in code and how to print from it.</span></span> <span data-ttu-id="3a095-108">また、ダイアログで、特定の範囲のページを設定するオプションをユーザーに提供する方法も示します。</span><span class="sxs-lookup"><span data-stu-id="3a095-108">It also shows how to ensure that the dialog will give the user the option of setting a specific range of pages.</span></span> <span data-ttu-id="3a095-109">このコード例では、C: ドライブのルートに FixedDocumentSequence.xps ファイルがあることを前提としています。</span><span class="sxs-lookup"><span data-stu-id="3a095-109">The example code assumes that there is a file FixedDocumentSequence.xps in the root of the C: drive.</span></span>  
  
 [!code-csharp[printdialog#1](~/samples/snippets/csharp/VS_Snippets_Wpf/PrintDialog/CSharp/Window1.xaml.cs#1)]
 [!code-vb[printdialog#1](~/samples/snippets/visualbasic/VS_Snippets_Wpf/PrintDialog/visualbasic/window1.xaml.vb#1)]  
  
 <span data-ttu-id="3a095-110">ダイアログが開くと、ユーザーはコンピューターにインストールされているプリンターから選択できます。</span><span class="sxs-lookup"><span data-stu-id="3a095-110">Once the dialog is open, users will be able to select from the printers installed on their computer.</span></span> <span data-ttu-id="3a095-111">また、[[Microsoft XPS ドキュメント ライター]](/windows/win32/printdocs/microsoft-xps-document-writer) を選択し、印刷するのではなく XML Paper Specification (XPS) ファイルを作成することもできます。</span><span class="sxs-lookup"><span data-stu-id="3a095-111">They will also have the option of selecting the [Microsoft XPS Document Writer](/windows/win32/printdocs/microsoft-xps-document-writer) to create an XML Paper Specification (XPS) file instead of printing.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="3a095-112">このトピックで説明されている WPF の <xref:System.Windows.Controls.PrintDialog?displayProperty=nameWithType> コントロールは、Windows フォームの <xref:System.Windows.Forms.PrintDialog?displayProperty=nameWithType> コンポーネントと混同しないでください。</span><span class="sxs-lookup"><span data-stu-id="3a095-112">The <xref:System.Windows.Controls.PrintDialog?displayProperty=nameWithType> control of WPF, which is discussed in this topic, should not be confused with the <xref:System.Windows.Forms.PrintDialog?displayProperty=nameWithType> component of Windows Forms.</span></span>  
  
 <span data-ttu-id="3a095-113">厳密に言うと、ダイアログを開かなくても <xref:System.Windows.Controls.PrintDialog.PrintDocument%2A> メソッドを使用できます。</span><span class="sxs-lookup"><span data-stu-id="3a095-113">Strictly speaking, you can use the <xref:System.Windows.Controls.PrintDialog.PrintDocument%2A> method without ever opening the dialog.</span></span> <span data-ttu-id="3a095-114">その意味で、コントロールは目に見えない印刷コンポーネントとして使用できます。</span><span class="sxs-lookup"><span data-stu-id="3a095-114">In that sense, the control can be used as an unseen printing component.</span></span> <span data-ttu-id="3a095-115">ただし、パフォーマンス上の理由から、<xref:System.Printing.PrintQueue.AddJob%2A> メソッド、または <xref:System.Windows.Xps.XpsDocumentWriter> の多くの <xref:System.Windows.Xps.XpsDocumentWriter.Write%2A> および <xref:System.Windows.Xps.XpsDocumentWriter.WriteAsync%2A> メソッドのいずれかを使用することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="3a095-115">But for performance reasons, it would be better to use either the <xref:System.Printing.PrintQueue.AddJob%2A> method or one of the many <xref:System.Windows.Xps.XpsDocumentWriter.Write%2A> and <xref:System.Windows.Xps.XpsDocumentWriter.WriteAsync%2A> methods of the <xref:System.Windows.Xps.XpsDocumentWriter>.</span></span> <span data-ttu-id="3a095-116">この詳細については、[プログラムによる XPS ファイルの印刷](how-to-programmatically-print-xps-files.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="3a095-116">For more about this, see [Programmatically Print XPS Files](how-to-programmatically-print-xps-files.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3a095-117">関連項目</span><span class="sxs-lookup"><span data-stu-id="3a095-117">See also</span></span>

- <xref:System.Windows.Controls.PrintDialog>
- [<span data-ttu-id="3a095-118">WPF のドキュメント</span><span class="sxs-lookup"><span data-stu-id="3a095-118">Documents in WPF</span></span>](documents-in-wpf.md)
- [<span data-ttu-id="3a095-119">印刷の概要</span><span class="sxs-lookup"><span data-stu-id="3a095-119">Printing Overview</span></span>](printing-overview.md)
- [<span data-ttu-id="3a095-120">Microsoft XPS Document Writer</span><span class="sxs-lookup"><span data-stu-id="3a095-120">Microsoft XPS Document Writer</span></span>](/windows/win32/printdocs/microsoft-xps-document-writer)
