---
title: Функция Форматфромраввалуе (Справочник по неуправляемым API)
description: Функция Форматфромраввалуе преобразует необработанные данные производительности в указанный формат.
ms.date: 11/21/2017
api_name:
- FormatFromRawValue
api_location:
- PerfCounter.dll
api_type:
- DLLExport
f1_keywords:
- FormatFromRawValue
helpviewer_keywords:
- FormatFromRawValue function [.NET WMI and performance counters]
topic_type:
- Reference
ms.openlocfilehash: e678aca5baf82c07ec9fc5c85cef22630af5ab0a
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/24/2020
ms.locfileid: "95672335"
---
# <a name="formatfromrawvalue-function"></a><span data-ttu-id="a6561-103">Функция FormatFromRawValue</span><span class="sxs-lookup"><span data-stu-id="a6561-103">FormatFromRawValue function</span></span>

<span data-ttu-id="a6561-104">Преобразует одно значение необработанных данных о производительности в указанный формат или делает это для двух значений, если преобразование формата зависит от времени.</span><span class="sxs-lookup"><span data-stu-id="a6561-104">Converts one raw performance data value to the specified format, or two raw performance data values if the format conversion is time-based.</span></span>

[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]

## <a name="syntax"></a><span data-ttu-id="a6561-105">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="a6561-105">Syntax</span></span>

```cpp
int FormatFromRawValue (
   [in] uint                    dwCounterType,
   [in] uint                    dwFormat,
   [in] long*                   pTimeBase,
   [in] PDH_RAW_COUNTER*        pRawValue1,
   [in] PDH_RAW_COUNTER*        pRawValue2,
   [out] PDH_FMT_COUNTERVALUE*  pFmtValue
);
```

## <a name="parameters"></a><span data-ttu-id="a6561-106">Параметры</span><span class="sxs-lookup"><span data-stu-id="a6561-106">Parameters</span></span>

`dwCounterType`\
<span data-ttu-id="a6561-107">окне Тип счетчика.</span><span class="sxs-lookup"><span data-stu-id="a6561-107">[in] The counter type.</span></span> <span data-ttu-id="a6561-108">Список типов счетчиков см. в разделе [типы счетчиков производительности WMI](/windows/desktop/WmiSdk/wmi-performance-counter-types).</span><span class="sxs-lookup"><span data-stu-id="a6561-108">For a list of counter types, see [WMI Performance Counter Types](/windows/desktop/WmiSdk/wmi-performance-counter-types).</span></span> <span data-ttu-id="a6561-109">`dwCounterType` может быть любым типом счетчика, за исключением `PERF_LARGE_RAW_FRACTION` и `PERF_LARGE_RAW_BASE` .</span><span class="sxs-lookup"><span data-stu-id="a6561-109">`dwCounterType` can be any counter type except for `PERF_LARGE_RAW_FRACTION` and `PERF_LARGE_RAW_BASE`.</span></span>

`dwFormat`\
<span data-ttu-id="a6561-110">окне Формат, в который преобразуются необработанные данные производительности.</span><span class="sxs-lookup"><span data-stu-id="a6561-110">[in] The format to which to convert the raw performance data.</span></span> <span data-ttu-id="a6561-111">Может иметь одно из следующих значений.</span><span class="sxs-lookup"><span data-stu-id="a6561-111">It can be one of the following values:</span></span>

