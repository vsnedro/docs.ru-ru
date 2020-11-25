---
title: Функция Жетобжекттекст (Справочник по неуправляемым API)
description: Функция Жетобжекттекст возвращает текстовую отрисовку объекта в синтаксисе MOF.
ms.date: 11/06/2017
api_name:
- GetObjectText
api_location:
- WMINet_Utils.dll
api_type:
- DLLExport
f1_keywords:
- GetObjectText
helpviewer_keywords:
- GetObjectText function [.NET WMI and performance counters]
topic_type:
- Reference
ms.openlocfilehash: 6ad2b29202222d594cc7976a13929002164314a7
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/24/2020
ms.locfileid: "95718375"
---
# <a name="getobjecttext-function"></a><span data-ttu-id="7e9a0-103">Функция GetObjectText</span><span class="sxs-lookup"><span data-stu-id="7e9a0-103">GetObjectText function</span></span>

<span data-ttu-id="7e9a0-104">Возвращает текстовое представление объекта в синтаксисе MOF (MOF).</span><span class="sxs-lookup"><span data-stu-id="7e9a0-104">Returns a textual rendering of the object in the Managed Object Format (MOF) syntax.</span></span>

[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]

## <a name="syntax"></a><span data-ttu-id="7e9a0-105">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="7e9a0-105">Syntax</span></span>  
  
```cpp  
HRESULT GetObjectText (
   [in] int                vFunc,
   [in] IWbemClassObject*   ptr,
   [in] LONG                lFlags,
   [out] BSTR*              pstrObjectText
);
```  

## <a name="parameters"></a><span data-ttu-id="7e9a0-106">Параметры</span><span class="sxs-lookup"><span data-stu-id="7e9a0-106">Parameters</span></span>

`vFunc`  
<span data-ttu-id="7e9a0-107">окне Этот параметр не используется.</span><span class="sxs-lookup"><span data-stu-id="7e9a0-107">[in] This parameter is unused.</span></span>

`ptr`  
<span data-ttu-id="7e9a0-108">окне Указатель на экземпляр [ивбемклассобжект](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject) .</span><span class="sxs-lookup"><span data-stu-id="7e9a0-108">[in] A pointer to an [IWbemClassObject](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject) instance.</span></span>

`lFlags`  
<span data-ttu-id="7e9a0-109">окне Обычно 0.</span><span class="sxs-lookup"><span data-stu-id="7e9a0-109">[in] Normally 0.</span></span> <span data-ttu-id="7e9a0-110">Если `WBEM_FLAG_NO_FLAVORS` задано значение (или 0x1), квалификаторы включаются без сведений о распространении или разновидности.</span><span class="sxs-lookup"><span data-stu-id="7e9a0-110">If `WBEM_FLAG_NO_FLAVORS` (or 0x1) is specified, qualifiers are included without propagation or flavor information.</span></span>

<span data-ttu-id="7e9a0-111">`pstrObjectText` заполняет Указатель на `null` запись в элементе.</span><span class="sxs-lookup"><span data-stu-id="7e9a0-111">`pstrObjectText` [out] A pointer to a `null` on entry.</span></span> <span data-ttu-id="7e9a0-112">При возврате вновь выделенное значение `BSTR` , содержащее Синтаксис MOF для отображения объекта.</span><span class="sxs-lookup"><span data-stu-id="7e9a0-112">On return, a newly allocated `BSTR` that contains a MOF syntax rendering of the object.</span></span>  

## <a name="return-value"></a><span data-ttu-id="7e9a0-113">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="7e9a0-113">Return value</span></span>

<span data-ttu-id="7e9a0-114">Следующие значения, возвращаемые этой функцией, определены в файле заголовка *вбемкли. h* , или их можно определить как константы в коде:</span><span class="sxs-lookup"><span data-stu-id="7e9a0-114">The following values returned by this function are defined in the *WbemCli.h* header file, or you can define them as constants in your code:</span></span>

