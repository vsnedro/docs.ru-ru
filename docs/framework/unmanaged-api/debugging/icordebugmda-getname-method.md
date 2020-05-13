---
title: Метод ICorDebugMDA::GetName
ms.date: 03/30/2017
api_name:
- ICorDebugMDA.GetName
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugMDA::GetName
helpviewer_keywords:
- ICorDebugMDA::GetName method [.NET Framework debugging]
- GetName method, ICorDebugMDA interface [.NET Framework debugging]
ms.assetid: 885bf5e8-00b7-4cd7-9d8d-e720d47918c4
topic_type:
- apiref
ms.openlocfilehash: 6a6769265a2e140f1fa001bb8240bc5d4bd76018
ms.sourcegitcommit: 488aced39b5f374bc0a139a4993616a54d15baf0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/12/2020
ms.locfileid: "83213677"
---
# <a name="icordebugmdagetname-method"></a><span data-ttu-id="68b7c-102">Метод ICorDebugMDA::GetName</span><span class="sxs-lookup"><span data-stu-id="68b7c-102">ICorDebugMDA::GetName Method</span></span>
<span data-ttu-id="68b7c-103">Возвращает строку, содержащую имя помощника по отладке управляемого кода (MDA), представленного [ICorDebugMDA](icordebugmda-interface.md).</span><span class="sxs-lookup"><span data-stu-id="68b7c-103">Gets a string containing the name of the managed debugging assistant (MDA) represented by [ICorDebugMDA](icordebugmda-interface.md).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="68b7c-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="68b7c-104">Syntax</span></span>  
  
```cpp  
HRESULT GetName (  
    [in] ULONG32   cchName,  
    [out] ULONG32  *pcchName,  
    [out, size_is(cchName), length_is(*pcchName)]  
        WCHAR      szName[]  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="68b7c-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="68b7c-105">Parameters</span></span>  
 `cchName`  
 <span data-ttu-id="68b7c-106">[in] Размер массива `szName`.</span><span class="sxs-lookup"><span data-stu-id="68b7c-106">[in] The size of the `szName` array.</span></span>  
  
 `pcchName`  
 <span data-ttu-id="68b7c-107">заполняет Указатель на длину имени.</span><span class="sxs-lookup"><span data-stu-id="68b7c-107">[out] A pointer to the length of the name.</span></span>  
  
 `szName`  
 <span data-ttu-id="68b7c-108">заполняет Массив, в котором сохраняется имя.</span><span class="sxs-lookup"><span data-stu-id="68b7c-108">[out] An array in which to store the name.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="68b7c-109">Remarks</span><span class="sxs-lookup"><span data-stu-id="68b7c-109">Remarks</span></span>  
 <span data-ttu-id="68b7c-110">Имена MDA являются уникальными значениями.</span><span class="sxs-lookup"><span data-stu-id="68b7c-110">MDA names are unique values.</span></span> <span data-ttu-id="68b7c-111">Этот `GetName` метод является удобной альтернативой производительности для получения XML-потока и извлечения имени из потока на основе схемы.</span><span class="sxs-lookup"><span data-stu-id="68b7c-111">The `GetName` method is a convenient performance alternative to getting the XML stream and extracting the name from the stream based on the schema.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="68b7c-112">Требования</span><span class="sxs-lookup"><span data-stu-id="68b7c-112">Requirements</span></span>  
 <span data-ttu-id="68b7c-113">**Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="68b7c-113">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="68b7c-114">**Заголовок:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="68b7c-114">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="68b7c-115">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="68b7c-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="68b7c-116">**.NET Framework версии:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="68b7c-116">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="68b7c-117">См. также</span><span class="sxs-lookup"><span data-stu-id="68b7c-117">See also</span></span>

- [<span data-ttu-id="68b7c-118">Интерфейс ICorDebugMDA</span><span class="sxs-lookup"><span data-stu-id="68b7c-118">ICorDebugMDA Interface</span></span>](icordebugmda-interface.md)
- [<span data-ttu-id="68b7c-119">Диагностика ошибок посредством управляемых помощников по отладке</span><span class="sxs-lookup"><span data-stu-id="68b7c-119">Diagnosing Errors with Managed Debugging Assistants</span></span>](../../debug-trace-profile/diagnosing-errors-with-managed-debugging-assistants.md)
