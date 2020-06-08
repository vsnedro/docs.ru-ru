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
ms.openlocfilehash: 7aed3e6877bfcd83754d462cdba81ccc229d002f
ms.sourcegitcommit: da21fc5a8cce1e028575acf31974681a1bc5aeed
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/08/2020
ms.locfileid: "84504008"
---
# <a name="iclrstrongnamestrongnamefreebuffer-method"></a><span data-ttu-id="88399-102">Метод ICLRStrongName::StrongNameFreeBuffer</span><span class="sxs-lookup"><span data-stu-id="88399-102">ICLRStrongName::StrongNameFreeBuffer Method</span></span>
<span data-ttu-id="88399-103">Освобождает память, выделенную с помощью предыдущего вызова метода строгого имени, такого как [метод iclrstrongname:: StrongNameGetPublicKey](iclrstrongname-strongnamegetpublickey-method.md), [метод iclrstrongname:: StrongNameTokenFromPublicKey](iclrstrongname-strongnametokenfrompublickey-method.md)или [метод iclrstrongname:: StrongNameSignatureGeneration](iclrstrongname-strongnamesignaturegeneration-method.md).</span><span class="sxs-lookup"><span data-stu-id="88399-103">Frees memory that was allocated with a previous call to a strong name method such as [ICLRStrongName::StrongNameGetPublicKey](iclrstrongname-strongnamegetpublickey-method.md), [ICLRStrongName::StrongNameTokenFromPublicKey](iclrstrongname-strongnametokenfrompublickey-method.md), or [ICLRStrongName::StrongNameSignatureGeneration](iclrstrongname-strongnamesignaturegeneration-method.md).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="88399-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="88399-104">Syntax</span></span>  
  
```cpp  
HRESULT StrongNameFreeBuffer (
   [in] BYTE   *pbMemory  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="88399-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="88399-105">Parameters</span></span>  
 `pbMemory`  
 <span data-ttu-id="88399-106">окне Указатель на память для освобождения.</span><span class="sxs-lookup"><span data-stu-id="88399-106">[in] A pointer to the memory to free.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="88399-107">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="88399-107">Return Value</span></span>  
 <span data-ttu-id="88399-108">`S_OK`значение, если метод успешно выполнен; в противном случае — значение HRESULT, указывающее на сбой (см. раздел [Общие значения HRESULT](/windows/win32/seccrypto/common-hresult-values) для списка).</span><span class="sxs-lookup"><span data-stu-id="88399-108">`S_OK` if the method completed successfully; otherwise, an HRESULT value that indicates failure (see [Common HRESULT Values](/windows/win32/seccrypto/common-hresult-values) for a list).</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="88399-109">Требования</span><span class="sxs-lookup"><span data-stu-id="88399-109">Requirements</span></span>  
 <span data-ttu-id="88399-110">**Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="88399-110">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="88399-111">**Заголовок:** Метахост. h</span><span class="sxs-lookup"><span data-stu-id="88399-111">**Header:** MetaHost.h</span></span>  
  
 <span data-ttu-id="88399-112">**Библиотека:** Включается в качестве ресурса в библиотеку MSCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="88399-112">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="88399-113">**.NET Framework версии:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="88399-113">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="88399-114">См. также</span><span class="sxs-lookup"><span data-stu-id="88399-114">See also</span></span>

- [<span data-ttu-id="88399-115">Интерфейс ICLRStrongName</span><span class="sxs-lookup"><span data-stu-id="88399-115">ICLRStrongName Interface</span></span>](iclrstrongname-interface.md)
