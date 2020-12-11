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
# <a name="how-to-add-a-custom-place-to-a-file-dialog-box"></a><span data-ttu-id="90c06-102">方法: よく使用する場所をファイル ダイアログ ボックスに追加する</span><span class="sxs-lookup"><span data-stu-id="90c06-102">How To: Add a Custom Place to a File Dialog Box</span></span>
<span data-ttu-id="90c06-103">Windows Vista の既定の [開く] および [保存] ダイアログボックスの左側には、[ **お気に入りリンク**] というタイトルの領域があります。</span><span class="sxs-lookup"><span data-stu-id="90c06-103">The default open and save dialog boxes on Windows Vista have an area on the left side of the dialog box titled **Favorite Links**.</span></span> <span data-ttu-id="90c06-104">この領域にはカスタム プレイスという名称が付いています。</span><span class="sxs-lookup"><span data-stu-id="90c06-104">This area is called custom places.</span></span> <span data-ttu-id="90c06-105"><xref:System.Windows.Forms.OpenFileDialog>クラスとクラスを使用すると、 <xref:System.Windows.Forms.SaveFileDialog> フォルダーをコレクションに追加でき <xref:System.Windows.Forms.FileDialog.CustomPlaces%2A> ます。</span><span class="sxs-lookup"><span data-stu-id="90c06-105">The <xref:System.Windows.Forms.OpenFileDialog> and <xref:System.Windows.Forms.SaveFileDialog> classes allow you to add folders to the <xref:System.Windows.Forms.FileDialog.CustomPlaces%2A> collection.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="90c06-106">カスタムプレースをまたはに表示するに <xref:System.Windows.Forms.OpenFileDialog> は、 <xref:System.Windows.Forms.SaveFileDialog> <xref:System.Windows.Forms.FileDialog.AutoUpgradeEnabled%2A> プロパティを (既定値) に設定する必要があり `true` ます。</span><span class="sxs-lookup"><span data-stu-id="90c06-106">In order for a custom place to appear in the <xref:System.Windows.Forms.OpenFileDialog> or <xref:System.Windows.Forms.SaveFileDialog>, the <xref:System.Windows.Forms.FileDialog.AutoUpgradeEnabled%2A> property must be set to `true` (the default).</span></span>  
  
### <a name="to-add-a-custom-place-to-a-file-dialog-box"></a><span data-ttu-id="90c06-107">ファイル ダイアログ ボックスにカスタム プレイスを追加するには</span><span class="sxs-lookup"><span data-stu-id="90c06-107">To add a custom place to a file dialog box</span></span>  
  
- <span data-ttu-id="90c06-108"><xref:System.Windows.Forms.FileDialogCustomPlace>ダイアログボックスのコレクションに、パス、既知のフォルダー GUID、またはオブジェクトを追加し <xref:System.Windows.Forms.FileDialog.CustomPlaces%2A> ます。</span><span class="sxs-lookup"><span data-stu-id="90c06-108">Add a path, a Known Folder GUID, or a <xref:System.Windows.Forms.FileDialogCustomPlace> object to the <xref:System.Windows.Forms.FileDialog.CustomPlaces%2A> collection of the dialog box.</span></span>  
  
     <span data-ttu-id="90c06-109">次のコード例は、パスを追加する方法を示しています。</span><span class="sxs-lookup"><span data-stu-id="90c06-109">The following code example shows how to add a path:</span></span>  
  
    ```vb  
    OpenFileDialog1.CustomPlaces.Add("C:\MyCustomPlace")  
    ```  
  
    ```csharp  
    openFileDialog1.CustomPlaces.Add("C:\\MyCustomPlace");  
    ```  
  
## <a name="see-also"></a><span data-ttu-id="90c06-110">関連項目</span><span class="sxs-lookup"><span data-stu-id="90c06-110">See also</span></span>

- <xref:System.Windows.Forms.FileDialog>
- <xref:System.Windows.Forms.FileDialogCustomPlacesCollection.Add%2A?displayProperty=nameWithType>
- [<span data-ttu-id="90c06-111">ファイル ダイアログ ボックスのカスタム プレイス用既知のフォルダー GUID</span><span class="sxs-lookup"><span data-stu-id="90c06-111">Known Folder GUIDs for File Dialog Custom Places</span></span>](known-folder-guids-for-file-dialog-custom-places.md)
