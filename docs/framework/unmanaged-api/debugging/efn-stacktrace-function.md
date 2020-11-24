---
title: Функция _EFN_StackTrace
ms.date: 03/30/2017
api_name:
- _EFN_StackTrace
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- _EFN_StackTrace
helpviewer_keywords:
- _EFN_StackTrace function [.NET Framework debugging]
ms.assetid: caea7754-867c-4360-a65c-5ced4408fd9d
topic_type:
- apiref
ms.openlocfilehash: 9b7624c2902d17e437cda9a0a84ddf288323b577
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/24/2020
ms.locfileid: "95676196"
---
# <a name="_efn_stacktrace-function"></a><span data-ttu-id="7199d-102">\_ЕФН \_ StackTrace, функция</span><span class="sxs-lookup"><span data-stu-id="7199d-102">\_EFN\_StackTrace Function</span></span>

<span data-ttu-id="7199d-103">Предоставляет текстовое представление трассировки управляемого стека и массив записей `CONTEXT`, по одной для каждого перехода между неуправляемым и управляемым кодом.</span><span class="sxs-lookup"><span data-stu-id="7199d-103">Provides a text representation of a managed stack trace and an array of `CONTEXT` records, one for each transition between unmanaged and managed code.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7199d-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="7199d-104">Syntax</span></span>  
  
