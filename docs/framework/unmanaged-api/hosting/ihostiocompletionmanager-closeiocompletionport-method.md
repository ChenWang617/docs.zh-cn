---
title: "IHostIoCompletionManager::CloseIoCompletionPort 方法"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IHostIoCompletionManager.CloseIoCompletionPort
api_location: mscoree.dll
api_type: COM
f1_keywords: IHostIoCompletionManager::CloseIoCompletionPort
helpviewer_keywords:
- IHostIoCompletionManager::CloseIoCompletionPort method [.NET Framework hosting]
- CloseIoCompletionPort method [.NET Framework hosting]
ms.assetid: e86ad7be-3758-498a-a972-5522d69dfbb3
topic_type: apiref
caps.latest.revision: "10"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 066d51c821cf86522ffaca4c15db360ce96ed773
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="ihostiocompletionmanagercloseiocompletionport-method"></a><span data-ttu-id="ab28d-102">IHostIoCompletionManager::CloseIoCompletionPort 方法</span><span class="sxs-lookup"><span data-stu-id="ab28d-102">IHostIoCompletionManager::CloseIoCompletionPort Method</span></span>
<span data-ttu-id="ab28d-103">请求主机关闭的端口已打开通过以前调用[CreateIoCompletionPort](../../../../docs/framework/unmanaged-api/hosting/ihostiocompletionmanager-createiocompletionport-method.md)。</span><span class="sxs-lookup"><span data-stu-id="ab28d-103">Requests that the host close a port that was opened through an earlier call to [CreateIoCompletionPort](../../../../docs/framework/unmanaged-api/hosting/ihostiocompletionmanager-createiocompletionport-method.md).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ab28d-104">语法</span><span class="sxs-lookup"><span data-stu-id="ab28d-104">Syntax</span></span>  
  
```  
HRESULT CloseIoCompletionPort (  
    [in] HANDLE hPort  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="ab28d-105">参数</span><span class="sxs-lookup"><span data-stu-id="ab28d-105">Parameters</span></span>  
 `hPort`  
 <span data-ttu-id="ab28d-106">[in]要关闭的端口的句柄。</span><span class="sxs-lookup"><span data-stu-id="ab28d-106">[in] The handle of the port to close.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="ab28d-107">返回值</span><span class="sxs-lookup"><span data-stu-id="ab28d-107">Return Value</span></span>  
  
|<span data-ttu-id="ab28d-108">HRESULT</span><span class="sxs-lookup"><span data-stu-id="ab28d-108">HRESULT</span></span>|<span data-ttu-id="ab28d-109">描述</span><span class="sxs-lookup"><span data-stu-id="ab28d-109">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="ab28d-110">S_OK</span><span class="sxs-lookup"><span data-stu-id="ab28d-110">S_OK</span></span>|<span data-ttu-id="ab28d-111">`CloseIoCompletionPort`已成功返回。</span><span class="sxs-lookup"><span data-stu-id="ab28d-111">`CloseIoCompletionPort` returned successfully.</span></span>|  
|<span data-ttu-id="ab28d-112">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="ab28d-112">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="ab28d-113">公共语言运行时 (CLR) 尚未加载到进程中，或 CLR 处于不能运行托管的代码或成功处理调用的状态。</span><span class="sxs-lookup"><span data-stu-id="ab28d-113">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="ab28d-114">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="ab28d-114">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="ab28d-115">调用操作已超时。</span><span class="sxs-lookup"><span data-stu-id="ab28d-115">The call timed out.</span></span>|  
|<span data-ttu-id="ab28d-116">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="ab28d-116">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="ab28d-117">调用方不拥有该锁。</span><span class="sxs-lookup"><span data-stu-id="ab28d-117">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="ab28d-118">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="ab28d-118">HOST_E_ABANDONED</span></span>|<span data-ttu-id="ab28d-119">事件已被取消时被阻塞的线程，或者纤程正在等待它。</span><span class="sxs-lookup"><span data-stu-id="ab28d-119">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="ab28d-120">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="ab28d-120">E_FAIL</span></span>|<span data-ttu-id="ab28d-121">出现未知的灾难性故障。</span><span class="sxs-lookup"><span data-stu-id="ab28d-121">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="ab28d-122">如果某方法返回 E_FAIL，CLR 不再可用进程内。</span><span class="sxs-lookup"><span data-stu-id="ab28d-122">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="ab28d-123">到托管方法的后续调用会返回 HOST_E_CLRNOTAVAILABLE。</span><span class="sxs-lookup"><span data-stu-id="ab28d-123">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="ab28d-124">E_INVALIDARG</span><span class="sxs-lookup"><span data-stu-id="ab28d-124">E_INVALIDARG</span></span>|<span data-ttu-id="ab28d-125">传递了无效的端口句柄。</span><span class="sxs-lookup"><span data-stu-id="ab28d-125">An invalid port handle was passed.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="ab28d-126">备注</span><span class="sxs-lookup"><span data-stu-id="ab28d-126">Remarks</span></span>  
 <span data-ttu-id="ab28d-127">`hPort`必须由以前调用的端口的句柄`CreateIoCompletionPort`。</span><span class="sxs-lookup"><span data-stu-id="ab28d-127">`hPort` must be a handle to a port that was created by an earlier call to `CreateIoCompletionPort`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="ab28d-128">要求</span><span class="sxs-lookup"><span data-stu-id="ab28d-128">Requirements</span></span>  
 <span data-ttu-id="ab28d-129">**平台：**请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="ab28d-129">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ab28d-130">**标头：** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="ab28d-130">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="ab28d-131">**库：**作为 MSCorEE.dll 中的资源</span><span class="sxs-lookup"><span data-stu-id="ab28d-131">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="ab28d-132">**.NET framework 版本：**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="ab28d-132">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ab28d-133">另请参阅</span><span class="sxs-lookup"><span data-stu-id="ab28d-133">See Also</span></span>  
 [<span data-ttu-id="ab28d-134">ICLRIoCompletionManager 接口</span><span class="sxs-lookup"><span data-stu-id="ab28d-134">ICLRIoCompletionManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclriocompletionmanager-interface.md)  
 [<span data-ttu-id="ab28d-135">IHostIoCompletionManager 接口</span><span class="sxs-lookup"><span data-stu-id="ab28d-135">IHostIoCompletionManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostiocompletionmanager-interface.md)