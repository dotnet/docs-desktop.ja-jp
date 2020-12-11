---
title: '方法: よく使用する場所をファイル ダイアログ ボックスに追加する'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- Custom Place to dialog box
- adding Custom Place to dialog box
- CustomPlaces collection
ms.assetid: 63f6469b-59cd-40f6-9e61-8b5831856780
ms.openlocfilehash: 7172e484451cf932413920910ec9124b3388bd76
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/09/2020
ms.locfileid: "96981015"
---
# <a name="how-to-add-a-custom-place-to-a-file-dialog-box"></a>方法: よく使用する場所をファイル ダイアログ ボックスに追加する
Windows Vista の既定の [開く] および [保存] ダイアログボックスの左側には、[ **お気に入りリンク**] というタイトルの領域があります。 この領域にはカスタム プレイスという名称が付いています。 <xref:System.Windows.Forms.OpenFileDialog>クラスとクラスを使用すると、 <xref:System.Windows.Forms.SaveFileDialog> フォルダーをコレクションに追加でき <xref:System.Windows.Forms.FileDialog.CustomPlaces%2A> ます。  
  
> [!NOTE]
> カスタムプレースをまたはに表示するに <xref:System.Windows.Forms.OpenFileDialog> は、 <xref:System.Windows.Forms.SaveFileDialog> <xref:System.Windows.Forms.FileDialog.AutoUpgradeEnabled%2A> プロパティを (既定値) に設定する必要があり `true` ます。  
  
### <a name="to-add-a-custom-place-to-a-file-dialog-box"></a>ファイル ダイアログ ボックスにカスタム プレイスを追加するには  
  
- <xref:System.Windows.Forms.FileDialogCustomPlace>ダイアログボックスのコレクションに、パス、既知のフォルダー GUID、またはオブジェクトを追加し <xref:System.Windows.Forms.FileDialog.CustomPlaces%2A> ます。  
  
     次のコード例は、パスを追加する方法を示しています。  
  
    ```vb  
    OpenFileDialog1.CustomPlaces.Add("C:\MyCustomPlace")  
    ```  
  
    ```csharp  
    openFileDialog1.CustomPlaces.Add("C:\\MyCustomPlace");  
    ```  
  
## <a name="see-also"></a>関連項目

- <xref:System.Windows.Forms.FileDialog>
- <xref:System.Windows.Forms.FileDialogCustomPlacesCollection.Add%2A?displayProperty=nameWithType>
- [ファイル ダイアログ ボックスのカスタム プレイス用既知のフォルダー GUID](known-folder-guids-for-file-dialog-custom-places.md)
