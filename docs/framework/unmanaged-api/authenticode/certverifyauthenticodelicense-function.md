---
title: "CertVerifyAuthenticodeLicense 函数"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: CertVerifyAuthenticodeLicense
api_location: clr.dll
api_type: DLLExport
ms.assetid: 00118de7-33c6-41c4-8e1f-5d5e35e0da83
caps.latest.revision: "5"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 16d8067b4cd5d0a7b3db5be5b3b9ed4d689e1b0e
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="certverifyauthenticodelicense-function"></a><span data-ttu-id="fb883-102">CertVerifyAuthenticodeLicense 函数</span><span class="sxs-lookup"><span data-stu-id="fb883-102">CertVerifyAuthenticodeLicense Function</span></span>
<span data-ttu-id="fb883-103">验证验证码 XrML 许可证的有效性。</span><span class="sxs-lookup"><span data-stu-id="fb883-103">Verifies the validity of an Authenticode XrML license.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="fb883-104">语法</span><span class="sxs-lookup"><span data-stu-id="fb883-104">Syntax</span></span>  
  
```  
HRESULT CertVerifyAuthenticodeLicense (  
    [in]   PCRYPT_DATA_BLOB                   pLicenseBlob,  
    [in]   OPTIONAL DWORD                     dwFlags,  
    [out]  PAXL_AUTHENTICODE_SIGNER_INFO      pSignerInfo,  
    [out]  PAXL_AUTHENTICODE_TIMESTAMPER_INFO pTimestamperInfo  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="fb883-105">参数</span><span class="sxs-lookup"><span data-stu-id="fb883-105">Parameters</span></span>  
 `pLicenseBlob`  
 <span data-ttu-id="fb883-106">[in] 要验证的验证码 XrML 许可证。</span><span class="sxs-lookup"><span data-stu-id="fb883-106">[in] The Authenticode XrML license to be verified.</span></span>  
  
 <span data-ttu-id="fb883-107">请参阅[CRYPTOAPI_BLOB](http://msdn.microsoft.com/library/windows/desktop/aa380238.aspx)结构。</span><span class="sxs-lookup"><span data-stu-id="fb883-107">See the [CRYPTOAPI_BLOB](http://msdn.microsoft.com/library/windows/desktop/aa380238.aspx) structure.</span></span>  
  
 `dwFlags`  
 <span data-ttu-id="fb883-108">[in] 可选。</span><span class="sxs-lookup"><span data-stu-id="fb883-108">[in] Optional.</span></span> <span data-ttu-id="fb883-109">以下值的组合：</span><span class="sxs-lookup"><span data-stu-id="fb883-109">A combination of following values:</span></span>  
  
-   <span data-ttu-id="fb883-110">AXL_REVOCATION_NO_CHECK</span><span class="sxs-lookup"><span data-stu-id="fb883-110">AXL_REVOCATION_NO_CHECK</span></span>  
  
-   <span data-ttu-id="fb883-111">AXL_REVOCATION_CHECK_END_CERT_ONLY</span><span class="sxs-lookup"><span data-stu-id="fb883-111">AXL_REVOCATION_CHECK_END_CERT_ONLY</span></span>  
  
-   <span data-ttu-id="fb883-112">AXL_REVOCATION_CHECK_ENTIRE_CHAIN</span><span class="sxs-lookup"><span data-stu-id="fb883-112">AXL_REVOCATION_CHECK_ENTIRE_CHAIN</span></span>  
  
-   <span data-ttu-id="fb883-113">AXL_URL_CACHE_ONLY_RETRIEVAL</span><span class="sxs-lookup"><span data-stu-id="fb883-113">AXL_URL_CACHE_ONLY_RETRIEVAL</span></span>  
  
-   <span data-ttu-id="fb883-114">AXL_LIFETIME_SIGNING</span><span class="sxs-lookup"><span data-stu-id="fb883-114">AXL_LIFETIME_SIGNING</span></span>  
  
-   <span data-ttu-id="fb883-115">AXL_TRUST_MICROSOFT_ROOT_ONLY</span><span class="sxs-lookup"><span data-stu-id="fb883-115">AXL_TRUST_MICROSOFT_ROOT_ONLY</span></span>  
  
 `pSignerInfo`  
 <span data-ttu-id="fb883-116">[out] 接收签署人的信息。</span><span class="sxs-lookup"><span data-stu-id="fb883-116">[out] To receive the signer's information.</span></span> <span data-ttu-id="fb883-117">如果许可证未进行签名，则 `dwError` 将设置为 TRUST_E_NOSIGNATURE。</span><span class="sxs-lookup"><span data-stu-id="fb883-117">If the license wasn't signed, `dwError` is set to TRUST_E_NOSIGNATURE.</span></span> <span data-ttu-id="fb883-118">在调用方负责使用释放资源[CertFreeAuthenticodeSignerInfo](../../../../docs/framework/unmanaged-api/authenticode/certfreeauthenticodesignerinfo-function.md)后使用的函数。</span><span class="sxs-lookup"><span data-stu-id="fb883-118">It is the caller's responsibility to free resources by using the [CertFreeAuthenticodeSignerInfo](../../../../docs/framework/unmanaged-api/authenticode/certfreeauthenticodesignerinfo-function.md) function after use.</span></span>  
  
 <span data-ttu-id="fb883-119">请参阅[AXL_AUTHENTICODE_SIGNER_INFO 结构](../../../../docs/framework/unmanaged-api/authenticode/axl-authenticode-signer-info-structure.md)。</span><span class="sxs-lookup"><span data-stu-id="fb883-119">See [AXL_AUTHENTICODE_SIGNER_INFO Structure](../../../../docs/framework/unmanaged-api/authenticode/axl-authenticode-signer-info-structure.md).</span></span>  
  
 `pTimestamperInfo`  
 <span data-ttu-id="fb883-120">[out] 接收时间戳签署人的信息（如果有）。</span><span class="sxs-lookup"><span data-stu-id="fb883-120">[out] To receive time stamper's information, if available.</span></span> <span data-ttu-id="fb883-121">如果未对许可证签署时间戳，则 `dwError` 将设置为 TRUST_E_NOSIGNATURE。</span><span class="sxs-lookup"><span data-stu-id="fb883-121">If the license was not time-stamped, `dwError` is set to TRUST_E_NOSIGNATURE.</span></span> <span data-ttu-id="fb883-122">在调用方负责使用释放资源[CertFreeAuthenticodeTimestamperInfo](../../../../docs/framework/unmanaged-api/authenticode/certfreeauthenticodetimestamperinfo-function.md)后使用的函数。</span><span class="sxs-lookup"><span data-stu-id="fb883-122">It is the caller's responsibility to free resources by using the [CertFreeAuthenticodeTimestamperInfo](../../../../docs/framework/unmanaged-api/authenticode/certfreeauthenticodetimestamperinfo-function.md) function after use.</span></span>  
  
 <span data-ttu-id="fb883-123">请参阅[AXL_AUTHENTICODE_TIMESTAMPER_INFO 结构](../../../../docs/framework/unmanaged-api/authenticode/axl-authenticode-timestamper-info-structure.md)。</span><span class="sxs-lookup"><span data-stu-id="fb883-123">See [AXL_AUTHENTICODE_TIMESTAMPER_INFO Structure](../../../../docs/framework/unmanaged-api/authenticode/axl-authenticode-timestamper-info-structure.md).</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="fb883-124">返回值</span><span class="sxs-lookup"><span data-stu-id="fb883-124">Return Value</span></span>  
 <span data-ttu-id="fb883-125">如果成功，则返回 `S_OK`。</span><span class="sxs-lookup"><span data-stu-id="fb883-125">Returns `S_OK` if successful.</span></span> <span data-ttu-id="fb883-126">否则，返回错误代码。</span><span class="sxs-lookup"><span data-stu-id="fb883-126">Otherwise, returns an error code.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fb883-127">另请参阅</span><span class="sxs-lookup"><span data-stu-id="fb883-127">See Also</span></span>  
 [<span data-ttu-id="fb883-128">验证码</span><span class="sxs-lookup"><span data-stu-id="fb883-128">Authenticode</span></span>](../../../../docs/framework/unmanaged-api/authenticode/index.md)  
 [<span data-ttu-id="fb883-129">GetHashFromHandle 方法</span><span class="sxs-lookup"><span data-stu-id="fb883-129">GetHashFromHandle Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-gethashfromhandle-method.md)  
 [<span data-ttu-id="fb883-130">ICLRStrongName 接口</span><span class="sxs-lookup"><span data-stu-id="fb883-130">ICLRStrongName Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-interface.md)