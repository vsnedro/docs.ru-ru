---
title: Метод ICLRStrongName::StrongNameFreeBuffer
ms.date: 03/30/2017
api_name:
- ICLRStrongName.StrongNameFreeBuffer
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRStrongName::StrongNameFreeBuffer
helpviewer_keywords:
- StrongNameFreeBuffer method, ICLRStrongName interface [.NET Framework hosting]
- ICLRStrongName::StrongNameFreeBuffer method [.NET Framework hosting]
ms.assetid: 6148c508-bd1d-4a37-85c3-06ecb09cc857
topic_type:
- apiref
ms.openlocfilehash: bd5275f4ef8bfecdcfcfa48afe59f3bea579bd30
ms.sourcegitcommit: c76c8b2c39ed2f0eee422b61a2ab4c05ca7771fa
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/21/2020
ms.locfileid: "83762042"
---
# <a name="iclrstrongnamestrongnamefreebuffer-method"></a><span data-ttu-id="bb4ba-102">Метод ICLRStrongName::StrongNameFreeBuffer</span><span class="sxs-lookup"><span data-stu-id="bb4ba-102">ICLRStrongName::StrongNameFreeBuffer Method</span></span>
<span data-ttu-id="bb4ba-103">Освобождает память, выделенную с помощью предыдущего вызова метода строгого имени, такого как [метод iclrstrongname:: StrongNameGetPublicKey](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamegetpublickey-method.md), [метод iclrstrongname:: StrongNameTokenFromPublicKey](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnametokenfrompublickey-method.md)или [метод iclrstrongname:: StrongNameSignatureGeneration](iclrstrongname-strongnamesignaturegeneration-method.md).</span><span class="sxs-lookup"><span data-stu-id="bb4ba-103">Frees memory that was allocated with a previous call to a strong name method such as [ICLRStrongName::StrongNameGetPublicKey](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamegetpublickey-method.md), [ICLRStrongName::StrongNameTokenFromPublicKey](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnametokenfrompublickey-method.md), or [ICLRStrongName::StrongNameSignatureGeneration](iclrstrongname-strongnamesignaturegeneration-method.md).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="bb4ba-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="bb4ba-104">Syntax</span></span>  
  
```cpp  
HRESULT StrongNameFreeBuffer (
   [in] BYTE   *pbMemory  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="bb4ba-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="bb4ba-105">Parameters</span></span>  
 `pbMemory`  
 <span data-ttu-id="bb4ba-106">окне Указатель на память для освобождения.</span><span class="sxs-lookup"><span data-stu-id="bb4ba-106">[in] A pointer to the memory to free.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="bb4ba-107">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="bb4ba-107">Return Value</span></span>  
 <span data-ttu-id="bb4ba-108">`S_OK`значение, если метод успешно выполнен; в противном случае — значение HRESULT, указывающее на сбой (см. раздел [Общие значения HRESULT](/windows/win32/seccrypto/common-hresult-values) для списка).</span><span class="sxs-lookup"><span data-stu-id="bb4ba-108">`S_OK` if the method completed successfully; otherwise, an HRESULT value that indicates failure (see [Common HRESULT Values](/windows/win32/seccrypto/common-hresult-values) for a list).</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="bb4ba-109">Требования</span><span class="sxs-lookup"><span data-stu-id="bb4ba-109">Requirements</span></span>  
 <span data-ttu-id="bb4ba-110">**Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="bb4ba-110">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="bb4ba-111">**Заголовок:** Метахост. h</span><span class="sxs-lookup"><span data-stu-id="bb4ba-111">**Header:** MetaHost.h</span></span>  
  
 <span data-ttu-id="bb4ba-112">**Библиотека:** Включается в качестве ресурса в библиотеку MSCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="bb4ba-112">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="bb4ba-113">**.NET Framework версии:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="bb4ba-113">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bb4ba-114">См. также</span><span class="sxs-lookup"><span data-stu-id="bb4ba-114">See also</span></span>

- [<span data-ttu-id="bb4ba-115">Интерфейс ICLRStrongName</span><span class="sxs-lookup"><span data-stu-id="bb4ba-115">ICLRStrongName Interface</span></span>](iclrstrongname-interface.md)
