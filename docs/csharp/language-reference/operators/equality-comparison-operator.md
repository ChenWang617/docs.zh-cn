---
title: == 运算符（C# 参考）
ms.date: 07/20/2015
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
f1_keywords:
- ==_CSharpKeyword
helpviewer_keywords:
- == operator [C#]
- equality operator [C#]
ms.assetid: 34c6b597-caa2-4855-a7cd-38ecdd11bd07
caps.latest.revision: 14
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: ca22846325968519a1f7625461867c0d83a1a9f5
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="-operator-c-reference"></a>== 运算符（C# 参考）
对于预定义的值类型，如果其操作数的值相等，则相等运算符 (`==`) 返回 true，否则返回 `false`。 对于 [string](../../../csharp/language-reference/keywords/string.md) 外的引用类型，如果两个操作数引用同一对象，则 `==` 会返回 `true`。 对于 `string` 类型，`==` 会比较字符串的值。  
  
## <a name="remarks"></a>备注  
 用户定义的值类型可以重载 `==` 运算符（请参阅[运算符](../../../csharp/language-reference/keywords/operator.md)）。 用户定义的引用类型情况也相似，但是默认情况下，`==` 的行为如上述预定义和用户定义的引用类型所述。 如果已重载 `==`，则必须同时重载 [!=](../../../csharp/language-reference/operators/not-equal-operator.md)。 对整数类型的操作通常可用于枚举。  
  
## <a name="example"></a>示例  
 [!code-csharp[csRefOperators#36](../../../csharp/language-reference/operators/codesnippet/CSharp/equality-comparison-operator_1.cs)]  
  
## <a name="see-also"></a>另请参阅  
 [C# 参考](../../../csharp/language-reference/index.md)  
 [C# 编程指南](../../../csharp/programming-guide/index.md)  
 [C# 运算符](../../../csharp/language-reference/operators/index.md)
