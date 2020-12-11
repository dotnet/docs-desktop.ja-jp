---
title: WPF コントロールの使用
ms.date: 03/30/2017
helpviewer_keywords:
- Windows Forms Designer [Windows Forms], interoperability with WPF
- interoperability [WPF]
ms.assetid: 03c85dce-26ad-44cd-bc1d-8e0cb56de096
author: jillre
ms.author: jillfra
manager: jillfra
ms.openlocfilehash: dfc086b4873c41bf1919b680d472807283e8a340
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/09/2020
ms.locfileid: "96975202"
---
# <a name="use-wpf-controls-in-windows-forms-apps"></a>Windows フォームアプリで WPF コントロールを使用する

Windows フォームベースのアプリケーションでは、Windows Presentation Foundation (WPF) コントロールを使用できます。 これらは2つの異なるビューテクノロジですが、円滑に相互運用されます。

Visual Studio の Windows フォームデザイナーには、Windows Presentation Foundation コントロールをホストするためのビジュアルデザイン環境が用意されています。 WPF コントロールは、という名前の特殊な Windows フォームコントロールによってホストされ <xref:System.Windows.Forms.Integration.ElementHost> ます。 このコントロールにより、WPF コントロールはフォームのレイアウトに参加し、キーボードおよびマウスメッセージを受け取ることができます。 デザイン時には、 <xref:System.Windows.Forms.Integration.ElementHost> Windows フォームコントロールと同じようにコントロールを配置できます。

WPF ベースのアプリケーションでは、Windows フォームコントロールを使用することもできます。 詳細については、「 [Visual Studio での XAML のデザイン](/visualstudio/xaml-tools/designing-xaml-in-visual-studio)」を参照してください。

## <a name="see-also"></a>関連項目

- [WPF と Windows フォームの相互運用](/dotnet/framework/wpf/advanced/wpf-and-windows-forms-interoperation)
