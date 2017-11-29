---
title: "ICorDebugArrayValue::GetCount 方法"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorDebugArrayValue.GetCount
api_location: mscordbi.dll
api_type: COM
f1_keywords: ICorDebugArrayValue::GetCount
helpviewer_keywords:
- ICorDebugArrayValue::GetCount method [.NET Framework debugging]
- GetCount method, ICorDebugArrayValue interface [.NET Framework debugging]
ms.assetid: 44cd98cf-2127-4d46-8c6a-da4e857bb6b0
topic_type: apiref
caps.latest.revision: "11"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 4b96a408b3e3f1965cb02b7b90205408d1c7a49f
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/18/2017
---
# <a name="icordebugarrayvaluegetcount-method"></a><span data-ttu-id="b13e0-102">ICorDebugArrayValue::GetCount 方法</span><span class="sxs-lookup"><span data-stu-id="b13e0-102">ICorDebugArrayValue::GetCount Method</span></span>
<span data-ttu-id="b13e0-103">获取数组中的元素总数。</span><span class="sxs-lookup"><span data-stu-id="b13e0-103">Gets the total number of elements in the array.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b13e0-104">语法</span><span class="sxs-lookup"><span data-stu-id="b13e0-104">Syntax</span></span>  
  
```  
HRESULT GetCount (  
    [out] ULONG32 *pnCount  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="b13e0-105">参数</span><span class="sxs-lookup"><span data-stu-id="b13e0-105">Parameters</span></span>  
 `pnCount`  
 <span data-ttu-id="b13e0-106">[out]指向数组中的元素总数的指针。</span><span class="sxs-lookup"><span data-stu-id="b13e0-106">[out] A pointer to the total number of elements in the array.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="b13e0-107">要求</span><span class="sxs-lookup"><span data-stu-id="b13e0-107">Requirements</span></span>  
 <span data-ttu-id="b13e0-108">**平台：**请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="b13e0-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="b13e0-109">**标头：** CorDebug.idl、 CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="b13e0-109">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="b13e0-110">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="b13e0-110">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="b13e0-111">**.NET framework 版本：**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="b13e0-111">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>