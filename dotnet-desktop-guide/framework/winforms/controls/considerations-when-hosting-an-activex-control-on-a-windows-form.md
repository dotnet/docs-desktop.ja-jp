---
title: Windows フォームで ActiveX コントロールをホストする場合の考慮事項
ms.date: 03/30/2017
helpviewer_keywords:
- Windows Forms controls, ActiveX controls
- ActiveX controls [Windows Forms], hosting
- Windows Forms, ActiveX controls
- Windows Forms, hosting ActiveX controls
- ActiveX controls [Windows Forms], adding
ms.assetid: 2509302d-a74e-484f-9890-2acdbfa67a68
ms.openlocfilehash: d4d990bf904fbd8f89fa2a6f70117212a44d3932
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/09/2020
ms.locfileid: "96974283"
---
# <a name="considerations-when-hosting-an-activex-control-on-a-windows-form"></a>Windows フォームで ActiveX コントロールをホストする場合の考慮事項

Windows フォームは、Windows フォーム コントロールをホストするために最適化されていますが、ActiveX コントロールを使うこともできます。 ActiveX コントロールを使うアプリケーションを計画するときは、次の考慮事項に留意してください。  
  
- **セキュリティ** 共通言語ランタイムは、コード アクセス セキュリティに関して強化されました。 Windows フォームを使うアプリケーションは、完全に信頼された環境では問題なく動作し、信頼性が高くない環境ではほとんどの機能がアクセス可能な状態で動作します。 Windows フォーム コントロールは、ブラウザーで問題なくホストできます。 ただし、Windows フォームの ActiveX コントロールは、これらのセキュリティ強化を利用できません。 ActiveX コントロールを実行するには、プロパティで設定されているアンマネージコードのアクセス許可が必要です <xref:System.Security.Permissions.SecurityPermissionAttribute.UnmanagedCode%2A?displayProperty=nameWithType> 。 セキュリティおよびアンマネージコードのアクセス許可の詳細については、「」を参照してください <xref:System.Security.Permissions.SecurityPermissionAttribute> 。  
  
- **総保有コスト** Windows フォームに追加される ActiveX コントロールは、その Windows フォーム全体と共に配置されるため、作成されるファイルのサイズが大幅に追加する可能性があります。 さらに、Windows フォームで ActiveX コントロールを使うには、レジストリへの書き込みが必要です。 これは、レジストリへの書き込みを必要としない Windows フォーム コントロールと比較して、ユーザーのコンピューターに大きく干渉します。  
  
    > [!NOTE]
    > ActiveX コントロールを操作するには、COM 相互運用ラッパーを使う必要があります。 詳しくは、「[Visual Basic および Visual C# における COM 相互運用性](/dotnet/visual-basic/programming-guide/com-interop/com-interoperability-in-net-framework-applications)」をご覧ください。  
    > [!NOTE]
    > ActiveX コントロールのメンバーの名前が .NET Framework で定義されている名前と一致する場合、ActiveX コントロールインポーターは、派生クラスの作成時にメンバー名の先頭に **Ctl** を付けます <xref:System.Windows.Forms.AxHost> 。 たとえば、ActiveX コントロールに **layout** という名前のメンバーがある場合、 **layout** イベントは .NET Framework 内で定義されるため、AxHost クラスの **CtlLayout** という名前に変更されます。  
  
## <a name="see-also"></a>関連項目

- [方法: Windows フォームに ActiveX コントロールを追加する](how-to-add-activex-controls-to-windows-forms.md)
- [コード アクセス セキュリティ](/dotnet/framework/misc/code-access-security)
- [各言語およびライブラリにおける、コントロールとプログラミング可能オブジェクトの比較](/previous-versions/visualstudio/visual-studio-2010/0061wezk(v=vs.100))
- [Windows フォームへのコントロールの追加](putting-controls-on-windows-forms.md)
- [Windows フォームコントロール](index.md)
