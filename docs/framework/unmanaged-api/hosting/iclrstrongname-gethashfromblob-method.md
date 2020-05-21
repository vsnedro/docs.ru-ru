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
ms.openlocfilehash: 081df31d1e3b1ca3345fe44b60cff6af27386953
ms.sourcegitcommit: c76c8b2c39ed2f0eee422b61a2ab4c05ca7771fa
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/21/2020
ms.locfileid: "83762127"
---
# <a name="iclrstrongnamegethashfromblob-method"></a><span data-ttu-id="621c9-102">Метод ICLRStrongName::GetHashFromBlob</span><span class="sxs-lookup"><span data-stu-id="621c9-102">ICLRStrongName::GetHashFromBlob Method</span></span>
<span data-ttu-id="621c9-103">Получает хэш сборки по указанному адресу памяти с помощью указанного хэш-алгоритма.</span><span class="sxs-lookup"><span data-stu-id="621c9-103">Gets a hash of the assembly at the specified memory address, using the specified hash algorithm.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="621c9-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="621c9-104">Syntax</span></span>  
  
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
  
## <a name="parameters"></a><span data-ttu-id="621c9-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="621c9-105">Parameters</span></span>  
 `pbBlob`  
 <span data-ttu-id="621c9-106">окне Указатель на адрес блока памяти, который необходимо хэшировать.</span><span class="sxs-lookup"><span data-stu-id="621c9-106">[in] A pointer to the address of the memory block to be hashed.</span></span>  
  
 `cchBlob`  
 <span data-ttu-id="621c9-107">окне Длина блока памяти в байтах.</span><span class="sxs-lookup"><span data-stu-id="621c9-107">[in] The length, in bytes, of the memory block.</span></span>  
  
 `piHashAlg`  
 <span data-ttu-id="621c9-108">[вход, выход] Константа, указывающая хэш-алгоритм.</span><span class="sxs-lookup"><span data-stu-id="621c9-108">[in, out] A constant that specifies the hash algorithm.</span></span> <span data-ttu-id="621c9-109">Используйте нуль для алгоритма по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="621c9-109">Use zero for the default algorithm.</span></span>  
  
 `pbHash`  
 <span data-ttu-id="621c9-110">заполняет Возвращаемый буфер хэша.</span><span class="sxs-lookup"><span data-stu-id="621c9-110">[out] The returned hash buffer.</span></span>  
  
 `cchHash`  
 <span data-ttu-id="621c9-111">окне Запрошенный максимальный размер `pbHash` .</span><span class="sxs-lookup"><span data-stu-id="621c9-111">[in] The requested maximum size of `pbHash`.</span></span>  
  
 `pchHash`  
 <span data-ttu-id="621c9-112">заполняет Размер возвращаемого объекта (в байтах) `pbHash` .</span><span class="sxs-lookup"><span data-stu-id="621c9-112">[out] The size, in bytes, of the returned `pbHash`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="621c9-113">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="621c9-113">Return Value</span></span>  
 <span data-ttu-id="621c9-114">`S_OK`значение, если метод успешно выполнен; в противном случае — значение HRESULT, указывающее на сбой (см. раздел [Общие значения HRESULT](/windows/win32/seccrypto/common-hresult-values) для списка).</span><span class="sxs-lookup"><span data-stu-id="621c9-114">`S_OK` if the method completed successfully; otherwise, an HRESULT value that indicates failure (see [Common HRESULT Values](/windows/win32/seccrypto/common-hresult-values) for a list).</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="621c9-115">Требования</span><span class="sxs-lookup"><span data-stu-id="621c9-115">Requirements</span></span>  
 <span data-ttu-id="621c9-116">**Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="621c9-116">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="621c9-117">**Заголовок:** Метахост. h</span><span class="sxs-lookup"><span data-stu-id="621c9-117">**Header:** MetaHost.h</span></span>  
  
 <span data-ttu-id="621c9-118">**Библиотека:** Включается в качестве ресурса в библиотеку MSCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="621c9-118">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="621c9-119">**.NET Framework версии:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="621c9-119">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="621c9-120">См. также</span><span class="sxs-lookup"><span data-stu-id="621c9-120">See also</span></span>

- [<span data-ttu-id="621c9-121">Интерфейс ICLRStrongName</span><span class="sxs-lookup"><span data-stu-id="621c9-121">ICLRStrongName Interface</span></span>](iclrstrongname-interface.md)
