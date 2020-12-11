---
title: '方法: プライベート フォント コレクションを作成する'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- private font collections [Windows Forms], creating
- fonts [Windows Forms], creating private collections
ms.assetid: 6533d5e5-a8dc-4b76-9fc4-3bf75c8b9212
ms.openlocfilehash: 0bb7293a5423004a13cf98b79bba0a6c411a7c97
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/09/2020
ms.locfileid: "96974838"
---
# <a name="how-to-create-a-private-font-collection"></a>方法: プライベート フォント コレクションを作成する
クラスは、 <xref:System.Drawing.Text.PrivateFontCollection> 抽象基本クラスから継承され <xref:System.Drawing.Text.FontCollection> ます。 オブジェクトを使用し <xref:System.Drawing.Text.PrivateFontCollection> て、アプリケーション専用の一連のフォントを維持することができます。 プライベートフォントコレクションには、インストールされているシステムフォントだけでなく、コンピューターにインストールされていないフォントを含めることができます。 フォントファイルをプライベートフォントコレクションに追加するには、 <xref:System.Drawing.Text.PrivateFontCollection.AddFontFile%2A> オブジェクトのメソッドを呼び出し <xref:System.Drawing.Text.PrivateFontCollection> ます。  
  
 <xref:System.Drawing.Text.FontCollection.Families%2A>オブジェクトのプロパティには、 <xref:System.Drawing.Text.PrivateFontCollection> オブジェクトの配列が含まれてい <xref:System.Drawing.FontFamily> ます。  
  
 プライベートフォントコレクション内のフォントファミリの数は、必ずしもコレクションに追加されたフォントファイルの数と同じではありません。 たとえば、ファイル ArialBd、Times. tff、および TimesBd. tff をコレクションに追加するとします。 2つのファイルがありますが、コレクション内のファミリは2つだけです。 tff と TimesBd は同じファミリに属しているためです。  
  
## <a name="example"></a>例  
 次の例では、オブジェクトに次の3つのフォントファイルを追加し <xref:System.Drawing.Text.PrivateFontCollection> ます。  
  
- C: \\ *systemroot*\ フォント \ \ ff (Arial、regular)  
  
- C: \\ *systemroot*\Fonts\CourBI.tff (Courier new、太字斜体)  
  
- C: \\ *systemroot*\Fonts\TimesBd.tff (Times New Roman, bold)  
  
 このコードは、オブジェクトのプロパティからオブジェクトの配列を取得し <xref:System.Drawing.FontFamily> <xref:System.Drawing.Text.FontCollection.Families%2A> <xref:System.Drawing.Text.PrivateFontCollection> ます。  
  
 コードは、コレクション内の各オブジェクトに対して、メソッドを呼び出して、 <xref:System.Drawing.FontFamily> <xref:System.Drawing.FontFamily.IsStyleAvailable%2A> さまざまなスタイル (標準、太字、斜体、太字の斜体、下線、および取り消し線) が使用可能かどうかを判断します。 メソッドに渡される引数 <xref:System.Drawing.FontFamily.IsStyleAvailable%2A> は、列挙体のメンバーです <xref:System.Drawing.FontStyle> 。  
  
 特定のファミリ/スタイルの組み合わせを使用できる場合は、 <xref:System.Drawing.Font> そのファミリとスタイルを使用してオブジェクトが作成されます。 コンストラクターに渡される最初の引数 <xref:System.Drawing.Font.%23ctor%2A> は、フォントファミリ名です ( <xref:System.Drawing.FontFamily> 他の種類のコンストラクターの場合と同様に、オブジェクトではありません <xref:System.Drawing.Font.%23ctor%2A> )。 <xref:System.Drawing.Font>オブジェクトが構築されると、 <xref:System.Drawing.Graphics.DrawString%2A> クラスのメソッドに渡され、 <xref:System.Drawing.Graphics> スタイルの名前と共にファミリ名が表示されます。  
  
 次のコードの出力は、次の図に示す出力に似ています。  
  
 ![さまざまなフォントのテキストを表示するスクリーンショット。](./media/how-to-create-a-private-font-collection/various-fonts-text-output.png)  
  
 Arial。 tff (次のコード例ではプライベートフォントコレクションに追加されています) は、Arial 標準スタイルのフォントファイルです。 ただし、プログラムの出力には、Arial フォントファミリに対して通常とは異なるいくつかのスタイルが表示されていることに注意してください。 これは、GDI + が標準スタイルの太字、斜体、太字の斜体スタイルをシミュレートできるためです。 GDI + では、標準スタイルから下線と strikeouts を生成することもできます。  
  
 同様に、GDI + は、太字スタイルまたは斜体スタイルから太字の斜体スタイルをシミュレートできます。 プログラムの出力は、タイムファミリでは、タイムファミリでも太字の斜体スタイルを使用できることを示しています。 tff (Times New Roman, bold) は、コレクション内の唯一の時刻ファイルです。  
  
 [!code-csharp[System.Drawing.FontsAndText#51](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.FontsAndText/CS/Class1.cs#51)]
 [!code-vb[System.Drawing.FontsAndText#51](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.FontsAndText/VB/Class1.vb#51)]  
  
## <a name="compiling-the-code"></a>コードのコンパイル  
 前の例は、Windows フォームで使用するように設計されてい <xref:System.Windows.Forms.PaintEventArgs> `e` ます。これは、のパラメーターであるを必要とし <xref:System.Windows.Forms.PaintEventHandler> ます。  
  
## <a name="see-also"></a>関連項目

- <xref:System.Drawing.Text.PrivateFontCollection>
- [フォントとテキストの使用](using-fonts-and-text.md)
