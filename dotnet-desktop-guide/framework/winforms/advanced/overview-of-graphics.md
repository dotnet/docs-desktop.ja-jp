---
title: グラフィックスについて
ms.date: 03/30/2017
ms.topic: overview
helpviewer_keywords:
- graphics [Windows Forms], using managed interface
- graphics [Windows Forms], about graphics
ms.assetid: a602aef8-a8c8-4c36-9816-74e7bad96a68
ms.openlocfilehash: e2cc534c32c24f3ac13248bd16b177205e480820
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/09/2020
ms.locfileid: "96979765"
---
# <a name="overview-of-graphics"></a>グラフィックスについて
GDI + は、Microsoft Windows オペレーティングシステムのサブシステムを形成するアプリケーションプログラミングインターフェイス (API) です。 GDI + は、画面やプリンターに関する情報を表示します。 名前が示すように、gdi + は GDI の後継であり、グラフィックスデバイスインターフェイス以前のバージョンの Windows に含まれています。  
  
## <a name="managed-class-interface"></a>マネージド クラスのインターフェイス  
 GDI + API は、マネージコードとして配置されたクラスのセットを介して公開されます。 この一連のクラスは、GDI + に対する *マネージクラスインターフェイス* と呼ばれます。 次の名前空間は、マネージド クラスのインターフェイスを構成します。  
  
- <xref:System.Drawing>  
  
- <xref:System.Drawing.Drawing2D>  
  
- <xref:System.Drawing.Imaging>  
  
- <xref:System.Drawing.Text>  
  
- <xref:System.Drawing.Printing>  
  
 GDI + などのグラフィックスデバイスインターフェイスを使用すると、特定のディスプレイデバイスの詳細を気にせずに、画面やプリンターに情報を表示できます。 プログラマは、GDI + クラスによって提供されるメソッドを呼び出します。 次に、これらのメソッドで、特定のデバイス ドライバーへの適切な呼び出しを実行します。 GDI + は、アプリケーションをグラフィックスハードウェアから分離します。 この分離により、プログラマがデバイスに依存しないアプリケーションを作成できるようになります。  
  
## <a name="see-also"></a>関連項目

- [グラフィックスの概要](graphics-overview-windows-forms.md)
