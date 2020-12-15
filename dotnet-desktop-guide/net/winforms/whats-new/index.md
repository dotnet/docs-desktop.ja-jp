---
title: Windows フォームの新機能
description: .NET 用の Windows フォームの新機能について学習します。 Windows フォーム。 .NET では、.NET Framework に対する新機能と拡張機能が提供されます。
ms.date: 11/05/2020
ms.topic: conceptual
ms.openlocfilehash: 5c22fdd2df68cd59b7bc0b93c6aa7223bdf06ec0
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/09/2020
ms.locfileid: "96992856"
---
# <a name="whats-new-windows-forms-net"></a>新機能 (Windows フォーム .NET)

.NET 5.0 用の Windows フォームには、.NET Framework に対する次の機能と拡張機能が追加されています。

.NET Framework から .NET 5.0 に移行するときに注意する必要がある破壊的変更がいくつかあります。 詳細については、[Windows フォームでの破壊的変更](/dotnet/core/compatibility/winforms)に関するページを参照してください。

## <a name="enhanced-features"></a>拡張機能

- Microsoft UI オートメーションのパターンは、ナレーターや Jaws などのユーザー補助ツールでより適切に動作します。
- パフォーマンスが向上します。
- VB.NET プロジェクトのテンプレートでは、4k モニターなどの高 DPI 解像度の場合、既定で DPI SystemAware に設定されます。
- 既定のフォントは、現在の Windows の設計上の推奨事項と一致します。

  > [!CAUTION]
  > これは、.NET Framework から移行されたアプリのレイアウトに影響を与える可能性があります。

## <a name="new-controls"></a>新しいコントロール

Windows フォームが .NET Framework に移植された後に、次のコントロールが追加されました。

- <xref:System.Windows.Forms.TaskDialog?displayProperty=fullName>
  
  タスク ダイアログは、情報の表示とユーザーからの単純な入力の受信に使用できるダイアログ ボックスです。 メッセージ ボックスと同様に、ユーザーが設定したパラメーターに従って、オペレーティング システムによって書式設定されます。 タスク ダイアログには、メッセージ ボックスよりも多くの機能があります。 詳細については、[タスク ダイアログのサンプル](https://github.com/dotnet/samples/tree/master/windowsforms/TaskDialogDemo)を参照してください。

- <xref:Microsoft.Web.WebView2.WinForms.WebView2?displayProperty=fullName>

  最新の Web をサポートする新しい Web ブラウザー コントロール。 Edge (Chromium) ベース。 詳細については、「[Windows フォームでの WebView2 の概要](/microsoft-edge/webview2/gettingstarted/winforms)」を参照してください。

## <a name="enhanced-controls"></a>強化されたコントロール

- <xref:System.Windows.Forms.ListView?displayProperty=fullName>

  - 折りたたみ可能なグループをサポート
  - フッター
  - 字幕、タスク、およびタイトルの画像をグループ化

- <xref:System.Windows.Forms.FolderBrowserDialog?displayProperty=fullName>

  このダイアログは、古い Windows 7 エクスペリエンスではなく、最新の Windows エクスペリエンスを使用するようにアップグレードされました。

- <xref:System.Windows.Forms.FileDialog?displayProperty=fullName>

  - <xref:System.Windows.Forms.FileDialog.ClientGuid> のサポートが追加されました。

    `ClientGuid` を使用すると、呼び出し元のアプリケーションで GUID とダイアログの保持された状態を関連付けることができます。 ダイアログの状態には、最後にアクセスしたフォルダーおよびダイアログの位置やサイズなどの要因を含めることができます。 通常、この状態は実行可能ファイルの名前に基づいて保持されます。 `ClientGuid` を使用すると、アプリケーションで同じアプリケーション内の異なる状態のダイアログを保持できます。

- <xref:System.Windows.Forms.TextRenderer?displayProperty=fullName>

  レンダリング テキストのパフォーマンスを向上させるために <xref:System.ReadOnlySpan%601> のサポートが追加されました。

## <a name="see-also"></a>関連項目

- [Windows フォームでの破壊的変更](/dotnet/core/compatibility/winforms)
- [チュートリアル: 新しい WinForms アプリを作成する (Windows フォーム .NET)](../get-started/create-app-visual-studio.md)
- [Windows フォーム デスクトップ アプリを .NET 5 に移行する方法](../migration/index.md)
