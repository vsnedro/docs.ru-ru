---
title: Функция Ендмесоденумератион (Справочник по неуправляемым API)
description: Функция Ендмесоденумератион завершает последовательность перечисления методов.
ms.date: 11/06/2017
api_name:
- EndMethodEnumeration
api_location:
- WMINet_Utils.dll
api_type:
- DLLExport
f1_keywords:
- EndMethodEnumeration
helpviewer_keywords:
- EndMethodEnumeration function [.NET WMI and performance counters]
topic_type:
- Reference
ms.openlocfilehash: 82f50530967699427d8a00b1c9f518b639273626
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/24/2020
ms.locfileid: "95708066"
---
# <a name="endmethodenumeration-function"></a><span data-ttu-id="1a9e1-103">Функция EndMethodEnumeration</span><span class="sxs-lookup"><span data-stu-id="1a9e1-103">EndMethodEnumeration function</span></span>

<span data-ttu-id="1a9e1-104">Завершает последовательность перечисления, запущенную с вызовом [функции бегинмесоденумератион](beginmethodenumeration.md).</span><span class="sxs-lookup"><span data-stu-id="1a9e1-104">Terminates an enumeration sequence started with a call to the [BeginMethodEnumeration function](beginmethodenumeration.md).</span></span>  

[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]

## <a name="syntax"></a><span data-ttu-id="1a9e1-105">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="1a9e1-105">Syntax</span></span>  
  
```cpp  
HRESULT EndMethodEnumeration (
   [in] int               vFunc,
   [in] IWbemClassObject* ptr
);
```  

## <a name="parameters"></a><span data-ttu-id="1a9e1-106">Параметры</span><span class="sxs-lookup"><span data-stu-id="1a9e1-106">Parameters</span></span>

`vFunc`  
<span data-ttu-id="1a9e1-107">окне Этот параметр не используется.</span><span class="sxs-lookup"><span data-stu-id="1a9e1-107">[in] This parameter is unused.</span></span>

`ptr`  
<span data-ttu-id="1a9e1-108">окне Указатель на экземпляр [ивбемклассобжект](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject) .</span><span class="sxs-lookup"><span data-stu-id="1a9e1-108">[in] A pointer to an [IWbemClassObject](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject) instance.</span></span>

## <a name="return-value"></a><span data-ttu-id="1a9e1-109">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="1a9e1-109">Return value</span></span>

<span data-ttu-id="1a9e1-110">Следующие значения, возвращаемые этой функцией, определены в файле заголовка *вбемкли. h* , или их можно определить как константы в коде:</span><span class="sxs-lookup"><span data-stu-id="1a9e1-110">The following values returned by this function are defined in the *WbemCli.h* header file, or you can define them as constants in your code:</span></span>

|<span data-ttu-id="1a9e1-111">Константа</span><span class="sxs-lookup"><span data-stu-id="1a9e1-111">Constant</span></span>  |<span data-ttu-id="1a9e1-112">Значение</span><span class="sxs-lookup"><span data-stu-id="1a9e1-112">Value</span></span>  |<span data-ttu-id="1a9e1-113">Описание</span><span class="sxs-lookup"><span data-stu-id="1a9e1-113">Description</span></span>  |
|---------|---------|---------|
|`WBEM_E_UNEXPECTED` | <span data-ttu-id="1a9e1-114">0x8004101d</span><span class="sxs-lookup"><span data-stu-id="1a9e1-114">0x8004101d</span></span> | <span data-ttu-id="1a9e1-115">Произошла внутренняя ошибка.</span><span class="sxs-lookup"><span data-stu-id="1a9e1-115">An internal error occurred.</span></span> |
|`WBEM_S_NO_ERROR` | <span data-ttu-id="1a9e1-116">0</span><span class="sxs-lookup"><span data-stu-id="1a9e1-116">0</span></span> | <span data-ttu-id="1a9e1-117">Вызов функции выполнен успешно.</span><span class="sxs-lookup"><span data-stu-id="1a9e1-117">The function call was successful.</span></span>  |
  
## <a name="remarks"></a><span data-ttu-id="1a9e1-118">Комментарии</span><span class="sxs-lookup"><span data-stu-id="1a9e1-118">Remarks</span></span>

<span data-ttu-id="1a9e1-119">Эта функция заключает в оболочку вызов метода [ивбемклассобжект:: ендмесоденумератион](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemclassobject-endmethodenumeration) .</span><span class="sxs-lookup"><span data-stu-id="1a9e1-119">This function wraps a call to the [IWbemClassObject::EndMethodEnumeration](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemclassobject-endmethodenumeration) method.</span></span>

<span data-ttu-id="1a9e1-120">Вызывающий объект начинает последовательность перечисления с помощью [функции бегинмесоденумератион](beginmethodenumeration.md), а затем вызывает [функцию некстмесод](nextmethod.md ), пока метод не вернет значение `WBEM_S_NO_MORE_DATA` .</span><span class="sxs-lookup"><span data-stu-id="1a9e1-120">The caller begins the enumeration sequence using [BeginMethodEnumeration function](beginmethodenumeration.md), and then calls the [NextMethod function](nextmethod.md )until the method  returns `WBEM_S_NO_MORE_DATA`.</span></span> <span data-ttu-id="1a9e1-121">Вызывающий объект, по желанию, завершает последовательность путем вызова `EndMethodEnumeration` .</span><span class="sxs-lookup"><span data-stu-id="1a9e1-121">The caller optionally finishes the sequence by calling `EndMethodEnumeration`.</span></span> <span data-ttu-id="1a9e1-122">Вызывающий объект может завершить перечисление раньше, вызвав `EndMethodEnumeration` в любое время.</span><span class="sxs-lookup"><span data-stu-id="1a9e1-122">The caller may terminate the enumeration early by calling `EndMethodEnumeration` at any time.</span></span>

## <a name="requirements"></a><span data-ttu-id="1a9e1-123">Требования</span><span class="sxs-lookup"><span data-stu-id="1a9e1-123">Requirements</span></span>  

 <span data-ttu-id="1a9e1-124">**Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="1a9e1-124">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="1a9e1-125">**Заголовок:** WMINet_Utils. idl</span><span class="sxs-lookup"><span data-stu-id="1a9e1-125">**Header:** WMINet_Utils.idl</span></span>  
  
 <span data-ttu-id="1a9e1-126">**.NET Framework версии:**[!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span><span class="sxs-lookup"><span data-stu-id="1a9e1-126">**.NET Framework Versions:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1a9e1-127">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="1a9e1-127">See also</span></span>

- [<span data-ttu-id="1a9e1-128">WMI и счетчики производительности (справочник по неуправляемым API)</span><span class="sxs-lookup"><span data-stu-id="1a9e1-128">WMI and Performance Counters (Unmanaged API Reference)</span></span>](index.md)
