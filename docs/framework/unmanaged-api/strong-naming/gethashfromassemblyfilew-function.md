---
title: Функция GetHashFromAssemblyFileW
ms.date: 03/30/2017
api_name:
- GetHashFromAssemblyFileW
api_location:
- mscoree.dll
api_type:
- DLLExport
f1_keywords:
- GetHashFromAssemblyFileW
helpviewer_keywords:
- GetHashFromAssemblyFileW function [.NET Framework strong naming]
ms.assetid: d1b2b172-5353-42af-a877-cf653c68ece0
topic_type:
- apiref
ms.openlocfilehash: b895c77850c0457fd2a152c1128c016093599f76
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/24/2020
ms.locfileid: "95730985"
---
# <a name="gethashfromassemblyfilew-function"></a><span data-ttu-id="2a596-102">Функция GetHashFromAssemblyFileW</span><span class="sxs-lookup"><span data-stu-id="2a596-102">GetHashFromAssemblyFileW Function</span></span>

<span data-ttu-id="2a596-103">Получает хэш указанного файла сборки с помощью указанного хэш-алгоритма.</span><span class="sxs-lookup"><span data-stu-id="2a596-103">Gets a hash of the specified assembly file, using the specified hash algorithm.</span></span> <span data-ttu-id="2a596-104">Путь к файлу сборки должен быть указан в виде строки в Юникоде.</span><span class="sxs-lookup"><span data-stu-id="2a596-104">The path to the assembly file must be specified as a Unicode string.</span></span>  
  
 <span data-ttu-id="2a596-105">Эта функция является устаревшей.</span><span class="sxs-lookup"><span data-stu-id="2a596-105">This function has been deprecated.</span></span> <span data-ttu-id="2a596-106">Используйте вместо этого метод [метод iclrstrongname:: GetHashFromAssemblyFileW](../hosting/iclrstrongname-gethashfromassemblyfilew-method.md) .</span><span class="sxs-lookup"><span data-stu-id="2a596-106">Use the [ICLRStrongName::GetHashFromAssemblyFileW](../hosting/iclrstrongname-gethashfromassemblyfilew-method.md) method instead.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2a596-107">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="2a596-107">Syntax</span></span>  
  
```cpp  
HRESULT GetHashFromAssemblyFileW (  
    [in]  LPCWSTR   wszFilePath,  
    [in, out] unsigned int   *piHashAlg,  
    [out] BYTE      *pbHash,  
    [in]  DWORD     cchHash,  
    [out] DWORD     *pchHash  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="2a596-108">Параметры</span><span class="sxs-lookup"><span data-stu-id="2a596-108">Parameters</span></span>  

 `wszFilePath`  
 <span data-ttu-id="2a596-109">окне Путь к файлу для хэширования.</span><span class="sxs-lookup"><span data-stu-id="2a596-109">[in] The path to the file to be hashed.</span></span> <span data-ttu-id="2a596-110">Этот параметр должен быть строкой в Юникоде.</span><span class="sxs-lookup"><span data-stu-id="2a596-110">This parameter must be a Unicode string.</span></span>  
  
 `piHashAlg`  
 <span data-ttu-id="2a596-111">[вход, выход] Константа, указывающая хэш-алгоритм.</span><span class="sxs-lookup"><span data-stu-id="2a596-111">[in, out] A constant that specifies the hash algorithm.</span></span> <span data-ttu-id="2a596-112">Для алгоритма хэширования по умолчанию используется нуль.</span><span class="sxs-lookup"><span data-stu-id="2a596-112">Use zero for the default hash algorithm.</span></span>  
  
 `pbHash`  
 <span data-ttu-id="2a596-113">заполняет Возвращаемый буфер хэша.</span><span class="sxs-lookup"><span data-stu-id="2a596-113">[out] The returned hash buffer.</span></span>  
  
 `cchHash`  
 <span data-ttu-id="2a596-114">окне Запрошенный максимальный размер `pbHash` .</span><span class="sxs-lookup"><span data-stu-id="2a596-114">[in] The requested maximum size of `pbHash`.</span></span>  
  
 `pchHash`  
 <span data-ttu-id="2a596-115">заполняет Возвращаемый размер (в байтах) для `pbHash` .</span><span class="sxs-lookup"><span data-stu-id="2a596-115">[out] The returned size, in bytes, of `pbHash`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="2a596-116">Требования</span><span class="sxs-lookup"><span data-stu-id="2a596-116">Requirements</span></span>  

 <span data-ttu-id="2a596-117">**Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="2a596-117">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="2a596-118">**Заголовок:** StrongName. h</span><span class="sxs-lookup"><span data-stu-id="2a596-118">**Header:** StrongName.h</span></span>  
  
 <span data-ttu-id="2a596-119">**Библиотека:** Включается в качестве ресурса в MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="2a596-119">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="2a596-120">**.NET Framework версии:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="2a596-120">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2a596-121">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="2a596-121">See also</span></span>

- [<span data-ttu-id="2a596-122">Метод GetHashFromAssemblyFileW</span><span class="sxs-lookup"><span data-stu-id="2a596-122">GetHashFromAssemblyFileW Method</span></span>](../hosting/iclrstrongname-gethashfromassemblyfilew-method.md)
- [<span data-ttu-id="2a596-123">Метод GetHashFromAssemblyFile</span><span class="sxs-lookup"><span data-stu-id="2a596-123">GetHashFromAssemblyFile Method</span></span>](../hosting/iclrstrongname-gethashfromassemblyfile-method.md)
- [<span data-ttu-id="2a596-124">Интерфейс ICLRStrongName</span><span class="sxs-lookup"><span data-stu-id="2a596-124">ICLRStrongName Interface</span></span>](../hosting/iclrstrongname-interface.md)