|<span data-ttu-id="a6561-112">Константа</span><span class="sxs-lookup"><span data-stu-id="a6561-112">Constant</span></span>  |<span data-ttu-id="a6561-113">Значение</span><span class="sxs-lookup"><span data-stu-id="a6561-113">Value</span></span>  |<span data-ttu-id="a6561-114">Описание</span><span class="sxs-lookup"><span data-stu-id="a6561-114">Description</span></span> |
|---------|---------|---------|
| `PDH_FMT_DOUBLE` |<span data-ttu-id="a6561-115">0x00000200</span><span class="sxs-lookup"><span data-stu-id="a6561-115">0x00000200</span></span> | <span data-ttu-id="a6561-116">Возвращает вычисленное значение в виде значения с плавающей запятой двойной точности.</span><span class="sxs-lookup"><span data-stu-id="a6561-116">Return the calculated value as a double-precision floating point value.</span></span> |
| `PDH_FMT_LARGE` | <span data-ttu-id="a6561-117">0x00000400</span><span class="sxs-lookup"><span data-stu-id="a6561-117">0x00000400</span></span> | <span data-ttu-id="a6561-118">Возвращает вычисленное значение как 64-разрядное целое число.</span><span class="sxs-lookup"><span data-stu-id="a6561-118">Return the calculated value as a 64-bit integer.</span></span> |
| `PDH_FMT_LONG` | <span data-ttu-id="a6561-119">0x00000100</span><span class="sxs-lookup"><span data-stu-id="a6561-119">0x00000100</span></span> | <span data-ttu-id="a6561-120">Возвращает вычисленное значение как 32-разрядное целое число.</span><span class="sxs-lookup"><span data-stu-id="a6561-120">Return the calculated value as a 32-bit integer.</span></span> |

<span data-ttu-id="a6561-121">Одно из предыдущих значений можно ORed с помощью одного из следующих флагов масштабирования:</span><span class="sxs-lookup"><span data-stu-id="a6561-121">One of the previous values can be ORed with one of the following scaling flags:</span></span>

|<span data-ttu-id="a6561-122">Константа</span><span class="sxs-lookup"><span data-stu-id="a6561-122">Constant</span></span>  |<span data-ttu-id="a6561-123">Значение</span><span class="sxs-lookup"><span data-stu-id="a6561-123">Value</span></span>  |<span data-ttu-id="a6561-124">Описание</span><span class="sxs-lookup"><span data-stu-id="a6561-124">Description</span></span> |
|---------|---------|---------|
| `PDH_FMT_NOSCALE` | <span data-ttu-id="a6561-125">0x00001000</span><span class="sxs-lookup"><span data-stu-id="a6561-125">0x00001000</span></span> | <span data-ttu-id="a6561-126">Не применяйте коэффициенты масштабирования счетчика.</span><span class="sxs-lookup"><span data-stu-id="a6561-126">Do not apply the counter's scaling factors.</span></span> |
| `PDH_FMT_1000` | <span data-ttu-id="a6561-127">0x00002000</span><span class="sxs-lookup"><span data-stu-id="a6561-127">0x00002000</span></span> | <span data-ttu-id="a6561-128">Умножьте окончательное значение на 1 000.</span><span class="sxs-lookup"><span data-stu-id="a6561-128">Multiply the final value by 1,000.</span></span> |

`pTimeBase`\
<span data-ttu-id="a6561-129">окне Указатель на базовую базу времени, если это необходимо для преобразования формата.</span><span class="sxs-lookup"><span data-stu-id="a6561-129">[in] A pointer to the time base, if necessary for the format conversion.</span></span> <span data-ttu-id="a6561-130">Если для преобразования формата не требуется базовая информация времени, значение этого параметра игнорируется.</span><span class="sxs-lookup"><span data-stu-id="a6561-130">If time base information is not necessary for the format conversion, the value of this parameter is ignored.</span></span>

`pRawValue1`\
<span data-ttu-id="a6561-131">окне Указатель на [`PDH_RAW_COUNTER`](/windows/win32/api/pdh/ns-pdh-pdh_raw_counter) структуру, представляющую необработанное значение производительности.</span><span class="sxs-lookup"><span data-stu-id="a6561-131">[in] A pointer to a [`PDH_RAW_COUNTER`](/windows/win32/api/pdh/ns-pdh-pdh_raw_counter) structure that represents a raw performance value.</span></span>

`pRawValue2`\
<span data-ttu-id="a6561-132">окне Указатель на [`PDH_RAW_COUNTER`](/windows/win32/api/pdh/ns-pdh-pdh_raw_counter) структуру, представляющую второе необработанное значение производительности.</span><span class="sxs-lookup"><span data-stu-id="a6561-132">[in] A pointer to a [`PDH_RAW_COUNTER`](/windows/win32/api/pdh/ns-pdh-pdh_raw_counter) structure that represents a second raw performance value.</span></span> <span data-ttu-id="a6561-133">Если второе необработанное значение производительности не требуется, этот параметр должен быть равен `null` .</span><span class="sxs-lookup"><span data-stu-id="a6561-133">If a second raw performance value is not necessary, this parameter should be `null`.</span></span>

