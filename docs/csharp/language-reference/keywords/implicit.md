---
title: implicit（C# 参考）
ms.date: 07/20/2015
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
f1_keywords:
- implicit
- implicit_CSharpKeyword
helpviewer_keywords:
- implicit keyword [C#]
ms.assetid: 34db590e-eb3a-4f11-88d0-ffb3cd753dab
caps.latest.revision: 19
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: c893c7a9afbdc6f715010d537e9ccaf66c5785c1
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="implicit-c-reference"></a>implicit（C# 参考）
`implicit` 关键字用于声明隐式的用户定义类型转换运算符。 如果可以确保转换过程不会造成数据丢失，则可使用该关键字在用户定义类型和其他类型之间进行隐式转换。  
  
## <a name="example"></a>示例  
 [!code-csharp[csrefKeywordsConversion#5](../../../csharp/language-reference/keywords/codesnippet/CSharp/implicit_1.cs)]  
  
 隐式转换可以通过消除不必要的强制转换来提高源代码的可读性。 但是，因为隐式转换不需要程序员将一种类型显式强制转换为另一种类型，所以使用隐式转换时必须格外小心，以免出现意外结果。 一般情况下，隐式转换运算符应当从不引发异常并且从不丢失信息，以便可以在程序员不知晓的情况下安全使用它们。 如果转换运算符不能满足那些条件，则应将其标记为 `explicit`。 有关详细信息，请参阅[使用转换运算符](../../../csharp/programming-guide/statements-expressions-operators/using-conversion-operators.md)。  
  
## <a name="c-language-specification"></a>C# 语言规范  
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a>另请参阅  
 [C# 参考](../../../csharp/language-reference/index.md)  
 [C# 编程指南](../../../csharp/programming-guide/index.md)  
 [C# 关键字](../../../csharp/language-reference/keywords/index.md)  
 [explicit](../../../csharp/language-reference/keywords/explicit.md)  
 [运算符（C# 参考）](../../../csharp/language-reference/keywords/operator.md)  
 [如何：在结构之间实现用户定义的转换](../../../csharp/programming-guide/statements-expressions-operators/how-to-implement-user-defined-conversions-between-structs.md)
