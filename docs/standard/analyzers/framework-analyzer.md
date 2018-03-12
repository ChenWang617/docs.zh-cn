---
title: ".NET 安全分析器 - .NET"
description: "了解如何使用 .NET Framework 分析器包中的.NET 安全分析器来查找和解决安全风险"
keywords: .NET, .NET Core
author: billwagner
ms.author: billwagner
ms.date: 01/25/2018
ms.topic: article
ms.prod: .net
ms.technology: dotnet-standard
ms.devlang: dotnet
ms.openlocfilehash: 06a387d72d06609182c8894dd874b241a5d7b69c
ms.sourcegitcommit: 3a96c706e4dbb4667bf3bf37edac9e1666646f93
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/27/2018
---
# <a name="the-net-framework-analyzer"></a><span data-ttu-id="cb753-104">.NET Framework 分析器</span><span class="sxs-lookup"><span data-stu-id="cb753-104">The .NET Framework Analyzer</span></span>

<span data-ttu-id="cb753-105">.NET Framework 分析器可用于查找基于 .NET Framework 的应用程序代码中存在的潜在问题。</span><span class="sxs-lookup"><span data-stu-id="cb753-105">You can use the .NET Framework Analyzer to find potential issues in your .NET Framework-based application code.</span></span> <span data-ttu-id="cb753-106">此分析器会找到潜在问题并给出问题的修复建议。</span><span class="sxs-lookup"><span data-stu-id="cb753-106">This analyzer finds potential issues and suggests fixes to them.</span></span>

<span data-ttu-id="cb753-107">分析器在编写代码时在 Visual Studio 中以交互方式运行，或作为 CI 生成的一部分。</span><span class="sxs-lookup"><span data-stu-id="cb753-107">The analyzer runs interactively in Visual Studio as you write your code or as part of a CI build.</span></span> <span data-ttu-id="cb753-108">在开发过程中，应尽早将分析器添加至项目。</span><span class="sxs-lookup"><span data-stu-id="cb753-108">You should add the analyzer to your project as early as possible in your development.</span></span> <span data-ttu-id="cb753-109">越早找到代码中的潜在问题，这些问题就越早得到修复。</span><span class="sxs-lookup"><span data-stu-id="cb753-109">The sooner you find any potential issues in your code, the easier they are to fix.</span></span> <span data-ttu-id="cb753-110">不过你可以将其添加至开发周期中的任何时间点。</span><span class="sxs-lookup"><span data-stu-id="cb753-110">However, you can add it at any time in the development cycle.</span></span> <span data-ttu-id="cb753-111">它会找到现有代码中的问题，并在持续开发的过程中对新问题进行警告。</span><span class="sxs-lookup"><span data-stu-id="cb753-111">It finds any issues with the existing code and warns about new issues as you keep developing.</span></span>

## <a name="installing-and-configuring-the-net-framework-analyzer"></a><span data-ttu-id="cb753-112">安装并配置 .NET Framework 分析器</span><span class="sxs-lookup"><span data-stu-id="cb753-112">Installing and configuring the .NET Framework Analyzer</span></span>

<span data-ttu-id="cb753-113">.NET Framework 分析器必须以 NuGet 包的形式安装在每个需要它项目上。</span><span class="sxs-lookup"><span data-stu-id="cb753-113">The .NET Security Analyzers must be installed as a NuGet package on every project where you want them to run.</span></span> <span data-ttu-id="cb753-114">只有一个开发人员需要将它们添加到项目。</span><span class="sxs-lookup"><span data-stu-id="cb753-114">Only one developer needs to add them to the project.</span></span> <span data-ttu-id="cb753-115">分析器包是项目依赖项，并且一旦具有更新的解决方案就会在每个开发人员的计算机上运行。</span><span class="sxs-lookup"><span data-stu-id="cb753-115">The analyzer package is a project dependency and will run on every developer's machine once it has the updated solution.</span></span>

