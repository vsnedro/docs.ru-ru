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
ms.openlocfilehash: 6dbb3360132186c38c007fb5fa12a3724ca145aa
ms.sourcegitcommit: c76c8b2c39ed2f0eee422b61a2ab4c05ca7771fa
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/21/2020
ms.locfileid: "83762101"
---
# <a name="iclrstrongnamegethashfromfilew-method"></a><span data-ttu-id="b241b-102">Метод ICLRStrongName::GetHashFromFileW</span><span class="sxs-lookup"><span data-stu-id="b241b-102">ICLRStrongName::GetHashFromFileW Method</span></span>
<span data-ttu-id="b241b-103">Создает хэш содержимого файла, указанного строкой Юникода.</span><span class="sxs-lookup"><span data-stu-id="b241b-103">Generates a hash over the contents of the file specified by a Unicode string.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b241b-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="b241b-104">Syntax</span></span>  
  
```cpp  
HRESULT GetHashFromFileW (
    [in]  LPCWSTR   wszFilePath,  
    [in, out] unsigned int   *piHashAlg,  
    [out] BYTE      *pbHash,  
    [in]  DWORD     cchHash,  
    [out] DWORD     *pchHash  
);
```  
  
## <a name="parameters"></a><span data-ttu-id="b241b-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="b241b-105">Parameters</span></span>  
 `wszFilePath`  
 <span data-ttu-id="b241b-106">окне Имя файла в Юникоде для хэширования.</span><span class="sxs-lookup"><span data-stu-id="b241b-106">[in] The Unicode name of the file to hash.</span></span>  
  
 `piHashAlg`  
 <span data-ttu-id="b241b-107">[вход, выход] Алгоритм, используемый при формировании хэша.</span><span class="sxs-lookup"><span data-stu-id="b241b-107">[in, out] The algorithm to use when generating the hash.</span></span> <span data-ttu-id="b241b-108">Допустимыми являются алгоритмы, определяемые интерфейсом Win32 CryptoAPI.</span><span class="sxs-lookup"><span data-stu-id="b241b-108">Valid algorithms are those defined by the Win32 CryptoAPI.</span></span> <span data-ttu-id="b241b-109">Если параметр `piHashAlg` имеет значение 0, используется алгоритм по умолчанию CALG_SHA-1.</span><span class="sxs-lookup"><span data-stu-id="b241b-109">If `piHashAlg` is set to 0, the default algorithm CALG_SHA-1 is used.</span></span>  
  
 `pbHash`  
 <span data-ttu-id="b241b-110">заполняет Массив байтов, содержащий созданный хэш.</span><span class="sxs-lookup"><span data-stu-id="b241b-110">[out] A byte array containing the generated hash.</span></span>  
  
 `cchHash`  
 <span data-ttu-id="b241b-111">окне Максимальный размер буфера, на который указывает `pbHash` .</span><span class="sxs-lookup"><span data-stu-id="b241b-111">[in] The maximum size of the buffer pointed to by `pbHash`.</span></span>  
  
 `pchHash`  
 <span data-ttu-id="b241b-112">заполняет Размер (в байтах) `pbHash` .</span><span class="sxs-lookup"><span data-stu-id="b241b-112">[out] The size, in bytes, of `pbHash`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="b241b-113">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="b241b-113">Return Value</span></span>  
 <span data-ttu-id="b241b-114">`S_OK`значение, если метод успешно выполнен; в противном случае — значение HRESULT, указывающее на сбой (см. раздел [Общие значения HRESULT](/windows/win32/seccrypto/common-hresult-values) для списка).</span><span class="sxs-lookup"><span data-stu-id="b241b-114">`S_OK` if the method completed successfully; otherwise, an HRESULT value that indicates failure (see [Common HRESULT Values](/windows/win32/seccrypto/common-hresult-values) for a list).</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="b241b-115">Комментарии</span><span class="sxs-lookup"><span data-stu-id="b241b-115">Remarks</span></span>  
 <span data-ttu-id="b241b-116">Этот метод аналогичен методу [метод iclrstrongname:: GetHashFromFile](iclrstrongname-gethashfromfile-method.md) , за исключением того, что спецификация имени файла имеет кодировку Unicode, а не ANSI.</span><span class="sxs-lookup"><span data-stu-id="b241b-116">This method is the same as the [ICLRStrongName::GetHashFromFile](iclrstrongname-gethashfromfile-method.md) method, except that the file name specification is Unicode instead of ANSI.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="b241b-117">Требования</span><span class="sxs-lookup"><span data-stu-id="b241b-117">Requirements</span></span>  
 <span data-ttu-id="b241b-118">**Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="b241b-118">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="b241b-119">**Заголовок:** Метахост. h</span><span class="sxs-lookup"><span data-stu-id="b241b-119">**Header:** MetaHost.h</span></span>  
  
 <span data-ttu-id="b241b-120">**Библиотека:** Включается в качестве ресурса в библиотеку MSCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="b241b-120">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="b241b-121">**.NET Framework версии:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="b241b-121">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b241b-122">См. также</span><span class="sxs-lookup"><span data-stu-id="b241b-122">See also</span></span>

- [<span data-ttu-id="b241b-123">Метод GetHashFromFile</span><span class="sxs-lookup"><span data-stu-id="b241b-123">GetHashFromFile Method</span></span>](iclrstrongname-gethashfromfile-method.md)
- [<span data-ttu-id="b241b-124">Интерфейс ICLRStrongName</span><span class="sxs-lookup"><span data-stu-id="b241b-124">ICLRStrongName Interface</span></span>](iclrstrongname-interface.md)
