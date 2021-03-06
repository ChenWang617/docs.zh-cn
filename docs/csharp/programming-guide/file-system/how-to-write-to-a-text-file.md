---
title: 如何：写入文本文件（C# 编程指南）
ms.date: 07/20/2015
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
f1_keywords:
- TextWriter.WriteLine
- StreamWriter.Close
helpviewer_keywords:
- files [C#], text files
- text, writing to files [C#]
ms.assetid: 2e99f184-d88b-4719-a7f1-d9ec482aa809
caps.latest.revision: 23
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: fa6de76e3981e0f05b5b192045043422a8a912aa
ms.sourcegitcommit: 935d5267c44f9bce801468ef95f44572f1417e8c
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/28/2018
---
# <a name="how-to-write-to-a-text-file-c-programming-guide"></a>如何：写入文本文件（C# 编程指南）
以下示例给出了将文本写入文件的各种方法。 前两个示例对 <xref:System.IO.File?displayProperty=nameWithType> 类使用静态便捷方法以将任何 `IEnumerable<string>` 的每个元素和字符串写入文本文件。 示例 3 展示了在写入文件时必须分别处理文本的每一行时，如何将文本添加到文件。 示例 1-3 覆盖文件中的所有现有内容，但示例 4 展示如何将文本追加到现有文件。  
  
 这些示例都将字符串文本写入了文件。 如果想设置写入文件的文本的格式，请使用 <xref:System.String.Format%2A> 方法或 C# [字符串内插](../../../csharp/language-reference/tokens/interpolated.md)功能。  
  
## <a name="example"></a>示例  
 [!code-csharp[csFilesandFolders#3](../../../csharp/programming-guide/file-system/codesnippet/CSharp/how-to-write-to-a-text-file_1.cs)]  
  
## <a name="robust-programming"></a>可靠编程  
 以下情况可能会导致异常：  
  
-   文件已存在并且为只读。  
  
-   路径名可能太长。  
  
-   磁盘可能已满。  
  
## <a name="see-also"></a>请参阅  
 [C# 编程指南](../../../csharp/programming-guide/index.md)  
 [文件系统和注册表（C# 编程指南）](../../../csharp/programming-guide/file-system/index.md)  
 [示例：将集合保存到应用程序存储](http://code.msdn.microsoft.com/CSWinStoreAppSaveCollection-bed5d6e6)
