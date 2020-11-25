---
title: Функция QualifierSet_Get (Справочник по неуправляемым интерфейсам API)
description: Функция QualifierSet_Get Возвращает именованный квалификатор.
ms.date: 11/06/2017
api_name:
- QualifierSet_Get
api_location:
- WMINet_Utils.dll
api_type:
- DLLExport
f1_keywords:
- QualifierSet_Get
helpviewer_keywords:
- QualifierSet_Get function [.NET WMI and performance counters]
topic_type:
- Reference
ms.openlocfilehash: fd096287b85b4a51a8cae85dddcca95cc1a8dbae
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/24/2020
ms.locfileid: "95721144"
---
# <a name="qualifierset_get-function"></a><span data-ttu-id="54dcf-103">Функция QualifierSet_Get</span><span class="sxs-lookup"><span data-stu-id="54dcf-103">QualifierSet_Get function</span></span>

<span data-ttu-id="54dcf-104">Получает указанный именованный квалификатор.</span><span class="sxs-lookup"><span data-stu-id="54dcf-104">Gets the specified named qualifier.</span></span>  

[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]
  
## <a name="syntax"></a><span data-ttu-id="54dcf-105">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="54dcf-105">Syntax</span></span>  
  
```cpp  
HRESULT QualifierSet_Get (
   [in] int                  vFunc,
   [in] IWbemQualifierSet*   ptr,
   [in] LPCWSTR              wszName,
   [in] LONG                 lFlags,
   [out] VARIANT*            pVal,
   [out] LONG*               plFlavor
);
```  

## <a name="parameters"></a><span data-ttu-id="54dcf-106">Параметры</span><span class="sxs-lookup"><span data-stu-id="54dcf-106">Parameters</span></span>

<span data-ttu-id="54dcf-107">`vFunc` окне Этот параметр не используется.</span><span class="sxs-lookup"><span data-stu-id="54dcf-107">`vFunc` [in] This parameter is unused.</span></span>

<span data-ttu-id="54dcf-108">`ptr` окне Указатель на экземпляр [ивбемкуалифиерсет](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemqualifierset) .</span><span class="sxs-lookup"><span data-stu-id="54dcf-108">`ptr` [in] A pointer to an [IWbemQualifierSet](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemqualifierset) instance.</span></span>

<span data-ttu-id="54dcf-109">`wszName` окне Имя квалификатора, значение которого запрашивается.</span><span class="sxs-lookup"><span data-stu-id="54dcf-109">`wszName` [in] The name of the qualifier whose value is requested.</span></span>

<span data-ttu-id="54dcf-110">`lFlags` окне Процессу.</span><span class="sxs-lookup"><span data-stu-id="54dcf-110">`lFlags` [in] Reserved.</span></span> <span data-ttu-id="54dcf-111">Этот параметр должен иметь значение 0.</span><span class="sxs-lookup"><span data-stu-id="54dcf-111">This parameter must be 0.</span></span>

<span data-ttu-id="54dcf-112">`pVal` заполняет При успешном выполнении, правильный тип и значение для квалификатора.</span><span class="sxs-lookup"><span data-stu-id="54dcf-112">`pVal` [out] When successful, the correct type and value for the qualifier.</span></span> <span data-ttu-id="54dcf-113">Если функция завершается ошибкой, то, на `VARIANT` которую указывает, `pVal` не изменяется.</span><span class="sxs-lookup"><span data-stu-id="54dcf-113">If the function fails, the `VARIANT` pointed to by `pVal` is not modified.</span></span> <span data-ttu-id="54dcf-114">Если этот параметр имеет значение `null` , параметр игнорируется.</span><span class="sxs-lookup"><span data-stu-id="54dcf-114">If this parameter is `null`, the parameter is ignored.</span></span>

