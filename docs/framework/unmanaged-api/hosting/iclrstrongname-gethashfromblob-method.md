---
title: Метод ICLRStrongName::GetHashFromBlob
ms.date: 03/30/2017
api_name:
- ICLRStrongName.GetHashFromBlob
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRStrongName::GetHashFromBlob
helpviewer_keywords:
- ICLRStrongName::GetHashFromBlob method [.NET Framework hosting]
- GetHashFromBlob method, ICLRStrongName interface [.NET Framework hosting]
ms.assetid: f91d0f89-f356-49ac-aafb-50fad963c13d
topic_type:
- apiref
ms.openlocfilehash: 6b67aed90585f57d2635bb1a22d3e009edf01159
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/24/2020
ms.locfileid: "95714813"
---
# <a name="iclrstrongnamegethashfromblob-method"></a><span data-ttu-id="c88d8-102">Метод ICLRStrongName::GetHashFromBlob</span><span class="sxs-lookup"><span data-stu-id="c88d8-102">ICLRStrongName::GetHashFromBlob Method</span></span>

<span data-ttu-id="c88d8-103">Получает хэш сборки по указанному адресу памяти с помощью указанного хэш-алгоритма.</span><span class="sxs-lookup"><span data-stu-id="c88d8-103">Gets a hash of the assembly at the specified memory address, using the specified hash algorithm.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c88d8-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="c88d8-104">Syntax</span></span>  
  
```cpp  
HRESULT GetHashFromBlob (  
    [in]  BYTE    *pbBlob,  
    [in]  DWORD   cchBlob,  
    [in, out] unsigned int   *piHashAlg,  
    [out] BYTE    *pbHash,  
    [in]  DWORD   cchHash,  
    [out] DWORD   *pchHash  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="c88d8-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="c88d8-105">Parameters</span></span>  

 `pbBlob`  
 <span data-ttu-id="c88d8-106">окне Указатель на адрес блока памяти, который необходимо хэшировать.</span><span class="sxs-lookup"><span data-stu-id="c88d8-106">[in] A pointer to the address of the memory block to be hashed.</span></span>  
  
 `cchBlob`  
 <span data-ttu-id="c88d8-107">окне Длина блока памяти в байтах.</span><span class="sxs-lookup"><span data-stu-id="c88d8-107">[in] The length, in bytes, of the memory block.</span></span>  
  
 `piHashAlg`  
 <span data-ttu-id="c88d8-108">[вход, выход] Константа, указывающая хэш-алгоритм.</span><span class="sxs-lookup"><span data-stu-id="c88d8-108">[in, out] A constant that specifies the hash algorithm.</span></span> <span data-ttu-id="c88d8-109">Используйте нуль для алгоритма по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="c88d8-109">Use zero for the default algorithm.</span></span>  
  
 `pbHash`  
 <span data-ttu-id="c88d8-110">заполняет Возвращаемый буфер хэша.</span><span class="sxs-lookup"><span data-stu-id="c88d8-110">[out] The returned hash buffer.</span></span>  
  
 `cchHash`  
 <span data-ttu-id="c88d8-111">окне Запрошенный максимальный размер `pbHash` .</span><span class="sxs-lookup"><span data-stu-id="c88d8-111">[in] The requested maximum size of `pbHash`.</span></span>  
  
 `pchHash`  
 <span data-ttu-id="c88d8-112">заполняет Размер возвращаемого объекта (в байтах) `pbHash` .</span><span class="sxs-lookup"><span data-stu-id="c88d8-112">[out] The size, in bytes, of the returned `pbHash`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="c88d8-113">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="c88d8-113">Return Value</span></span>  

 <span data-ttu-id="c88d8-114">`S_OK` значение, если метод успешно выполнен; в противном случае — значение HRESULT, указывающее на сбой (см. раздел [Общие значения HRESULT](/windows/win32/seccrypto/common-hresult-values) для списка).</span><span class="sxs-lookup"><span data-stu-id="c88d8-114">`S_OK` if the method completed successfully; otherwise, an HRESULT value that indicates failure (see [Common HRESULT Values](/windows/win32/seccrypto/common-hresult-values) for a list).</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="c88d8-115">Требования</span><span class="sxs-lookup"><span data-stu-id="c88d8-115">Requirements</span></span>  

 <span data-ttu-id="c88d8-116">**Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="c88d8-116">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c88d8-117">**Заголовок:** Метахост. h</span><span class="sxs-lookup"><span data-stu-id="c88d8-117">**Header:** MetaHost.h</span></span>  
  
 <span data-ttu-id="c88d8-118">**Библиотека:** Включается в качестве ресурса в MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="c88d8-118">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="c88d8-119">**.NET Framework версии:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="c88d8-119">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c88d8-120">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="c88d8-120">See also</span></span>

- [<span data-ttu-id="c88d8-121">Интерфейс ICLRStrongName</span><span class="sxs-lookup"><span data-stu-id="c88d8-121">ICLRStrongName Interface</span></span>](iclrstrongname-interface.md)
