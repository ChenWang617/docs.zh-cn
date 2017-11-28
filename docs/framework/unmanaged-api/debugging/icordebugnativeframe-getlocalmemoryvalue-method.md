---
title: "ICorDebugNativeFrame::GetLocalMemoryValue 方法"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorDebugNativeFrame.GetLocalMemoryValue
api_location: mscordbi.dll
api_type: COM
f1_keywords: ICorDebugNativeFrame::GetLocalMemoryValue
helpviewer_keywords:
- GetLocalMemoryValue method [.NET Framework debugging]
- ICorDebugNativeFrame::GetLocalMemoryValue method [.NET Framework debugging]
ms.assetid: b600b3a2-9908-42d8-8093-ab6f39e9a2c9
topic_type: apiref
caps.latest.revision: "12"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: a43bc0b4bcfb50804e4bffbe4f4f18280f873436
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/18/2017
---
# <a name="icordebugnativeframegetlocalmemoryvalue-method"></a><span data-ttu-id="c1d14-102">ICorDebugNativeFrame::GetLocalMemoryValue 方法</span><span class="sxs-lookup"><span data-stu-id="c1d14-102">ICorDebugNativeFrame::GetLocalMemoryValue Method</span></span>
<span data-ttu-id="c1d14-103">获取自变量或存储在此本机框架的指定的内存位置的本地变量的值。</span><span class="sxs-lookup"><span data-stu-id="c1d14-103">Gets the value of an argument or local variable that is stored in the specified memory location for this native frame.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c1d14-104">语法</span><span class="sxs-lookup"><span data-stu-id="c1d14-104">Syntax</span></span>  
  
```  
HRESULT GetLocalMemoryValue (  
    [in]  CORDB_ADDRESS      address,  
    [in]  ULONG              cbSigBlob,  
    [in]  PCCOR_SIGNATURE    pvSigBlob,  
    [out] ICorDebugValue     **ppValue  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="c1d14-105">参数</span><span class="sxs-lookup"><span data-stu-id="c1d14-105">Parameters</span></span>  
 `address`  
 <span data-ttu-id="c1d14-106">[in]A`CORDB_ADDRESS`值，该值指定内存位置包含的值。</span><span class="sxs-lookup"><span data-stu-id="c1d14-106">[in] A `CORDB_ADDRESS` value that specifies the memory location containing the value.</span></span>  
  
 `cbSigBlob`  
 <span data-ttu-id="c1d14-107">[in]一个整数，指定的二进制元数据签名，这由引用的大小`pvSigBlob`参数。</span><span class="sxs-lookup"><span data-stu-id="c1d14-107">[in] An integer that specifies the size of the binary metadata signature which is referenced by the `pvSigBlob` parameter.</span></span>  
  
 `pvSigBlob`  
 <span data-ttu-id="c1d14-108">[in]A`PCCOR_SIGNATURE`值，该值指向的值类型的二进制元数据签名。</span><span class="sxs-lookup"><span data-stu-id="c1d14-108">[in] A `PCCOR_SIGNATURE` value that points to the binary metadata signature of the value's type.</span></span>  
  
 `ppValue`  
 <span data-ttu-id="c1d14-109">[out]指向表示检索到存储在指定的内存位置的值的"ICorDebugValue"对象的地址的指针。</span><span class="sxs-lookup"><span data-stu-id="c1d14-109">[out] A pointer to the address of an "ICorDebugValue" object representing the retrieved value that is stored in the specified memory location.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="c1d14-110">要求</span><span class="sxs-lookup"><span data-stu-id="c1d14-110">Requirements</span></span>  
 <span data-ttu-id="c1d14-111">**平台：**请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="c1d14-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c1d14-112">**标头：** CorDebug.idl、 CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="c1d14-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="c1d14-113">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="c1d14-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="c1d14-114">**.NET framework 版本：**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="c1d14-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c1d14-115">另请参阅</span><span class="sxs-lookup"><span data-stu-id="c1d14-115">See Also</span></span>  
 