---
title: BackgroundWorker コンポーネント
ms.date: 03/30/2017
helpviewer_keywords:
- BackgroundWorker component
- background tasks
- Asynchronous Pattern
- forms [Windows Forms], multithreading
- components [Windows Forms], asynchronous
- forms [Windows Forms], background operations
- threading [Windows Forms], background operations
- background operations
ms.assetid: bef7b0ab-ce57-475a-a2d6-fb8a702a9417
ms.openlocfilehash: 6a059a9d1eaf2238f21675fec5dc0329a1c714fa
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/09/2020
ms.locfileid: "96975149"
---
# <a name="backgroundworker-component"></a>BackgroundWorker コンポーネント

`BackgroundWorker`コンポーネントを使用すると、フォームまたはコントロールが非同期的に操作を実行できるようになります。  
  
## <a name="in-this-section"></a>このセクションの内容  

 [BackgroundWorker コンポーネントの概要](backgroundworker-component-overview.md)  
 `BackgroundWorker`アプリケーションのメイン UI スレッドとは異なるスレッドで、時間のかかる操作を非同期的に (バックグラウンドで) 実行する機能を提供するコンポーネントについて説明します。  
  
 [チュートリアル: 操作をバックグラウンドで実行する](walkthrough-running-an-operation-in-the-background.md)  
 デザイナーでコンポーネントを使用して、 `BackgroundWorker` 時間のかかる操作を別のスレッドで実行する方法を示します。  
  
 [方法: バックグラウンドで操作を実行する](how-to-run-an-operation-in-the-background.md)  
 コンポーネントを使用して、 `BackgroundWorker` 別のスレッドで時間のかかる操作を実行する方法を示します。  
  
 [チュートリアル: バックグラウンド操作を使用するフォームの実装](walkthrough-implementing-a-form-that-uses-a-background-operation.md)  
 数学的計算を非同期的に行うデザイナーを使用して、アプリケーションを作成します。  
  
 [方法: バックグラウンド操作を使用するフォームを実装する](how-to-implement-a-form-that-uses-a-background-operation.md)  
 数学的計算を非同期的に行うアプリケーションを作成します。  
  
 [方法: バックグラウンドでファイルをダウンロードする](how-to-download-a-file-in-the-background.md)  
 コンポーネントを使用し `BackgroundWorker` て、別のスレッドでファイルをダウンロードする方法を示します。  
  
## <a name="reference"></a>リファレンス  

 <xref:System.ComponentModel.BackgroundWorker>  
 このクラスについて説明し、すべてのメンバーへのリンクの一覧を示します。  
  
 <xref:System.ComponentModel.RunWorkerCompletedEventArgs>  
 イベントのデータを保持する型を記述し <xref:System.ComponentModel.BackgroundWorker.RunWorkerCompleted> ます。  
  
 <xref:System.ComponentModel.ProgressChangedEventArgs>  
 イベントのデータを保持する型を記述し <xref:System.ComponentModel.BackgroundWorker.ProgressChanged> ます。  
  
## <a name="related-sections"></a>関連項目  

 [イベントベースの非同期パターンの概要](/dotnet/standard/asynchronous-programming-patterns/event-based-asynchronous-pattern-overview)  
 非同期パターンでマルチスレッドアプリケーションの利点をどのように利用できるかを説明し、マルチスレッドデザインに固有の複雑な問題の多くを隠蔽します。
