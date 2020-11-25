---
title: Функция QualifierSet_EndEnumeration (Справочник по неуправляемым интерфейсам API)
description: Функция QualifierSet_EndEnumeration прерывает перечисление.
ms.date: 11/06/2017
api_name:
- QualifierSet_EndEnumeration
api_location:
- WMINet_Utils.dll
api_type:
- DLLExport
f1_keywords:
- QualifierSet_EndEnumeration
helpviewer_keywords:
- QualifierSet_EndEnumeration function [.NET WMI and performance counters]
topic_type:
- Reference
ms.openlocfilehash: 2739003fc9c1f93d379e4a59338cbef7a1a0f135
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/24/2020
ms.locfileid: "95726747"
---
# <a name="qualifierset_endenumeration-function"></a><span data-ttu-id="e2ec4-103">Функция QualifierSet_EndEnumeration</span><span class="sxs-lookup"><span data-stu-id="e2ec4-103">QualifierSet_EndEnumeration function</span></span>

<span data-ttu-id="e2ec4-104">Завершает перечисление, начатое вызовом функции [QualifierSet_BeginEnumeration](qualifierset-beginenumeration.md) .</span><span class="sxs-lookup"><span data-stu-id="e2ec4-104">Terminates the enumeration begun with a call to the [QualifierSet_BeginEnumeration](qualifierset-beginenumeration.md) function.</span></span>  

[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]
  
## <a name="syntax"></a><span data-ttu-id="e2ec4-105">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="e2ec4-105">Syntax</span></span>  
  
```cpp  
HRESULT QualifierSet_EndEnumeration (
   [in] int                  vFunc,
   [in] IWbemQualifierSet*   ptr
);
```  

## <a name="parameters"></a><span data-ttu-id="e2ec4-106">Параметры</span><span class="sxs-lookup"><span data-stu-id="e2ec4-106">Parameters</span></span>

`vFunc`  
<span data-ttu-id="e2ec4-107">окне Этот параметр не используется.</span><span class="sxs-lookup"><span data-stu-id="e2ec4-107">[in] This parameter is unused.</span></span>

<span data-ttu-id="e2ec4-108">`ptr` окне Указатель на экземпляр [ивбемкуалифиерсет](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemqualifierset) .</span><span class="sxs-lookup"><span data-stu-id="e2ec4-108">`ptr` [in] A pointer to an [IWbemQualifierSet](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemqualifierset) instance.</span></span>

## <a name="return-value"></a><span data-ttu-id="e2ec4-109">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="e2ec4-109">Return value</span></span>

<span data-ttu-id="e2ec4-110">Следующее значение, возвращаемое этой функцией, определено в файле заголовка *вбемкли. h* , или его можно определить как константу в коде:</span><span class="sxs-lookup"><span data-stu-id="e2ec4-110">The following value returned by this function is defined in the *WbemCli.h* header file, or you can define it as a constant in your code:</span></span>

|<span data-ttu-id="e2ec4-111">Константа</span><span class="sxs-lookup"><span data-stu-id="e2ec4-111">Constant</span></span>  |<span data-ttu-id="e2ec4-112">Значение</span><span class="sxs-lookup"><span data-stu-id="e2ec4-112">Value</span></span>  |<span data-ttu-id="e2ec4-113">Описание</span><span class="sxs-lookup"><span data-stu-id="e2ec4-113">Description</span></span>  |
|---------|---------|---------|
|`WBEM_S_NO_ERROR` | <span data-ttu-id="e2ec4-114">0</span><span class="sxs-lookup"><span data-stu-id="e2ec4-114">0</span></span> | <span data-ttu-id="e2ec4-115">Вызов функции выполнен успешно.</span><span class="sxs-lookup"><span data-stu-id="e2ec4-115">The function call was successful.</span></span>  |
  
## <a name="remarks"></a><span data-ttu-id="e2ec4-116">Комментарии</span><span class="sxs-lookup"><span data-stu-id="e2ec4-116">Remarks</span></span>

<span data-ttu-id="e2ec4-117">Эта функция заключает в оболочку вызов метода [ивбемкуалифиерсет:: EndEnumeration](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemqualifierset-endenumeration) .</span><span class="sxs-lookup"><span data-stu-id="e2ec4-117">This function wraps a call to the [IWbemQualifierSet::EndEnumeration](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemqualifierset-endenumeration) method.</span></span>

<span data-ttu-id="e2ec4-118">Этот вызов рекомендуется, но не является обязательным.</span><span class="sxs-lookup"><span data-stu-id="e2ec4-118">This call is recommended, but not required.</span></span> <span data-ttu-id="e2ec4-119">Он немедленно освобождает ресурсы, связанные с перечислением.</span><span class="sxs-lookup"><span data-stu-id="e2ec4-119">It immediately releases resources associated with the enumeration.</span></span>

## <a name="requirements"></a><span data-ttu-id="e2ec4-120">Требования</span><span class="sxs-lookup"><span data-stu-id="e2ec4-120">Requirements</span></span>  

<span data-ttu-id="e2ec4-121">**Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="e2ec4-121">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
<span data-ttu-id="e2ec4-122">**Заголовок:** WMINet_Utils. idl</span><span class="sxs-lookup"><span data-stu-id="e2ec4-122">**Header:** WMINet_Utils.idl</span></span>  
  
<span data-ttu-id="e2ec4-123">**.NET Framework версии:**[!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span><span class="sxs-lookup"><span data-stu-id="e2ec4-123">**.NET Framework Versions:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e2ec4-124">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="e2ec4-124">See also</span></span>

- [<span data-ttu-id="e2ec4-125">WMI и счетчики производительности (справочник по неуправляемым API)</span><span class="sxs-lookup"><span data-stu-id="e2ec4-125">WMI and Performance Counters (Unmanaged API Reference)</span></span>](index.md)
