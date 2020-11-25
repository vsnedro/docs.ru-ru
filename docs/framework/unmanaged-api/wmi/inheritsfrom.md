---
title: Функция раскрывшемся (Справочник по неуправляемым API)
description: Функция раскрывшемся определяет, является ли класс или экземпляр производным от конкретного родительского класса.
ms.date: 11/06/2017
api_name:
- InheritsFrom
api_location:
- WMINet_Utils.dll
api_type:
- DLLExport
f1_keywords:
- InheritsFrom
helpviewer_keywords:
- InheritsFrom function [.NET WMI and performance counters]
topic_type:
- Reference
ms.openlocfilehash: 3cfe3388dc808335e6d3daaf7ec949108e95f52e
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/24/2020
ms.locfileid: "95726799"
---
# <a name="inheritsfrom-function"></a><span data-ttu-id="f74d4-103">Функция InheritsFrom</span><span class="sxs-lookup"><span data-stu-id="f74d4-103">InheritsFrom function</span></span>

<span data-ttu-id="f74d4-104">Определяет, является ли текущий класс или экземпляр производным от указанного родительского класса.</span><span class="sxs-lookup"><span data-stu-id="f74d4-104">Determines whether the current class or instance derives from a specified parent class.</span></span>

[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]

## <a name="syntax"></a><span data-ttu-id="f74d4-105">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="f74d4-105">Syntax</span></span>  
  
```cpp
HRESULT InheritsFrom (
   [in] int               vFunc,
   [in] IWbemClassObject* ptr,
   [in] LPCWSTR           wszAncestor
);
```  

## <a name="parameters"></a><span data-ttu-id="f74d4-106">Параметры</span><span class="sxs-lookup"><span data-stu-id="f74d4-106">Parameters</span></span>

`vFunc`  
<span data-ttu-id="f74d4-107">окне Этот параметр не используется.</span><span class="sxs-lookup"><span data-stu-id="f74d4-107">[in] This parameter is unused.</span></span>

`ptr`  
<span data-ttu-id="f74d4-108">окне Указатель на экземпляр [ивбемклассобжект](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject) .</span><span class="sxs-lookup"><span data-stu-id="f74d4-108">[in] A pointer to an [IWbemClassObject](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject) instance.</span></span>

`wszAncestor`  
<span data-ttu-id="f74d4-109">окне Имя класса.</span><span class="sxs-lookup"><span data-stu-id="f74d4-109">[in] The name of the class.</span></span> <span data-ttu-id="f74d4-110">`wszAncestor` должен указывать на допустимое значение `LPCWSTR` .</span><span class="sxs-lookup"><span data-stu-id="f74d4-110">`wszAncestor` must point to a valid `LPCWSTR`.</span></span>

## <a name="return-value"></a><span data-ttu-id="f74d4-111">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="f74d4-111">Return value</span></span>

<span data-ttu-id="f74d4-112">Следующие значения, возвращаемые этой функцией, определены в файле заголовка *вбемкли. h* , или их можно определить как константы в коде:</span><span class="sxs-lookup"><span data-stu-id="f74d4-112">The following values returned by this function are defined in the *WbemCli.h* header file, or you can define them as constants in your code:</span></span>

|<span data-ttu-id="f74d4-113">Константа</span><span class="sxs-lookup"><span data-stu-id="f74d4-113">Constant</span></span>  |<span data-ttu-id="f74d4-114">Значение</span><span class="sxs-lookup"><span data-stu-id="f74d4-114">Value</span></span>  |<span data-ttu-id="f74d4-115">Описание</span><span class="sxs-lookup"><span data-stu-id="f74d4-115">Description</span></span>  |
|---------|---------|---------|
| `WBEM_S_NO_ERROR` | <span data-ttu-id="f74d4-116">0</span><span class="sxs-lookup"><span data-stu-id="f74d4-116">0</span></span> | <span data-ttu-id="f74d4-117">Текущий объект наследует от `wszAncestor` .</span><span class="sxs-lookup"><span data-stu-id="f74d4-117">The current object inherits from `wszAncestor`.</span></span>  |
| `WBEM_S_FALSE` | <span data-ttu-id="f74d4-118">1</span><span class="sxs-lookup"><span data-stu-id="f74d4-118">1</span></span> | <span data-ttu-id="f74d4-119">Текущий объект не наследует от `wszAncestor` .</span><span class="sxs-lookup"><span data-stu-id="f74d4-119">The current object does not inherit from `wszAncestor`.</span></span> |
|`WBEM_E_INVALID_PARAMETER` | <span data-ttu-id="f74d4-120">0x80041008</span><span class="sxs-lookup"><span data-stu-id="f74d4-120">0x80041008</span></span> | <span data-ttu-id="f74d4-121">`wszAncestor` имеет значение `null`.</span><span class="sxs-lookup"><span data-stu-id="f74d4-121">`wszAncestor` is `null`.</span></span> |
  
## <a name="remarks"></a><span data-ttu-id="f74d4-122">Комментарии</span><span class="sxs-lookup"><span data-stu-id="f74d4-122">Remarks</span></span>

<span data-ttu-id="f74d4-123">Эта функция заключает в оболочку вызов метода [ивбемклассобжект:: раскрывшемся](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemclassobject-inheritsfrom) .</span><span class="sxs-lookup"><span data-stu-id="f74d4-123">This function wraps a call to the [IWbemClassObject::InheritsFrom](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemclassobject-inheritsfrom) method.</span></span>

## <a name="requirements"></a><span data-ttu-id="f74d4-124">Требования</span><span class="sxs-lookup"><span data-stu-id="f74d4-124">Requirements</span></span>  

 <span data-ttu-id="f74d4-125">**Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="f74d4-125">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f74d4-126">**Заголовок:** WMINet_Utils. idl</span><span class="sxs-lookup"><span data-stu-id="f74d4-126">**Header:** WMINet_Utils.idl</span></span>  
  
 <span data-ttu-id="f74d4-127">**.NET Framework версии:**[!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span><span class="sxs-lookup"><span data-stu-id="f74d4-127">**.NET Framework Versions:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f74d4-128">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="f74d4-128">See also</span></span>

- [<span data-ttu-id="f74d4-129">WMI и счетчики производительности (справочник по неуправляемым API)</span><span class="sxs-lookup"><span data-stu-id="f74d4-129">WMI and Performance Counters (Unmanaged API Reference)</span></span>](index.md)