```cpp  
HRESULT CALLBACK _EFN_StackTrace(  
    [in]  PDEBUG_CLIENT  Client,  
    [out] WCHAR          wszTextOut[],  
    [out] size_t         *puiTextLength,  
    [out] LPVOID         pTransitionContexts,  
    [out] size_t         *puiTransitionContextCount,  
    [in]  size_t         uiSizeOfContext,  
    [in]  DWORD          Flags  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="7199d-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="7199d-105">Parameters</span></span>  

 `Client`  
 <span data-ttu-id="7199d-106">окне Отлаживаемый клиент.</span><span class="sxs-lookup"><span data-stu-id="7199d-106">[in] The client being debugged.</span></span>  
  
 `wszTextOut`  
 <span data-ttu-id="7199d-107">заполняет Текстовое представление трассировки стека.</span><span class="sxs-lookup"><span data-stu-id="7199d-107">[out] The text representation of the stack trace.</span></span>  
  
 `puiTextLength`  
 <span data-ttu-id="7199d-108">заполняет Указатель на число символов в `wszTextOut` .</span><span class="sxs-lookup"><span data-stu-id="7199d-108">[out] A pointer to the number of characters in `wszTextOut`.</span></span>  
  
 `pTransitionContexts`  
 <span data-ttu-id="7199d-109">заполняет Массив контекстов перехода.</span><span class="sxs-lookup"><span data-stu-id="7199d-109">[out] The array of transition contexts.</span></span>  
  
 `puiTransitionContextCount`  
 <span data-ttu-id="7199d-110">заполняет Указатель на число контекстов перехода в массиве.</span><span class="sxs-lookup"><span data-stu-id="7199d-110">[out] A pointer to the number of transition contexts in the array.</span></span>  
  
 `uiSizeOfContext`  
 <span data-ttu-id="7199d-111">окне Размер структуры контекста.</span><span class="sxs-lookup"><span data-stu-id="7199d-111">[in] The size of the context structure.</span></span>  
  
 `Flags`  
 <span data-ttu-id="7199d-112">окне Задайте значение 0 или SOS_STACKTRACE_SHOWADDRESSES (0x01) для отображения регистра EBP и указателя ввода стека (ESP) перед каждой `module!functionname` строкой.</span><span class="sxs-lookup"><span data-stu-id="7199d-112">[in] Set to either 0 or SOS_STACKTRACE_SHOWADDRESSES (0x01) to show the EBP register and the enter stack pointer (ESP) in front of each `module!functionname` line.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="7199d-113">Комментарии</span><span class="sxs-lookup"><span data-stu-id="7199d-113">Remarks</span></span>  

 <span data-ttu-id="7199d-114">`_EFN_StackTrace`Структуру можно вызвать из программного интерфейса WinDbg.</span><span class="sxs-lookup"><span data-stu-id="7199d-114">The `_EFN_StackTrace` structure can be called from a WinDbg programmatic interface.</span></span> <span data-ttu-id="7199d-115">Параметры используются следующим образом.</span><span class="sxs-lookup"><span data-stu-id="7199d-115">Parameters are used as follows:</span></span>  
  
- <span data-ttu-id="7199d-116">Если значение `wszTextOut` равно NULL и не равно `puiTextLength` null, функция возвращает длину строки в `puiTextLength` .</span><span class="sxs-lookup"><span data-stu-id="7199d-116">If `wszTextOut` is null and `puiTextLength` is not null, the function returns the string length in `puiTextLength`.</span></span>  
  
- <span data-ttu-id="7199d-117">Если `wszTextOut` параметр не равен null, функция сохраняет текст в `wszTextOut` расположении, указанном параметром `puiTextLength` .</span><span class="sxs-lookup"><span data-stu-id="7199d-117">If `wszTextOut` is not null, the function stores text in `wszTextOut` up to the location indicated by `puiTextLength`.</span></span> <span data-ttu-id="7199d-118">Он возвращает значение, если в буфере достаточно места, или возвращает E_OUTOFMEMORY, если буфер недостаточно длинный.</span><span class="sxs-lookup"><span data-stu-id="7199d-118">It returns successfully if there was enough room in the buffer, or returns E_OUTOFMEMORY if the buffer was not long enough.</span></span>  
  
- <span data-ttu-id="7199d-119">Часть перехода функции игнорируется, если `pTransitionContexts` и `puiTransitionContextCount` равны NULL.</span><span class="sxs-lookup"><span data-stu-id="7199d-119">The transition portion of the function is ignored if `pTransitionContexts` and `puiTransitionContextCount` are both null.</span></span> <span data-ttu-id="7199d-120">В этом случае функция предоставляет вызывающим объектам текстовые выходные данные только имен функций.</span><span class="sxs-lookup"><span data-stu-id="7199d-120">In this case, the function provides callers with text output of only the function names.</span></span>  
  
- <span data-ttu-id="7199d-121">Если `pTransitionContexts` параметр имеет значение NULL и не равен `puiTransitionContextCount` null, функция возвращает необходимое число контекстных записей в `puiTransitionContextCount` .</span><span class="sxs-lookup"><span data-stu-id="7199d-121">If `pTransitionContexts` is null and `puiTransitionContextCount` is not null, the function returns the necessary number of context entries in `puiTransitionContextCount`.</span></span>  
  
- <span data-ttu-id="7199d-122">Если `pTransitionContexts` параметр не равен null, функция обрабатывает ее как массив структур с длиной `puiTransitionContextCount` .</span><span class="sxs-lookup"><span data-stu-id="7199d-122">If `pTransitionContexts` is not null, the function treats it as an array of structures of length `puiTransitionContextCount`.</span></span> <span data-ttu-id="7199d-123">Размер структуры определяется параметром `uiSizeOfContext` и должен быть размером [симплеконтекст](stacktrace-simplecontext-structure.md) или `CONTEXT` для архитектуры.</span><span class="sxs-lookup"><span data-stu-id="7199d-123">The structure size is given by `uiSizeOfContext`, and must be the size of [SimpleContext](stacktrace-simplecontext-structure.md) or `CONTEXT` for the architecture.</span></span>  
  
- <span data-ttu-id="7199d-124">`wszTextOut` записывается в следующем формате:</span><span class="sxs-lookup"><span data-stu-id="7199d-124">`wszTextOut` is written in the following format:</span></span>  
  
    ```output  
    "<ModuleName>!<Function Name>[+<offset in hex>]  
    ...  
    (TRANSITION)  
    ..."  
    ```  
  
- <span data-ttu-id="7199d-125">Если смещение в шестнадцатеричном формате имеет значение 0x0, смещение не записывается.</span><span class="sxs-lookup"><span data-stu-id="7199d-125">If the offset in hex is 0x0, no offset is written.</span></span>  
  
- <span data-ttu-id="7199d-126">Если в текущем потоке нет управляемого кода, функция возвращает SOS_E_NOMANAGEDCODE.</span><span class="sxs-lookup"><span data-stu-id="7199d-126">If there is no managed code on the thread currently in context, the function returns SOS_E_NOMANAGEDCODE.</span></span>  
  
- <span data-ttu-id="7199d-127">`Flags`Параметр имеет значение 0 или SOS_STACKTRACE_SHOWADDRESSES, чтобы видеть ebp и ESP в начале каждой `module!functionname` строки.</span><span class="sxs-lookup"><span data-stu-id="7199d-127">The `Flags` parameter is either 0 or SOS_STACKTRACE_SHOWADDRESSES to see EBP and ESP in front of each `module!functionname` line.</span></span> <span data-ttu-id="7199d-128">По умолчанию это 0.</span><span class="sxs-lookup"><span data-stu-id="7199d-128">By default, it is 0.</span></span>  
  
    ```cpp  
    #define SOS_STACKTRACE_SHOWADDRESSES   0x00000001  
    ```  
  
## <a name="requirements"></a><span data-ttu-id="7199d-129">Требования</span><span class="sxs-lookup"><span data-stu-id="7199d-129">Requirements</span></span>  

 <span data-ttu-id="7199d-130">**Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="7199d-130">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="7199d-131">**Заголовок:** SOS_Stacktrace. h</span><span class="sxs-lookup"><span data-stu-id="7199d-131">**Header:** SOS_Stacktrace.h</span></span>  
  
 <span data-ttu-id="7199d-132">**.NET Framework версии:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="7199d-132">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7199d-133">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="7199d-133">See also</span></span>

- [<span data-ttu-id="7199d-134">Глобальные статические функции отладки</span><span class="sxs-lookup"><span data-stu-id="7199d-134">Debugging Global Static Functions</span></span>](debugging-global-static-functions.md)
