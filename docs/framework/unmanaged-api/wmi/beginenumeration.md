---
title: Функция BeginEnumeration (Справочник по неуправляемым API)
description: Функция BeginEnumeration Сбрасывает перечислитель до начала перечисления
ms.date: 11/06/2017
api_name:
- BeginEnumeration
api_location:
- WMINet_Utils.dll
api_type:
- DLLExport
f1_keywords:
- BeginEnumeration
helpviewer_keywords:
- BeginEnumeration function [.NET WMI and performance counters]
topic_type:
- Reference
ms.openlocfilehash: 6057526ddbe2efed65f8569e829c35524829e43e
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/24/2020
ms.locfileid: "95708222"
---
# <a name="beginenumeration-function"></a><span data-ttu-id="5b831-103">Функция BeginEnumeration</span><span class="sxs-lookup"><span data-stu-id="5b831-103">BeginEnumeration function</span></span>

<span data-ttu-id="5b831-104">Сбрасывает перечислитель обратно в начало перечисления.</span><span class="sxs-lookup"><span data-stu-id="5b831-104">Resets an enumerator back to the beginning of the enumeration.</span></span>  

[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]
  
## <a name="syntax"></a><span data-ttu-id="5b831-105">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="5b831-105">Syntax</span></span>  
  
```cpp  
HRESULT BeginEnumeration (
   [in] int               vFunc,
   [in] IWbemClassObject* ptr,
   [in] LONG              lEnumFlags
);
```  

## <a name="parameters"></a><span data-ttu-id="5b831-106">Параметры</span><span class="sxs-lookup"><span data-stu-id="5b831-106">Parameters</span></span>

`vFunc`\
<span data-ttu-id="5b831-107">окне Этот параметр не используется.</span><span class="sxs-lookup"><span data-stu-id="5b831-107">[in] This parameter is unused.</span></span>

`ptr`\
<span data-ttu-id="5b831-108">окне Указатель на экземпляр [ивбемклассобжект](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject) .</span><span class="sxs-lookup"><span data-stu-id="5b831-108">[in] A pointer to an [IWbemClassObject](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject) instance.</span></span>

