---
title: 二进制文件中的第一个操作数&#39;如果&#39;表达式必须是可以为 null 或为类型引用
ms.date: 07/20/2015
f1_keywords:
- bc33107
- vbc33107
helpviewer_keywords:
- BC33107
ms.assetid: 493c8899-3f6b-4471-8eb6-9284e8492768
ms.openlocfilehash: 85094ba6d6a44bf2e6cc4fba7946598c286a08a2
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/23/2019
ms.locfileid: "54668260"
---
# <a name="first-operand-in-a-binary-39if39-expression-must-be-nullable-or-a-reference-type"></a>二进制文件中的第一个操作数&#39;如果&#39;表达式必须是可以为 null 或为类型引用
`If`表达式可以采用两个或三个参数。 当你发送只有两个参数时，第一个参数必须是引用类型或可以为 null 的类型。 如果第一个参数的计算结果为任何值不是`Nothing`，则返回其值。 如果第一个参数的计算结果为`Nothing`，进行计算并返回第二个参数。  
  
 例如，下面的代码包含两个`If`表达式，一个带有三个参数，另一个具有两个参数。 表达式计算并返回相同的值。  
  
```vb  
' firstChoice is a nullable value type.  
Dim firstChoice? As Integer = Nothing  
Dim secondChoice As Integer = 1128  
' If expression with three arguments.  
Console.WriteLine(If(firstChoice IsNot Nothing, firstChoice, secondChoice))  
' If expression with two arguments.  
Console.WriteLine(If(firstChoice, secondChoice))  
```  
  
 以下表达式会导致此错误：  
  
```vb  
Dim choice1 = 4  
Dim choice2 = 5  
Dim booleanVar = True  
  
' Not valid.  
'Console.WriteLine(If(choice1 < choice2, 1))  
' Not valid.  
'Console.WriteLine(If(booleanVar, "Test returns True."))  
```  
  
 **错误 ID:** BC33107  
  
## <a name="to-correct-this-error"></a>更正此错误  
  
-   如果您不能更改代码，以便第一个参数是可以为 null 的类型或引用类型，请考虑将转换为三个参数`If`表达式，或设置为`If...Then...Else`语句。  
  
```vb  
Console.WriteLine(If(choice1 < choice2, 1, 2))  
Console.WriteLine(If(booleanVar, "Test returns True.", "Test returns False."))  
```  
  
## <a name="see-also"></a>请参阅
- [If 运算符](../../../visual-basic/language-reference/operators/if-operator.md)
- [If...Then...Else 语句](../../../visual-basic/language-reference/statements/if-then-else-statement.md)
- [可以为 null 的值类型](../../../visual-basic/programming-guide/language-features/data-types/nullable-value-types.md)
