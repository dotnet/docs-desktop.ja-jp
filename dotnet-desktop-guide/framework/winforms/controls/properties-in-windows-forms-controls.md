---
title: コントロールのプロパティ
ms.date: 03/30/2017
helpviewer_keywords:
- custom controls [Windows Forms], properties overview (using code)
- controls [Windows Forms], properties
- properties [Windows Forms]
ms.assetid: 2785279b-fb57-4937-8f6b-2050e475db6f
ms.openlocfilehash: 3f9873ff032497a9cda6de199ed9db5ee9522d81
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/09/2020
ms.locfileid: "96974388"
---
# <a name="properties-in-windows-forms-controls"></a>Windows フォーム コントロールのプロパティ

Windows フォームコントロールは、基本クラスを形成する多くのプロパティを継承し <xref:System.Windows.Forms.Control?displayProperty=nameWithType> ます。 これには、、、、、、、、、、、、などのプロパティが含ま <xref:System.Windows.Forms.Control.Font%2A> <xref:System.Windows.Forms.Control.ForeColor%2A> <xref:System.Windows.Forms.Control.BackColor%2A> <xref:System.Windows.Forms.Control.Bounds%2A> <xref:System.Windows.Forms.Control.ClientRectangle%2A> <xref:System.Windows.Forms.Control.DisplayRectangle%2A> <xref:System.Windows.Forms.Control.Enabled%2A> <xref:System.Windows.Forms.Control.Focused%2A> <xref:System.Windows.Forms.Control.Height%2A> <xref:System.Windows.Forms.Control.Width%2A> <xref:System.Windows.Forms.Control.Visible%2A> <xref:System.Windows.Forms.Control.AutoSize%2A> れます。 継承されたプロパティの詳細については、「」を参照してください <xref:System.Windows.Forms.Control?displayProperty=nameWithType> 。  
  
 コントロールで継承されたプロパティをオーバーライドしたり、新しいプロパティを定義したりできます。  
  
## <a name="in-this-section"></a>このセクションの内容  

 [プロパティの定義](defining-a-property-in-windows-forms-controls.md)  
 カスタム コントロールまたはカスタム コンポーネントのプロパティを実装する方法と、そのプロパティをデザイン環境に統合する方法について説明します。  
  
 [ShouldSerialize メソッドと Reset メソッドによる既定値の定義](defining-default-values-with-the-shouldserialize-and-reset-methods.md)  
 カスタム コントロールまたはカスタム コンポーネントの既定のプロパティ値を定義する方法について説明します。  
  
 [プロパティ変更イベント](property-changed-events.md)  
 プロパティ値が変更されたときに、プロパティ変更通知を有効にする方法について説明します。  
  
 [方法: 内在コントロールのプロパティを公開する](how-to-expose-properties-of-constituent-controls.md)  
 カスタム複合コントロール内の内在コントロールのプロパティを公開する方法について説明します。  
  
 [カスタム コントロールへのメソッドの実装](method-implementation-in-custom-controls.md)  
 カスタム コントロールおよびカスタム コンポーネントにメソッドを実装する方法について説明します。  
  
## <a name="reference"></a>リファレンス  

 <xref:System.Windows.Forms.UserControl>  
 複合コントロールを実装するための基本クラスについて説明します。  
  
 <xref:System.ComponentModel.TypeConverterAttribute>  
 カスタムプロパティ型に使用するを指定する属性を文書にし <xref:System.ComponentModel.TypeConverter> ます。  
  
 <xref:System.ComponentModel.EditorAttribute>  
 カスタムプロパティに使用するを指定する属性を文書にし <xref:System.Drawing.Design.UITypeEditor> ます。  
  
## <a name="related-sections"></a>関連項目  

 [Windows フォーム コントロールの属性](attributes-in-windows-forms-controls.md)  
 カスタム コントロールとコンポーネントのプロパティや他のメンバーに適用できる属性について説明します。  
  
 [コンポーネントのデザイン時属性](/previous-versions/visualstudio/visual-studio-2013/tk67c2t8(v=vs.120))  
 ビジュアル デザイナーでデザインするときに正しく表示されるようにコンポーネントとコントロールに適用するメタデータ属性の一覧を表示します。  
  
 [デザイン時サポートの拡張](/previous-versions/visualstudio/visual-studio-2013/37899azc(v=vs.120))  
 デザイン時サポートを提供するエディターやデザイナーなどのクラスを実装する方法について説明します。
