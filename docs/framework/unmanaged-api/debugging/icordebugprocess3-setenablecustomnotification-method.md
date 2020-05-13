---
title: Метод ICorDebugProcess3::SetEnableCustomNotification
ms.date: 03/30/2017
api_name:
- ICorDebugProcess3.SetEnableCustomNotification Method
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugProcess3::SetEnableCustomNotification
helpviewer_keywords:
- ICorDebugProcess3::SetEnableCustomNotification method [.NET Framework debugging]
- SetEnableCustomNotification method [.NET Framework debugging]
ms.assetid: afd88ee9-2589-4461-a75a-9b6fe55a2525
topic_type:
- apiref
ms.openlocfilehash: 523d9665ffd2637a0e856d74d4d3b3838cb5e83c
ms.sourcegitcommit: 488aced39b5f374bc0a139a4993616a54d15baf0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/12/2020
ms.locfileid: "83212130"
---
# <a name="icordebugprocess3setenablecustomnotification-method"></a><span data-ttu-id="412ed-102">Метод ICorDebugProcess3::SetEnableCustomNotification</span><span class="sxs-lookup"><span data-stu-id="412ed-102">ICorDebugProcess3::SetEnableCustomNotification Method</span></span>
<span data-ttu-id="412ed-103">Включает и отключает настраиваемые уведомления отладчика указанного типа.</span><span class="sxs-lookup"><span data-stu-id="412ed-103">Enables and disables custom debugger notifications of the specified type.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="412ed-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="412ed-104">Syntax</span></span>  
  
```cpp  
HRESULT SetEnableCustomNotification(ICorDebugClass * pClass,  
                                    BOOL fEnable);  
```  
  
## <a name="parameters"></a><span data-ttu-id="412ed-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="412ed-105">Parameters</span></span>  
 `pClass`  
 <span data-ttu-id="412ed-106">окне Тип, указывающий пользовательские уведомления отладчика.</span><span class="sxs-lookup"><span data-stu-id="412ed-106">[in] The type that specifies custom debugger notifications.</span></span>  
  
 `fEnable`  
 <span data-ttu-id="412ed-107">[входные] `true` для включения настраиваемых уведомлений отладчика; `false`для отключения уведомлений.</span><span class="sxs-lookup"><span data-stu-id="412ed-107">[in] `true` to enable custom debugger notifications; `false` to disable notifications.</span></span> <span data-ttu-id="412ed-108">Значение по умолчанию — `false`.</span><span class="sxs-lookup"><span data-stu-id="412ed-108">The default value is `false`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="412ed-109">Remarks</span><span class="sxs-lookup"><span data-stu-id="412ed-109">Remarks</span></span>  
 <span data-ttu-id="412ed-110">Если параметр `fEnable` имеет значение `true` , вызовы <xref:System.Diagnostics.Debugger.NotifyOfCrossThreadDependency%2A?displayProperty=nameWithType> метода активируют обратный вызов [ICorDebugManagedCallback3:: CustomNotification](icordebugmanagedcallback3-customnotification-method.md) .</span><span class="sxs-lookup"><span data-stu-id="412ed-110">When `fEnable` is set to `true`, calls to the <xref:System.Diagnostics.Debugger.NotifyOfCrossThreadDependency%2A?displayProperty=nameWithType> method trigger an [ICorDebugManagedCallback3::CustomNotification](icordebugmanagedcallback3-customnotification-method.md) callback.</span></span> <span data-ttu-id="412ed-111">По умолчанию уведомления отключены. Поэтому в отладчике должны быть указаны все типы уведомлений, о которых он знает, и требуется его обработку.</span><span class="sxs-lookup"><span data-stu-id="412ed-111">Notifications are disabled by default; therefore, the debugger must specify any notification types it knows about and wants to handle.</span></span> <span data-ttu-id="412ed-112">Так как класс [ICorDebugClass](icordebug-interface.md) ограничивается доменом приложения, отладчик должен вызвать `SetEnableCustomNotification` для каждого домена приложения в процессе, если он хочет получить уведомление во всем процессе.</span><span class="sxs-lookup"><span data-stu-id="412ed-112">Because the [ICorDebugClass](icordebug-interface.md) class is scoped by application domain, the debugger must call `SetEnableCustomNotification` for every application domain in the process if it wants to receive the notification across the entire process.</span></span>  
  
 <span data-ttu-id="412ed-113">Начиная с .NET Framework 4, единственным поддерживаемым уведомлением является уведомление о зависимости между потоками.</span><span class="sxs-lookup"><span data-stu-id="412ed-113">Starting with the .NET Framework 4, the only supported notification is a cross-thread dependency notification.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="412ed-114">Требования</span><span class="sxs-lookup"><span data-stu-id="412ed-114">Requirements</span></span>  
 <span data-ttu-id="412ed-115">**Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="412ed-115">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="412ed-116">**Заголовок:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="412ed-116">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="412ed-117">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="412ed-117">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="412ed-118">**.NET Framework версии:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="412ed-118">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="412ed-119">См. также</span><span class="sxs-lookup"><span data-stu-id="412ed-119">See also</span></span>

- [<span data-ttu-id="412ed-120">Интерфейс ICorDebugProcess3</span><span class="sxs-lookup"><span data-stu-id="412ed-120">ICorDebugProcess3 Interface</span></span>](icordebugprocess3-interface.md)
- [<span data-ttu-id="412ed-121">Интерфейсы отладки</span><span class="sxs-lookup"><span data-stu-id="412ed-121">Debugging Interfaces</span></span>](debugging-interfaces.md)
- [<span data-ttu-id="412ed-122">Отладка</span><span class="sxs-lookup"><span data-stu-id="412ed-122">Debugging</span></span>](index.md)
