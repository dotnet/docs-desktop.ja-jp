---
title: フォームへの ActiveX コントロールの追加
ms.date: 03/30/2017
helpviewer_keywords:
- Windows Forms controls, ActiveX controls
- forms [Windows Forms], adding ActiveX controls
- ActiveX controls [Windows Forms], adding
ms.assetid: 54a61e5b-555e-4887-b41e-6244fed271eb
ms.openlocfilehash: ebcaf984e3c64bae2988b5c2d1c94abac79ad36e
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/09/2020
ms.locfileid: "96981016"
---
# <a name="how-to-add-activex-controls-to-windows-forms"></a>方法 : Windows フォームに ActiveX コントロールを追加する

Visual Studio の Windows フォームデザイナーは Windows フォームコントロールをホストするように最適化されていますが、Windows フォームに ActiveX コントロールを配置することもできます。

> [!CAUTION]
> ActiveX コントロールが追加されたときの Windows フォームには、パフォーマンス上の制限があります。

ActiveX コントロールをフォームに追加する前に、そのコントロールをツールボックスに追加する必要があります。 詳細については、「 [COM コンポーネント、[ツールボックスのカスタマイズ] ダイアログボックス](/previous-versions/visualstudio/visual-studio-2010/cby6tzh5(v=vs.100))」を参照してください。

## <a name="add-an-activex-control-to-your-windows-form"></a>Windows フォームへの ActiveX コントロールの追加

Windows フォームに ActiveX コントロールを追加するには、ツールボックスのコントロールをダブルクリックします。

Visual Studio は、プロジェクト内のコントロールへのすべての参照を追加します。 Windows フォームで ActiveX コントロールを使用する場合の注意事項の詳細については、「 [Windows フォームで Activex コントロールをホストする場合の考慮事項](considerations-when-hosting-an-activex-control-on-a-windows-form.md)」を参照してください。

> [!NOTE]
> Activex コントロールインポーター (AxImp.exe) Windows フォームは、ActiveX ダイナミックリンクライブラリをインポートするときに、予期しない種類のイベント引数を作成します。 AxImp.exe によって作成される引数は `Invoke(object sender, DWebBrowserEvents2_ProgressChangeEvent e)` 、 `Invoke(object sender, DWebBrowserEvents2_ProgressChangeEventArgs e)` が必要な場合に、のようになります。 この irregularity では、コードが正常に機能しないようにすることはできないことに注意してください。 詳細については、「 [Windows フォーム ActiveX コントロールインポーター (Aximp.exe)](/dotnet/framework/tools/aximp-exe-windows-forms-activex-control-importer)」を参照してください。

## <a name="see-also"></a>関連項目

- [Windows フォームコントロール](index.md)
- [各言語およびライブラリにおける、コントロールとプログラミング可能オブジェクトの比較](/previous-versions/visualstudio/visual-studio-2010/0061wezk(v=vs.100))
- [方法: Windows フォームにコントロールを追加する](how-to-add-controls-to-windows-forms.md)
- [各 Windows フォーム コントロールのラベル設定とショートカットの作成](labeling-individual-windows-forms-controls-and-providing-shortcuts-to-them.md)
- [Windows フォームで使用するコントロール](controls-to-use-on-windows-forms.md)
- [Windows フォーム コントロールの機能別一覧](windows-forms-controls-by-function.md)
