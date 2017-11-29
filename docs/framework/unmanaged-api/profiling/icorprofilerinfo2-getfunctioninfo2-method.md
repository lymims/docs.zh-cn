---
title: "ICorProfilerInfo2::GetFunctionInfo2 方法"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorProfilerInfo2.GetFunctionInfo2
api_location: mscorwks.dll
api_type: COM
f1_keywords: ICorProfilerInfo2::GetFunctionInfo2
helpviewer_keywords:
- GetFunctionInfo2 method [.NET Framework profiling]
- ICorProfilerInfo2::GetFunctionInfo2 method [.NET Framework profiling]
ms.assetid: 0aa60f24-8bbd-4c83-83c5-86ad191b1d82
topic_type: apiref
caps.latest.revision: "18"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: 8b0c288b88c868bc6e324ec57b3956344f03f34e
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="icorprofilerinfo2getfunctioninfo2-method"></a><span data-ttu-id="fa8b5-102">ICorProfilerInfo2::GetFunctionInfo2 方法</span><span class="sxs-lookup"><span data-stu-id="fa8b5-102">ICorProfilerInfo2::GetFunctionInfo2 Method</span></span>
<span data-ttu-id="fa8b5-103">获取每个类型参数或某个函数（如果存在）的父类、元数据标记和 `ClassID`。</span><span class="sxs-lookup"><span data-stu-id="fa8b5-103">Gets the parent class, the metadata token, and the `ClassID` of each type argument, if present, of a function.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="fa8b5-104">语法</span><span class="sxs-lookup"><span data-stu-id="fa8b5-104">Syntax</span></span>  
  