<span data-ttu-id="cb753-116">[Microsoft.NetFramework.Analyzers](https://www.nuget.org/packages/Microsoft.NetFramework.Analyzers/) NuGet 包中提供了 .NET Framework 分析器。</span><span class="sxs-lookup"><span data-stu-id="cb753-116">The .NET Framework Analyzer is delivered in the [Microsoft.NetFramework.Analyzers](https://www.nuget.org/packages/Microsoft.NetFramework.Analyzers/) NuGet package.</span></span> <span data-ttu-id="cb753-117">此包只提供特定于 .NET Framework 的分析器，其中包括安全分析器。</span><span class="sxs-lookup"><span data-stu-id="cb753-117">This package provides only the analyzers specific to the .NET Framework, which includes security analyzers.</span></span> <span data-ttu-id="cb753-118">大多数情况下，你将需要 [Microsoft.CodeAnalysis.FxCopAnalyzers](https://www.nuget.org/packages/Microsoft.CodeAnalysis.FxCopAnalyzers) NuGet 包。</span><span class="sxs-lookup"><span data-stu-id="cb753-118">In most cases, you'll want the [Microsoft.CodeAnalysis.FxCopAnalyzers](https://www.nuget.org/packages/Microsoft.CodeAnalysis.FxCopAnalyzers) NuGet package.</span></span> <span data-ttu-id="cb753-119">FxCopAnalyzers 聚合包中包含了 Framework.Analyzers 包中的所有框架分析器以及下列分析器：</span><span class="sxs-lookup"><span data-stu-id="cb753-119">The FxCopAnalyzers aggregate package contains all the framework analyzers included in the Framework.Analyzers package as well as the following analyzers:</span></span>
- <span data-ttu-id="cb753-120">[Microsoft.CodeQuality.Analyzers](https://www.nuget.org/packages/Microsoft.CodeQuality.Analyzers)：提供通用指南和.NET Standard API 指南</span><span class="sxs-lookup"><span data-stu-id="cb753-120">[Microsoft.CodeQuality.Analyzers](https://www.nuget.org/packages/Microsoft.CodeQuality.Analyzers): Provides general guidance and guidance for .NET Standard APIs</span></span>
- <span data-ttu-id="cb753-121">[Microsoft.NetCore.Analyzers](https://www.nuget.org/packages/Microsoft.NetCore.Analyzers)：提供特定于 .NET Core API 的分析器。</span><span class="sxs-lookup"><span data-stu-id="cb753-121">[Microsoft.NetCore.Analyzers](https://www.nuget.org/packages/Microsoft.NetCore.Analyzers): Provides analyzers specific to .NET Core APIs.</span></span>
- <span data-ttu-id="cb753-122">[Text.Analyzers](https://www.nuget.org/packages/Text.Analyzers)：提供作为代码包含的文本指南（包括注释）。</span><span class="sxs-lookup"><span data-stu-id="cb753-122">[Text.Analyzers](https://www.nuget.org/packages/Text.Analyzers): Provides guidance for text included as code, including comments.</span></span>

<span data-ttu-id="cb753-123">若要进行安装，请右键单击项目，并选择“管理依赖项”。</span><span class="sxs-lookup"><span data-stu-id="cb753-123">To install it, right-click on the project, and select "Manage Dependencies".</span></span>
<span data-ttu-id="cb753-124">在 NuGet 资源管理器中搜索“NetFramework 分析器”，或根据自己的喜好选择“Fx Cop 分析器”。</span><span class="sxs-lookup"><span data-stu-id="cb753-124">From the NuGet explorer, search for "NetFramework Analyzer", or if you prefer, "Fx Cop Analyzer".</span></span> <span data-ttu-id="cb753-125">将最新稳定版本安装至解决方案中的所有项目。</span><span class="sxs-lookup"><span data-stu-id="cb753-125">Install the latest stable version in all projects in your solution.</span></span>

## <a name="using-the-net-framework-analyzer"></a><span data-ttu-id="cb753-126">使用 .NET Framework 分析器</span><span class="sxs-lookup"><span data-stu-id="cb753-126">Using the .NET Framework Analyzer</span></span>

<span data-ttu-id="cb753-127">安装 NuGet 包后，生成解决方案。</span><span class="sxs-lookup"><span data-stu-id="cb753-127">Once the NuGet package is installed, build your solution.</span></span> <span data-ttu-id="cb753-128">分析器将报告它在基本代码中找到的所有问题。</span><span class="sxs-lookup"><span data-stu-id="cb753-128">The analyzer will report any issues it locates in your codebase.</span></span> <span data-ttu-id="cb753-129">问题将以警告形式在 Visual Studio 错误列表窗口中报告，如下图中所示：</span><span class="sxs-lookup"><span data-stu-id="cb753-129">The issues are reported as warnings in the Visual Studio Error List window, as shown in the following image:</span></span>

![框架分析器报告的问题](./media/framework-analyzers-2.png)

<span data-ttu-id="cb753-131">编写代码时，代码中所有的潜在问题下方都会有波浪线。</span><span class="sxs-lookup"><span data-stu-id="cb753-131">As you write code, you see squiggles underneath any potential issue in your code.</span></span>
<span data-ttu-id="cb753-132">将鼠标悬停在问题位置就能看到该问题的详细信息和可能的修复方法建议，如下图所示：</span><span class="sxs-lookup"><span data-stu-id="cb753-132">Hover over any issue and you see details about the issue, and suggestions for any possible fix, as shown in the following image:</span></span>

![框架分析器所发现问题的交互式报告](./media/framework-analyzers-1.png)

<span data-ttu-id="cb753-134">分析器会检查解决方案中的代码，并对下列所有问题提供警告列表：</span><span class="sxs-lookup"><span data-stu-id="cb753-134">The analyzers examine the code in your solution and provide you with a list of warnings for any of these issues:</span></span>

### <a name="ca1058-types-should-not-extend-certain-base-types"></a><span data-ttu-id="cb753-135">CA1058：类型不应扩展某些基类型</span><span class="sxs-lookup"><span data-stu-id="cb753-135">CA1058: Types should not extend certain base types</span></span>

<span data-ttu-id="cb753-136">.NET Framework 中有少量不应直接自其派生的类型。</span><span class="sxs-lookup"><span data-stu-id="cb753-136">There are a small number of types in the .NET Framework that you should not derived from directly.</span></span> 

<span data-ttu-id="cb753-137">**类别：**设计</span><span class="sxs-lookup"><span data-stu-id="cb753-137">**Category:** Design</span></span>

<span data-ttu-id="cb753-138">**严重性：** 警告</span><span class="sxs-lookup"><span data-stu-id="cb753-138">**Severity:** Warning</span></span>

<span data-ttu-id="cb753-139">其他信息：[CA:1058：类型不应扩展某些基类型](/visualstudio/code-quality/ca1058-types-should-not-extend-certain-base-types)</span><span class="sxs-lookup"><span data-stu-id="cb753-139">Additional information: [CA:1058: Types should not extend certain base types](/visualstudio/code-quality/ca1058-types-should-not-extend-certain-base-types)</span></span>

### <a name="ca2153-do-not-catch-corrupted-state-exceptions"></a><span data-ttu-id="cb753-140">CA2153：请勿捕获损坏状态异常</span><span class="sxs-lookup"><span data-stu-id="cb753-140">CA2153: Do not catch corrupted state exceptions</span></span>

<span data-ttu-id="cb753-141">捕获损坏状态异常可能会掩盖错误（例如，访问冲突），导致执行状态不一致或使系统更容易遭到攻击者的破坏。</span><span class="sxs-lookup"><span data-stu-id="cb753-141">Catching corrupted state exceptions could mask errors (such as access violations), resulting in an inconsistent state of execution or making it easier for attackers to compromise a system.</span></span> <span data-ttu-id="cb753-142">改为捕获并处理更精确的异常类型或重新引发异常</span><span class="sxs-lookup"><span data-stu-id="cb753-142">Instead, catch and handle a more specific set of exception type(s) or re-throw the exception</span></span>

<span data-ttu-id="cb753-143">**类别：**安全</span><span class="sxs-lookup"><span data-stu-id="cb753-143">**Category:** Security</span></span>

<span data-ttu-id="cb753-144">**严重性：** 警告</span><span class="sxs-lookup"><span data-stu-id="cb753-144">**Severity:** Warning</span></span>

<span data-ttu-id="cb753-145">其他信息：[##CA2153：请勿捕获损坏状态异常](/visualstudio/code-quality/ca2153-avoid-handling-corrupted-state-exceptions)</span><span class="sxs-lookup"><span data-stu-id="cb753-145">Additional information: [## CA2153: Do not catch corrupted state exceptions](/visualstudio/code-quality/ca2153-avoid-handling-corrupted-state-exceptions)</span></span>

### <a name="ca2229-implement-serialization-constructors"></a><span data-ttu-id="cb753-146">CA2229：实现序列化构造函数</span><span class="sxs-lookup"><span data-stu-id="cb753-146">CA2229: Implement serialization constructors</span></span>

<span data-ttu-id="cb753-147">在创建实现 <xref:System.Runtime.Serialization.ISerializable> 接口的类型却没有定义所需序列化构造函数时，分析器会生成此警告。</span><span class="sxs-lookup"><span data-stu-id="cb753-147">The analyzer generates this warning when you create a type that implements the <xref:System.Runtime.Serialization.ISerializable> interface but does not define the required serialization constructor.</span></span> <span data-ttu-id="cb753-148">要修复与该规则的冲突，请实现序列化构造函数。</span><span class="sxs-lookup"><span data-stu-id="cb753-148">To fix a violation of this rule, implement the serialization constructor.</span></span> <span data-ttu-id="cb753-149">对于密封类，请使构造函数成为私有；否则，请使构造函数成为受保护。</span><span class="sxs-lookup"><span data-stu-id="cb753-149">For a sealed class, make the constructor private; otherwise, make it protected.</span></span> <span data-ttu-id="cb753-150">序列化构造函数具有以下签名：</span><span class="sxs-lookup"><span data-stu-id="cb753-150">The serialization constructor has the following signature:</span></span>

```csharp
public class MyItemType
{
    // The special constructor is used to deserialize values.
    public MyItemType(SerializationInfo info, StreamingContext context)
    {
        // implementation removed.
    }
}
```

<span data-ttu-id="cb753-151">**类别：**使用情况</span><span class="sxs-lookup"><span data-stu-id="cb753-151">**Category:** Usage</span></span>

<span data-ttu-id="cb753-152">**严重性：** 警告</span><span class="sxs-lookup"><span data-stu-id="cb753-152">**Severity:** Warning</span></span>

<span data-ttu-id="cb753-153">其他信息：[CA2229：实现序列化构造函数](/visualstudio/code-quality/ca2229-implement-serialization-constructors)</span><span class="sxs-lookup"><span data-stu-id="cb753-153">Additional information: [CA2229: Implement serialization constructors](/visualstudio/code-quality/ca2229-implement-serialization-constructors)</span></span>

### <a name="ca2235-mark-all-non-serializable-fields"></a><span data-ttu-id="cb753-154">CA2235：标记所有不可序列化的字段</span><span class="sxs-lookup"><span data-stu-id="cb753-154">CA2235: Mark all non-serializable fields</span></span>

<span data-ttu-id="cb753-155">在可以序列化的类型中声明了类型不可序列化的实例字段。</span><span class="sxs-lookup"><span data-stu-id="cb753-155">An instance field of a type that is not serializable is declared in a type that is serializable.</span></span> <span data-ttu-id="cb753-156">必须用 <xref:System.NonSerializedAttribute> 对该字段进行显式标记以修复此警告。</span><span class="sxs-lookup"><span data-stu-id="cb753-156">You must explicitly mark that field with the <xref:System.NonSerializedAttribute> to fix this warning.</span></span>

<span data-ttu-id="cb753-157">**类别：**使用情况</span><span class="sxs-lookup"><span data-stu-id="cb753-157">**Category:** Usage</span></span>

<span data-ttu-id="cb753-158">**严重性：** 警告</span><span class="sxs-lookup"><span data-stu-id="cb753-158">**Severity:** Warning</span></span>

<span data-ttu-id="cb753-159">其他信息：[CA2235：标记所有不可序列化的字段](/visualstudio/code-quality/ca2235-mark-all-non-serializable-fields)</span><span class="sxs-lookup"><span data-stu-id="cb753-159">Additional information: [CA2235: Mark all non-serializable fields](/visualstudio/code-quality/ca2235-mark-all-non-serializable-fields)</span></span>

### <a name="ca2237-mark-iserializable-types-with-serializable"></a><span data-ttu-id="cb753-160">CA2237：用 serializable 标记 ISerializable 类型</span><span class="sxs-lookup"><span data-stu-id="cb753-160">CA2237: Mark ISerializable types with serializable</span></span>

<span data-ttu-id="cb753-161">若要被公共语言运行时识别为可序列化，类型必须用 <xref:System.SerializableAttribute> 特性标记，即使该类型通过实现 <xref:System.Runtime.Serialization.ISerializable> 接口使用自定义序列化例程也是如此。</span><span class="sxs-lookup"><span data-stu-id="cb753-161">To be recognized by the common language runtime as serializable, types must be marked by using the <xref:System.SerializableAttribute> attribute even when the type uses a custom serialization routine by implementing the <xref:System.Runtime.Serialization.ISerializable> interface.</span></span>

<span data-ttu-id="cb753-162">**类别：**使用情况</span><span class="sxs-lookup"><span data-stu-id="cb753-162">**Category:** Usage</span></span>

<span data-ttu-id="cb753-163">**严重性：** 警告</span><span class="sxs-lookup"><span data-stu-id="cb753-163">**Severity:** Warning</span></span>

<span data-ttu-id="cb753-164">其他信息：[CA2237：用 serializable 标记 ISerializable 类型](/visualstudio/code-quality/ca2237-mark-iserializable-types-with-serializableattribute)</span><span class="sxs-lookup"><span data-stu-id="cb753-164">Additional information: [CA2237: Mark ISerializable types with serializable](/visualstudio/code-quality/ca2237-mark-iserializable-types-with-serializableattribute)</span></span>

### <a name="ca3075-insecure-dtd-processing-in-xml"></a><span data-ttu-id="cb753-165">CA3075：XML 中不安全的 DTD 处理</span><span class="sxs-lookup"><span data-stu-id="cb753-165">CA3075: Insecure DTD processing in XML</span></span>

<span data-ttu-id="cb753-166">如果使用不安全的 <xref:System.Xml.XmlReaderSettings.DtdProcessing%2A> 实例或引用外部实体源，分析器可能会接受不受信任的输入并将敏感信息泄露给攻击者。</span><span class="sxs-lookup"><span data-stu-id="cb753-166">If you use insecure <xref:System.Xml.XmlReaderSettings.DtdProcessing%2A> instances or reference external entity sources, the parser may accept untrusted input and disclose sensitive information to attackers.</span></span>  

<span data-ttu-id="cb753-167">**类别：**安全</span><span class="sxs-lookup"><span data-stu-id="cb753-167">**Category:** Security</span></span>

<span data-ttu-id="cb753-168">**严重性：** 警告</span><span class="sxs-lookup"><span data-stu-id="cb753-168">**Severity:** Warning</span></span>

<span data-ttu-id="cb753-169">其他信息：[A3075：XML 中不安全的 DTD 处理](/visualstudio/code-quality/ca2237-mark-iserializable-types-with-serializableattribute)</span><span class="sxs-lookup"><span data-stu-id="cb753-169">Additional information: [A3075: Insecure DTD processing in XML](/visualstudio/code-quality/ca2237-mark-iserializable-types-with-serializableattribute)</span></span>


### <a name="ca5350-do-not-use-weak-cryptographic-algorithms"></a><span data-ttu-id="cb753-170">CA5350：请勿使用弱加密算法</span><span class="sxs-lookup"><span data-stu-id="cb753-170">CA5350: Do not use weak cryptographic algorithms</span></span>

<span data-ttu-id="cb753-171">随着攻击越来越高级，加密算法会相对退化。</span><span class="sxs-lookup"><span data-stu-id="cb753-171">Cryptographic algorithms degrade over time as attacks become more advanced.</span></span> <span data-ttu-id="cb753-172">根据加密算法的类型和应用，其加密强度的进一步降低可能会使攻击者读取到加密消息、篡改加密消息、伪造数字签名、篡改经过哈希处理的内容或者破坏基于此算法的所有加密系统。</span><span class="sxs-lookup"><span data-stu-id="cb753-172">Depending on the type and application of this cryptographic algorithm, further degradation of its cryptographic strength may allow attackers to read enciphered messages, tamper with enciphered messages, forge digital signatures, tamper with hashed content, or otherwise compromise any cryptosystem based on this algorithm.</span></span> <span data-ttu-id="cb753-173">加密时，请使用 AES 算法（AES-256、AES-192 和 AES-128 都可以）并确保密钥长度大于或等于 128 位。</span><span class="sxs-lookup"><span data-stu-id="cb753-173">For encryption, use an AES algorithm (AES-256, AES-192 and AES-128 are acceptable) with a key length greater than or equal to 128 bits.</span></span> <span data-ttu-id="cb753-174">进行哈希处理时，请使用 SHA-2 系列中的哈希函数，例如 SHA-2 512、SHA-2 384 或 SHA-2 256。</span><span class="sxs-lookup"><span data-stu-id="cb753-174">For hashing, use a hashing function in the SHA-2 family, such as SHA-2 512, SHA-2 384, or SHA-2 256.</span></span>

<span data-ttu-id="cb753-175">**类别：**安全</span><span class="sxs-lookup"><span data-stu-id="cb753-175">**Category:** Security</span></span>

<span data-ttu-id="cb753-176">**严重性：** 警告</span><span class="sxs-lookup"><span data-stu-id="cb753-176">**Severity:** Warning</span></span>

<span data-ttu-id="cb753-177">其他信息：[CA5350：请勿使用弱加密算法](/visualstudio/code-quality/ca5350-do-not-use-weak-cryptographic-algorithms)</span><span class="sxs-lookup"><span data-stu-id="cb753-177">Additional information: [CA5350: Do not use weak cryptographic algorithms](/visualstudio/code-quality/ca5350-do-not-use-weak-cryptographic-algorithms)</span></span>

### <a name="ca5351-do-not-use-broken-cryptographic-algorithms"></a><span data-ttu-id="cb753-178">CA5351：请勿使用损坏的加密算法</span><span class="sxs-lookup"><span data-stu-id="cb753-178">CA5351: Do not use broken cryptographic algorithms</span></span>

<span data-ttu-id="cb753-179">在计算上，攻击可以破坏现有算法。</span><span class="sxs-lookup"><span data-stu-id="cb753-179">An attack making it computationally feasible to break this algorithm exists.</span></span> <span data-ttu-id="cb753-180">这使得攻击者可以破坏本应提供的加密保障。</span><span class="sxs-lookup"><span data-stu-id="cb753-180">This allows attackers to break the cryptographic guarantees it is designed to provide.</span></span> <span data-ttu-id="cb753-181">根据加密算法的类型和应用，这可能会使攻击者读取到加密消息、篡改加密消息、伪造数字签名、篡改经过哈希处理的内容或者破坏基于此算法的所有加密系统。</span><span class="sxs-lookup"><span data-stu-id="cb753-181">Depending on the type and application of this cryptographic algorithm, this may allow attackers to read enciphered messages, tamper with enciphered messages, forge digital signatures, tamper with hashed content, or otherwise compromise any cryptosystem based on this algorithm.</span></span> <span data-ttu-id="cb753-182">加密时，请使用 AES 算法（AES-256、AES-192 和 AES-128 都可以）并确保密钥长度大于或等于 128 位。</span><span class="sxs-lookup"><span data-stu-id="cb753-182">For encryption, use an AES algorithm (AES-256, AES-192 and AES-128 are acceptable) with a key length greater than or equal to 128 bits.</span></span> <span data-ttu-id="cb753-183">进行哈希处理时，请使用 SHA-2 系列中的哈希函数，例如 SHA512、SHA384 或 SHA256。</span><span class="sxs-lookup"><span data-stu-id="cb753-183">For hashing, use a hashing function in the SHA-2 family, such as SHA512, SHA384, or SHA256.</span></span> <span data-ttu-id="cb753-184">进行数字签名时，请使用 RSA 并确保密钥长度大于或等于 2048 位，或使用 ECDSA 并确保密钥长度大于或等于 256 位。</span><span class="sxs-lookup"><span data-stu-id="cb753-184">For digital signatures, use RSA with a key length greater than or equal to 2048-bits, or ECDSA with a key length greater than or equal to 256 bits.</span></span>

<span data-ttu-id="cb753-185">**类别：**安全</span><span class="sxs-lookup"><span data-stu-id="cb753-185">**Category:** Security</span></span>

<span data-ttu-id="cb753-186">**严重性：** 警告</span><span class="sxs-lookup"><span data-stu-id="cb753-186">**Severity:** Warning</span></span>

<span data-ttu-id="cb753-187">其他信息：[CA5351：请勿使用损坏的加密算法](/visualstudio/code-quality/ca5351-do-not-use-broken-cryptographic-algorithms)</span><span class="sxs-lookup"><span data-stu-id="cb753-187">Additional Information: [CA5351: Do not use broken cryptographic algorithms](/visualstudio/code-quality/ca5351-do-not-use-broken-cryptographic-algorithms)</span></span>

