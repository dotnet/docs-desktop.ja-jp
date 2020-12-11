---
title: '方法: データ バインドで XML 名前空間を使用する'
ms.date: 03/30/2017
helpviewer_keywords:
- XML [WPF], namespaces
- data binding [WPF], XML namespaces
- namespaces [WPF], XML
ms.assetid: a47c832f-dc84-48f2-96d5-cde18fc4284b
ms.openlocfilehash: ad671b81bdfc1c168294123d035ccf7287b3b2fc
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/09/2020
ms.locfileid: "96982612"
---
# <a name="how-to-use-xml-namespaces-in-data-binding"></a>方法: データ バインドで XML 名前空間を使用する
## <a name="example"></a>例
 この例では、XML のバインディング ソースに指定された名前空間の処理方法を示します。

 XML データに次の XML 名前空間定義がある場合:

 `<rss version="2.0" xmlns:dc="http://purl.org/dc/elements/1.1/">`

 次の例で示すように、<xref:System.Windows.Data.XmlNamespaceMapping> 要素を使用して、名前空間を <xref:System.Windows.Data.XmlNamespaceMapping.Prefix%2A> にマップできます。 その後、<xref:System.Windows.Data.XmlNamespaceMapping.Prefix%2A> を使用して、XML 名前空間を参照できます。 この例の <xref:System.Windows.Controls.ListBox> には、各 *item* の *title* と *dc:date* が表示されます。

 [!code-xaml[XmlnsBindSnippet#XmlNamespaceMapping](~/samples/snippets/csharp/VS_Snippets_Wpf/XmlnsBindSnippet/CS/Window1.xaml#xmlnamespacemapping)]

 指定する <xref:System.Windows.Data.XmlNamespaceMapping.Prefix%2A> は、XML ソースで使用されているものと一致する必要はありません。XML ソースでプレフィックスが変更された場合でも、マッピングは引き続き機能します。

 この特定の例では、XML データは Web サービスから取得されますが、<xref:System.Windows.Data.XmlNamespaceMapping> 要素は、インラインの XML でも、埋め込まれているファイルの XML データでも有効です。

## <a name="see-also"></a>関連項目

- [XMLDataProvider と XPath クエリを使用して XML データにバインドする](how-to-bind-to-xml-data-using-an-xmldataprovider-and-xpath-queries.md)
- [データ バインディングの概要](/dotnet/desktop-wpf/data/data-binding-overview)
- [方法トピック](data-binding-how-to-topics.md)
