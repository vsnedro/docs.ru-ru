---
title: Метод ICLRStrongName::GetHashFromHandle
ms.date: 03/30/2017
api_name:
- ICLRStrongName.GetHashFromHandle
- ICLRStrongName.StrongNameCompareAssemblies
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRStrongName::GetHashFromHandle
helpviewer_keywords:
- GetHashFromHandle method, ICLRStrongName interface [.NET Framework hosting]
- ICLRStrongName::GetHashFromHandle method [.NET Framework hosting]
ms.assetid: 3bedbb7d-3cdd-4175-b370-10ae734062db
topic_type:
- apiref
ms.openlocfilehash: e2d71f7c61b02273bdcaf182f6f79ca3c2a2c75f
ms.sourcegitcommit: c76c8b2c39ed2f0eee422b61a2ab4c05ca7771fa
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/21/2020
ms.locfileid: "83762085"
---
# <a name="iclrstrongnamegethashfromhandle-method"></a><span data-ttu-id="59df1-102">Метод ICLRStrongName::GetHashFromHandle</span><span class="sxs-lookup"><span data-stu-id="59df1-102">ICLRStrongName::GetHashFromHandle Method</span></span>
<span data-ttu-id="59df1-103">Создает хэш для содержимого файла с указанным файлом, используя указанный хэш-алгоритм.</span><span class="sxs-lookup"><span data-stu-id="59df1-103">Generates a hash over the contents of the file that has the specified file handle, using the specified hash algorithm.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="59df1-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="59df1-104">Syntax</span></span>  
  
```cpp  
HRESULT GetHashFromHandle (  
    [in]  HANDLE   hFile,  
    [in, out] unsigned int   *piHashAlg,  
    [out] BYTE     *pbHash,  
    [in]  DWORD    cchHash,  
    [out] DWORD    *pchHash  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="59df1-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="59df1-105">Parameters</span></span>  
 `hFile`  
 <span data-ttu-id="59df1-106">окне Описатель файла для хэширования.</span><span class="sxs-lookup"><span data-stu-id="59df1-106">[in] The handle of the file to be hashed.</span></span>  
  
 `piHashAlg`  
 <span data-ttu-id="59df1-107">[вход, выход] Константа, указывающая хэш-алгоритм.</span><span class="sxs-lookup"><span data-stu-id="59df1-107">[in, out] A constant that specifies the hash algorithm.</span></span> <span data-ttu-id="59df1-108">Используйте нуль для алгоритма по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="59df1-108">Use zero for the default algorithm.</span></span>  
  
 `pbHash`  
 <span data-ttu-id="59df1-109">заполняет Возвращаемый буфер хэша.</span><span class="sxs-lookup"><span data-stu-id="59df1-109">[out] The returned hash buffer.</span></span>  
  
 `cchHash`  
 <span data-ttu-id="59df1-110">окне Запрошенный максимальный размер `pbHash` .</span><span class="sxs-lookup"><span data-stu-id="59df1-110">[in] The requested maximum size of `pbHash`.</span></span>  
  
 `pchHash`  
 <span data-ttu-id="59df1-111">заполняет Размер возвращаемого объекта (в байтах) `pbHash` .</span><span class="sxs-lookup"><span data-stu-id="59df1-111">[out] The size, in bytes, of the returned `pbHash`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="59df1-112">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="59df1-112">Return Value</span></span>  
 <span data-ttu-id="59df1-113">`S_OK`значение, если метод успешно выполнен; в противном случае — значение HRESULT, указывающее на сбой (см. раздел [Общие значения HRESULT](/windows/win32/seccrypto/common-hresult-values) для списка).</span><span class="sxs-lookup"><span data-stu-id="59df1-113">`S_OK` if the method completed successfully; otherwise, an HRESULT value that indicates failure (see [Common HRESULT Values](/windows/win32/seccrypto/common-hresult-values) for a list).</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="59df1-114">Требования</span><span class="sxs-lookup"><span data-stu-id="59df1-114">Requirements</span></span>  
 <span data-ttu-id="59df1-115">**Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="59df1-115">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="59df1-116">**Заголовок:** Метахост. h</span><span class="sxs-lookup"><span data-stu-id="59df1-116">**Header:** MetaHost.h</span></span>  
  
 <span data-ttu-id="59df1-117">**Библиотека:** Включается в качестве ресурса в библиотеку MSCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="59df1-117">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="59df1-118">**.NET Framework версии:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="59df1-118">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="59df1-119">См. также</span><span class="sxs-lookup"><span data-stu-id="59df1-119">See also</span></span>

- [<span data-ttu-id="59df1-120">Интерфейс ICLRStrongName</span><span class="sxs-lookup"><span data-stu-id="59df1-120">ICLRStrongName Interface</span></span>](iclrstrongname-interface.md)
