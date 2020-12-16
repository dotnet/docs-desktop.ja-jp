---
title: コントロールの使用の概要
description: .NET 用の Windows フォームでのコントロールの使用方法について説明します。 コントロールは、ユーザーに機能を提供する再利用可能なコンポーネントです。 すぐに使用できるさまざまなコントロールが用意されています。 新しいコントロールを作成することもできます。
ms.date: 10/26/2020
ms.topic: overview
dev_langs:
- csharp
- vb
helpviewer_keywords:
- Windows Forms, controls
- controls [Windows Forms]
- custom controls [Windows Forms]
ms.openlocfilehash: 7476ce47a1767a2ab13c25a7408f5861014e7de8
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/09/2020
ms.locfileid: "96942335"
---
# <a name="overview-of-using-controls-windows-forms-net"></a>コントロールの使用の概要 (Windows フォーム .NET)

Windows フォーム コントロールは、ユーザー インターフェイスの機能をカプセル化して、クライアント側の Windows ベースのアプリケーションで使用される再利用可能なコンポーネントです。 Windows フォームは、すぐに使用できる多数のコントロールを提供するだけでなく、独自のコントロールを開発するためのインフラストラクチャも提供します。 既存のコントロールの結合、既存のコントロールの拡張、または独自のカスタム コントロールの記述ができます。 詳細については、「[カスタム コントロールの種類](custom.md)」を参照してください。

[!INCLUDE [desktop guide under construction](../../includes/desktop-guide-preview-note.md)]

## <a name="adding-controls"></a>コントロールの追加

コントロールは、Visual Studio デザイナーを使用して追加します。 デザイナーを使用すると、コントロールの配置、サイズ変更、配置、および移動を行うことができます。 または、コードを使用してコントロールを追加することもできます。 詳細については、「[コントロールを追加する (Windows フォーム)](how-to-add-to-a-form.md)」を参照してください。

## <a name="layout-options"></a>レイアウト オプション

親の上に表示されるコントロールの位置は、親サーフェイスの左上に対して相対的な <xref:System.Windows.Forms.Control.Location> プロパティの値によって決まります。 親の左上の位置座標は `(x0,y0)` です。 コントロールのサイズは、<xref:System.Windows.Forms.Control.Size> プロパティによって決定され、コントロールの幅と高さを表します。

手動での配置やサイズ変更以外にも、コントロールの自動配置に役立つさまざまなコンテナー コントロールが用意されています。

詳細については、「[コントロールの位置とレイアウト](layout.md)」を参照してください。
<!-- TODO

## Control events

-->

## <a name="see-also"></a>関連項目

- [コントロールの位置とレイアウト](layout.md)
- [Label コントロールの概要 (Windows フォーム .NET)](labels.md)
- [コントロールを追加する (Windows フォーム .NET)](how-to-add-to-a-form.md)
