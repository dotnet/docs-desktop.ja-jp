---
title: ラベルコントロールでアクセスキーを作成する
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- controls [Windows Forms], access keys
- dialog box controls [Windows Forms], mnemonics
- access keys [Windows Forms], creating for controls
- Label control [Windows Forms], creating access keys
- mnemonics [Windows Forms], adding to dialog box controls
- mnemonics
- Windows Forms controls, access keys
- UseMnemonic property [Windows Forms], Label control
- keyboard shortcuts [Windows Forms], creating for controls
- access keys [Windows Forms], Windows Forms
ms.assetid: 5ee8f823-80be-4a4f-96a4-412671e2e306
ms.openlocfilehash: 800afc03e71435e2721456b93bb9704af01f714a
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/09/2020
ms.locfileid: "96980907"
---
# <a name="how-to-create-access-keys-with-windows-forms-label-controls"></a>方法: Windows フォームの Label コントロールでアクセス キーを作成する
Windows フォーム <xref:System.Windows.Forms.Label> コントロールを使用して、他のコントロールのアクセスキーを定義できます。 ラベルコントロールでアクセスキーを定義すると、ユーザーは ALT キーと指定した文字を押して、タブオーダーでその後のコントロールにフォーカスを移動できます。 ラベルはフォーカスを受け取ることができないため、フォーカスはタブオーダーの次のコントロールに自動的に移動します。 この手法を使用すると、テキストボックス、コンボボックス、リストボックス、およびデータグリッドにアクセスキーを割り当てることができます。  
  
### <a name="to-assign-an-access-key-to-a-control-with-a-label"></a>ラベルを持つコントロールにアクセスキーを割り当てるには  
  
1. まず、ラベルを描画してから、もう一方のコントロールを描画します。  
  
     または  
  
     コントロールを任意の順序で描画し、 <xref:System.Windows.Forms.Control.TabIndex%2A> ラベルのプロパティを他のコントロールよりも1小さい値に設定します。  
  
2. ラベルの <xref:System.Windows.Forms.Label.UseMnemonic%2A> プロパティをに設定し `true` ます。  
  
3. ラベルのプロパティにアンパサンド (&) を使用して、 <xref:System.Windows.Forms.Label.Text%2A> ラベルのアクセスキーを割り当てます。 詳細については、「 [Windows フォームコントロールのアクセスキーの作成](how-to-create-access-keys-for-windows-forms-controls.md)」を参照してください。  
  
    > [!NOTE]
    > アンパサンドは、アクセスキーの作成に使用するのではなく、ラベルコントロールに表示することができます。 これは、データにアンパサンドが含まれているレコードセット内のフィールドにラベルコントロールをバインドした場合に発生する可能性があります。 ラベルコントロールにアンパサンドを表示するには、 <xref:System.Windows.Forms.Label.UseMnemonic%2A> プロパティをに設定し `false` ます。 アンパサンドを表示し、アクセスキーも持っている場合は、 <xref:System.Windows.Forms.Label.UseMnemonic%2A> プロパティをに設定 `true` し、1つのアンパサンド (&) とアンパサンドを2つのアンパサンドで表示するようにアクセスキーを指定します。  
  
    ```vb  
    Label1.UseMnemonic = True  
    Label1.Text = "&Print"  
    Label2.UseMnemonic = True  
    Label2.Text = "&Copy && Paste"  
    ```  
  
    ```csharp  
    label1.UseMnemonic = true;  
    label1.Text = "&Print";  
    label2.UseMnemonic = true;  
    label2.Text = "&Copy && Paste";  
    ```  
  
    ```cpp  
    label1->UseMnemonic = true;  
    label1->Text = "&Print";  
    label2->UseMnemonic = true;  
    label2->Text = "&Copy && Paste";  
    ```  
  
## <a name="see-also"></a>関連項目

- [方法: Windows フォーム Label コントロールのサイズを内容に合わせて変更する](how-to-size-a-windows-forms-label-control-to-fit-its-contents.md)
- [Label コントロールの概要](label-control-overview-windows-forms.md)
- [Label コントロール](label-control-windows-forms.md)
