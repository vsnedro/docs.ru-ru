---
title: Метод ICLRStrongName::GetHashFromAssemblyFile
ms.date: 03/30/2017
api_name:
- ICLRStrongName.GetHashFromAssemblyFile
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRStrongName::GetHashFromAssemblyFile
helpviewer_keywords:
- ICLRStrongName::GetHashFromAssemblyFile method [.NET Framework hosting]
- GetHashFromAssemblyFile method, ICLRStrongName interface [.NET Framework hosting]
ms.assetid: 0b67ea03-d474-4605-acaa-57455790250c
topic_type:
- apiref
ms.openlocfilehash: 007de0365bf70b1f4a9a9e0f01807e7fdac19f54
ms.sourcegitcommit: c76c8b2c39ed2f0eee422b61a2ab4c05ca7771fa
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/21/2020
ms.locfileid: "83762153"
---
# <a name="iclrstrongnamegethashfromassemblyfile-method"></a><span data-ttu-id="cd4fa-102">Метод ICLRStrongName::GetHashFromAssemblyFile</span><span class="sxs-lookup"><span data-stu-id="cd4fa-102">ICLRStrongName::GetHashFromAssemblyFile Method</span></span>
<span data-ttu-id="cd4fa-103">Получает хэш указанного файла сборки с помощью указанного хэш-алгоритма.</span><span class="sxs-lookup"><span data-stu-id="cd4fa-103">Gets a hash of the specified assembly file, using the specified hash algorithm.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="cd4fa-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="cd4fa-104">Syntax</span></span>  
  
```cpp  
HRESULT GetHashFromAssemblyFile (  
    [in]  LPCSTR   szFilePath,  
    [in, out] unsigned int   *piHashAlg,  
    [out] BYTE     *pbHash,  
    [in]  DWORD    cchHash,  
    [out] DWORD    *pchHash  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="cd4fa-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="cd4fa-105">Parameters</span></span>  
 `szFilePath`  
 <span data-ttu-id="cd4fa-106">окне Путь к файлу для хэширования.</span><span class="sxs-lookup"><span data-stu-id="cd4fa-106">[in] The path to the file to be hashed.</span></span>  
  
 `piHashAlg`  
 <span data-ttu-id="cd4fa-107">[вход, выход] Константа, указывающая хэш-алгоритм.</span><span class="sxs-lookup"><span data-stu-id="cd4fa-107">[in, out] A constant that specifies the hash algorithm.</span></span> <span data-ttu-id="cd4fa-108">Для алгоритма хэширования по умолчанию используется нуль.</span><span class="sxs-lookup"><span data-stu-id="cd4fa-108">Use zero for the default hash algorithm.</span></span>  
  
 `pbHash`  
 <span data-ttu-id="cd4fa-109">заполняет Возвращаемый буфер хэша.</span><span class="sxs-lookup"><span data-stu-id="cd4fa-109">[out] The returned hash buffer.</span></span>  
  
 `cchHash`  
 <span data-ttu-id="cd4fa-110">окне Запрошенный максимальный размер `pbHash` .</span><span class="sxs-lookup"><span data-stu-id="cd4fa-110">[in] The requested maximum size of `pbHash`.</span></span>  
  
 `pchHash`  
 <span data-ttu-id="cd4fa-111">заполняет Возвращаемый размер (в байтах) для `pbHash` .</span><span class="sxs-lookup"><span data-stu-id="cd4fa-111">[out] The returned size, in bytes, of `pbHash`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="cd4fa-112">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="cd4fa-112">Return Value</span></span>  
 <span data-ttu-id="cd4fa-113">`S_OK`значение, если метод успешно выполнен; в противном случае — значение HRESULT, указывающее на сбой (см. раздел [Общие значения HRESULT](/windows/win32/seccrypto/common-hresult-values) для списка).</span><span class="sxs-lookup"><span data-stu-id="cd4fa-113">`S_OK` if the method completed successfully; otherwise, an HRESULT value that indicates failure (see [Common HRESULT Values](/windows/win32/seccrypto/common-hresult-values) for a list).</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="cd4fa-114">Требования</span><span class="sxs-lookup"><span data-stu-id="cd4fa-114">Requirements</span></span>  
 <span data-ttu-id="cd4fa-115">**Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="cd4fa-115">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="cd4fa-116">**Заголовок:** Метахост. h</span><span class="sxs-lookup"><span data-stu-id="cd4fa-116">**Header:** MetaHost.h</span></span>  
  
 <span data-ttu-id="cd4fa-117">**Библиотека:** Включается в качестве ресурса в библиотеку MSCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="cd4fa-117">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="cd4fa-118">**.NET Framework версии:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="cd4fa-118">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="cd4fa-119">См. также</span><span class="sxs-lookup"><span data-stu-id="cd4fa-119">See also</span></span>

- [<span data-ttu-id="cd4fa-120">Метод GetHashFromAssemblyFileW</span><span class="sxs-lookup"><span data-stu-id="cd4fa-120">GetHashFromAssemblyFileW Method</span></span>](iclrstrongname-gethashfromassemblyfilew-method.md)
- [<span data-ttu-id="cd4fa-121">Интерфейс ICLRStrongName</span><span class="sxs-lookup"><span data-stu-id="cd4fa-121">ICLRStrongName Interface</span></span>](iclrstrongname-interface.md)
