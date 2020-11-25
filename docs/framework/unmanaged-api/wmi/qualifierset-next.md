---
title: Функция QualifierSet_Next (Справочник по неуправляемым интерфейсам API)
description: Функция QualifierSet_Next извлекает следующий квалификатор в перечислении.
ms.date: 11/06/2017
api_name:
- QualifierSet_Next
api_location:
- WMINet_Utils.dll
api_type:
- DLLExport
f1_keywords:
- QualifierSet_Next
helpviewer_keywords:
- QualifierSet_Next function [.NET WMI and performance counters]
topic_type:
- Reference
ms.openlocfilehash: 54d79a3dc081e9cdcb42153b6f7aa457557e3399
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/24/2020
ms.locfileid: "95721131"
---
# <a name="qualifierset_next-function"></a><span data-ttu-id="ff30f-103">Функция QualifierSet_Next</span><span class="sxs-lookup"><span data-stu-id="ff30f-103">QualifierSet_Next function</span></span>

<span data-ttu-id="ff30f-104">Получает следующий квалификатор в перечислении, начатом вызовом функции [QualifierSet_BeginEnumeration](qualifierset-beginenumeration.md).</span><span class="sxs-lookup"><span data-stu-id="ff30f-104">Retrieves the next qualifier in an enumeration that started with a call to the [QualifierSet_BeginEnumeration](qualifierset-beginenumeration.md) function.</span></span>

[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]
  
## <a name="syntax"></a><span data-ttu-id="ff30f-105">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="ff30f-105">Syntax</span></span>  
  
```cpp  
HRESULT QualifierSet_Next (
   [in] int                  vFunc,
   [in] IWbemQualifierSet*   ptr,
   [in] LONG                 lFlags,
   [out] BSTR*               pstrName,
   [out] VARIANT*            pVal,
   [out] LONG*               plFlavor
);
```  

## <a name="parameters"></a><span data-ttu-id="ff30f-106">Параметры</span><span class="sxs-lookup"><span data-stu-id="ff30f-106">Parameters</span></span>

<span data-ttu-id="ff30f-107">`vFunc` окне Этот параметр не используется.</span><span class="sxs-lookup"><span data-stu-id="ff30f-107">`vFunc` [in] This parameter is unused.</span></span>

<span data-ttu-id="ff30f-108">`ptr` окне Указатель на экземпляр [ивбемкуалифиерсет](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemqualifierset) .</span><span class="sxs-lookup"><span data-stu-id="ff30f-108">`ptr` [in] A pointer to an [IWbemQualifierSet](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemqualifierset) instance.</span></span>

<span data-ttu-id="ff30f-109">`lFlags` окне Процессу.</span><span class="sxs-lookup"><span data-stu-id="ff30f-109">`lFlags` [in] Reserved.</span></span> <span data-ttu-id="ff30f-110">Этот параметр должен иметь значение 0.</span><span class="sxs-lookup"><span data-stu-id="ff30f-110">This parameter must be 0.</span></span>

<span data-ttu-id="ff30f-111">`pstrName` заполняет Имя квалификатора.</span><span class="sxs-lookup"><span data-stu-id="ff30f-111">`pstrName` [out] The name of the qualifier.</span></span> <span data-ttu-id="ff30f-112">`null`Значение, если этот параметр не учитывается; в противном случае `pstrName` не должен указывать на допустимый `BSTR` или утечку памяти.</span><span class="sxs-lookup"><span data-stu-id="ff30f-112">If `null`, this parameter is ignored; otherwise, `pstrName` should not point to a valid `BSTR` or a memory leak occurs.</span></span> <span data-ttu-id="ff30f-113">Если значение не равно null, функция всегда выделяет новый `BSTR` при возврате `WBEM_S_NO_ERROR` .</span><span class="sxs-lookup"><span data-stu-id="ff30f-113">If not null, the function always allocates a new `BSTR` when it returns `WBEM_S_NO_ERROR`.</span></span>

<span data-ttu-id="ff30f-114">`pVal` заполняет В случае успеха значение квалификатора.</span><span class="sxs-lookup"><span data-stu-id="ff30f-114">`pVal` [out] When successful, the value for the qualifier.</span></span> <span data-ttu-id="ff30f-115">Если функция завершается ошибкой, то, на `VARIANT` которую указывает, `pVal` не изменяется.</span><span class="sxs-lookup"><span data-stu-id="ff30f-115">If the function fails, the `VARIANT` pointed to by `pVal` is not modified.</span></span> <span data-ttu-id="ff30f-116">Если этот параметр имеет значение `null` , параметр игнорируется.</span><span class="sxs-lookup"><span data-stu-id="ff30f-116">If this parameter is `null`, the parameter is ignored.</span></span>

<span data-ttu-id="ff30f-117">`plFlavor` заполняет Указатель на значение типа LONG, которое получает флаг квалификатора.</span><span class="sxs-lookup"><span data-stu-id="ff30f-117">`plFlavor` [out] A pointer to a LONG that receives the qualifier flavor.</span></span> <span data-ttu-id="ff30f-118">Если сведения о разновидностях не нужны, этот параметр может иметь значение `null` .</span><span class="sxs-lookup"><span data-stu-id="ff30f-118">If flavor information is not desired, this parameter can be `null`.</span></span>

## <a name="return-value"></a><span data-ttu-id="ff30f-119">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="ff30f-119">Return value</span></span>

