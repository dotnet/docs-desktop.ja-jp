---
title: Unmanaged apps
ms.date: 03/30/2017
helpviewer_keywords:
- ActiveX controls [Windows Forms]
- COM interop [Windows Forms], Windows Forms
- COM [Windows Forms]
- Windows Forms, unmanaged
- Windows Forms, interop
ms.assetid: 81bc100c-fa49-4614-85a6-0f7ab59eac8a
ms.openlocfilehash: 2d60eef2788f144a4b14facdce6e179e7d0fc3c6
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/09/2020
ms.locfileid: "96975193"
---
# <a name="windows-forms-and-unmanaged-applications"></a>Windows フォームとアンマネージ アプリケーション

Windows フォーム アプリケーションとコントロールは、いくつかの注意事項がありますが、アンマネージ アプリケーションと相互運用できます。 次のセクションでは、Windows フォーム アプリケーションとコントロールがサポートするシナリオと構成、および、サポートしないシナリオと構成について説明します。  
  
## <a name="in-this-section"></a>このセクションの内容  

 [Windows フォームおよびアンマネージ アプリケーションの概要](windows-forms-and-unmanaged-applications-overview.md)  
 アンマネージ アプリケーションで使用する Windows フォーム コントロールを実装する方法に関する一般的な情報を提供します。  
  
 [方法: ShowDialog メソッドで Windows フォームを表示して COM 相互運用機能をサポートする](com-interop-by-displaying-a-windows-form-shadow.md)  
 <xref:System.Windows.Forms.Form.ShowDialog%2A?displayProperty=nameWithType> メソッドを使用して Windows フォームをアンマネージ アプリケーションで実行する方法を示すコード例を提供します。  
  
 [方法: 独自のスレッドで各 Windows フォームを表示して COM 相互運用機能をサポートする](how-to-support-com-interop-by-displaying-each-windows-form-on-its-own-thread.md)  
 独自のスレッドで Windows フォームを実行する方法を示すコード例を提供します。  
  
 「 [チュートリアル: Windows フォームを別個のスレッドに表示することによって COM 相互運用をサポートする](/previous-versions/visualstudio/visual-studio-2010/ms233639(v=vs.100))」も参照してください。  
  
## <a name="reference"></a>リファレンス  

 <xref:System.Windows.Forms.Form.ShowDialog%2A?displayProperty=nameWithType>  
 Windows フォーム用の個別のスレッドの作成に使用します。  
  
 <xref:System.Windows.Forms.Application.Run%2A?displayProperty=nameWithType>  
 スレッドのメッセージ ループを開始します。  
  
 <xref:System.Windows.Forms.Control.Invoke%2A>  
 フォームにアンマネージ アプリケーションからの呼び出しをマーシャリングします。  
  
## <a name="related-sections"></a>関連項目  

 [COM への .NET Framework コンポーネントの公開](/dotnet/framework/interop/exposing-dotnet-components-to-co)  
 .NET Framework の型をアンマネージ アプリケーションで使用する方法に関する一般情報を提供します。
