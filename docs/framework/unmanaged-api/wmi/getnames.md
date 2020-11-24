---
title: Функция Names (Справочник по неуправляемым интерфейсам API)
description: Функция Names извлекает имена свойств объекта.
ms.date: 11/06/2017
api_name:
- GetNames
api_location:
- WMINet_Utils.dll
api_type:
- DLLExport
f1_keywords:
- GetNames
helpviewer_keywords:
- GetNames function [.NET WMI and performance counters]
topic_type:
- Reference
ms.openlocfilehash: fd889158e61b86f42d88bcf86eda7d816277e6ac
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/24/2020
ms.locfileid: "95687662"
---
# <a name="getnames-function"></a><span data-ttu-id="40ab5-103">Функция GetNames</span><span class="sxs-lookup"><span data-stu-id="40ab5-103">GetNames function</span></span>

<span data-ttu-id="40ab5-104">Получает подмножество имен или все имена свойств объекта.</span><span class="sxs-lookup"><span data-stu-id="40ab5-104">Retrieves either a subset or all of the names of the properties of an object.</span></span>

[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]

## <a name="syntax"></a><span data-ttu-id="40ab5-105">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="40ab5-105">Syntax</span></span>  
  
```cpp  
HRESULT GetNames (
   [in] int                 vFunc,
   [in] IWbemClassObject*   ptr,
   [in] LPCWSTR             wszQualifierName,
   [in] LONG                lFlags,
   [in] VARIANT*            pQualifierValue,
   [out] SAFEARRAY (BSTR)** pstrNames
);
```  

## <a name="parameters"></a><span data-ttu-id="40ab5-106">Параметры</span><span class="sxs-lookup"><span data-stu-id="40ab5-106">Parameters</span></span>

`vFunc`  
<span data-ttu-id="40ab5-107">окне Этот параметр не используется.</span><span class="sxs-lookup"><span data-stu-id="40ab5-107">[in] This parameter is unused.</span></span>

`ptr`  
<span data-ttu-id="40ab5-108">окне Указатель на экземпляр [ивбемклассобжект](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject) .</span><span class="sxs-lookup"><span data-stu-id="40ab5-108">[in] A pointer to an [IWbemClassObject](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject) instance.</span></span>

