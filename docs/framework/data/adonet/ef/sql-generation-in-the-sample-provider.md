---
title: 示例提供程序中的 SQL 生成
ms.date: 03/30/2017
ms.assetid: e70f553d-4622-4627-928e-1aa2ee605d8e
ms.openlocfilehash: b2397570bb5f312aa6a3955a76234bde508fcc6a
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/23/2019
ms.locfileid: "54505494"
---
# <a name="sql-generation-in-the-sample-provider"></a>示例提供程序中的 SQL 生成
[实体框架示例提供程序](https://code.msdn.microsoft.com/windowsdesktop/Entity-Framework-Sample-6a9801d0)演示了 ADO.NET 数据提供程序支持的新组件[!INCLUDE[adonet_ef](../../../../../includes/adonet-ef-md.md)]。  它使用 SQL Server 2005 数据库，并实现为 System.Data.SqlClient ADO.NET 2.0 数据提供程序的一个包装。  
  
 该示例提供程序的 SQL 生成模块（位于 SQL Generation 文件夹下，不包括 DmlSqlGenerator.cs 文件）采用一个输入 DbQueryCommandTree，并且生成单个 SQL SELECT 语句。  
  
## <a name="in-this-section"></a>本节内容  
 本节包括下列主题：  
  
 [体系结构和设计](../../../../../docs/framework/data/adonet/ef/architecture-and-design.md)  
  
 [演练：SQL 生成](../../../../../docs/framework/data/adonet/ef/walkthrough-sql-generation.md)  
  
## <a name="see-also"></a>请参阅
- [SQL 生成](../../../../../docs/framework/data/adonet/ef/sql-generation.md)
