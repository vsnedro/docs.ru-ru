---
title: Функция GetHashFromFile
ms.date: 03/30/2017
api_name:
- GetHashFromFile
api_location:
- mscoree.dll
api_type:
- DLLExport
f1_keywords:
- GetHashFromFile
helpviewer_keywords:
- GetHashFromFile function [.NET Framework strong naming]
ms.assetid: b3c526a4-8fb4-4ad6-b6af-42ce9c06492e
topic_type:
- apiref
ms.openlocfilehash: ee9f9cd9a9f35c6c54497ad382bb6f9817d186bd
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/24/2020
ms.locfileid: "95732376"
---
# <a name="gethashfromfile-function"></a><span data-ttu-id="db3b9-102">Функция GetHashFromFile</span><span class="sxs-lookup"><span data-stu-id="db3b9-102">GetHashFromFile Function</span></span>

<span data-ttu-id="db3b9-103">Создает хэш содержимого указанного файла.</span><span class="sxs-lookup"><span data-stu-id="db3b9-103">Generates a hash over the contents of the specified file.</span></span>  
  
 <span data-ttu-id="db3b9-104">Эта функция является устаревшей.</span><span class="sxs-lookup"><span data-stu-id="db3b9-104">This function has been deprecated.</span></span> <span data-ttu-id="db3b9-105">Используйте вместо этого метод [метод iclrstrongname:: GetHashFromFile](../hosting/iclrstrongname-gethashfromfile-method.md) .</span><span class="sxs-lookup"><span data-stu-id="db3b9-105">Use the [ICLRStrongName::GetHashFromFile](../hosting/iclrstrongname-gethashfromfile-method.md) method instead.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="db3b9-106">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="db3b9-106">Syntax</span></span>  
  
```cpp  
HRESULT GetHashFromFile (  
    [in]  LPCSTR   szFilePath,  
    [in, out] unsigned int   *piHashAlg,
    [out] BYTE     *pbHash,
    [in]  DWORD    cchHash,
    [out] DWORD    *pchHash  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="db3b9-107">Параметры</span><span class="sxs-lookup"><span data-stu-id="db3b9-107">Parameters</span></span>  

 `szFilePath`  
 <span data-ttu-id="db3b9-108">окне Имя файла для хэширования.</span><span class="sxs-lookup"><span data-stu-id="db3b9-108">[in] The name of the file to hash.</span></span>  
  
 `piHashAlg`  
 <span data-ttu-id="db3b9-109">[вход, выход] Алгоритм, используемый при формировании хэша.</span><span class="sxs-lookup"><span data-stu-id="db3b9-109">[in, out] The algorithm to use when generating the hash.</span></span> <span data-ttu-id="db3b9-110">Допустимыми являются алгоритмы, определяемые интерфейсом Win32 CryptoAPI.</span><span class="sxs-lookup"><span data-stu-id="db3b9-110">Valid algorithms are those defined by the Win32 CryptoAPI.</span></span> <span data-ttu-id="db3b9-111">Если параметр `piHashAlg` имеет значение 0, используется алгоритм по умолчанию CALG_SHA-1.</span><span class="sxs-lookup"><span data-stu-id="db3b9-111">If `piHashAlg` is set to 0, the default algorithm CALG_SHA-1 is used.</span></span>  
  
 `pbHash`  
 <span data-ttu-id="db3b9-112">заполняет Массив байтов, содержащий созданный хэш.</span><span class="sxs-lookup"><span data-stu-id="db3b9-112">[out] A byte array containing the generated hash.</span></span>  
  
 `cchHash`  
 <span data-ttu-id="db3b9-113">окне Максимальный размер буфера, `pbHash` на который указывает.</span><span class="sxs-lookup"><span data-stu-id="db3b9-113">[in] The maximum size of the buffer that `pbHash` points to.</span></span>  
  
 `pchHash`  
 <span data-ttu-id="db3b9-114">заполняет Размер возвращаемого объекта (в байтах) `pbHash` .</span><span class="sxs-lookup"><span data-stu-id="db3b9-114">[out] The size, in bytes, of the returned `pbHash`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="db3b9-115">Комментарии</span><span class="sxs-lookup"><span data-stu-id="db3b9-115">Remarks</span></span>  

 <span data-ttu-id="db3b9-116">Эта функция аналогична [GetHashFromFileW](gethashfromfilew-function.md), за исключением того, что спецификация имени файла является ANSI, а не Unicode.</span><span class="sxs-lookup"><span data-stu-id="db3b9-116">This function is the same as [GetHashFromFileW](gethashfromfilew-function.md), except that the file name specification is ANSI instead of Unicode.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="db3b9-117">Требования</span><span class="sxs-lookup"><span data-stu-id="db3b9-117">Requirements</span></span>  

 <span data-ttu-id="db3b9-118">**Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="db3b9-118">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="db3b9-119">**Заголовок:** StrongName. h</span><span class="sxs-lookup"><span data-stu-id="db3b9-119">**Header:** StrongName.h</span></span>  
  
 <span data-ttu-id="db3b9-120">**Библиотека:** Включается в качестве ресурса в MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="db3b9-120">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="db3b9-121">**.NET Framework версии:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="db3b9-121">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="db3b9-122">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="db3b9-122">See also</span></span>

- [<span data-ttu-id="db3b9-123">Метод GetHashFromFile</span><span class="sxs-lookup"><span data-stu-id="db3b9-123">GetHashFromFile Method</span></span>](../hosting/iclrstrongname-gethashfromfile-method.md)
- [<span data-ttu-id="db3b9-124">Метод GetHashFromFileW</span><span class="sxs-lookup"><span data-stu-id="db3b9-124">GetHashFromFileW Method</span></span>](../hosting/iclrstrongname-gethashfromfilew-method.md)
- [<span data-ttu-id="db3b9-125">Интерфейс ICLRStrongName</span><span class="sxs-lookup"><span data-stu-id="db3b9-125">ICLRStrongName Interface</span></span>](../hosting/iclrstrongname-interface.md)
