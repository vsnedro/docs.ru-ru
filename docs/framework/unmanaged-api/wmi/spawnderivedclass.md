---
title: Функция Спавндериведкласс (Справочник по неуправляемым API)
description: Функция Спавндериведкласс создает новый объект, производный от объекта.
ms.date: 11/06/2017
api_name:
- SpawnDerivedClass
api_location:
- WMINet_Utils.dll
api_type:
- DLLExport
f1_keywords:
- SpawnDerivedClass
helpviewer_keywords:
- SpawnDerivedClass function [.NET WMI and performance counters]
topic_type:
- Reference
ms.openlocfilehash: 8020dd851b6773e6c76c53892c4b2bc21e4261bb
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/24/2020
ms.locfileid: "95716516"
---
# <a name="spawnderivedclass-function"></a><span data-ttu-id="274f1-103">Функция SpawnDerivedClass</span><span class="sxs-lookup"><span data-stu-id="274f1-103">SpawnDerivedClass function</span></span>

<span data-ttu-id="274f1-104">Создает объект производного класса из указанного объекта.</span><span class="sxs-lookup"><span data-stu-id="274f1-104">Creates a newly derived class object from a specified object.</span></span>
  
[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]
  
## <a name="syntax"></a><span data-ttu-id="274f1-105">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="274f1-105">Syntax</span></span>  
  
```cpp  
HRESULT SpawnDerivedClass (
   [in] int                  vFunc,
   [in] IWbemClassObject*    ptr,
   [in] LONG                 lFlags,
   [out] IWbemClassObject**  ppNewClass);
```  

## <a name="parameters"></a><span data-ttu-id="274f1-106">Параметры</span><span class="sxs-lookup"><span data-stu-id="274f1-106">Parameters</span></span>

`vFunc`  
<span data-ttu-id="274f1-107">окне Этот параметр не используется.</span><span class="sxs-lookup"><span data-stu-id="274f1-107">[in] This parameter is unused.</span></span>

`ptr`  
<span data-ttu-id="274f1-108">окне Указатель на экземпляр [ивбемклассобжект](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject) .</span><span class="sxs-lookup"><span data-stu-id="274f1-108">[in] A pointer to an [IWbemClassObject](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject) instance.</span></span>

`lFlags`  
<span data-ttu-id="274f1-109">[in] Зарезервировано.</span><span class="sxs-lookup"><span data-stu-id="274f1-109">[in] Reserved.</span></span> <span data-ttu-id="274f1-110">Этот параметр должен иметь значение 0.</span><span class="sxs-lookup"><span data-stu-id="274f1-110">This parameter must be 0.</span></span>

`ppNewClass`  
<span data-ttu-id="274f1-111">заполняет Получает указатель на новый объект определения класса.</span><span class="sxs-lookup"><span data-stu-id="274f1-111">[out] Receives the pointer to the new class definition object.</span></span> <span data-ttu-id="274f1-112">При возникновении ошибки новый объект не возвращается и остается `ppNewClass` неизменным.</span><span class="sxs-lookup"><span data-stu-id="274f1-112">If an error occurs, a new object is not returned, and `ppNewClass` is left unmodified.</span></span> <span data-ttu-id="274f1-113">Его значение не может быть `null` .</span><span class="sxs-lookup"><span data-stu-id="274f1-113">Its value cannot be `null`.</span></span>

## <a name="return-value"></a><span data-ttu-id="274f1-114">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="274f1-114">Return value</span></span>

<span data-ttu-id="274f1-115">Следующие значения, возвращаемые этой функцией, определены в файле заголовка *вбемкли. h* , или их можно определить как константы в коде:</span><span class="sxs-lookup"><span data-stu-id="274f1-115">The following values returned by this function are defined in the *WbemCli.h* header file, or you can define them as constants in your code:</span></span>