`lEnumFlags`\
<span data-ttu-id="5b831-109">окне Побитовое сочетание флагов или значений, описанных в разделе « [Примечания](#remarks) », которое управляет свойствами, входящими в перечисление.</span><span class="sxs-lookup"><span data-stu-id="5b831-109">[in] A bitwise combination of the flags or values described in the [Remarks](#remarks) section that controls the properties included in the enumeration.</span></span>

## <a name="return-value"></a><span data-ttu-id="5b831-110">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="5b831-110">Return value</span></span>

<span data-ttu-id="5b831-111">Следующие значения, возвращаемые этой функцией, определены в файле заголовка *вбемкли. h* , или их можно определить как константы в коде:</span><span class="sxs-lookup"><span data-stu-id="5b831-111">The following values returned by this function are defined in the *WbemCli.h* header file, or you can define them as constants in your code:</span></span>

|<span data-ttu-id="5b831-112">Константа</span><span class="sxs-lookup"><span data-stu-id="5b831-112">Constant</span></span>  |<span data-ttu-id="5b831-113">Значение</span><span class="sxs-lookup"><span data-stu-id="5b831-113">Value</span></span>  |<span data-ttu-id="5b831-114">Описание</span><span class="sxs-lookup"><span data-stu-id="5b831-114">Description</span></span>  |
|---------|---------|---------|
|`WBEM_E_INVALID_PARAMETER` | <span data-ttu-id="5b831-115">0x80041008</span><span class="sxs-lookup"><span data-stu-id="5b831-115">0x80041008</span></span> | <span data-ttu-id="5b831-116">Недопустимое сочетание флагов в `lEnumFlags` параметре или указан недопустимый аргумент.</span><span class="sxs-lookup"><span data-stu-id="5b831-116">The combination of flags in `lEnumFlags` is invalid, or an invalid argument was specified.</span></span> |
|`WBEM_E_UNEXPECTED` | <span data-ttu-id="5b831-117">0x8004101d</span><span class="sxs-lookup"><span data-stu-id="5b831-117">0x8004101d</span></span> | <span data-ttu-id="5b831-118">Второй вызов `BeginEnumeration` был выполнен без промежуточного вызова [`EndEnumeration`](endenumeration.md) .</span><span class="sxs-lookup"><span data-stu-id="5b831-118">A second call to `BeginEnumeration` was made without an intervening call to [`EndEnumeration`](endenumeration.md).</span></span> |
|`WBEM_E_OUT_OF_MEMORY` | <span data-ttu-id="5b831-119">0x80041006</span><span class="sxs-lookup"><span data-stu-id="5b831-119">0x80041006</span></span> | <span data-ttu-id="5b831-120">Недостаточно памяти для начала нового перечисления.</span><span class="sxs-lookup"><span data-stu-id="5b831-120">Not enough memory is available to begin a new enumeration.</span></span> |
|`WBEM_S_NO_ERROR` | <span data-ttu-id="5b831-121">0</span><span class="sxs-lookup"><span data-stu-id="5b831-121">0</span></span> | <span data-ttu-id="5b831-122">Вызов функции выполнен успешно.</span><span class="sxs-lookup"><span data-stu-id="5b831-122">The function call was successful.</span></span>  |
  
## <a name="remarks"></a><span data-ttu-id="5b831-123">Комментарии</span><span class="sxs-lookup"><span data-stu-id="5b831-123">Remarks</span></span>

<span data-ttu-id="5b831-124">Эта функция заключает в оболочку вызов метода [ивбемклассобжект:: BeginEnumeration](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject) .</span><span class="sxs-lookup"><span data-stu-id="5b831-124">This function wraps a call to the [IWbemClassObject::BeginEnumeration](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject) method.</span></span>

<span data-ttu-id="5b831-125">Флаги, которые могут быть переданы `lEnumFlags` в качестве аргумента, определяются в файле заголовка *вбемкли. h* или могут быть определены в коде в виде констант.</span><span class="sxs-lookup"><span data-stu-id="5b831-125">The flags that can be passed as the `lEnumFlags` argument are defined in the *WbemCli.h* header file, or you can define them as constants in your code.</span></span>  <span data-ttu-id="5b831-126">Можно объединить один флаг из каждой группы с любым флагом из любой другой группы.</span><span class="sxs-lookup"><span data-stu-id="5b831-126">You can combine one flag from each group with any flag from any other group.</span></span> <span data-ttu-id="5b831-127">Однако флаги из одной и той же группы являются взаимоисключающими.</span><span class="sxs-lookup"><span data-stu-id="5b831-127">However, flags from the same group are mutually exclusive.</span></span>

<span data-ttu-id="5b831-128">**Группа 1**</span><span class="sxs-lookup"><span data-stu-id="5b831-128">**Group 1**</span></span>

|<span data-ttu-id="5b831-129">Константа</span><span class="sxs-lookup"><span data-stu-id="5b831-129">Constant</span></span>  |<span data-ttu-id="5b831-130">Значение</span><span class="sxs-lookup"><span data-stu-id="5b831-130">Value</span></span>  |<span data-ttu-id="5b831-131">Описание</span><span class="sxs-lookup"><span data-stu-id="5b831-131">Description</span></span>  |
|---------|---------|---------|
|`WBEM_FLAG_KEYS_ONLY` | <span data-ttu-id="5b831-132">0x4</span><span class="sxs-lookup"><span data-stu-id="5b831-132">0x4</span></span> | <span data-ttu-id="5b831-133">Включить свойства, которые составляют только ключ.</span><span class="sxs-lookup"><span data-stu-id="5b831-133">Include properties that constitute the key only.</span></span> |
|`WBEM_FLAG_REFS_ONLY` | <span data-ttu-id="5b831-134">0x8</span><span class="sxs-lookup"><span data-stu-id="5b831-134">0x8</span></span> | <span data-ttu-id="5b831-135">Включить свойства, которые являются только ссылками на объекты.</span><span class="sxs-lookup"><span data-stu-id="5b831-135">Include properties that are object references only.</span></span> |

<span data-ttu-id="5b831-136">**Группа 2**</span><span class="sxs-lookup"><span data-stu-id="5b831-136">**Group 2**</span></span>

<span data-ttu-id="5b831-137">Константа</span><span class="sxs-lookup"><span data-stu-id="5b831-137">Constant</span></span>  |<span data-ttu-id="5b831-138">Значение</span><span class="sxs-lookup"><span data-stu-id="5b831-138">Value</span></span>  |<span data-ttu-id="5b831-139">Описание</span><span class="sxs-lookup"><span data-stu-id="5b831-139">Description</span></span>  |
|---------|---------|---------|
|`WBEM_FLAG_SYSTEM_ONLY` | <span data-ttu-id="5b831-140">0x30</span><span class="sxs-lookup"><span data-stu-id="5b831-140">0x30</span></span> | <span data-ttu-id="5b831-141">Ограничьте перечисление только системными свойствами.</span><span class="sxs-lookup"><span data-stu-id="5b831-141">Limit the enumeration to system properties only.</span></span> |
|`WBEM_FLAG_NONSYSTEM_ONLY` | <span data-ttu-id="5b831-142">0x40</span><span class="sxs-lookup"><span data-stu-id="5b831-142">0x40</span></span> | <span data-ttu-id="5b831-143">Включить локальные и распространенные свойства, но исключить системные свойства из перечисления.</span><span class="sxs-lookup"><span data-stu-id="5b831-143">Include local and propagated properties but exclude system properties from the enumeration.</span></span> |

<span data-ttu-id="5b831-144">Для классов:</span><span class="sxs-lookup"><span data-stu-id="5b831-144">For classes:</span></span>

<span data-ttu-id="5b831-145">Константа</span><span class="sxs-lookup"><span data-stu-id="5b831-145">Constant</span></span>  |<span data-ttu-id="5b831-146">Значение</span><span class="sxs-lookup"><span data-stu-id="5b831-146">Value</span></span>  |<span data-ttu-id="5b831-147">Описание</span><span class="sxs-lookup"><span data-stu-id="5b831-147">Description</span></span>  |
|---------|---------|---------|
|`WBEM_FLAG_CLASS_OVERRIDES_ONLY` | <span data-ttu-id="5b831-148">0x100</span><span class="sxs-lookup"><span data-stu-id="5b831-148">0x100</span></span> | <span data-ttu-id="5b831-149">Ограничьте перечисление свойствами, переопределенными в определении класса.</span><span class="sxs-lookup"><span data-stu-id="5b831-149">Limit the enumeration to properties overridden in the class definition.</span></span> |
|`WBEM_FLAG_CLASS_LOCAL_AND_OVERRIDES` | <span data-ttu-id="5b831-150">0x100</span><span class="sxs-lookup"><span data-stu-id="5b831-150">0x100</span></span> | <span data-ttu-id="5b831-151">Ограничьте перечисление свойствами, переопределенными в текущем определении класса, и новыми свойствами, определенными в классе.</span><span class="sxs-lookup"><span data-stu-id="5b831-151">Limit the enumeration to properties overridden in the current class definition and to new properties defined in the class.</span></span> |
| `WBEM_MASK_CLASS_CONDITION` | <span data-ttu-id="5b831-152">0x300</span><span class="sxs-lookup"><span data-stu-id="5b831-152">0x300</span></span> | <span data-ttu-id="5b831-153">Маска (а не флаг), применяемая к `lEnumFlags` значению для проверки того, установлен ли параметр `WBEM_FLAG_CLASS_OVERRIDES_ONLY` или `WBEM_FLAG_CLASS_LOCAL_AND_OVERRIDES` .</span><span class="sxs-lookup"><span data-stu-id="5b831-153">A mask (rather than a flag) to apply against a `lEnumFlags` value to check if either `WBEM_FLAG_CLASS_OVERRIDES_ONLY` or `WBEM_FLAG_CLASS_LOCAL_AND_OVERRIDES` is set.</span></span> |
| `WBEM_FLAG_LOCAL_ONLY` | <span data-ttu-id="5b831-154">0x10</span><span class="sxs-lookup"><span data-stu-id="5b831-154">0x10</span></span> | <span data-ttu-id="5b831-155">Ограничьте перечисление свойствами, которые определены или изменены в самом классе.</span><span class="sxs-lookup"><span data-stu-id="5b831-155">Limit the enumeration to properties that are defined or modified in the class itself.</span></span> |
| `WBEM_FLAG_PROPAGATED_ONLY` |  <span data-ttu-id="5b831-156">0x20</span><span class="sxs-lookup"><span data-stu-id="5b831-156">0x20</span></span> | <span data-ttu-id="5b831-157">Ограничьте перечисление свойствами, унаследованными от базовых классов.</span><span class="sxs-lookup"><span data-stu-id="5b831-157">Limit the enumeration to properties that are inherited from base classes.</span></span> |

<span data-ttu-id="5b831-158">Для экземпляров:</span><span class="sxs-lookup"><span data-stu-id="5b831-158">For instances:</span></span>

<span data-ttu-id="5b831-159">Константа</span><span class="sxs-lookup"><span data-stu-id="5b831-159">Constant</span></span>  |<span data-ttu-id="5b831-160">Значение</span><span class="sxs-lookup"><span data-stu-id="5b831-160">Value</span></span>  |<span data-ttu-id="5b831-161">Описание</span><span class="sxs-lookup"><span data-stu-id="5b831-161">Description</span></span>  |
|---------|---------|---------|
| `WBEM_FLAG_LOCAL_ONLY` | <span data-ttu-id="5b831-162">0x10</span><span class="sxs-lookup"><span data-stu-id="5b831-162">0x10</span></span> | <span data-ttu-id="5b831-163">Ограничьте перечисление свойствами, которые определены или изменены в самом классе.</span><span class="sxs-lookup"><span data-stu-id="5b831-163">Limit the enumeration to properties that are defined or modified in the class itself.</span></span> |
| `WBEM_FLAG_PROPAGATED_ONLY` |  <span data-ttu-id="5b831-164">0x20</span><span class="sxs-lookup"><span data-stu-id="5b831-164">0x20</span></span> | <span data-ttu-id="5b831-165">Ограничьте перечисление свойствами, унаследованными от базовых классов.</span><span class="sxs-lookup"><span data-stu-id="5b831-165">Limit the enumeration to properties that are inherited from base classes.</span></span> |

## <a name="requirements"></a><span data-ttu-id="5b831-166">Требования</span><span class="sxs-lookup"><span data-stu-id="5b831-166">Requirements</span></span>  

 <span data-ttu-id="5b831-167">**Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="5b831-167">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="5b831-168">**Заголовок:** WMINet_Utils. idl</span><span class="sxs-lookup"><span data-stu-id="5b831-168">**Header:** WMINet_Utils.idl</span></span>  
  
 <span data-ttu-id="5b831-169">**.NET Framework версии:**[!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span><span class="sxs-lookup"><span data-stu-id="5b831-169">**.NET Framework Versions:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5b831-170">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="5b831-170">See also</span></span>

- [<span data-ttu-id="5b831-171">WMI и счетчики производительности (справочник по неуправляемым API)</span><span class="sxs-lookup"><span data-stu-id="5b831-171">WMI and Performance Counters (Unmanaged API Reference)</span></span>](index.md)