```  
HRESULT GetFunctionInfo2(  
    [in]  FunctionID funcId,  
    [in]  COR_PRF_FRAME_INFO frameInfo,  
    [out] ClassID *pClassId,  
    [out] ModuleID *pModuleId,  
    [out] mdToken *pToken,  
    [in]  ULONG32 cTypeArgs,  
    [out] ULONG32 *pcTypeArgs,  
    [out] ClassID typeArgs[]);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="fa8b5-105">参数</span><span class="sxs-lookup"><span data-stu-id="fa8b5-105">Parameters</span></span>  
 `funcId`  
 <span data-ttu-id="fa8b5-106">[in] 要获取其父类和其他信息的函数的 ID。</span><span class="sxs-lookup"><span data-stu-id="fa8b5-106">[in] The ID of the function for which to get the parent class and other information.</span></span>  
  
 `frameInfo`  
 <span data-ttu-id="fa8b5-107">[in] 一个 `COR_PRF_FRAME_INFO` 值，该值指向有关堆栈帧的信息。</span><span class="sxs-lookup"><span data-stu-id="fa8b5-107">[in] A `COR_PRF_FRAME_INFO` value that points to information about a stack frame.</span></span>  
  
 `pClassId`  
 <span data-ttu-id="fa8b5-108">[out] 一个指向函数的父类的指针。</span><span class="sxs-lookup"><span data-stu-id="fa8b5-108">[out] A pointer to the parent class of the function.</span></span>  
  
 `pModuleId`  
 <span data-ttu-id="fa8b5-109">[out] 一个指向在其中定义函数父类的模块的指针。</span><span class="sxs-lookup"><span data-stu-id="fa8b5-109">[out] A pointer to the module in which the function's parent class is defined.</span></span>  
  
 `pToken`  
 <span data-ttu-id="fa8b5-110">[out] 指向函数的元数据标记的指针。</span><span class="sxs-lookup"><span data-stu-id="fa8b5-110">[out] A pointer to the metadata token for the function.</span></span>  
  
 `cTypeArgs`  
 <span data-ttu-id="fa8b5-111">[in] `typeArgs` 数组的大小。</span><span class="sxs-lookup"><span data-stu-id="fa8b5-111">[in] The size of the `typeArgs` array.</span></span>  
  
 `pcTypeArgs`  
 <span data-ttu-id="fa8b5-112">[out] 一个指向 `ClassID` 值的总数的指针。</span><span class="sxs-lookup"><span data-stu-id="fa8b5-112">[out] A pointer to the total number of `ClassID` values.</span></span>  
  
 `typeArgs`  
 <span data-ttu-id="fa8b5-113">[out] 一个由 `ClassID` 值构成的数组，其中的每个值都是函数的类型参数的 ID。</span><span class="sxs-lookup"><span data-stu-id="fa8b5-113">[out] An array of `ClassID` values, each of which is the ID of a type argument of the function.</span></span> <span data-ttu-id="fa8b5-114">方法返回时，`typeArgs` 将包含部分或全部 `ClassID` 值。</span><span class="sxs-lookup"><span data-stu-id="fa8b5-114">When the method returns, `typeArgs` will contain some or all of the `ClassID` values.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="fa8b5-115">备注</span><span class="sxs-lookup"><span data-stu-id="fa8b5-115">Remarks</span></span>  
 <span data-ttu-id="fa8b5-116">探查器代码可以调用[icorprofilerinfo:: Getmodulemetadata](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-getmodulemetadata-method.md)获取[元数据](../../../../docs/framework/unmanaged-api/metadata/index.md)给定模块的接口。</span><span class="sxs-lookup"><span data-stu-id="fa8b5-116">The profiler code can call [ICorProfilerInfo::GetModuleMetaData](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-getmodulemetadata-method.md) to obtain a [metadata](../../../../docs/framework/unmanaged-api/metadata/index.md) interface for a given module.</span></span> <span data-ttu-id="fa8b5-117">然后，返回到 `pToken` 所引用位置的元数据标记便可用于访问该函数的元数据。</span><span class="sxs-lookup"><span data-stu-id="fa8b5-117">The metadata token that is returned to the location referenced by `pToken` can then be used to access the metadata for the function.</span></span>  
  
 <span data-ttu-id="fa8b5-118">通过 `pClassId` 和 `typeArgs` 参数返回的类 ID 和类型参数取决于传入 `frameInfo` 参数的值，如下表中所示。</span><span class="sxs-lookup"><span data-stu-id="fa8b5-118">The class ID and type arguments that are returned through the `pClassId` and `typeArgs` parameters depend on the value that is passed in the `frameInfo` parameter, as shown in the following table.</span></span>  
  
|<span data-ttu-id="fa8b5-119">`frameInfo` 参数的值</span><span class="sxs-lookup"><span data-stu-id="fa8b5-119">Value of the `frameInfo` parameter</span></span>|<span data-ttu-id="fa8b5-120">结果</span><span class="sxs-lookup"><span data-stu-id="fa8b5-120">Result</span></span>|  
|----------------------------------------|------------|  
|<span data-ttu-id="fa8b5-121">从 `FunctionEnter2` 回调中获得的 `COR_PRF_FRAME_INFO` 值</span><span class="sxs-lookup"><span data-stu-id="fa8b5-121">A `COR_PRF_FRAME_INFO` value that was obtained from a `FunctionEnter2` callback</span></span>|<span data-ttu-id="fa8b5-122">在 `pClassId` 所引用位置中返回的 `ClassID` 以及在 `typeArgs` 数组中返回的所有类型参数都将是准确的。</span><span class="sxs-lookup"><span data-stu-id="fa8b5-122">The `ClassID`, returned in the location referenced by `pClassId`, and all type arguments, returned in the `typeArgs` array, will be exact.</span></span>|  
|<span data-ttu-id="fa8b5-123">从 `FunctionEnter2` 回调以外的源中获得的 `COR_PRF_FRAME_INFO`</span><span class="sxs-lookup"><span data-stu-id="fa8b5-123">A `COR_PRF_FRAME_INFO` that was obtained from a source other than a `FunctionEnter2` callback</span></span>|<span data-ttu-id="fa8b5-124">无法确定准确的 `ClassID` 和类型参数。</span><span class="sxs-lookup"><span data-stu-id="fa8b5-124">The exact `ClassID` and type arguments cannot be determined.</span></span> <span data-ttu-id="fa8b5-125">也就是说，`ClassID` 可能为 NULL，并且某些类型参数可能作为 <xref:System.Object> 返回。</span><span class="sxs-lookup"><span data-stu-id="fa8b5-125">That is, the `ClassID` might be null and some type arguments might come back as <xref:System.Object>.</span></span>|  
|<span data-ttu-id="fa8b5-126">零</span><span class="sxs-lookup"><span data-stu-id="fa8b5-126">Zero</span></span>|<span data-ttu-id="fa8b5-127">无法确定准确的 `ClassID` 和类型参数。</span><span class="sxs-lookup"><span data-stu-id="fa8b5-127">The exact `ClassID` and type arguments cannot be determined.</span></span> <span data-ttu-id="fa8b5-128">也就是说，`ClassID` 可能为 NULL，并且某些类型参数可能作为 <xref:System.Object> 返回。</span><span class="sxs-lookup"><span data-stu-id="fa8b5-128">That is, the `ClassID` might be null and some type arguments might come back as <xref:System.Object>.</span></span>|  
  
 <span data-ttu-id="fa8b5-129">`GetFunctionInfo2` 返回后，必须验证 `typeArgs` 缓冲区是否足够大，可包含所有 `ClassID` 值。</span><span class="sxs-lookup"><span data-stu-id="fa8b5-129">After `GetFunctionInfo2` returns, you must verify that the `typeArgs` buffer was large enough to contain all the `ClassID` values.</span></span> <span data-ttu-id="fa8b5-130">为此，请比较 `pcTypeArgs` 指向的值和 `cTypeArgs` 参数的值。</span><span class="sxs-lookup"><span data-stu-id="fa8b5-130">To do this, compare the value that `pcTypeArgs` points to with the value of the `cTypeArgs` parameter.</span></span> <span data-ttu-id="fa8b5-131">如果 `pcTypeArgs` 指向大于`cTypeArgs` 除以 `ClassID` 值大小的值，请分配更大的 `pcTypeArgs` 缓冲区，使用新的、更大的大小更新 `cTypeArgs`，然后再次调用 `GetFunctionInfo2`。</span><span class="sxs-lookup"><span data-stu-id="fa8b5-131">If `pcTypeArgs` points to a value that is larger than `cTypeArgs` divided by the size of a `ClassID` value, allocate a larger `pcTypeArgs` buffer, update `cTypeArgs` with the new, larger size, and call `GetFunctionInfo2` again.</span></span>  
  
 <span data-ttu-id="fa8b5-132">或者，可以先用长度为零的 `pcTypeArgs` 缓冲区调用 `GetFunctionInfo2` 以获取正确的缓冲区大小。</span><span class="sxs-lookup"><span data-stu-id="fa8b5-132">Alternatively, you can first call `GetFunctionInfo2` with a zero-length `pcTypeArgs` buffer to obtain the correct buffer size.</span></span> <span data-ttu-id="fa8b5-133">然后，可将缓冲区大小设置为 `pcTypeArgs` 中返回的值除以 `ClassID` 值的大小，然后再次调用 `GetFunctionInfo2`。</span><span class="sxs-lookup"><span data-stu-id="fa8b5-133">You can then set the buffer size to the value returned in `pcTypeArgs` divided by the size of a `ClassID` value, and call `GetFunctionInfo2` again.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="fa8b5-134">要求</span><span class="sxs-lookup"><span data-stu-id="fa8b5-134">Requirements</span></span>  
 <span data-ttu-id="fa8b5-135">**平台：**请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="fa8b5-135">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="fa8b5-136">**头文件：** CorProf.idl、CorProf.h</span><span class="sxs-lookup"><span data-stu-id="fa8b5-136">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="fa8b5-137">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="fa8b5-137">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="fa8b5-138">**.NET framework 版本：**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="fa8b5-138">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fa8b5-139">另请参阅</span><span class="sxs-lookup"><span data-stu-id="fa8b5-139">See Also</span></span>  
 [<span data-ttu-id="fa8b5-140">ICorProfilerInfo 接口</span><span class="sxs-lookup"><span data-stu-id="fa8b5-140">ICorProfilerInfo Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-interface.md)  
 [<span data-ttu-id="fa8b5-141">ICorProfilerInfo2 接口</span><span class="sxs-lookup"><span data-stu-id="fa8b5-141">ICorProfilerInfo2 Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-interface.md)  
 [<span data-ttu-id="fa8b5-142">分析接口</span><span class="sxs-lookup"><span data-stu-id="fa8b5-142">Profiling Interfaces</span></span>](../../../../docs/framework/unmanaged-api/profiling/profiling-interfaces.md)  
 [<span data-ttu-id="fa8b5-143">分析</span><span class="sxs-lookup"><span data-stu-id="fa8b5-143">Profiling</span></span>](../../../../docs/framework/unmanaged-api/profiling/index.md)