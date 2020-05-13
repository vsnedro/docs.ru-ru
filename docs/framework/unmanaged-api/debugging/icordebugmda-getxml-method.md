---
title: Метод ICorDebugMDA::GetXML
ms.date: 03/30/2017
api_name:
- ICorDebugMDA.GetXML
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugMDA::GetXML
helpviewer_keywords:
- ICorDebugMDA::GetXML method [.NET Framework debugging]
- GetXML method [.NET Framework debugging]
ms.assetid: 29746b24-3766-4255-8813-0426c45e73e5
topic_type:
- apiref
ms.openlocfilehash: 219aa27296dffa525bf3e2b836825437a8ce77b0
ms.sourcegitcommit: 488aced39b5f374bc0a139a4993616a54d15baf0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/12/2020
ms.locfileid: "83207658"
---
# <a name="icordebugmdagetxml-method"></a><span data-ttu-id="91684-102">Метод ICorDebugMDA::GetXML</span><span class="sxs-lookup"><span data-stu-id="91684-102">ICorDebugMDA::GetXML Method</span></span>
<span data-ttu-id="91684-103">Возвращает полный XML-поток, связанный с помощником по отладке управляемого кода (MDA), представленным [ICorDebugMDA](icordebugmda-interface.md).</span><span class="sxs-lookup"><span data-stu-id="91684-103">Gets the full XML stream associated with the managed debugging assistant (MDA) represented by [ICorDebugMDA](icordebugmda-interface.md).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="91684-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="91684-104">Syntax</span></span>  
  
```cpp  
HRESULT GetXML (  
    [in] ULONG32   cchName,  
    [out] ULONG32  *pcchName,  
    [out, size_is(cchName), length_is(*pcchName)]  
        WCHAR      szName[]  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="91684-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="91684-105">Parameters</span></span>  
 `cchName`  
 <span data-ttu-id="91684-106">[in] Размер массива `szName`.</span><span class="sxs-lookup"><span data-stu-id="91684-106">[in] The size of the `szName` array.</span></span>  
  
 `pcchName`  
 <span data-ttu-id="91684-107">заполняет Указатель на длину XML-потока.</span><span class="sxs-lookup"><span data-stu-id="91684-107">[out] A pointer to the length of the XML stream.</span></span>  
  
 `szName`  
 <span data-ttu-id="91684-108">заполняет Массив, в котором хранится XML-поток.</span><span class="sxs-lookup"><span data-stu-id="91684-108">[out] An array in which to store the XML stream.</span></span> <span data-ttu-id="91684-109">Массив может быть пустым.</span><span class="sxs-lookup"><span data-stu-id="91684-109">The array may be empty.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="91684-110">Remarks</span><span class="sxs-lookup"><span data-stu-id="91684-110">Remarks</span></span>  
 <span data-ttu-id="91684-111">`GetXML`Метод может повлиять на производительность в зависимости от размера соответствующего потока XML.</span><span class="sxs-lookup"><span data-stu-id="91684-111">The `GetXML` method can potentially affect performance, depending on the size of the associated XML stream.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="91684-112">Требования</span><span class="sxs-lookup"><span data-stu-id="91684-112">Requirements</span></span>  
 <span data-ttu-id="91684-113">**Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="91684-113">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="91684-114">**Заголовок:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="91684-114">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="91684-115">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="91684-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="91684-116">**.NET Framework версии:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="91684-116">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="91684-117">См. также</span><span class="sxs-lookup"><span data-stu-id="91684-117">See also</span></span>

- [<span data-ttu-id="91684-118">Интерфейс ICorDebugMDA</span><span class="sxs-lookup"><span data-stu-id="91684-118">ICorDebugMDA Interface</span></span>](icordebugmda-interface.md)
- [<span data-ttu-id="91684-119">Диагностика ошибок посредством управляемых помощников по отладке</span><span class="sxs-lookup"><span data-stu-id="91684-119">Diagnosing Errors with Managed Debugging Assistants</span></span>](../../debug-trace-profile/diagnosing-errors-with-managed-debugging-assistants.md)
