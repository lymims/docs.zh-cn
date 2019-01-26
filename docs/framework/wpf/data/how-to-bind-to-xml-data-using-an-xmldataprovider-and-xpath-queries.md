---
title: 如何：使用 XMLDataProvider 和 XPath 查询绑定到 XML 数据
ms.date: 03/30/2017
helpviewer_keywords:
- XmlDataProvider [WPF], binding to XML data
- data binding [WPF], binding to XML data using XmlDataProvider queries
- binding [WPF], to XML data using XmlDataProvider queries
ms.assetid: 7dcd018f-16aa-4870-8e47-c1b4ea31e574
ms.openlocfilehash: bb8eb727fb6614440721c4d34a7d1828182d2f14
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
ms.locfileid: "33557441"
---
# <a name="how-to-bind-to-xml-data-using-an-xmldataprovider-and-xpath-queries"></a>如何：使用 XMLDataProvider 和 XPath 查询绑定到 XML 数据
此示例演示如何通过 <xref:System.Windows.Data.XmlDataProvider> 绑定到 [!INCLUDE[TLA#tla_xml](../../../../includes/tlasharptla-xml-md.md)] 数据。  
  
 使用 <xref:System.Windows.Data.XmlDataProvider>，应用程序能通过数据绑定访问的底层数据可以是任何 [!INCLUDE[TLA2#tla_xml](../../../../includes/tla2sharptla-xml-md.md)] 树。 换而言之，<xref:System.Windows.Data.XmlDataProvider> 提供一种简便方式来让 [!INCLUDE[TLA#tla_xml](../../../../includes/tlasharptla-xml-md.md)] 树用作绑定源。  
  
## <a name="example"></a>示例  
 在下面的示例中，数据被作为 [!INCLUDE[TLA2#tla_xml](../../../../includes/tla2sharptla-xml-md.md)] *数据岛*，通过 <xref:System.Windows.FrameworkElement.Resources%2A> 块直接嵌入。 [!INCLUDE[TLA2#tla_xml](../../../../includes/tla2sharptla-xml-md.md)] 数据岛必须包装在 `<x:XData>` 标记中，且只能有一个根节点，在本示例中根节点为 *Inventory*。  
  
> [!NOTE]
>  [!INCLUDE[TLA2#tla_xml](../../../../includes/tla2sharptla-xml-md.md)] 数据的根节点具有一个将 [!INCLUDE[TLA2#tla_xml](../../../../includes/tla2sharptla-xml-md.md)] 命名空间设置为空字符串的 **xmlns** 属性。 将 XPath 查询应用到 [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] 页中内联的数据岛时，需要此属性。 在本内联示例中，[!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]继承 <xref:System.Windows> 命名空间，数据岛也是如此。 因此，你需要将命名空间设置为空，以防止 XPath 查询被限制在 <xref:System.Windows> 命名空间，从而误导查询。  
  
 [!code-xaml[XMLDataSource#1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/XmlDataSource/CS/Window1.xaml#1)]  
  
 如示例中所示，若要使用属性语法创建相同的绑定声明，必须对特殊字符进行正确转义。 有关详细信息，请参阅 [XML 字符实体和 XAML](../../../../docs/framework/xaml-services/xml-character-entities-and-xaml.md)。  
  
 运行此示例时，<xref:System.Windows.Controls.ListBox> 将显示以下项目。 它们是 *Books* 中，*Stock* 值为“*out*”，或者 *Number* 值为 3 或者大于等于 8 的所有元素的 *Title*。 请注意，没有返回 *CD* 项，因为 <xref:System.Windows.Data.XmlDataProvider> 中设置的 <xref:System.Windows.Data.XmlDataProvider.XPath%2A> 值指定了仅公开*Books*元素（实质上设置了一个筛选器）。  
  
 ![XPath 示例](../../../../docs/framework/wpf/data/media/xpathexample.PNG "XPathExample")  
  
 在此示例中，显示书名是因为在 <xref:System.Windows.DataTemplate> 中，<xref:System.Windows.Controls.TextBlock> 中的绑定的 <xref:System.Windows.Data.Binding.XPath%2A> 被设置为"*Title*"。 如果你想要显示某个属性的值，如*ISBN*，则可以将 <xref:System.Windows.Data.Binding.XPath%2A> 的值赋为 "`@ISBN`"。  
  
 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 中的 **XPath** 属性使用 XmlNode.SelectNodes 方法处理。 可以修改 **XPath** 查询以获取不同的结果。 以下是前一示例中被绑定 <xref:System.Windows.Controls.ListBox> 的 <xref:System.Windows.Data.Binding.XPath%2A> 查询的一些示例：  
  
-   `XPath="Book[1]"` 将返回第一个 Book 元素（“XML in Action”）。 请注意，**XPath** 索引从 1 而不是从 0 开始。  
  
-   `XPath="Book[@*]"` 将返回带有任意属性的所有 Book 元素。  
  
-   `XPath="Book[last()-1]"` 将返回倒数第二个 Book 元素（“Introducing Microsoft .NET”）。  
  
-   `XPath="*[position()>3]"` 将返回除前 3 个元素之外的所有 Book 元素。  
  
 当运行**XPath**查询时，它将返回 <xref:System.Xml.XmlNode> 或 XmlNodes 的列表。 <xref:System.Xml.XmlNode> 是[!INCLUDE[TLA#tla_clr](../../../../includes/tlasharptla-clr-md.md)]对象，这意味着你可以使用 <xref:System.Windows.Data.Binding.Path%2A> 属性来绑定到[!INCLUDE[TLA#tla_clr](../../../../includes/tlasharptla-clr-md.md)]属性。 再以上述示例为例。 如果该示例的其余部分保持不变，更改 <xref:System.Windows.Controls.TextBlock> 绑定为如下所示，你将在 <xref:System.Windows.Controls.ListBox> 中看到返回的 XmlNodes 的名称。 在此情况下，所有返回节点的名称为“*Book*”。  
  
 [!code-xaml[XmlDataSourceVariation#XmlNodePath](../../../../samples/snippets/csharp/VS_Snippets_Wpf/XmlDataSourceVariation/CS/Page1.xaml#xmlnodepath)]  
  
 在某些应用程序中，将 [!INCLUDE[TLA2#tla_xml](../../../../includes/tla2sharptla-xml-md.md)] 作为 [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] 页面源码内的数据岛嵌入可能很不方便，因为在编译时必须知道该数据的确切内容。 因此，从外部 [!INCLUDE[TLA2#tla_xml](../../../../includes/tla2sharptla-xml-md.md)] 文件获取数据也是支持的，如下面的示例所示：  
  
 [!code-xaml[XMLDataSource2#XmlFileExample](../../../../samples/snippets/csharp/VS_Snippets_Wpf/XmlDataSource2/CS/Window1.xaml#xmlfileexample)]  
  
 如果[!INCLUDE[TLA2#tla_xml](../../../../includes/tla2sharptla-xml-md.md)]数据驻留在远程[!INCLUDE[TLA2#tla_xml](../../../../includes/tla2sharptla-xml-md.md)]文件，可以通过指定对应的[!INCLUDE[TLA2#tla_url](../../../../includes/tla2sharptla-url-md.md)]到 <xref:System.Windows.Data.XmlDataProvider.Source%2A> 属性来访问数据，如下所示：  
  
```xml  
<XmlDataProvider x:Key="BookData" Source="http://MyUrl" XPath="Books"/>  
```  
  
## <a name="see-also"></a>请参阅  
 <xref:System.Windows.Data.ObjectDataProvider>  
 [绑定到 XDocument、XElement 或 LINQ to XML 查询结果](../../../../docs/framework/wpf/data/how-to-bind-to-xdocument-xelement-or-linq-for-xml-query-results.md)  
 [将主-详细模式与分层 XML 数据结合使用](../../../../docs/framework/wpf/data/how-to-use-the-master-detail-pattern-with-hierarchical-xml-data.md)  
 [绑定源概述](../../../../docs/framework/wpf/data/binding-sources-overview.md)  
 [数据绑定概述](../../../../docs/framework/wpf/data/data-binding-overview.md)  
 [帮助主题](../../../../docs/framework/wpf/data/data-binding-how-to-topics.md)
