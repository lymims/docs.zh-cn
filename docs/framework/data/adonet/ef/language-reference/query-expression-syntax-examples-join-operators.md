---
title: 查询表达式语法示例：联接运算符
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 343e8dda-70b2-409d-9334-ce9a880c3cea
ms.openlocfilehash: 0791b0e6d28c4967e513f4f81c6d46e07ddbdf86
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/23/2019
ms.locfileid: "54691874"
---
# <a name="query-expression-syntax-examples-join-operators"></a>查询表达式语法示例：联接运算符
联接是面向相互之间没有可导航关系的数据源（如关系数据库表）的查询中的一项重要操作。 联接两个数据源就是将一个数据源中的对象与另一个数据源中具有相同公共属性的对象相关联。 有关详细信息，请参阅[标准查询运算符概述](https://msdn.microsoft.com/library/24cda21e-8af8-4632-b519-c404a839b9b2)。  
  
 本主题中的示例演示如何使用<xref:System.Linq.Enumerable.GroupJoin%2A>并<xref:System.Linq.Enumerable.Join%2A>方法来查询[AdventureWorks 销售模型](https://msdn.microsoft.com/library/f16cd988-673f-4376-b034-129ca93c7832)使用查询表达式语法。 这些示例中使用的 AdventureWorks 销售模型从 AdventureWorks 示例数据库中的 Contact、Address、Product、SalesOrderHeader 和 SalesOrderDetail 等表生成。  
  
 本主题中的示例使用以下`using` / `Imports`语句：  
  
 [!code-csharp[DP L2E Examples#ImportsUsing](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DP L2E Examples/CS/Program.cs#importsusing)]
 [!code-vb[DP L2E Examples#ImportsUsing](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DP L2E Examples/VB/Module1.vb#importsusing)]  
  
## <a name="groupjoin"></a>GroupJoin  
  
### <a name="example"></a>示例  
 以下示例针对 SalesOrderHeader 表和 SalesOrderDetail 表执行 <xref:System.Linq.Enumerable.GroupJoin%2A> 以查找每个客户的订单数。 组联接等效于左外部联接，它返回第一个（左侧）数据源的每个元素（即使其他数据源中没有关联元素）。  
  
 [!code-csharp[DP L2E Examples#GroupJoin2](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DP L2E Examples/CS/Program.cs#groupjoin2)]
 [!code-vb[DP L2E Examples#GroupJoin2](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DP L2E Examples/VB/Module1.vb#groupjoin2)]  
  
### <a name="example"></a>示例  
 下面的示例对 Contact 和 SalesOrderHeader 表执行 <xref:System.Linq.Enumerable.GroupJoin%2A> 以查找每个联系人的订单数。 将显示每个联系人的订单数和 ID。  
  
 [!code-csharp[DP L2E Examples#GroupJoin](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DP L2E Examples/CS/Program.cs#groupjoin)]
 [!code-vb[DP L2E Examples#GroupJoin](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DP L2E Examples/VB/Module1.vb#groupjoin)]  
  
## <a name="join"></a>联接  
  
### <a name="example"></a>示例  
 以下示例针对 SalesOrderHeader 表和 SalesOrderDetail 表执行联接，以获得八月份的联机订单。  
  
 [!code-csharp[DP L2E Examples#Join](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DP L2E Examples/CS/Program.cs#join)]
 [!code-vb[DP L2E Examples#Join](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DP L2E Examples/VB/Module1.vb#join)]  
  
## <a name="see-also"></a>请参阅
- [LINQ to Entities 中的查询](../../../../../../docs/framework/data/adonet/ef/language-reference/queries-in-linq-to-entities.md)
