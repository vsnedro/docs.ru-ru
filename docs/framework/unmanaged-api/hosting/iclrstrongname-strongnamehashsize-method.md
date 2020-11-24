---
title: Метод ICLRStrongName::StrongNameHashSize
ms.date: 03/30/2017
api_name:
- ICLRStrongName.StrongNameHashSize
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRStrongName::StrongNameHashSize
helpviewer_keywords:
- ICLRStrongName::StrongNameHashSize method [.NET Framework hosting]
- StrongNameHashSize method, ICLRStrongName interface [.NET Framework hosting]
ms.assetid: 4a05ee56-08e4-4f3a-86a9-9b52083d5c0f
topic_type:
- apiref
ms.openlocfilehash: 6ee87fdbf75d4a07a7337a1c9fdc58a06191b992
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/24/2020
ms.locfileid: "95674824"
---
# <a name="iclrstrongnamestrongnamehashsize-method"></a><span data-ttu-id="7893c-102">Метод ICLRStrongName::StrongNameHashSize</span><span class="sxs-lookup"><span data-stu-id="7893c-102">ICLRStrongName::StrongNameHashSize Method</span></span>

<span data-ttu-id="7893c-103">Получает размер буфера, необходимый для хэша, с помощью указанного хэш-алгоритма.</span><span class="sxs-lookup"><span data-stu-id="7893c-103">Gets the buffer size required for a hash, using the specified hash algorithm.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7893c-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="7893c-104">Syntax</span></span>  
  
```cpp  
HRESULT StrongNameHashSize (  
    [in]  ULONG   ulHashAlg,  
    [out] DWORD   *pcbSize  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="7893c-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="7893c-105">Parameters</span></span>  

 `ulHashAlg`  
 <span data-ttu-id="7893c-106">окне Хэш-алгоритм, используемый для вычисления размера буфера.</span><span class="sxs-lookup"><span data-stu-id="7893c-106">[in] The hash algorithm used to compute the buffer size.</span></span>  
  
 `pcbSize`  
 <span data-ttu-id="7893c-107">заполняет Размер возвращенного буфера в байтах.</span><span class="sxs-lookup"><span data-stu-id="7893c-107">[out] The returned buffer size, in bytes.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="7893c-108">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="7893c-108">Return Value</span></span>  

 <span data-ttu-id="7893c-109">`S_OK` значение, если метод успешно выполнен; в противном случае — значение HRESULT, указывающее на сбой (см. раздел [Общие значения HRESULT](/windows/win32/seccrypto/common-hresult-values) для списка).</span><span class="sxs-lookup"><span data-stu-id="7893c-109">`S_OK` if the method completed successfully; otherwise, an HRESULT value that indicates failure (see [Common HRESULT Values](/windows/win32/seccrypto/common-hresult-values) for a list).</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="7893c-110">Требования</span><span class="sxs-lookup"><span data-stu-id="7893c-110">Requirements</span></span>  

 <span data-ttu-id="7893c-111">**Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="7893c-111">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="7893c-112">**Заголовок:** Метахост. h</span><span class="sxs-lookup"><span data-stu-id="7893c-112">**Header:** MetaHost.h</span></span>  
  
 <span data-ttu-id="7893c-113">**Библиотека:** Включается в качестве ресурса в MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="7893c-113">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="7893c-114">**.NET Framework версии:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="7893c-114">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7893c-115">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="7893c-115">See also</span></span>

- [<span data-ttu-id="7893c-116">Интерфейс ICLRStrongName</span><span class="sxs-lookup"><span data-stu-id="7893c-116">ICLRStrongName Interface</span></span>](iclrstrongname-interface.md)
