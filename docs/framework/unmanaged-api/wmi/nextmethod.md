---
title: Функция Некстмесод (Справочник по неуправляемым API)
description: Функция Некстмесод извлекает следующий метод в перечислении.
ms.date: 11/06/2017
api_name:
- NextMethod
api_location:
- WMINet_Utils.dll
api_type:
- DLLExport
f1_keywords:
- NextMethod
helpviewer_keywords:
- NextMethod function [.NET WMI and performance counters]
topic_type:
- Reference
ms.openlocfilehash: a0466aee47b0a6142870640c78b43f49e221ac2b
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/24/2020
ms.locfileid: "95726773"
---
# <a name="nextmethod-function"></a><span data-ttu-id="6e2ae-103">Функция NextMethod</span><span class="sxs-lookup"><span data-stu-id="6e2ae-103">NextMethod function</span></span>

<span data-ttu-id="6e2ae-104">Извлекает следующий метод в перечислении, который начинается с вызова [бегинмесоденумератион](beginmethodenumeration.md).</span><span class="sxs-lookup"><span data-stu-id="6e2ae-104">Retrieves the next method in an enumeration that begins with a call to [BeginMethodEnumeration](beginmethodenumeration.md).</span></span>  

[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]
  
## <a name="syntax"></a><span data-ttu-id="6e2ae-105">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="6e2ae-105">Syntax</span></span>  
  
```cpp  
HRESULT NextMethod (
   [in] int                 vFunc,
   [in] IWbemClassObject*   ptr,
   [in] LONG                lFlags,
   [out] BSTR*              pName,
   [out] IWbemClassObject** ppInSignature,
   [out] IWbemClassObject** ppOutSignature
);
```  

## <a name="parameters"></a><span data-ttu-id="6e2ae-106">Параметры</span><span class="sxs-lookup"><span data-stu-id="6e2ae-106">Parameters</span></span>

`vFunc`  
<span data-ttu-id="6e2ae-107">окне Этот параметр не используется.</span><span class="sxs-lookup"><span data-stu-id="6e2ae-107">[in] This parameter is unused.</span></span>

`ptr`  
<span data-ttu-id="6e2ae-108">окне Указатель на экземпляр [ивбемклассобжект](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject) .</span><span class="sxs-lookup"><span data-stu-id="6e2ae-108">[in] A pointer to an [IWbemClassObject](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject) instance.</span></span>

`lFlags`  
<span data-ttu-id="6e2ae-109">[in] Зарезервировано.</span><span class="sxs-lookup"><span data-stu-id="6e2ae-109">[in] Reserved.</span></span> <span data-ttu-id="6e2ae-110">Этот параметр должен иметь значение 0.</span><span class="sxs-lookup"><span data-stu-id="6e2ae-110">This parameter must be 0.</span></span>

`pName`  
<span data-ttu-id="6e2ae-111">заполняет Указатель, указывающий на `null` перед вызовом.</span><span class="sxs-lookup"><span data-stu-id="6e2ae-111">[out] A pointer that points to `null` prior to the call.</span></span> <span data-ttu-id="6e2ae-112">Когда функция возвращает, адрес нового `BSTR` , который содержит имя метода.</span><span class="sxs-lookup"><span data-stu-id="6e2ae-112">When the function returns, the address of a new `BSTR` that contains the method name.</span></span>

`ppSignatureIn`  
<span data-ttu-id="6e2ae-113">заполняет Указатель, получающий указатель на объект [ивбемклассобжект](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject) , содержащий `in` параметры для метода.</span><span class="sxs-lookup"><span data-stu-id="6e2ae-113">[out] A pointer that receives a pointer to an [IWbemClassObject](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject) that contains the `in` parameters for the method.</span></span>

`ppSignatureOut`  
<span data-ttu-id="6e2ae-114">заполняет Указатель, получающий указатель на объект [ивбемклассобжект](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject) , содержащий `out` параметры для метода.</span><span class="sxs-lookup"><span data-stu-id="6e2ae-114">[out] A pointer that receives a pointer to an [IWbemClassObject](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject) that contains the `out` parameters for the method.</span></span>

## <a name="return-value"></a><span data-ttu-id="6e2ae-115">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="6e2ae-115">Return value</span></span>

<span data-ttu-id="6e2ae-116">Следующие значения, возвращаемые этой функцией, определены в файле заголовка *вбемкли. h* , или их можно определить как константы в коде:</span><span class="sxs-lookup"><span data-stu-id="6e2ae-116">The following values returned by this function are defined in the *WbemCli.h* header file, or you can define them as constants in your code:</span></span>

