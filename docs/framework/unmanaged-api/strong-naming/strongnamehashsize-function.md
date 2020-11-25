---
title: Функция StrongNameHashSize
ms.date: 03/30/2017
api_name:
- StrongNameHashSize
api_location:
- mscoree.dll
api_type:
- DLLExport
f1_keywords:
- StrongNameHashSize
helpviewer_keywords:
- StrongNameHashSize function [.NET Framework strong naming]
ms.assetid: 738c98d7-a60c-45fe-a296-220af05e6991
topic_type:
- apiref
ms.openlocfilehash: 1116fcde754f966a783f4fdca85df8bd3ca1b0ba
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/24/2020
ms.locfileid: "95724446"
---
# <a name="strongnamehashsize-function"></a><span data-ttu-id="b3afc-102">Функция StrongNameHashSize</span><span class="sxs-lookup"><span data-stu-id="b3afc-102">StrongNameHashSize Function</span></span>

<span data-ttu-id="b3afc-103">Получает размер буфера, необходимый для хэша, с помощью указанного хэш-алгоритма.</span><span class="sxs-lookup"><span data-stu-id="b3afc-103">Gets the buffer size required for a hash, using the specified hash algorithm.</span></span>  
  
 <span data-ttu-id="b3afc-104">Эта функция является устаревшей.</span><span class="sxs-lookup"><span data-stu-id="b3afc-104">This function has been deprecated.</span></span> <span data-ttu-id="b3afc-105">Используйте вместо этого метод [метод iclrstrongname:: StrongNameHashSize](../hosting/iclrstrongname-strongnamehashsize-method.md) .</span><span class="sxs-lookup"><span data-stu-id="b3afc-105">Use the [ICLRStrongName::StrongNameHashSize](../hosting/iclrstrongname-strongnamehashsize-method.md) method instead.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b3afc-106">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="b3afc-106">Syntax</span></span>  
  
```cpp  
BOOLEAN StrongNameHashSize (  
    [in]  ULONG   ulHashAlg,  
    [out] DWORD   *pcbSize  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="b3afc-107">Параметры</span><span class="sxs-lookup"><span data-stu-id="b3afc-107">Parameters</span></span>  

 `ulHashAlg`  
 <span data-ttu-id="b3afc-108">окне Хэш-алгоритм, используемый для вычисления размера буфера.</span><span class="sxs-lookup"><span data-stu-id="b3afc-108">[in] The hash algorithm used to compute the buffer size.</span></span>  
  
 `pcbSize`  
 <span data-ttu-id="b3afc-109">заполняет Размер возвращенного буфера в байтах.</span><span class="sxs-lookup"><span data-stu-id="b3afc-109">[out] The returned buffer size, in bytes.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="b3afc-110">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="b3afc-110">Return Value</span></span>  

 <span data-ttu-id="b3afc-111">`true` При успешном завершении; в противном случае — `false` .</span><span class="sxs-lookup"><span data-stu-id="b3afc-111">`true` on successful completion; otherwise, `false`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="b3afc-112">Комментарии</span><span class="sxs-lookup"><span data-stu-id="b3afc-112">Remarks</span></span>  

 <span data-ttu-id="b3afc-113">Если `StrongNameHashSize` функция не завершается успешно, вызовите функцию [стронгнамирроринфо](strongnameerrorinfo-function.md) , чтобы получить последнюю созданную ошибку.</span><span class="sxs-lookup"><span data-stu-id="b3afc-113">If the `StrongNameHashSize` function does not complete successfully, call the [StrongNameErrorInfo](strongnameerrorinfo-function.md) function to retrieve the last generated error.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="b3afc-114">Требования</span><span class="sxs-lookup"><span data-stu-id="b3afc-114">Requirements</span></span>  

 <span data-ttu-id="b3afc-115">**Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="b3afc-115">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="b3afc-116">**Заголовок:** StrongName. h</span><span class="sxs-lookup"><span data-stu-id="b3afc-116">**Header:** StrongName.h</span></span>  
  
 <span data-ttu-id="b3afc-117">**Библиотека:** Включается в качестве ресурса в MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="b3afc-117">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="b3afc-118">**.NET Framework версии:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="b3afc-118">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b3afc-119">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="b3afc-119">See also</span></span>

- [<span data-ttu-id="b3afc-120">Метод StrongNameHashSize</span><span class="sxs-lookup"><span data-stu-id="b3afc-120">StrongNameHashSize Method</span></span>](../hosting/iclrstrongname-strongnamehashsize-method.md)
- [<span data-ttu-id="b3afc-121">Интерфейс ICLRStrongName</span><span class="sxs-lookup"><span data-stu-id="b3afc-121">ICLRStrongName Interface</span></span>](../hosting/iclrstrongname-interface.md)
