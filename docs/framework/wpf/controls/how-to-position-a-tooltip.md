---
title: 如何：定位 ToolTip
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- ToolTip control [WPF], positioning
- positioning ToolTip controls [WPF]
ms.assetid: cddf3757-9e5f-4ce3-a6eb-44489cf3804a
ms.openlocfilehash: 403b070e782a6f243fd5a420e569daa02044dbb1
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/23/2019
ms.locfileid: "54727698"
---
# <a name="how-to-position-a-tooltip"></a>如何：定位 ToolTip
此示例演示如何在屏幕上指定的工具提示的位置。  
  
## <a name="example"></a>示例  
 可以使用一组中都定义的五个属性来定位 tooltip<xref:System.Windows.Controls.ToolTip>和<xref:System.Windows.Controls.ToolTipService>类。 下表显示了这两个五个属性集，并提供指向其根据类的参考文档。  
  
### <a name="corresponding-tooltip-properties-according-to-class"></a>类根据相应的工具提示属性  
  
|<xref:System.Windows.Controls.ToolTip?displayProperty=nameWithType> 类属性|<xref:System.Windows.Controls.ToolTipService?displayProperty=nameWithType> 类属性|  
|--------------------------------------------------------------------------------------------------------------------------------------------------------------|---------------------------------------------------------------------------------------------------------------------------------------------------------------------|  
|<xref:System.Windows.Controls.ToolTip.Placement%2A?displayProperty=nameWithType>|<xref:System.Windows.Controls.ToolTipService.Placement%2A?displayProperty=nameWithType>|  
|<xref:System.Windows.Controls.ToolTip.PlacementTarget%2A?displayProperty=nameWithType>|<xref:System.Windows.Controls.ToolTipService.PlacementTarget%2A?displayProperty=nameWithType>|  
|<xref:System.Windows.Controls.ToolTip.PlacementRectangle%2A?displayProperty=nameWithType>|<xref:System.Windows.Controls.ToolTipService.PlacementRectangle%2A?displayProperty=nameWithType>|  
|<xref:System.Windows.Controls.ToolTip.HorizontalOffset%2A?displayProperty=nameWithType>|<xref:System.Windows.Controls.ToolTipService.HorizontalOffset%2A?displayProperty=nameWithType>|  
|<xref:System.Windows.Controls.ToolTip.VerticalOffset%2A?displayProperty=nameWithType>|<xref:System.Windows.Controls.ToolTipService.VerticalOffset%2A?displayProperty=nameWithType>|  
  
 如果您通过使用定义的工具提示内容<xref:System.Windows.Controls.ToolTip>对象，可以使用其中一个类的属性; 但是，<xref:System.Windows.Controls.ToolTipService>属性优先。 使用<xref:System.Windows.Controls.ToolTipService>属性未定义为的工具提示<xref:System.Windows.Controls.ToolTip>对象。  
  
 下图显示如何使用这些属性来定位 tooltip。 虽然，则[!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)]在这些说明中的示例演示如何设置所定义的属性<xref:System.Windows.Controls.ToolTip>类的相应属性<xref:System.Windows.Controls.ToolTipService>类遵循相同的布局规则。 有关位置属性的可能值的详细信息，请参阅[Popup 放置行为](../../../../docs/framework/wpf/controls/popup-placement-behavior.md)。  
  
 ![工具提示放置](../../../../docs/framework/wpf/controls/media/tooltipplacement.png "ToolTipPlacement")  
通过使用放置属性的工具提示放置  
  
 ![通过使用放置矩形 tooltip](../../../../docs/framework/wpf/controls/media/tooltipplacementrectangle.png "ToolTipPlacementRectangle")  
通过使用放置和 PlacementRectangle 属性的工具提示放置  
  
 ![ToolTip 定位示意图](../../../../docs/framework/wpf/controls/media/tooltipplacementprhv.png "ToolTipPlacementPRHV")  
通过使用放置、 PlacementRectangle 和偏移量属性的工具提示放置  
  
 下面的示例演示如何使用<xref:System.Windows.Controls.ToolTip>属性来指定其内容的工具提示的位置<xref:System.Windows.Controls.ToolTip>对象。  
  
 [!code-xaml[ToolTipService#ToolTip](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ToolTipService/CSharp/Pane1.xaml#tooltip)]  
  
 [!code-csharp[ToolTipService#ToolTipCode](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ToolTipService/CSharp/Pane1.xaml.cs#tooltipcode)]
 [!code-vb[ToolTipService#ToolTipCode](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/ToolTipService/visualbasic/pane1.xaml.vb#tooltipcode)]  
  
 下面的示例演示如何使用<xref:System.Windows.Controls.ToolTipService>属性来指定其内容不是一个工具提示的位置<xref:System.Windows.Controls.ToolTip>对象。  
  
 [!code-xaml[ToolTipService#NoToolTip](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ToolTipService/CSharp/Pane1.xaml#notooltip)]  
  
 [!code-csharp[ToolTipService#NoToolTipCode](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ToolTipService/CSharp/Pane1.xaml.cs#notooltipcode)]
 [!code-vb[ToolTipService#NoToolTipCode](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/ToolTipService/visualbasic/pane1.xaml.vb#notooltipcode)]  
  
## <a name="see-also"></a>请参阅
- <xref:System.Windows.Controls.ToolTip>
- <xref:System.Windows.Controls.ToolTipService>
- [帮助主题](../../../../docs/framework/wpf/controls/tooltip-how-to-topics.md)
- [ToolTip 概述](../../../../docs/framework/wpf/controls/tooltip-overview.md)
- [使用 ContextMenuService 和 ToolTipService](https://msdn.microsoft.com/library/809b0e9c-d612-4cda-b8af-1a698c68f4d1)
