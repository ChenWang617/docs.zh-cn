---
title: 变量&#39; &lt;variablename&gt; &#39;隐藏封闭块中的变量
ms.date: 07/20/2015
f1_keywords:
- vbc30616
- bc30616
helpviewer_keywords:
- BC30616
ms.assetid: e7658ebc-da45-451b-a409-a0f8915f0beb
ms.openlocfilehash: 58e09caeb477d6b1df7f3be17e0a8ee05be3551e
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
---
# <a name="variable-39ltvariablenamegt39-hides-a-variable-in-an-enclosing-block"></a>变量&#39; &lt;variablename&gt; &#39;隐藏封闭块中的变量
变量包含在块中具有同名的另一个本地变量。  
  
 **错误 ID:** BC30616  
  
## <a name="to-correct-this-error"></a>更正此错误  
  
-   重命名封闭块中的变量，以便它不与任何其他本地变量相同。 例如：  
  
    ```  
    Dim a, b, x As Integer  
    If a = b Then  
       Dim y As Integer = 20 ' Uniquely named block variable.  
    End If  
    ```  
  
-   此错误的常见原因是使用`Catch e As Exception`的事件处理程序内。 如果出现这种情况，命名`Catch`块变量`ex`而非`e`。  
  
-   此错误的另一个常见来源是尝试访问在中声明的局部变量`Try`阻止在单独`Catch`块。 若要纠正此问题，声明外部变量`Try...Catch...Finally`结构。  
  
## <a name="see-also"></a>请参阅  
 [Try...Catch...Finally 语句](../../../visual-basic/language-reference/statements/try-catch-finally-statement.md)  
 [变量声明](../../../visual-basic/programming-guide/language-features/variables/variable-declaration.md)
