---
title: 如何：在数据绑定中使用 XML 命名空间
ms.date: 03/30/2017
helpviewer_keywords:
- XML [WPF], namespaces
- data binding [WPF], XML namespaces
- namespaces [WPF], XML
ms.assetid: a47c832f-dc84-48f2-96d5-cde18fc4284b
ms.openlocfilehash: bd2a156920057dc197fabbaa46e3a2d886a1b322
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/23/2019
ms.locfileid: "54600344"
---
# <a name="how-to-use-xml-namespaces-in-data-binding"></a>如何：在数据绑定中使用 XML 命名空间
## <a name="example"></a>示例  
 本示例演示如何处理在 [!INCLUDE[TLA#tla_xml](../../../../includes/tlasharptla-xml-md.md)] 绑定源中指定的命名空间。  
  
 如果 [!INCLUDE[TLA2#tla_xml](../../../../includes/tla2sharptla-xml-md.md)] 数据具有以下 [!INCLUDE[TLA2#tla_xml](../../../../includes/tla2sharptla-xml-md.md)] 命名空间定义：  
  
 `<rss version="2.0" xmlns:dc="http://purl.org/dc/elements/1.1/">`  
  
 可以使用<xref:System.Windows.Data.XmlNamespaceMapping>元素将映射到命名空间<xref:System.Windows.Data.XmlNamespaceMapping.Prefix%2A>，如下面的示例。 然后，可以使用<xref:System.Windows.Data.XmlNamespaceMapping.Prefix%2A>来指代[!INCLUDE[TLA2#tla_xml](../../../../includes/tla2sharptla-xml-md.md)]命名空间。 <xref:System.Windows.Controls.ListBox>在此示例中显示*标题*并*标题*每个*项*。  
  
 [!code-xaml[XmlnsBindSnippet#XmlNamespaceMapping](../../../../samples/snippets/csharp/VS_Snippets_Wpf/XmlnsBindSnippet/CS/Window1.xaml#xmlnamespacemapping)]  
  
 请注意，<xref:System.Windows.Data.XmlNamespaceMapping.Prefix%2A>指定不需要匹配中使用的一个[!INCLUDE[TLA2#tla_xml](../../../../includes/tla2sharptla-xml-md.md)]源; 如果前缀中的更改[!INCLUDE[TLA2#tla_xml](../../../../includes/tla2sharptla-xml-md.md)]源映射仍然正常工作。  
  
 在此特定示例中，[!INCLUDE[TLA2#tla_xml](../../../../includes/tla2sharptla-xml-md.md)]数据来自于 web 服务，但<xref:System.Windows.Data.XmlNamespaceMapping>元素还处理内联[!INCLUDE[TLA2#tla_xml](../../../../includes/tla2sharptla-xml-md.md)]或[!INCLUDE[TLA2#tla_xml](../../../../includes/tla2sharptla-xml-md.md)]嵌入的文件中的数据。  
  
## <a name="see-also"></a>请参阅
- [使用 XMLDataProvider 和 XPath 查询绑定到 XML 数据](../../../../docs/framework/wpf/data/how-to-bind-to-xml-data-using-an-xmldataprovider-and-xpath-queries.md)
- [数据绑定概述](../../../../docs/framework/wpf/data/data-binding-overview.md)
- [帮助主题](../../../../docs/framework/wpf/data/data-binding-how-to-topics.md)
