---
title: WF 中的状态机活动
ms.date: 03/30/2017
ms.assetid: 93312eaf-07e0-4a55-b4f7-4cdbbc4dee2d
ms.openlocfilehash: 3086348d1c4f29e3f446e9525a12a9c207efb328
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/23/2019
ms.locfileid: "54618995"
---
# <a name="state-machine-activities-in-wf"></a>WF 中的状态机活动
[!INCLUDE[net_v45](../../../includes/net-v45-md.md)] 提供几个系统提供的活动和用于创建状态机工作流的活动设计器。  
  
|||  
|-|-|  
|<xref:System.Activities.Statements.StateMachine>|使用熟悉的状态机范例执行包含的活动。|  
|<xref:System.Activities.Statements.State>|代表状态机中的状态。|  
|<xref:System.Activities.Core.Presentation.FinalState>|表示状态机中的终止状态。 <xref:System.Activities.Core.Presentation.FinalState> 是在创建预配置为终止状态的 <xref:System.Activities.Statements.State> 时所使用的活动设计器。 有关详细信息，请参阅[FinalState 活动设计器](/visualstudio/workflow-designer/finalstate-activity-designer)。|  
|<xref:System.Activities.Statements.Transition>|表示两个状态间的转换。 没有任何**工具箱**项<xref:System.Activities.Statements.Transition>; 通过拖放两个状态之间的一条线方式在工作流设计器上创建转换或通过删除状态时出现的三角形上一个状态悬停在另一个. 有关详细信息，请参阅[Transition 活动设计器](/visualstudio/workflow-designer/transition-activity-designer)。|  
  
## <a name="see-also"></a>请参阅
- [入门教程](../../../docs/framework/windows-workflow-foundation/getting-started-tutorial.md)