<span data-ttu-id="54dcf-115">`plFlavor` заполняет Указатель на значение типа LONG, которое получает биты флагов для запрошенного описателя.</span><span class="sxs-lookup"><span data-stu-id="54dcf-115">`plFlavor` [out] A pointer to a LONG that receives the qualifier flavor bits for the requested qualifier.</span></span> <span data-ttu-id="54dcf-116">Если сведения о разновидностях не нужны, этот параметр может иметь значение `null` .</span><span class="sxs-lookup"><span data-stu-id="54dcf-116">If flavor information is not desired, this parameter can be `null`.</span></span>

## <a name="return-value"></a><span data-ttu-id="54dcf-117">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="54dcf-117">Return value</span></span>

<span data-ttu-id="54dcf-118">Следующие значения, возвращаемые этой функцией, определены в файле заголовка *вбемкли. h* , или их можно определить как константы в коде:</span><span class="sxs-lookup"><span data-stu-id="54dcf-118">The following values returned by this function are defined in the *WbemCli.h* header file, or you can define them as constants in your code:</span></span>

|<span data-ttu-id="54dcf-119">Константа</span><span class="sxs-lookup"><span data-stu-id="54dcf-119">Constant</span></span>  |<span data-ttu-id="54dcf-120">Значение</span><span class="sxs-lookup"><span data-stu-id="54dcf-120">Value</span></span>  |<span data-ttu-id="54dcf-121">Описание</span><span class="sxs-lookup"><span data-stu-id="54dcf-121">Description</span></span>  |
|---------|---------|---------|
|`WBEM_E_INVALID_PARAMETER` | <span data-ttu-id="54dcf-122">0x80041008</span><span class="sxs-lookup"><span data-stu-id="54dcf-122">0x80041008</span></span> | <span data-ttu-id="54dcf-123">Недействительный параметр.</span><span class="sxs-lookup"><span data-stu-id="54dcf-123">A parameter is not valid.</span></span> |
|`WBEM_E_NOT_FOUND` | <span data-ttu-id="54dcf-124">0x80041002</span><span class="sxs-lookup"><span data-stu-id="54dcf-124">0x80041002</span></span> | <span data-ttu-id="54dcf-125">Указанный квалификатор не существует.</span><span class="sxs-lookup"><span data-stu-id="54dcf-125">The specified qualifier does not exist.</span></span> |
|`WBEM_S_NO_ERROR` | <span data-ttu-id="54dcf-126">0</span><span class="sxs-lookup"><span data-stu-id="54dcf-126">0</span></span> | <span data-ttu-id="54dcf-127">Вызов функции выполнен успешно.</span><span class="sxs-lookup"><span data-stu-id="54dcf-127">The function call was successful.</span></span>  |
  
## <a name="remarks"></a><span data-ttu-id="54dcf-128">Комментарии</span><span class="sxs-lookup"><span data-stu-id="54dcf-128">Remarks</span></span>

<span data-ttu-id="54dcf-129">Эта функция заключает в оболочку вызов метода [ивбемкуалифиерсет:: Get](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemqualifierset-get) .</span><span class="sxs-lookup"><span data-stu-id="54dcf-129">This function wraps a call to the [IWbemQualifierSet::Get](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemqualifierset-get) method.</span></span>

## <a name="requirements"></a><span data-ttu-id="54dcf-130">Требования</span><span class="sxs-lookup"><span data-stu-id="54dcf-130">Requirements</span></span>  

 <span data-ttu-id="54dcf-131">**Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="54dcf-131">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="54dcf-132">**Заголовок:** WMINet_Utils. idl</span><span class="sxs-lookup"><span data-stu-id="54dcf-132">**Header:** WMINet_Utils.idl</span></span>  
  
 <span data-ttu-id="54dcf-133">**.NET Framework версии:**[!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span><span class="sxs-lookup"><span data-stu-id="54dcf-133">**.NET Framework Versions:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="54dcf-134">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="54dcf-134">See also</span></span>

- [<span data-ttu-id="54dcf-135">WMI и счетчики производительности (справочник по неуправляемым API)</span><span class="sxs-lookup"><span data-stu-id="54dcf-135">WMI and Performance Counters (Unmanaged API Reference)</span></span>](index.md)
