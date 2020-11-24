---
title: Метод ICLRStrongName::GetHashFromFileW
ms.date: 03/30/2017
api_name:
- ICLRStrongName.GetHashFromFileW
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRStrongName::GetHashFromFileW
helpviewer_keywords:
- GetHashFromFileW method, ICLRStrongName interface [.NET Framework hosting]
- ICLRStrongName::GetHashFromFileW method [.NET Framework hosting]
ms.assetid: c6ff45fc-905d-4c6e-b00c-97c6c7c55d99
topic_type:
- apiref
ms.openlocfilehash: eda78976f175230cc2405b9cb151993e63697e48
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/24/2020
ms.locfileid: "95685764"
---
# <a name="iclrstrongnamegethashfromfilew-method"></a><span data-ttu-id="68969-102">Метод ICLRStrongName::GetHashFromFileW</span><span class="sxs-lookup"><span data-stu-id="68969-102">ICLRStrongName::GetHashFromFileW Method</span></span>

<span data-ttu-id="68969-103">Создает хэш содержимого файла, указанного строкой Юникода.</span><span class="sxs-lookup"><span data-stu-id="68969-103">Generates a hash over the contents of the file specified by a Unicode string.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="68969-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="68969-104">Syntax</span></span>  
  
```cpp  
HRESULT GetHashFromFileW (
    [in]  LPCWSTR   wszFilePath,  
    [in, out] unsigned int   *piHashAlg,  
    [out] BYTE      *pbHash,  
    [in]  DWORD     cchHash,  
    [out] DWORD     *pchHash  
);
```  
  
## <a name="parameters"></a><span data-ttu-id="68969-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="68969-105">Parameters</span></span>  

 `wszFilePath`  
 <span data-ttu-id="68969-106">окне Имя файла в Юникоде для хэширования.</span><span class="sxs-lookup"><span data-stu-id="68969-106">[in] The Unicode name of the file to hash.</span></span>  
  
 `piHashAlg`  
 <span data-ttu-id="68969-107">[вход, выход] Алгоритм, используемый при формировании хэша.</span><span class="sxs-lookup"><span data-stu-id="68969-107">[in, out] The algorithm to use when generating the hash.</span></span> <span data-ttu-id="68969-108">Допустимыми являются алгоритмы, определяемые интерфейсом Win32 CryptoAPI.</span><span class="sxs-lookup"><span data-stu-id="68969-108">Valid algorithms are those defined by the Win32 CryptoAPI.</span></span> <span data-ttu-id="68969-109">Если параметр `piHashAlg` имеет значение 0, используется алгоритм по умолчанию CALG_SHA-1.</span><span class="sxs-lookup"><span data-stu-id="68969-109">If `piHashAlg` is set to 0, the default algorithm CALG_SHA-1 is used.</span></span>  
  
 `pbHash`  
 <span data-ttu-id="68969-110">заполняет Массив байтов, содержащий созданный хэш.</span><span class="sxs-lookup"><span data-stu-id="68969-110">[out] A byte array containing the generated hash.</span></span>  
  
 `cchHash`  
 <span data-ttu-id="68969-111">окне Максимальный размер буфера, на который указывает `pbHash` .</span><span class="sxs-lookup"><span data-stu-id="68969-111">[in] The maximum size of the buffer pointed to by `pbHash`.</span></span>  
  
 `pchHash`  
 <span data-ttu-id="68969-112">заполняет Размер (в байтах) `pbHash` .</span><span class="sxs-lookup"><span data-stu-id="68969-112">[out] The size, in bytes, of `pbHash`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="68969-113">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="68969-113">Return Value</span></span>  

 <span data-ttu-id="68969-114">`S_OK` значение, если метод успешно выполнен; в противном случае — значение HRESULT, указывающее на сбой (см. раздел [Общие значения HRESULT](/windows/win32/seccrypto/common-hresult-values) для списка).</span><span class="sxs-lookup"><span data-stu-id="68969-114">`S_OK` if the method completed successfully; otherwise, an HRESULT value that indicates failure (see [Common HRESULT Values](/windows/win32/seccrypto/common-hresult-values) for a list).</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="68969-115">Комментарии</span><span class="sxs-lookup"><span data-stu-id="68969-115">Remarks</span></span>  

 <span data-ttu-id="68969-116">Этот метод аналогичен методу [метод iclrstrongname:: GetHashFromFile](iclrstrongname-gethashfromfile-method.md) , за исключением того, что спецификация имени файла имеет кодировку Unicode, а не ANSI.</span><span class="sxs-lookup"><span data-stu-id="68969-116">This method is the same as the [ICLRStrongName::GetHashFromFile](iclrstrongname-gethashfromfile-method.md) method, except that the file name specification is Unicode instead of ANSI.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="68969-117">Требования</span><span class="sxs-lookup"><span data-stu-id="68969-117">Requirements</span></span>  

 <span data-ttu-id="68969-118">**Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="68969-118">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="68969-119">**Заголовок:** Метахост. h</span><span class="sxs-lookup"><span data-stu-id="68969-119">**Header:** MetaHost.h</span></span>  
  
 <span data-ttu-id="68969-120">**Библиотека:** Включается в качестве ресурса в MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="68969-120">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="68969-121">**.NET Framework версии:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="68969-121">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="68969-122">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="68969-122">See also</span></span>

- [<span data-ttu-id="68969-123">Метод GetHashFromFile</span><span class="sxs-lookup"><span data-stu-id="68969-123">GetHashFromFile Method</span></span>](iclrstrongname-gethashfromfile-method.md)
- [<span data-ttu-id="68969-124">Интерфейс ICLRStrongName</span><span class="sxs-lookup"><span data-stu-id="68969-124">ICLRStrongName Interface</span></span>](iclrstrongname-interface.md)
