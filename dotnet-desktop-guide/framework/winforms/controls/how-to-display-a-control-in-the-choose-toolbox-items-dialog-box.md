---
title: '方法: [ツールボックス アイテムの選択] ダイアログ ボックスにコントロールを表示する'
ms.date: 08/23/2019
helpviewer_keywords:
- global assembly cache [Windows Forms], Choose Toolbox Items dialog box
- AssemblyFoldersEx [Windows Forms], Choose Toolbox Items dialog box
- controls [Windows Forms], display in Choose Toolbox Items dialog box
- assembly folder registration [Windows Forms], Choose Toolbox Items dialog box
- Choose Toolbox Items dialog box [Windows Forms], display control
ms.assetid: 01ef6eba-d044-40f0-951d-78eff7ebd9a9
ms.openlocfilehash: 501fd1054a0c7cc1accec6c7a3f8257da1a94417
ms.sourcegitcommit: 7f48b9ecf8a30db42c8ecea0dd4df577736631a2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/28/2021
ms.locfileid: "98957527"
---
# <a name="how-to-display-a-control-in-the-choose-toolbox-items-dialog-box"></a>方法: [ツールボックス アイテムの選択] ダイアログ ボックスにコントロールを表示する

コントロールを開発および配布するときに、Visual Studio の [ **ツールボックスアイテムの選択** ] ダイアログボックスにこれらのコントロールを表示することをお勧めします。これは、 **ツール** ボックスを右クリックして [ **アイテムの選択**] をクリックすると表示されます。 このダイアログボックスにコントロールが表示されるようにするには、AssemblyFoldersEx 登録プロシージャを使用します。

[ツールボックスアイテムの選択] ダイアログボックスにコントロールを表示するには、次のようにします。

- コントロールアセンブリをグローバルアセンブリキャッシュにインストールします。 詳細については、「 [方法: グローバルアセンブリキャッシュにアセンブリをインストール](/dotnet/framework/app-domains/install-assembly-into-gac)する」を参照してください。

  または

- AssemblyFoldersEx 登録プロシージャを使用して、コントロールとそれに関連付けられたデザイン時アセンブリを登録します。 AssemblyFoldersEx は、サードパーティベンダーがサポートする各バージョンのフレームワークのパスを格納するレジストリの場所です。 デザイン時の解決では、このレジストリの場所で参照アセンブリを見つけることができます。 レジストリスクリプトでは、ツールボックスに表示するコントロールを指定できます。

## <a name="see-also"></a>関連項目

- [デザイン時の Windows フォーム コントロールの開発](developing-windows-forms-controls-at-design-time.md)
- [方法: アセンブリをグローバル アセンブリ キャッシュにインストールする](/dotnet/framework/app-domains/install-assembly-into-gac)
- [チュートリアル: ツールボックスへのカスタム コンポーネントの自動設定](walkthrough-automatically-populating-the-toolbox-with-custom-components.md)