`pFmtValue`\
<span data-ttu-id="a6561-134">заполняет Указатель на [`PDH_FMT_COUNTERVALUE`](/windows/win32/api/pdh/ns-pdh-pdh_fmt_countervalue) структуру, получающую отформатированное значение производительности.</span><span class="sxs-lookup"><span data-stu-id="a6561-134">[out] A pointer to a [`PDH_FMT_COUNTERVALUE`](/windows/win32/api/pdh/ns-pdh-pdh_fmt_countervalue) structure that receives the formatted performance value.</span></span>

## <a name="return-value"></a><span data-ttu-id="a6561-135">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="a6561-135">Return value</span></span>

<span data-ttu-id="a6561-136">Эта функция возвращает следующие значения:</span><span class="sxs-lookup"><span data-stu-id="a6561-136">The following values are returned by this function:</span></span>

|<span data-ttu-id="a6561-137">Константа</span><span class="sxs-lookup"><span data-stu-id="a6561-137">Constant</span></span>  |<span data-ttu-id="a6561-138">Значение</span><span class="sxs-lookup"><span data-stu-id="a6561-138">Value</span></span>  |<span data-ttu-id="a6561-139">Описание</span><span class="sxs-lookup"><span data-stu-id="a6561-139">Description</span></span>  |
|---------|---------|---------|
| `ERROR_SUCCESS` | <span data-ttu-id="a6561-140">0</span><span class="sxs-lookup"><span data-stu-id="a6561-140">0</span></span> | <span data-ttu-id="a6561-141">Вызов функции выполнен успешно.</span><span class="sxs-lookup"><span data-stu-id="a6561-141">The function call is successful.</span></span> |
| `PDH_INVALID_ARGUMENT` | <span data-ttu-id="a6561-142">0xC0000BBD</span><span class="sxs-lookup"><span data-stu-id="a6561-142">0xC0000BBD</span></span> | <span data-ttu-id="a6561-143">Обязательный аргумент отсутствует или неверен.</span><span class="sxs-lookup"><span data-stu-id="a6561-143">A required argument is missing or incorrect.</span></span> |
| `PDH_INVALID_HANDLE` | <span data-ttu-id="a6561-144">0xC0000BBC</span><span class="sxs-lookup"><span data-stu-id="a6561-144">0xC0000BBC</span></span> | <span data-ttu-id="a6561-145">Этот маркер не является допустимым объектом PDH.</span><span class="sxs-lookup"><span data-stu-id="a6561-145">The handle is not a valid PDH object.</span></span> |

## <a name="remarks"></a><span data-ttu-id="a6561-146">Комментарии</span><span class="sxs-lookup"><span data-stu-id="a6561-146">Remarks</span></span>

<span data-ttu-id="a6561-147">Эта функция заключает в оболочку вызов функции [форматфромраввалуе](/previous-versions/ms231047(v=vs.85)) .</span><span class="sxs-lookup"><span data-stu-id="a6561-147">This function wraps a call to the [FormatFromRawValue](/previous-versions/ms231047(v=vs.85)) function.</span></span>

## <a name="requirements"></a><span data-ttu-id="a6561-148">Требования</span><span class="sxs-lookup"><span data-stu-id="a6561-148">Requirements</span></span>

 <span data-ttu-id="a6561-149">**Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="a6561-149">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>

 <span data-ttu-id="a6561-150">**Библиотека:** PerfCounter.dll</span><span class="sxs-lookup"><span data-stu-id="a6561-150">**Library:** PerfCounter.dll</span></span>

 <span data-ttu-id="a6561-151">**.NET Framework версии:**[!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span><span class="sxs-lookup"><span data-stu-id="a6561-151">**.NET Framework Versions:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span></span>

## <a name="see-also"></a><span data-ttu-id="a6561-152">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="a6561-152">See also</span></span>

- [<span data-ttu-id="a6561-153">WMI и счетчики производительности (справочник по неуправляемым API)</span><span class="sxs-lookup"><span data-stu-id="a6561-153">WMI and Performance Counters (Unmanaged API Reference)</span></span>](index.md)
