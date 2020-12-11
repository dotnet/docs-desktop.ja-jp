---
title: コントロールでのマルチスレッド
ms.date: 03/30/2017
helpviewer_keywords:
- BackgroundWorker component
- threading [Windows Forms], controls
ms.assetid: c311d652-0f26-45fa-bdcc-b1615d73ce4e
ms.openlocfilehash: 79832e12a10f02c909d2a28270594bcb4ea68656
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/09/2020
ms.locfileid: "96980602"
---
# <a name="multithreading-in-windows-forms-controls"></a>Windows フォーム コントロールのマルチスレッド処理
多くのアプリケーションでは、別のスレッドで時間のかかる操作を実行することで、ユーザーインターフェイス (UI) の応答性を高めることができます。 <xref:System.Threading>名前空間、メソッド、コンポーネントなど、Windows フォームコントロールのマルチスレッドでは、さまざまなツールを使用でき <xref:System.Windows.Forms.Control.BeginInvoke%2A?displayProperty=nameWithType> `BackgroundWorker` ます。  
  
> [!NOTE]
> コンポーネントは、 `BackgroundWorker` 名前空間とメソッドに置き換えられ、機能を追加します。 <xref:System.Threading> <xref:System.Windows.Forms.Control.BeginInvoke%2A?displayProperty=nameWithType> ただし、これらは下位互換性と将来の使用の両方のために保持されます (選択した場合)。 詳細については、「 [BackgroundWorker コンポーネントの概要](backgroundworker-component-overview.md)」を参照してください。  
  
## <a name="in-this-section"></a>このセクションの内容  
 [方法: Windows フォーム コントロールのスレッド セーフな呼び出しを行う](how-to-make-thread-safe-calls-to-windows-forms-controls.md)  
 Windows フォームコントロールに対してスレッドセーフな呼び出しを行う方法を示します。  
  
 [方法: バックグラウンド スレッドを使用してファイルを検索する](how-to-use-a-background-thread-to-search-for-files.md)  
 名前空間とメソッドを使用して、 <xref:System.Threading> <xref:System.Windows.Forms.Control.BeginInvoke%2A> ファイルを非同期的に検索する方法を示します。  
  
## <a name="reference"></a>リファレンス  
 <xref:System.ComponentModel.BackgroundWorker>  
 非同期操作のワーカースレッドをカプセル化するコンポーネントについて説明します。  
  
 <xref:System.Media.SoundPlayer.LoadAsync%2A>  
 サウンドを非同期に読み込む方法を説明します。  
  
 <xref:System.Windows.Forms.PictureBox.LoadAsync%2A>  
 画像を非同期に読み込む方法を説明します。  
  
## <a name="related-sections"></a>関連項目  
 [方法: バックグラウンドで操作を実行する](how-to-run-an-operation-in-the-background.md)  
 コンポーネントで時間のかかる操作を実行する方法について説明 <xref:System.ComponentModel.BackgroundWorker> します。  
  
 [BackgroundWorker コンポーネントの概要](backgroundworker-component-overview.md)  
 コンポーネントを非同期操作に使用する方法について説明するトピックを示し <xref:System.ComponentModel.BackgroundWorker> ます。
