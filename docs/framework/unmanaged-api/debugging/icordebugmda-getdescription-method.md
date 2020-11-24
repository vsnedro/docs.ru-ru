---
title: Метод ICorDebugMDA::GetDescription
ms.date: 03/30/2017
api_name:
- ICorDebugMDA.GetDescription
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugMDA::GetDescription
helpviewer_keywords:
- GetDescription method [.NET Framework debugging]
- ICorDebugMDA::GetDescription method [.NET Framework debugging]
ms.assetid: 01d1b481-ca67-4712-8744-d342ec0df639
topic_type:
- apiref
ms.openlocfilehash: cb1e0f2bc597b48496dc362c9d7a364421c68a87
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/24/2020
ms.locfileid: "95681851"
---
# <a name="icordebugmdagetdescription-method"></a><span data-ttu-id="383ca-102">Метод ICorDebugMDA::GetDescription</span><span class="sxs-lookup"><span data-stu-id="383ca-102">ICorDebugMDA::GetDescription Method</span></span>

<span data-ttu-id="383ca-103">Возвращает строку, содержащую описание помощника по отладке управляемого кода (MDA), представленного [ICorDebugMDA](icordebugmda-interface.md).</span><span class="sxs-lookup"><span data-stu-id="383ca-103">Gets a string containing the description of the managed debugging assistant (MDA) represented by [ICorDebugMDA](icordebugmda-interface.md).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="383ca-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="383ca-104">Syntax</span></span>  
  
```cpp  
HRESULT GetDescription (  
    [in] ULONG32   cchName,  
    [out] ULONG32  *pcchName,  
    [out, size_is(cchName), length_is(*pcchName)]  
        WCHAR      szName[]  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="383ca-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="383ca-105">Parameters</span></span>  

 `cchName`  
 <span data-ttu-id="383ca-106">окне Размер строкового буфера, в котором будет храниться описание.</span><span class="sxs-lookup"><span data-stu-id="383ca-106">[in] The size of the string buffer that will store the description.</span></span>  
  
 `pcchName`  
 <span data-ttu-id="383ca-107">заполняет Указатель на число байтов, возвращенных в буфере строк.</span><span class="sxs-lookup"><span data-stu-id="383ca-107">[out] A pointer to the number of bytes returned in the string buffer.</span></span>  
  
 `szName`  
 <span data-ttu-id="383ca-108">заполняет Строковый буфер, содержащий описание MDA.</span><span class="sxs-lookup"><span data-stu-id="383ca-108">[out] A string buffer containing the description of the MDA.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="383ca-109">Комментарии</span><span class="sxs-lookup"><span data-stu-id="383ca-109">Remarks</span></span>  

 <span data-ttu-id="383ca-110">Строка может иметь нулевую длину.</span><span class="sxs-lookup"><span data-stu-id="383ca-110">The string can be zero in length.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="383ca-111">Требования</span><span class="sxs-lookup"><span data-stu-id="383ca-111">Requirements</span></span>  

 <span data-ttu-id="383ca-112">**Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="383ca-112">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="383ca-113">**Заголовок:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="383ca-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="383ca-114">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="383ca-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="383ca-115">**.NET Framework версии:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="383ca-115">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="383ca-116">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="383ca-116">See also</span></span>

- [<span data-ttu-id="383ca-117">Интерфейс ICorDebugMDA</span><span class="sxs-lookup"><span data-stu-id="383ca-117">ICorDebugMDA Interface</span></span>](icordebugmda-interface.md)
- [<span data-ttu-id="383ca-118">Диагностика ошибок посредством управляемых помощников по отладке</span><span class="sxs-lookup"><span data-stu-id="383ca-118">Diagnosing Errors with Managed Debugging Assistants</span></span>](../../debug-trace-profile/diagnosing-errors-with-managed-debugging-assistants.md)