<span data-ttu-id="ff30f-120">Следующие значения, возвращаемые этой функцией, определены в файле заголовка *вбемкли. h* , или их можно определить как константы в коде:</span><span class="sxs-lookup"><span data-stu-id="ff30f-120">The following values returned by this function are defined in the *WbemCli.h* header file, or you can define them as constants in your code:</span></span>

|<span data-ttu-id="ff30f-121">Константа</span><span class="sxs-lookup"><span data-stu-id="ff30f-121">Constant</span></span>  |<span data-ttu-id="ff30f-122">Значение</span><span class="sxs-lookup"><span data-stu-id="ff30f-122">Value</span></span>  |<span data-ttu-id="ff30f-123">Описание</span><span class="sxs-lookup"><span data-stu-id="ff30f-123">Description</span></span>  |
|---------|---------|---------|
|`WBEM_E_INVALID_PARAMETER` | <span data-ttu-id="ff30f-124">0x80041008</span><span class="sxs-lookup"><span data-stu-id="ff30f-124">0x80041008</span></span> | <span data-ttu-id="ff30f-125">Недействительный параметр.</span><span class="sxs-lookup"><span data-stu-id="ff30f-125">A parameter is not valid.</span></span> |
|`WBEM_E_UNEXPECTED` | <span data-ttu-id="ff30f-126">0x8004101d</span><span class="sxs-lookup"><span data-stu-id="ff30f-126">0x8004101d</span></span> | <span data-ttu-id="ff30f-127">Вызывающий объект не вызывал [QualifierSet_BeginEnumeration](qualifierset-beginenumeration.md).</span><span class="sxs-lookup"><span data-stu-id="ff30f-127">The caller did not call [QualifierSet_BeginEnumeration](qualifierset-beginenumeration.md).</span></span> |
|`WBEM_E_OUT_OF_MEMORY` | <span data-ttu-id="ff30f-128">0x80041006</span><span class="sxs-lookup"><span data-stu-id="ff30f-128">0x80041006</span></span> | <span data-ttu-id="ff30f-129">Недостаточно памяти для начала нового перечисления.</span><span class="sxs-lookup"><span data-stu-id="ff30f-129">Not enough memory is available to begin a new enumeration.</span></span> |
| `WBEM_S_NO_MORE_DATA` | <span data-ttu-id="ff30f-130">0x40005</span><span class="sxs-lookup"><span data-stu-id="ff30f-130">0x40005</span></span> | <span data-ttu-id="ff30f-131">В перечислении не осталось квалификаторов.</span><span class="sxs-lookup"><span data-stu-id="ff30f-131">No more qualifiers are left in the enumeration.</span></span> |
|`WBEM_S_NO_ERROR` | <span data-ttu-id="ff30f-132">0</span><span class="sxs-lookup"><span data-stu-id="ff30f-132">0</span></span> | <span data-ttu-id="ff30f-133">Вызов функции выполнен успешно.</span><span class="sxs-lookup"><span data-stu-id="ff30f-133">The function call was successful.</span></span>  |
  
## <a name="remarks"></a><span data-ttu-id="ff30f-134">Комментарии</span><span class="sxs-lookup"><span data-stu-id="ff30f-134">Remarks</span></span>

<span data-ttu-id="ff30f-135">Эта функция заключает в оболочку вызов метода [ивбемкуалифиерсет:: Next](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemqualifierset-next) .</span><span class="sxs-lookup"><span data-stu-id="ff30f-135">This function wraps a call to the [IWbemQualifierSet::Next](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemqualifierset-next) method.</span></span>

<span data-ttu-id="ff30f-136">Функция вызывается `QualifierSet_Next` повторно для перечисления всех квалификаторов до возвращения функции `WBEM_S_NO_MORE_DATA` .</span><span class="sxs-lookup"><span data-stu-id="ff30f-136">You call the `QualifierSet_Next` function repeatedly to enumerate all the qualifiers until the function return `WBEM_S_NO_MORE_DATA`.</span></span> <span data-ttu-id="ff30f-137">Чтобы завершить перечисление раньше, вызовите функцию [QualifierSet_EndEnumeration](qualifierset-endenumeration.md) .</span><span class="sxs-lookup"><span data-stu-id="ff30f-137">To terminate the enumeration early, call the [QualifierSet_EndEnumeration](qualifierset-endenumeration.md) function.</span></span>

<span data-ttu-id="ff30f-138">Порядок квалификаторов, возвращаемых во время перечисления, не определен.</span><span class="sxs-lookup"><span data-stu-id="ff30f-138">The order of the qualifiers returned during the enumeration is undefined.</span></span>

## <a name="requirements"></a><span data-ttu-id="ff30f-139">Требования</span><span class="sxs-lookup"><span data-stu-id="ff30f-139">Requirements</span></span>  

 <span data-ttu-id="ff30f-140">**Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="ff30f-140">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ff30f-141">**Заголовок:** WMINet_Utils. idl</span><span class="sxs-lookup"><span data-stu-id="ff30f-141">**Header:** WMINet_Utils.idl</span></span>  
  
 <span data-ttu-id="ff30f-142">**.NET Framework версии:**[!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span><span class="sxs-lookup"><span data-stu-id="ff30f-142">**.NET Framework Versions:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ff30f-143">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="ff30f-143">See also</span></span>

- [<span data-ttu-id="ff30f-144">WMI и счетчики производительности (справочник по неуправляемым API)</span><span class="sxs-lookup"><span data-stu-id="ff30f-144">WMI and Performance Counters (Unmanaged API Reference)</span></span>](index.md)