|<span data-ttu-id="6e2ae-117">Константа</span><span class="sxs-lookup"><span data-stu-id="6e2ae-117">Constant</span></span>  |<span data-ttu-id="6e2ae-118">Значение</span><span class="sxs-lookup"><span data-stu-id="6e2ae-118">Value</span></span>  |<span data-ttu-id="6e2ae-119">Описание</span><span class="sxs-lookup"><span data-stu-id="6e2ae-119">Description</span></span>  |
|---------|---------|---------|
| `WBEM_E_UNEXPECTED` | <span data-ttu-id="6e2ae-120">0x8004101d</span><span class="sxs-lookup"><span data-stu-id="6e2ae-120">0x8004101d</span></span> | <span data-ttu-id="6e2ae-121">Нет вызова [`BeginEnumeration`](beginenumeration.md) функции.</span><span class="sxs-lookup"><span data-stu-id="6e2ae-121">There was no call to the [`BeginEnumeration`](beginenumeration.md) function.</span></span> |
| `WBEM_S_NO_ERROR` | <span data-ttu-id="6e2ae-122">0</span><span class="sxs-lookup"><span data-stu-id="6e2ae-122">0</span></span> | <span data-ttu-id="6e2ae-123">Вызов функции выполнен успешно.</span><span class="sxs-lookup"><span data-stu-id="6e2ae-123">The function call was successful.</span></span>  |
| `WBEM_S_NO_MORE_DATA` | <span data-ttu-id="6e2ae-124">0x40005</span><span class="sxs-lookup"><span data-stu-id="6e2ae-124">0x40005</span></span> | <span data-ttu-id="6e2ae-125">В перечислении больше нет свойств.</span><span class="sxs-lookup"><span data-stu-id="6e2ae-125">There are no more properties in the enumeration.</span></span> |
  
## <a name="remarks"></a><span data-ttu-id="6e2ae-126">Комментарии</span><span class="sxs-lookup"><span data-stu-id="6e2ae-126">Remarks</span></span>

<span data-ttu-id="6e2ae-127">Эта функция заключает в оболочку вызов метода [ивбемклассобжект:: некстмесод](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemclassobject-nextmethod) .</span><span class="sxs-lookup"><span data-stu-id="6e2ae-127">This function wraps a call to the [IWbemClassObject::NextMethod](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemclassobject-nextmethod) method.</span></span>

<span data-ttu-id="6e2ae-128">Вызывающий объект начинает последовательность перечисления, вызывая функцию [бегинмесоденумератион](beginmethodenumeration.md) , а затем вызывает функцию [некстмесод] до тех пор, пока функция не вернет значение `WBEM_S_NO_MORE_DATA` .</span><span class="sxs-lookup"><span data-stu-id="6e2ae-128">The caller begins the enumeration sequence by calling the [BeginMethodEnumeration](beginmethodenumeration.md) function, and then calls the [NextMethod] function until the function returns `WBEM_S_NO_MORE_DATA`.</span></span> <span data-ttu-id="6e2ae-129">При необходимости вызывающий объект завершает последовательность путем вызова [ендмесоденумератион](endmethodenumeration.md).</span><span class="sxs-lookup"><span data-stu-id="6e2ae-129">Optionally, the caller finishes the sequence by calling [EndMethodEnumeration](endmethodenumeration.md).</span></span> <span data-ttu-id="6e2ae-130">Вызывающий объект может завершить перечисление раньше, вызвав [ендмесоденумератион](endmethodenumeration.md) в любое время.</span><span class="sxs-lookup"><span data-stu-id="6e2ae-130">The caller may terminate the enumeration early by calling [EndMethodEnumeration](endmethodenumeration.md) at any time.</span></span>

## <a name="example"></a><span data-ttu-id="6e2ae-131">Пример</span><span class="sxs-lookup"><span data-stu-id="6e2ae-131">Example</span></span>

<span data-ttu-id="6e2ae-132">Пример для C++ см. в описании метода [ивбемклассобжект:: некстмесод](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemclassobject-nextmethod) .</span><span class="sxs-lookup"><span data-stu-id="6e2ae-132">For a C++ example, see the [IWbemClassObject::NextMethod](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemclassobject-nextmethod) method.</span></span>

## <a name="requirements"></a><span data-ttu-id="6e2ae-133">Требования</span><span class="sxs-lookup"><span data-stu-id="6e2ae-133">Requirements</span></span>  

 <span data-ttu-id="6e2ae-134">**Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="6e2ae-134">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="6e2ae-135">**Заголовок:** WMINet_Utils. idl</span><span class="sxs-lookup"><span data-stu-id="6e2ae-135">**Header:** WMINet_Utils.idl</span></span>  
  
 <span data-ttu-id="6e2ae-136">**.NET Framework версии:**[!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span><span class="sxs-lookup"><span data-stu-id="6e2ae-136">**.NET Framework Versions:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6e2ae-137">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="6e2ae-137">See also</span></span>

- [<span data-ttu-id="6e2ae-138">WMI и счетчики производительности (справочник по неуправляемым API)</span><span class="sxs-lookup"><span data-stu-id="6e2ae-138">WMI and Performance Counters (Unmanaged API Reference)</span></span>](index.md)
