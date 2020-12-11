---
title: マウス キャプチャ
ms.date: 03/30/2017
helpviewer_keywords:
- mouse [Windows Forms], capture
ms.assetid: 8911d4b0-a4f8-4f93-8246-371aebd27d0c
ms.openlocfilehash: 10583f074831b16dce3c713b4ac9a76c7005c9f5
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/09/2020
ms.locfileid: "96983171"
---
# <a name="mouse-capture-in-windows-forms"></a>Windows フォームにおけるマウスのキャプチャ
*マウスキャプチャ* は、コントロールがすべてのマウス入力のコマンドを受け取るときに参照します。 コントロールは、マウスをキャプチャしたときに、ポインターが境界内にあるかどうかにかかわらず、マウス入力を受け取ります。  
  
## <a name="setting-mouse-capture"></a>マウスキャプチャの設定  
 Windows フォーム、ユーザーがコントロール上でマウスボタンを押したときにコントロールによってマウスがキャプチャされ、ユーザーがマウスボタンを離したときにコントロールによってマウスが解放されます。  
  
 <xref:System.Windows.Forms.Control.Capture%2A>クラスのプロパティは、 <xref:System.Windows.Forms.Control> コントロールがマウスをキャプチャしたかどうかを指定します。 コントロールがマウスのキャプチャを失ったタイミングを判断するには、イベントを処理し <xref:System.Windows.Forms.Control.MouseCaptureChanged> ます。  
  
 前面のウィンドウだけがマウスをキャプチャできます。 バックグラウンドウィンドウがマウスをキャプチャしようとすると、ウィンドウは、マウスポインターがウィンドウの表示部分内にあるときに発生するマウスイベントに対してのみメッセージを受信します。 また、前景ウィンドウがマウスをキャプチャした場合でも、ユーザーは別のウィンドウをクリックして、前面に表示することができます。 マウスがキャプチャされると、ショートカットキーは機能しません。  
  
## <a name="see-also"></a>関連項目

- [Windows フォーム アプリケーションにおけるマウス入力](mouse-input-in-a-windows-forms-application.md)