`wszQualifierName`  
<span data-ttu-id="40ab5-109">окне Указатель на допустимое значение `LPCWSTR` , указывающее имя квалификатора, которое действует как часть фильтра.</span><span class="sxs-lookup"><span data-stu-id="40ab5-109">[in] A pointer to a valid `LPCWSTR` that specifies a qualifier name that operates as part of a filter.</span></span> <span data-ttu-id="40ab5-110">Дополнительные сведения см. в разделе [Примечания](#remarks).</span><span class="sxs-lookup"><span data-stu-id="40ab5-110">For more information, see the [Remarks](#remarks) section.</span></span> <span data-ttu-id="40ab5-111">Этот параметр может иметь значение `null`.</span><span class="sxs-lookup"><span data-stu-id="40ab5-111">This parameter can be `null`.</span></span>

`lFlags`  
<span data-ttu-id="40ab5-112">окне Сочетание битовых полей.</span><span class="sxs-lookup"><span data-stu-id="40ab5-112">[in] A combination of bit fields.</span></span> <span data-ttu-id="40ab5-113">Дополнительные сведения см. в разделе [Примечания](#remarks).</span><span class="sxs-lookup"><span data-stu-id="40ab5-113">For more information, see the [Remarks](#remarks) section.</span></span>

<span data-ttu-id="40ab5-114">`pQualifierValue` окне Указатель на допустимую `VARIANT` структуру, инициализированную значением фильтра.</span><span class="sxs-lookup"><span data-stu-id="40ab5-114">`pQualifierValue` [in] A pointer to a valid `VARIANT` structure initialized to a filter value.</span></span> <span data-ttu-id="40ab5-115">Этот параметр может иметь значение `null`.</span><span class="sxs-lookup"><span data-stu-id="40ab5-115">This parameter can be `null`.</span></span>

`pstrNames`  
<span data-ttu-id="40ab5-116">заполняет `SAFEARRAY` Структура, содержащая имена свойств.</span><span class="sxs-lookup"><span data-stu-id="40ab5-116">[out] A `SAFEARRAY` structure that contains property names.</span></span> <span data-ttu-id="40ab5-117">При входе этот параметр всегда должен быть указателем на `null` .</span><span class="sxs-lookup"><span data-stu-id="40ab5-117">On entry, this parameter must always be a pointer to `null`.</span></span> <span data-ttu-id="40ab5-118">Дополнительные сведения см. в разделе ["Примечания"](#remarks) .</span><span class="sxs-lookup"><span data-stu-id="40ab5-118">See the [Remarks](#remarks) section for more information.</span></span>

## <a name="return-value"></a><span data-ttu-id="40ab5-119">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="40ab5-119">Return value</span></span>

<span data-ttu-id="40ab5-120">Следующие значения, возвращаемые этой функцией, определены в файле заголовка *вбемкли. h* , или их можно определить как константы в коде:</span><span class="sxs-lookup"><span data-stu-id="40ab5-120">The following values returned by this function are defined in the *WbemCli.h* header file, or you can define them as constants in your code:</span></span>

|<span data-ttu-id="40ab5-121">Константа</span><span class="sxs-lookup"><span data-stu-id="40ab5-121">Constant</span></span>  |<span data-ttu-id="40ab5-122">Значение</span><span class="sxs-lookup"><span data-stu-id="40ab5-122">Value</span></span>  |<span data-ttu-id="40ab5-123">Описание</span><span class="sxs-lookup"><span data-stu-id="40ab5-123">Description</span></span>  |
|---------|---------|---------|
|`WBEM_E_FAILED` | <span data-ttu-id="40ab5-124">0x80041001</span><span class="sxs-lookup"><span data-stu-id="40ab5-124">0x80041001</span></span> | <span data-ttu-id="40ab5-125">Общий сбой.</span><span class="sxs-lookup"><span data-stu-id="40ab5-125">There has been a general failure.</span></span> |
|`WBEM_E_INVALID_PARAMETER` | <span data-ttu-id="40ab5-126">0x80041008</span><span class="sxs-lookup"><span data-stu-id="40ab5-126">0x80041008</span></span> | <span data-ttu-id="40ab5-127">Один или несколько параметров недопустимы или указаны неверное сочетание флагов и параметров.</span><span class="sxs-lookup"><span data-stu-id="40ab5-127">One or more parameters are not valid, or an incorrect combination of flags and parameters was specified.</span></span> |
|`WBEM_E_OUT_OF_MEMORY` | <span data-ttu-id="40ab5-128">0x80041006</span><span class="sxs-lookup"><span data-stu-id="40ab5-128">0x80041006</span></span> | <span data-ttu-id="40ab5-129">Недостаточно памяти для выполнения операции.</span><span class="sxs-lookup"><span data-stu-id="40ab5-129">Not enough memory is available to complete the operation.</span></span> |
|`WBEM_S_NO_ERROR` | <span data-ttu-id="40ab5-130">0</span><span class="sxs-lookup"><span data-stu-id="40ab5-130">0</span></span> | <span data-ttu-id="40ab5-131">Вызов функции выполнен успешно.</span><span class="sxs-lookup"><span data-stu-id="40ab5-131">The function call was successful.</span></span>  |
  
## <a name="remarks"></a><span data-ttu-id="40ab5-132">Комментарии</span><span class="sxs-lookup"><span data-stu-id="40ab5-132">Remarks</span></span>

<span data-ttu-id="40ab5-133">Эта функция заключает в оболочку вызов метода [ивбемклассобжект:: Names](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemclassobject-getnames) .</span><span class="sxs-lookup"><span data-stu-id="40ab5-133">This function wraps a call to the [IWbemClassObject::GetNames](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemclassobject-getnames) method.</span></span>

<span data-ttu-id="40ab5-134">Возвращаемые именованные параметры управляются сочетанием флагов и параметров.</span><span class="sxs-lookup"><span data-stu-id="40ab5-134">The named returned are controlled by a combination of flags and parameters.</span></span> <span data-ttu-id="40ab5-135">Например, функция может возвращать имена всех свойств или только имена ключевых свойств.</span><span class="sxs-lookup"><span data-stu-id="40ab5-135">For example, the function can return the names of all properties or only the names of the key properties.</span></span>  <span data-ttu-id="40ab5-136">Основной фильтр указывается в `lFlags` параметре, а другие параметры зависят от него.</span><span class="sxs-lookup"><span data-stu-id="40ab5-136">The primary filter is specified in the `lFlags` parameter, and the other parameters vary depending on it.</span></span>

<span data-ttu-id="40ab5-137">Значения флагов в `lFlags` являются битовыми полями</span><span class="sxs-lookup"><span data-stu-id="40ab5-137">The flag values in `lFlags` are bit fields</span></span>

<span data-ttu-id="40ab5-138">Флаги, которые могут быть переданы в качестве `lEnumFlags` аргумента, являются битовыми полями, определенными в файле заголовка *вбемкли. h* , или их можно определить как константы в коде.</span><span class="sxs-lookup"><span data-stu-id="40ab5-138">The flags that can be passed as the `lEnumFlags` argument are bit fields that are defined in the *WbemCli.h* header file, or you can define them as constants in your code.</span></span>  <span data-ttu-id="40ab5-139">Можно объединить один флаг из каждой группы с любым флагом из любой другой группы.</span><span class="sxs-lookup"><span data-stu-id="40ab5-139">You can combine one flag from each group with any flag from any other group.</span></span> <span data-ttu-id="40ab5-140">Однако флаги из одной и той же группы являются взаимоисключающими.</span><span class="sxs-lookup"><span data-stu-id="40ab5-140">However, flags from the same group are mutually exclusive.</span></span>

| <span data-ttu-id="40ab5-141">Флаги группы 1</span><span class="sxs-lookup"><span data-stu-id="40ab5-141">Group 1 flags</span></span> |<span data-ttu-id="40ab5-142">Значение</span><span class="sxs-lookup"><span data-stu-id="40ab5-142">Value</span></span>  |<span data-ttu-id="40ab5-143">Описание</span><span class="sxs-lookup"><span data-stu-id="40ab5-143">Description</span></span>  |
|---------|---------|---------|
| `WBEM_FLAG_ALWAYS` | <span data-ttu-id="40ab5-144">0</span><span class="sxs-lookup"><span data-stu-id="40ab5-144">0</span></span> | <span data-ttu-id="40ab5-145">Возвращает все имена свойств.</span><span class="sxs-lookup"><span data-stu-id="40ab5-145">Return all property names.</span></span> <span data-ttu-id="40ab5-146">`strQualifierName` и `pQualifierVal` не используются.</span><span class="sxs-lookup"><span data-stu-id="40ab5-146">`strQualifierName` and `pQualifierVal` are unused.</span></span> |
| `WBEM_FLAG_ONLY_IF_TRUE` | <span data-ttu-id="40ab5-147">1</span><span class="sxs-lookup"><span data-stu-id="40ab5-147">1</span></span> | <span data-ttu-id="40ab5-148">Возвращать только те свойства, которые имеют квалификатор имени, заданного `strQualifierName` параметром.</span><span class="sxs-lookup"><span data-stu-id="40ab5-148">Return only properties that have a qualifier of the name specified by the `strQualifierName` parameter.</span></span> <span data-ttu-id="40ab5-149">Если используется этот флаг, необходимо указать `strQualifierName` .</span><span class="sxs-lookup"><span data-stu-id="40ab5-149">If this flag is used, you must specify `strQualifierName`.</span></span> |
|`WBEM_FLAG_ONLY_IF_FALSE` | <span data-ttu-id="40ab5-150">2</span><span class="sxs-lookup"><span data-stu-id="40ab5-150">2</span></span> |  <span data-ttu-id="40ab5-151">Возвращать только те свойства, у которых нет квалификатора имени, указанного в `strQualifierName` параметре.</span><span class="sxs-lookup"><span data-stu-id="40ab5-151">Return only properties that do not have a qualifier of the name specified by the `strQualifierName` parameter.</span></span> <span data-ttu-id="40ab5-152">Если используется этот флаг, необходимо указать `strQualifierName` .</span><span class="sxs-lookup"><span data-stu-id="40ab5-152">If this flag is used, you must specify `strQualifierName`.</span></span> |
|`WBEM_FLAG_ONLY_IF_IDENTICAL` | <span data-ttu-id="40ab5-153">3</span><span class="sxs-lookup"><span data-stu-id="40ab5-153">3</span></span> | <span data-ttu-id="40ab5-154">Возвращать только те свойства, которые имеют квалификатор имени, заданного `wszQualifierName` параметром, и имеют значение, идентичное значению, заданному `pQualifierVal` структурой.</span><span class="sxs-lookup"><span data-stu-id="40ab5-154">Return only properties that have a qualifier of the name specified by the `wszQualifierName` parameter and also have a value identical to that specified by the `pQualifierVal` structure.</span></span> <span data-ttu-id="40ab5-155">Если используется этот флаг, необходимо указать `wszQualifierName` и, и `pQualifierValue` .</span><span class="sxs-lookup"><span data-stu-id="40ab5-155">If this flag is used, you must specify both a `wszQualifierName` and a `pQualifierValue`.</span></span> |

| <span data-ttu-id="40ab5-156">Флаги группы 2</span><span class="sxs-lookup"><span data-stu-id="40ab5-156">Group 2 flags</span></span> |<span data-ttu-id="40ab5-157">Значение</span><span class="sxs-lookup"><span data-stu-id="40ab5-157">Value</span></span>  |<span data-ttu-id="40ab5-158">Описание</span><span class="sxs-lookup"><span data-stu-id="40ab5-158">Description</span></span>  |
|---------|---------|---------|
|`WBEM_FLAG_KEYS_ONLY` | <span data-ttu-id="40ab5-159">0x4</span><span class="sxs-lookup"><span data-stu-id="40ab5-159">0x4</span></span> | <span data-ttu-id="40ab5-160">Возвращать только имена свойств, которые определяют ключи.</span><span class="sxs-lookup"><span data-stu-id="40ab5-160">Return only the names of properties that define the keys.</span></span> |
|`WBEM_FLAG_REFS_ONLY` | <span data-ttu-id="40ab5-161">0x8</span><span class="sxs-lookup"><span data-stu-id="40ab5-161">0x8</span></span> | <span data-ttu-id="40ab5-162">Возвращать только имена свойств, которые являются ссылками на объекты.</span><span class="sxs-lookup"><span data-stu-id="40ab5-162">Return only property names that are object references.</span></span> |

| <span data-ttu-id="40ab5-163">Флаги группы 3</span><span class="sxs-lookup"><span data-stu-id="40ab5-163">Group 3 flags</span></span> |<span data-ttu-id="40ab5-164">Значение</span><span class="sxs-lookup"><span data-stu-id="40ab5-164">Value</span></span>  |<span data-ttu-id="40ab5-165">Описание</span><span class="sxs-lookup"><span data-stu-id="40ab5-165">Description</span></span>  |
|---------|---------|---------|
| `WBEM_FLAG_LOCAL_ONLY` | <span data-ttu-id="40ab5-166">0x10</span><span class="sxs-lookup"><span data-stu-id="40ab5-166">0x10</span></span> | <span data-ttu-id="40ab5-167">Возвращать только имена свойств, принадлежащих наиболее производному классу.</span><span class="sxs-lookup"><span data-stu-id="40ab5-167">Return only property names that belong to the most derived class.</span></span> <span data-ttu-id="40ab5-168">Исключите свойства из родительских классов.</span><span class="sxs-lookup"><span data-stu-id="40ab5-168">Exclude properties from the parent classes.</span></span> |
| `WBEM_FLAG_PROPAGATED_ONLY` |  <span data-ttu-id="40ab5-169">0x20</span><span class="sxs-lookup"><span data-stu-id="40ab5-169">0x20</span></span> | <span data-ttu-id="40ab5-170">Возвращать только имена свойств, принадлежащих родительским классам.</span><span class="sxs-lookup"><span data-stu-id="40ab5-170">Return only property names that belong to the parent classes.</span></span> |
|`WBEM_FLAG_SYSTEM_ONLY` | <span data-ttu-id="40ab5-171">0x30</span><span class="sxs-lookup"><span data-stu-id="40ab5-171">0x30</span></span> | <span data-ttu-id="40ab5-172">Возвращать только имена системных свойств.</span><span class="sxs-lookup"><span data-stu-id="40ab5-172">Return only the names of system properties.</span></span> |
|`WBEM_FLAG_NONSYSTEM_ONLY` | <span data-ttu-id="40ab5-173">0x40</span><span class="sxs-lookup"><span data-stu-id="40ab5-173">0x40</span></span> | <span data-ttu-id="40ab5-174">Возвращать только имена свойств, не являющихся системными.</span><span class="sxs-lookup"><span data-stu-id="40ab5-174">Return only the names of non-system properties.</span></span> |

<span data-ttu-id="40ab5-175">Функция всегда выделяет новую `SAFEARRAY` , если она возвращает `WBEM_S_NO_ERROR` , и `pstrNames` всегда устанавливается для указания на нее.</span><span class="sxs-lookup"><span data-stu-id="40ab5-175">The function always allocates a new `SAFEARRAY` if it returns `WBEM_S_NO_ERROR`, and `pstrNames` is always set to point to it.</span></span> <span data-ttu-id="40ab5-176">Возвращаемый массив может иметь 0 элементов, если свойства не соответствуют указанным фильтрам.</span><span class="sxs-lookup"><span data-stu-id="40ab5-176">The returned array can have 0 elements if no properties match the specified filters.</span></span> <span data-ttu-id="40ab5-177">Если функция возвращает значение, отличное от `WBM_S_NO_ERROR` , Новая `SAFEARRAY` структура не возвращается.</span><span class="sxs-lookup"><span data-stu-id="40ab5-177">If the function returns an value other than `WBM_S_NO_ERROR`, a new `SAFEARRAY` structure is not returned.</span></span>

## <a name="requirements"></a><span data-ttu-id="40ab5-178">Требования</span><span class="sxs-lookup"><span data-stu-id="40ab5-178">Requirements</span></span>  

 <span data-ttu-id="40ab5-179">**Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="40ab5-179">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="40ab5-180">**Заголовок:** WMINet_Utils. idl</span><span class="sxs-lookup"><span data-stu-id="40ab5-180">**Header:** WMINet_Utils.idl</span></span>  
  
 <span data-ttu-id="40ab5-181">**.NET Framework версии:**[!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span><span class="sxs-lookup"><span data-stu-id="40ab5-181">**.NET Framework Versions:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="40ab5-182">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="40ab5-182">See also</span></span>

- [<span data-ttu-id="40ab5-183">WMI и счетчики производительности (справочник по неуправляемым API)</span><span class="sxs-lookup"><span data-stu-id="40ab5-183">WMI and Performance Counters (Unmanaged API Reference)</span></span>](index.md)
