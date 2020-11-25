---
title: Функция Жетдемултиплекседстуб (Справочник по неуправляемым API)
description: Функция Жетдемултиплекседстуб создает приемник сервера пересылки объектов, чтобы помочь клиенту получать асинхронные вызовы из управления Windows.
ms.date: 11/06/2017
api_name:
- GetDemultiplexedStub
api_location:
- WMINet_Utils.dll
api_type:
- DLLExport
f1_keywords:
- GetDemultiplexedStub
helpviewer_keywords:
- GetDemultiplexedStub function [.NET WMI and performance counters]
topic_type:
- Reference
ms.openlocfilehash: f8f9b56268168bb16c476a9366facd17e8ac44e5
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/24/2020
ms.locfileid: "95730634"
---
# <a name="getdemultiplexedstub-function"></a><span data-ttu-id="456fe-103">Функция GetDemultiplexedStub</span><span class="sxs-lookup"><span data-stu-id="456fe-103">GetDemultiplexedStub function</span></span>

<span data-ttu-id="456fe-104">Создает приемник переадресации объекта, который помогает клиенту получать асинхронные вызовы из службы управления Windows.</span><span class="sxs-lookup"><span data-stu-id="456fe-104">Creates an object forwarder sink to assist a client in receiving asynchronous calls from Windows Management.</span></span>
  
[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]
  
## <a name="syntax"></a><span data-ttu-id="456fe-105">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="456fe-105">Syntax</span></span>  
  
```cpp  
HRESULT GetDemultiplexedStub (
   [in] IUnknown*    pObject,
   [in] boolean      isLocal,
   [out] IUnknown**  ppObject
);
```  

## <a name="parameters"></a><span data-ttu-id="456fe-106">Параметры</span><span class="sxs-lookup"><span data-stu-id="456fe-106">Parameters</span></span>

`pObject`  
<span data-ttu-id="456fe-107">окне Указатель на внутрипроцессный клиентскую реализацию [ивбемобжектсинк](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemobjectsink).</span><span class="sxs-lookup"><span data-stu-id="456fe-107">[in] A pointer to the client's in-process implementation of [IWbemObjectSink](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemobjectsink).</span></span>

`isLocal`  
<span data-ttu-id="456fe-108">окне Флаг, указывающий, является ли событие локальным ( `true` ); в противном случае — значение `false` .</span><span class="sxs-lookup"><span data-stu-id="456fe-108">[in] A flag that indicates whether the event is local (`true`); otherwise, `false`.</span></span>

`ppObject`  
<span data-ttu-id="456fe-109">заполняет Приемник объекта сервера пересылки, который помогает клиенту получать асинхронные вызовы из управления Windows.</span><span class="sxs-lookup"><span data-stu-id="456fe-109">[out] A object forwarder sink to assist a client in receiving asynchronous calls from Windows Management.</span></span>

## <a name="return-value"></a><span data-ttu-id="456fe-110">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="456fe-110">Return value</span></span>

<span data-ttu-id="456fe-111">Если функция выполнена, возвращаемое значение равно `S_OK` (0).</span><span class="sxs-lookup"><span data-stu-id="456fe-111">If the function succeeds, the return value is `S_OK` (0).</span></span>

<span data-ttu-id="456fe-112">Если функция завершается ошибкой, возвращаемое значение является ненулевым кодом ошибки.</span><span class="sxs-lookup"><span data-stu-id="456fe-112">If the function fails, the return value is a non-zero error code.</span></span> <span data-ttu-id="456fe-113">Чтобы получить расширенные сведения об ошибке, вызовите функцию [жетерроринфо](geterrorinfo.md) .</span><span class="sxs-lookup"><span data-stu-id="456fe-113">To get extended error information, call the [GetErrorInfo](geterrorinfo.md) function.</span></span>

## <a name="requirements"></a><span data-ttu-id="456fe-114">Требования</span><span class="sxs-lookup"><span data-stu-id="456fe-114">Requirements</span></span>  

 <span data-ttu-id="456fe-115">**Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="456fe-115">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="456fe-116">**Заголовок:** WMINet_Utils. idl</span><span class="sxs-lookup"><span data-stu-id="456fe-116">**Header:** WMINet_Utils.idl</span></span>  
  
 <span data-ttu-id="456fe-117">**.NET Framework версии:**[!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span><span class="sxs-lookup"><span data-stu-id="456fe-117">**.NET Framework Versions:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="456fe-118">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="456fe-118">See also</span></span>

- [<span data-ttu-id="456fe-119">WMI и счетчики производительности (справочник по неуправляемым API)</span><span class="sxs-lookup"><span data-stu-id="456fe-119">WMI and Performance Counters (Unmanaged API Reference)</span></span>](index.md)
