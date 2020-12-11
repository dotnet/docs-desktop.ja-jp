---
title: '方法: PropertyNameChanged パターンを適用する'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- custom controls [Windows Forms], property changes (using code)
- data binding [Windows Forms], custom controls
- PropertyNameChanged pattern [Windows Forms], applying
ms.assetid: aa47ddf6-5223-40c4-833f-a78992194836
ms.openlocfilehash: 01afa713e97206ea192ba55dc2affad20163f872
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/09/2020
ms.locfileid: "96974366"
---
# <a name="how-to-apply-the-propertynamechanged-pattern"></a>方法: PropertyNameChanged パターンを適用する
次のコード例は、 *PropertyName* Changed パターンをカスタムコントロールに適用する方法を示しています。 Windows フォームデータバインディングエンジンで使用されるカスタムコントロールを実装するときに、このパターンを適用します。  
  
## <a name="example"></a>例  
 [!code-csharp[System.Windows.Forms.ChangeNotification#3](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.ChangeNotification/CS/Form1.cs#3)]
 [!code-vb[System.Windows.Forms.ChangeNotification#3](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.ChangeNotification/VB/Form1.vb#3)]  
  
## <a name="compiling-the-code"></a>コードのコンパイル  
 前のコード例をコンパイルするには、次の手順を実行します。  
  
- コードを空のコードファイルに貼り付けます。 カスタムコントロールは、メソッドを含む Windows フォームで使用する必要があり `Main` ます。  
  
## <a name="see-also"></a>関連項目

- [方法: INotifyPropertyChanged インターフェイスを実装する](how-to-implement-the-inotifypropertychanged-interface.md)
- [Windows フォーム データ バインディングの変更通知](change-notification-in-windows-forms-data-binding.md)
- [Windows フォームでのデータ バインディング](windows-forms-data-binding.md)