|<span data-ttu-id="7e9a0-115">Константа</span><span class="sxs-lookup"><span data-stu-id="7e9a0-115">Constant</span></span>  |<span data-ttu-id="7e9a0-116">Значение</span><span class="sxs-lookup"><span data-stu-id="7e9a0-116">Value</span></span>  |<span data-ttu-id="7e9a0-117">Описание</span><span class="sxs-lookup"><span data-stu-id="7e9a0-117">Description</span></span>  |
|---------|---------|---------|
|`WBEM_E_FAILED` | <span data-ttu-id="7e9a0-118">0x80041001</span><span class="sxs-lookup"><span data-stu-id="7e9a0-118">0x80041001</span></span> | <span data-ttu-id="7e9a0-119">Общий сбой.</span><span class="sxs-lookup"><span data-stu-id="7e9a0-119">There has been a general failure.</span></span> |
|`WBEM_E_INVALID_PARAMETER` | <span data-ttu-id="7e9a0-120">0x80041008</span><span class="sxs-lookup"><span data-stu-id="7e9a0-120">0x80041008</span></span> | <span data-ttu-id="7e9a0-121">Недействительный параметр.</span><span class="sxs-lookup"><span data-stu-id="7e9a0-121">A parameter is not valid.</span></span> |
|`WBEM_E_OUT_OF_MEMORY` | <span data-ttu-id="7e9a0-122">0x80041006</span><span class="sxs-lookup"><span data-stu-id="7e9a0-122">0x80041006</span></span> | <span data-ttu-id="7e9a0-123">Недостаточно памяти для выполнения операции.</span><span class="sxs-lookup"><span data-stu-id="7e9a0-123">Not enough memory is available to complete the operation.</span></span> |
|`WBEM_S_NO_ERROR` | <span data-ttu-id="7e9a0-124">0</span><span class="sxs-lookup"><span data-stu-id="7e9a0-124">0</span></span> | <span data-ttu-id="7e9a0-125">Вызов функции выполнен успешно.</span><span class="sxs-lookup"><span data-stu-id="7e9a0-125">The function call was successful.</span></span>  |
  
## <a name="remarks"></a><span data-ttu-id="7e9a0-126">Комментарии</span><span class="sxs-lookup"><span data-stu-id="7e9a0-126">Remarks</span></span>

<span data-ttu-id="7e9a0-127">Эта функция заключает в оболочку вызов метода [ивбемклассобжект:: жетобжекттекст](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemclassobject-getobjecttext) .</span><span class="sxs-lookup"><span data-stu-id="7e9a0-127">This function wraps a call to the [IWbemClassObject::GetObjectText](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemclassobject-getobjecttext) method.</span></span>

<span data-ttu-id="7e9a0-128">Возвращенный текст MOF не содержит все сведения об объекте, но достаточно информации для компилятора MOF, чтобы иметь возможность воссоздать исходный объект.</span><span class="sxs-lookup"><span data-stu-id="7e9a0-128">The MOF text returned does not contain all the information about the object, but only enough information for the MOF compiler to be able to recreate the original object.</span></span> <span data-ttu-id="7e9a0-129">Например, не включаются распространенные квалификаторы или свойства родительского класса.</span><span class="sxs-lookup"><span data-stu-id="7e9a0-129">For instance, no propagated qualifiers or parent class properties are included.</span></span>

<span data-ttu-id="7e9a0-130">Для восстановления текста параметров метода используется следующий алгоритм:</span><span class="sxs-lookup"><span data-stu-id="7e9a0-130">The following algorithm is used to reconstruct the text of the parameters of a method:</span></span>

1. <span data-ttu-id="7e9a0-131">Параметры переупорядочиваются в порядке их значений идентификаторов.</span><span class="sxs-lookup"><span data-stu-id="7e9a0-131">Parameters are resequenced in the order of their identifier values.</span></span>
1. <span data-ttu-id="7e9a0-132">Параметры, заданные как `[in]` и `[out]` , объединяются в один параметр.</span><span class="sxs-lookup"><span data-stu-id="7e9a0-132">Parameters that are specified as `[in]` and `[out]` are combined into a single parameter.</span></span>

<span data-ttu-id="7e9a0-133">`pstrObjectText` должен быть указателем на объект `null` при вызове функции; он не должен указывать на строку, допустимую до вызова метода, так как указатель не будет освобожден.</span><span class="sxs-lookup"><span data-stu-id="7e9a0-133">`pstrObjectText` must be a pointer to a `null` when the function is called; it must not point to a string that is valid before the method call, because the pointer will not be deallocated.</span></span>

## <a name="requirements"></a><span data-ttu-id="7e9a0-134">Требования</span><span class="sxs-lookup"><span data-stu-id="7e9a0-134">Requirements</span></span>  

<span data-ttu-id="7e9a0-135">**Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="7e9a0-135">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="7e9a0-136">**Заголовок:** WMINet_Utils. idl</span><span class="sxs-lookup"><span data-stu-id="7e9a0-136">**Header:** WMINet_Utils.idl</span></span>  
  
 <span data-ttu-id="7e9a0-137">**.NET Framework версии:**[!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span><span class="sxs-lookup"><span data-stu-id="7e9a0-137">**.NET Framework Versions:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7e9a0-138">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="7e9a0-138">See also</span></span>

- [<span data-ttu-id="7e9a0-139">WMI и счетчики производительности (справочник по неуправляемым API)</span><span class="sxs-lookup"><span data-stu-id="7e9a0-139">WMI and Performance Counters (Unmanaged API Reference)</span></span>](index.md)
