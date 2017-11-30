---
title: "IMetaDataTables::GetNumTables 方法"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IMetaDataTables.GetNumTables
api_location: mscoree.dll
api_type: COM
f1_keywords: IMetaDataTables::GetNumTables
helpviewer_keywords:
- GetNumTables method [.NET Framework metadata]
- IMetaDataTables::GetNumTables method [.NET Framework metadata]
ms.assetid: 8196f2a3-bbf2-45d3-a6cd-74502c356644
topic_type: apiref
caps.latest.revision: "11"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: 23aa78f8daf649c4fdba218cdc964e4e47070580
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="imetadatatablesgetnumtables-method"></a><span data-ttu-id="46891-102">IMetaDataTables::GetNumTables 方法</span><span class="sxs-lookup"><span data-stu-id="46891-102">IMetaDataTables::GetNumTables Method</span></span>
<span data-ttu-id="46891-103">获取当前的作用域中的表数`IMetaDataTables`实例。</span><span class="sxs-lookup"><span data-stu-id="46891-103">Gets the number of tables in the scope of the current `IMetaDataTables` instance.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="46891-104">语法</span><span class="sxs-lookup"><span data-stu-id="46891-104">Syntax</span></span>  
  
```  
HRESULT GetNumTables (  
    [out]  ULONG   *pcTables  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="46891-105">参数</span><span class="sxs-lookup"><span data-stu-id="46891-105">Parameters</span></span>  
 `pcTables`  
 <span data-ttu-id="46891-106">[out]指向当前实例作用域中的表数的指针。</span><span class="sxs-lookup"><span data-stu-id="46891-106">[out] A pointer to the number of tables in the current instance scope.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="46891-107">要求</span><span class="sxs-lookup"><span data-stu-id="46891-107">Requirements</span></span>  
 <span data-ttu-id="46891-108">**平台：**请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="46891-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="46891-109">**标头：** Cor.h</span><span class="sxs-lookup"><span data-stu-id="46891-109">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="46891-110">**库：**用作 MsCorEE.dll 中的资源</span><span class="sxs-lookup"><span data-stu-id="46891-110">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="46891-111">**.NET framework 版本：**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="46891-111">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="46891-112">另请参阅</span><span class="sxs-lookup"><span data-stu-id="46891-112">See Also</span></span>  
 [<span data-ttu-id="46891-113">IMetaDataTables 接口</span><span class="sxs-lookup"><span data-stu-id="46891-113">IMetaDataTables Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatatables-interface.md)  
 [<span data-ttu-id="46891-114">IMetaDataTables2 接口</span><span class="sxs-lookup"><span data-stu-id="46891-114">IMetaDataTables2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatatables2-interface.md)