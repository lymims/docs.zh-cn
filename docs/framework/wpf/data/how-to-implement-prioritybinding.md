---
title: 如何：实现 PriorityBinding
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- data binding [WPF], PriorityBinding class
ms.assetid: d63b65ab-b3e9-4322-9aa8-1450f8d89532
ms.openlocfilehash: a7729ec3d06ec701cf2194bed5d90b5bed76573a
ms.sourcegitcommit: fb78d8abbdb87144a3872cf154930157090dd933
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/27/2018
ms.locfileid: "47398805"
---
# <a name="how-to-implement-prioritybinding"></a>如何：实现 PriorityBinding
[!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] 中的 <xref:System.Windows.Data.PriorityBinding> 的工作方式是指定一个绑定列表。 列表中的绑定按优先级从高到低排序。 对最高优先级绑定进行处理时，如果它成功返回了一个值，就不再需要处理列表中的其他绑定。 在最高优先级绑定需要长时间计算的情况下，将使用已经成功返回了值的绑定中优先级最高的那一个，直到较高优先级的绑定成功返回了值。  
  
## <a name="example"></a>示例  
 为了演示 <xref:System.Windows.Data.PriorityBinding> 的工作原理，我们创建了 `AsyncDataSource` 对象，它有三个属性： `FastDP`， `SlowerDP`，和 `SlowestDP`。  
  
 `FastDP` 的 Get 访问器返回数据成员 `_fastDP` 的值。  
  
 `SlowerDP` 的 Get 访问器等待 3 秒后返回数据成员 `_slowerDP` 的值。  
  
 `SlowestDP` 的 Get 访问器等待 5 秒后返回数据成员 `_slowestDP` 的值。  
  
> [!NOTE]
>  此示例只是为了方便演示。 [!INCLUDE[TLA#tla_net](../../../../includes/tlasharptla-net-md.md)] 准则不建议将比字段设置更慢的操作定义为属性。 有关详细信息，请参阅[NIB： 选择属性和方法](https://msdn.microsoft.com/library/55825e8f-7e2e-448a-9505-7217cc91b1af)。  
  
 [!code-csharp[PriorityBinding#1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/PriorityBinding/CSharp/Window1.xaml.cs#1)]
 [!code-vb[PriorityBinding#1](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/PriorityBinding/VisualBasic/AsyncDataSource.vb#1)]  
  
 <xref:System.Windows.Controls.TextBlock.Text%2A> 属性通过 <xref:System.Windows.Data.PriorityBinding> 绑定到上述的 `AsyncDS`:  
  
 [!code-xaml[PriorityBinding#2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/PriorityBinding/CSharp/Window1.xaml#2)]  
  
 当绑定引擎处理 <xref:System.Windows.Data.Binding> 对象时，它从已经绑定到 `SlowestDP` 属性的第一个 <xref:System.Windows.Data.Binding> 开始。 这个<xref:System.Windows.Data.Binding> 被处理时并没有成功返回值，因为它正处于 5 秒的睡眠状态，因此下一个 <xref:System.Windows.Data.Binding> 元素开始被处理。 下一个 <xref:System.Windows.Data.Binding> 也没有成功返回值，因为它正处于 3 秒的睡眠状态。 绑定引擎随后会转至下一个 <xref:System.Windows.Data.Binding> 元素，它绑定到了`FastDP` 属性。 该<xref:System.Windows.Data.Binding> 返回 "Fast Value" 的值。 于是 <xref:System.Windows.Controls.TextBlock> 显示出值 "Fast Value"。  
  
 3 秒后 `SlowerDP` 属性返回了值 "Slower Value"。 于是 <xref:System.Windows.Controls.TextBlock> 显示出值 "Slower Value"。  
  
 5 秒后 `SlowestDP` 属性返回了值 "Slowest Value"。 该绑定第一个列出，因此具有最高优先级。 于是 <xref:System.Windows.Controls.TextBlock> 显示出值 "Slowest Value"。  
  
 请参阅 <xref:System.Windows.Data.PriorityBinding> 获取有关 “怎样算是成功的绑定返回值” 的信息。  
  
## <a name="see-also"></a>请参阅  
 <xref:System.Windows.Data.Binding.IsAsync%2A?displayProperty=nameWithType>  
 [数据绑定概述](../../../../docs/framework/wpf/data/data-binding-overview.md)  
 [帮助主题](../../../../docs/framework/wpf/data/data-binding-how-to-topics.md)
