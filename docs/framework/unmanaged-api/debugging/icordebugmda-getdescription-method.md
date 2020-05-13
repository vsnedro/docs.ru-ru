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
ms.openlocfilehash: 522e992e6d7e9a64f7590bbec0e9106e0e1f8f47
ms.sourcegitcommit: 488aced39b5f374bc0a139a4993616a54d15baf0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/12/2020
ms.locfileid: "83212143"
---
# <a name="icordebugmdagetdescription-method"></a><span data-ttu-id="d96db-102">Метод ICorDebugMDA::GetDescription</span><span class="sxs-lookup"><span data-stu-id="d96db-102">ICorDebugMDA::GetDescription Method</span></span>
<span data-ttu-id="d96db-103">Возвращает строку, содержащую описание помощника по отладке управляемого кода (MDA), представленного [ICorDebugMDA](icordebugmda-interface.md).</span><span class="sxs-lookup"><span data-stu-id="d96db-103">Gets a string containing the description of the managed debugging assistant (MDA) represented by [ICorDebugMDA](icordebugmda-interface.md).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d96db-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="d96db-104">Syntax</span></span>  
  
```cpp  
HRESULT GetDescription (  
    [in] ULONG32   cchName,  
    [out] ULONG32  *pcchName,  
    [out, size_is(cchName), length_is(*pcchName)]  
        WCHAR      szName[]  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="d96db-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="d96db-105">Parameters</span></span>  
 `cchName`  
 <span data-ttu-id="d96db-106">окне Размер строкового буфера, в котором будет храниться описание.</span><span class="sxs-lookup"><span data-stu-id="d96db-106">[in] The size of the string buffer that will store the description.</span></span>  
  
 `pcchName`  
 <span data-ttu-id="d96db-107">заполняет Указатель на число байтов, возвращенных в буфере строк.</span><span class="sxs-lookup"><span data-stu-id="d96db-107">[out] A pointer to the number of bytes returned in the string buffer.</span></span>  
  
 `szName`  
 <span data-ttu-id="d96db-108">заполняет Строковый буфер, содержащий описание MDA.</span><span class="sxs-lookup"><span data-stu-id="d96db-108">[out] A string buffer containing the description of the MDA.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="d96db-109">Remarks</span><span class="sxs-lookup"><span data-stu-id="d96db-109">Remarks</span></span>  
 <span data-ttu-id="d96db-110">Строка может иметь нулевую длину.</span><span class="sxs-lookup"><span data-stu-id="d96db-110">The string can be zero in length.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="d96db-111">Требования</span><span class="sxs-lookup"><span data-stu-id="d96db-111">Requirements</span></span>  
 <span data-ttu-id="d96db-112">**Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="d96db-112">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="d96db-113">**Заголовок:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="d96db-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="d96db-114">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="d96db-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="d96db-115">**.NET Framework версии:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="d96db-115">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d96db-116">См. также</span><span class="sxs-lookup"><span data-stu-id="d96db-116">See also</span></span>

- [<span data-ttu-id="d96db-117">Интерфейс ICorDebugMDA</span><span class="sxs-lookup"><span data-stu-id="d96db-117">ICorDebugMDA Interface</span></span>](icordebugmda-interface.md)
- [<span data-ttu-id="d96db-118">Диагностика ошибок посредством управляемых помощников по отладке</span><span class="sxs-lookup"><span data-stu-id="d96db-118">Diagnosing Errors with Managed Debugging Assistants</span></span>](../../debug-trace-profile/diagnosing-errors-with-managed-debugging-assistants.md)