|<span data-ttu-id="274f1-116">Константа</span><span class="sxs-lookup"><span data-stu-id="274f1-116">Constant</span></span>  |<span data-ttu-id="274f1-117">Значение</span><span class="sxs-lookup"><span data-stu-id="274f1-117">Value</span></span>  |<span data-ttu-id="274f1-118">Описание</span><span class="sxs-lookup"><span data-stu-id="274f1-118">Description</span></span>  |
|---------|---------|---------|
| `WBEM_E_FAILED` | <span data-ttu-id="274f1-119">0x80041001</span><span class="sxs-lookup"><span data-stu-id="274f1-119">0x80041001</span></span> | <span data-ttu-id="274f1-120">Общий сбой.</span><span class="sxs-lookup"><span data-stu-id="274f1-120">There has been a general failure.</span></span> |
| `WBEM_E_INVALID_OPERATION` | <span data-ttu-id="274f1-121">0x80041016</span><span class="sxs-lookup"><span data-stu-id="274f1-121">0x80041016</span></span> | <span data-ttu-id="274f1-122">Запрошена Недопустимая операция, например порождение класса из экземпляра.</span><span class="sxs-lookup"><span data-stu-id="274f1-122">An invalid operation, such as spawning a class from an instance, was requested.</span></span> |
| `WBEM_E_INCOMPLETE_CLASS` | <span data-ttu-id="274f1-123">Исходный класс не был полностью определен или зарегистрирован в управлении Windows, поэтому новый производный класс не разрешен.</span><span class="sxs-lookup"><span data-stu-id="274f1-123">The source class was not completely defined or registered with Windows Management, so a new derived class is not permitted.</span></span> |
| `WBEM_E_OUT_OF_MEMORY` | <span data-ttu-id="274f1-124">0x80041006</span><span class="sxs-lookup"><span data-stu-id="274f1-124">0x80041006</span></span> | <span data-ttu-id="274f1-125">Недостаточно памяти для выполнения операции.</span><span class="sxs-lookup"><span data-stu-id="274f1-125">Not enough memory is available to complete the operation.</span></span> |
| `WBEM_E_INVALID_PARAMETER` | <span data-ttu-id="274f1-126">0x80041008</span><span class="sxs-lookup"><span data-stu-id="274f1-126">0x80041008</span></span> | <span data-ttu-id="274f1-127">`ppNewClass` имеет значение `null`.</span><span class="sxs-lookup"><span data-stu-id="274f1-127">`ppNewClass` is `null`.</span></span> |
| `WBEM_S_NO_ERROR` | <span data-ttu-id="274f1-128">0</span><span class="sxs-lookup"><span data-stu-id="274f1-128">0</span></span> | <span data-ttu-id="274f1-129">Вызов функции выполнен успешно.</span><span class="sxs-lookup"><span data-stu-id="274f1-129">The function call was successful.</span></span>  |
  
## <a name="remarks"></a><span data-ttu-id="274f1-130">Комментарии</span><span class="sxs-lookup"><span data-stu-id="274f1-130">Remarks</span></span>

<span data-ttu-id="274f1-131">Эта функция заключает в оболочку вызов метода [ивбемклассобжект:: спавндериведкласс](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemclassobject-clone) .</span><span class="sxs-lookup"><span data-stu-id="274f1-131">This function wraps a call to the [IWbemClassObject::SpawnDerivedClass](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemclassobject-clone) method.</span></span>

<span data-ttu-id="274f1-132">`ptr` должно быть определением класса, который станет родительским классом порожденного объекта.</span><span class="sxs-lookup"><span data-stu-id="274f1-132">`ptr` must be a class definition that becomes the parent class of the spawned object.</span></span> <span data-ttu-id="274f1-133">Возвращаемый объект превращается в подкласс текущего объекта.</span><span class="sxs-lookup"><span data-stu-id="274f1-133">The returned object becomes a subclass of the current object.</span></span>

<span data-ttu-id="274f1-134">Новый объект, возвращенный в `ppNewClass` , автоматически станет подклассом текущего объекта.</span><span class="sxs-lookup"><span data-stu-id="274f1-134">The new object returned in `ppNewClass` automatically becomes a subclass of the current object.</span></span> <span data-ttu-id="274f1-135">Это поведение не может быть переопределено.</span><span class="sxs-lookup"><span data-stu-id="274f1-135">This behavior cannot be overridden.</span></span> <span data-ttu-id="274f1-136">Нет других методов, с помощью которых можно создать подклассы (производные классы).</span><span class="sxs-lookup"><span data-stu-id="274f1-136">There is no other method by which subclasses (derived classes) can be created.</span></span>

## <a name="requirements"></a><span data-ttu-id="274f1-137">Требования</span><span class="sxs-lookup"><span data-stu-id="274f1-137">Requirements</span></span>  

 <span data-ttu-id="274f1-138">**Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="274f1-138">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="274f1-139">**Заголовок:** WMINet_Utils. idl</span><span class="sxs-lookup"><span data-stu-id="274f1-139">**Header:** WMINet_Utils.idl</span></span>  
  
 <span data-ttu-id="274f1-140">**.NET Framework версии:**[!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span><span class="sxs-lookup"><span data-stu-id="274f1-140">**.NET Framework Versions:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="274f1-141">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="274f1-141">See also</span></span>

- [<span data-ttu-id="274f1-142">WMI и счетчики производительности (справочник по неуправляемым API)</span><span class="sxs-lookup"><span data-stu-id="274f1-142">WMI and Performance Counters (Unmanaged API Reference)</span></span>](index.md)
