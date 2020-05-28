---
title: Метод IMetaDataEmit::DefineMethod
ms.date: 03/30/2017
api_name:
- IMetaDataEmit.DefineMethod
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataEmit::DefineMethod
helpviewer_keywords:
- DefineMethod method [.NET Framework metadata]
- IMetaDataEmit::DefineMethod method [.NET Framework metadata]
ms.assetid: 3e2102c5-48b7-4c0e-b805-7e2b5e156e3d
topic_type:
- apiref
ms.openlocfilehash: 514f227e3c0c385f61090079d2f5214dac9b3924
ms.sourcegitcommit: 03fec33630b46e78d5e81e91b40518f32c4bd7b5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/27/2020
ms.locfileid: "84004534"
---
# <a name="imetadataemitdefinemethod-method"></a><span data-ttu-id="113ce-102">Метод IMetaDataEmit::DefineMethod</span><span class="sxs-lookup"><span data-stu-id="113ce-102">IMetaDataEmit::DefineMethod Method</span></span>
<span data-ttu-id="113ce-103">Создает определение для метода или глобальной функции с указанной сигнатурой и возвращает маркер в это определение метода.</span><span class="sxs-lookup"><span data-stu-id="113ce-103">Creates a definition for a method or global function with the specified signature, and returns a token to that method definition.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="113ce-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="113ce-104">Syntax</span></span>  
  
```cpp  
HRESULT DefineMethod (
    [in]  mdTypeDef         td,
    [in]  LPCWSTR           szName,
    [in]  DWORD             dwMethodFlags,
    [in]  PCCOR_SIGNATURE   pvSigBlob,
    [in]  ULONG             cbSigBlob,
    [in]  ULONG             ulCodeRVA,
    [in]  DWORD             dwImplFlags,
    [out] mdMethodDef      *pmd  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="113ce-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="113ce-105">Parameters</span></span>  
 `td`  
 <span data-ttu-id="113ce-106">окне `mdTypedef`Маркер родительского класса или родительского интерфейса метода.</span><span class="sxs-lookup"><span data-stu-id="113ce-106">[in] The `mdTypedef` token of the parent class or parent interface of the method.</span></span> <span data-ttu-id="113ce-107">Задайте `td` значение `mdTokenNil` , если вы определяете глобальную функцию.</span><span class="sxs-lookup"><span data-stu-id="113ce-107">Set `td` to `mdTokenNil`, if you are defining a global function.</span></span>  
  
 `szName`  
 <span data-ttu-id="113ce-108">окне Имя члена в Юникоде.</span><span class="sxs-lookup"><span data-stu-id="113ce-108">[in] The member name in Unicode.</span></span>  
  
 `dwMethodFlags`  
 <span data-ttu-id="113ce-109">окне Значение перечисления [кормесодаттр](cormethodattr-enumeration.md) , определяющее атрибуты метода или глобальной функции.</span><span class="sxs-lookup"><span data-stu-id="113ce-109">[in] A value of the [CorMethodAttr](cormethodattr-enumeration.md) enumeration that specifies the attributes of the method or global function.</span></span>  
  
 `pvSigBlob`  
 <span data-ttu-id="113ce-110">окне Сигнатура метода.</span><span class="sxs-lookup"><span data-stu-id="113ce-110">[in] The method signature.</span></span> <span data-ttu-id="113ce-111">Подпись сохраняется, как указано.</span><span class="sxs-lookup"><span data-stu-id="113ce-111">The signature is persisted as supplied.</span></span> <span data-ttu-id="113ce-112">Если необходимо указать дополнительные сведения для всех параметров, используйте метод [IMetaDataEmit:: сетпарампропс](imetadataemit-setparamprops-method.md) .</span><span class="sxs-lookup"><span data-stu-id="113ce-112">If you need to specify additional information for any parameters, use the [IMetaDataEmit::SetParamProps](imetadataemit-setparamprops-method.md) method.</span></span>  
  
 `cbSigBlob`  
 <span data-ttu-id="113ce-113">окне Число байтов в `pvSigBlob` .</span><span class="sxs-lookup"><span data-stu-id="113ce-113">[in] The count of bytes in `pvSigBlob`.</span></span>  
  
 `ulCodeRVA`  
 <span data-ttu-id="113ce-114">окне Адрес кода.</span><span class="sxs-lookup"><span data-stu-id="113ce-114">[in] The address of the code.</span></span>  
  
 `dwImplFlags`  
 <span data-ttu-id="113ce-115">окне Значение перечисления [кормесодимпл](cormethodimpl-enumeration.md) , указывающее функции реализации метода.</span><span class="sxs-lookup"><span data-stu-id="113ce-115">[in] A value of the [CorMethodImpl](cormethodimpl-enumeration.md) enumeration that specifies the implementation features of the method.</span></span>  
  
 `pmd`  
 <span data-ttu-id="113ce-116">заполняет Токен элемента.</span><span class="sxs-lookup"><span data-stu-id="113ce-116">[out] The member token.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="113ce-117">Примечания</span><span class="sxs-lookup"><span data-stu-id="113ce-117">Remarks</span></span>  
 <span data-ttu-id="113ce-118">API метаданных гарантирует сохранение методов в том же порядке, в котором вызывающий объект создает их для данного включающего класса или интерфейса, указанного в `td` параметре.</span><span class="sxs-lookup"><span data-stu-id="113ce-118">The metadata API guarantees to persist methods in the same order as the caller emits them for a given enclosing class or interface, which is specified in the `td` parameter.</span></span>  
  
 <span data-ttu-id="113ce-119">Дополнительные сведения об использовании `DefineMethod` и определенных параметрах параметров приведены ниже.</span><span class="sxs-lookup"><span data-stu-id="113ce-119">Additional information regarding the use of `DefineMethod` and particular parameter settings is given below.</span></span>  
  
## <a name="slots-in-the-v-table"></a><span data-ttu-id="113ce-120">Слоты в таблице V-Table</span><span class="sxs-lookup"><span data-stu-id="113ce-120">Slots in the V-table</span></span>  
 <span data-ttu-id="113ce-121">Среда выполнения использует определения методов для настройки слотов v-table.</span><span class="sxs-lookup"><span data-stu-id="113ce-121">The runtime uses method definitions to set up v-table slots.</span></span> <span data-ttu-id="113ce-122">В случае, когда необходимо пропустить один или несколько слотов, например для сохранения четности с помощью макета COM-интерфейса, будет определен фиктивный метод, который занимает область или слоты в таблице v-table. Присвойте свойству `dwMethodFlags` `mdRTSpecialName` значение перечисления [кормесодаттр](cormethodattr-enumeration.md) и укажите имя:</span><span class="sxs-lookup"><span data-stu-id="113ce-122">In the case where one or more slots need to be skipped, such as to preserve parity with a COM interface layout, a dummy method is defined to take up the slot or slots in the v-table; set the `dwMethodFlags` to the `mdRTSpecialName` value of the [CorMethodAttr](cormethodattr-enumeration.md) enumeration and specify the name as:</span></span>  
  
 <span data-ttu-id="113ce-123">_VtblGap\<*SequenceNumber*>\<\_*CountOfSlots*></span><span class="sxs-lookup"><span data-stu-id="113ce-123">_VtblGap\<*SequenceNumber*>\<\_*CountOfSlots*></span></span>
  
 <span data-ttu-id="113ce-124">где *SequenceNumber* — порядковый номер метода, а *каунтофслотс* — число слотов для пропуска в таблице v-table.</span><span class="sxs-lookup"><span data-stu-id="113ce-124">where *SequenceNumber* is the sequence number of the method and *CountOfSlots* is the number of slots to skip in the v-table.</span></span> <span data-ttu-id="113ce-125">Если *каунтофслотс* опущен, то предполагается значение 1.</span><span class="sxs-lookup"><span data-stu-id="113ce-125">If *CountOfSlots* is omitted, 1 is assumed.</span></span> <span data-ttu-id="113ce-126">Эти фиктивные методы не могут быть вызываемыми из управляемого или неуправляемого кода и любая попытка их вызова из управляемого или неуправляемого кода создает исключение.</span><span class="sxs-lookup"><span data-stu-id="113ce-126">These dummy methods are not callable from either managed or unmanaged code and any attempt to call them, from either managed or unmanaged code, generates an exception.</span></span> <span data-ttu-id="113ce-127">Их единственная задача состоит в том, чтобы освободить место в таблице v-table, которую среда выполнения создает для интеграции COM.</span><span class="sxs-lookup"><span data-stu-id="113ce-127">Their only purpose is to take up space in the v-table that the runtime generates for COM integration.</span></span>  
  
## <a name="duplicate-methods"></a><span data-ttu-id="113ce-128">Дублирующиеся методы</span><span class="sxs-lookup"><span data-stu-id="113ce-128">Duplicate Methods</span></span>  
 <span data-ttu-id="113ce-129">Не следует определять дублирующиеся методы.</span><span class="sxs-lookup"><span data-stu-id="113ce-129">You should not define duplicate methods.</span></span> <span data-ttu-id="113ce-130">Это значит, что не следует вызывать `DefineMethod` с помощью повторяющегося набора значений в `td` `wzName` `pvSig` параметрах, и.</span><span class="sxs-lookup"><span data-stu-id="113ce-130">That is, you should not call `DefineMethod` with a duplicate set of values in the `td`, `wzName`, and `pvSig` parameters.</span></span> <span data-ttu-id="113ce-131">(Эти три параметра вместе уникально определяют метод.)</span><span class="sxs-lookup"><span data-stu-id="113ce-131">(These three parameters together uniquely define the method.).</span></span> <span data-ttu-id="113ce-132">Однако можно использовать повторяющееся тройное значение, если для одного из определений методов задается `mdPrivateScope` бит в `dwMethodFlags` параметре.</span><span class="sxs-lookup"><span data-stu-id="113ce-132">However, you can use a duplicate triple provided that, for one of the method definitions, you set the `mdPrivateScope` bit in the `dwMethodFlags` parameter.</span></span> <span data-ttu-id="113ce-133">( `mdPrivateScope` Бит означает, что компилятор не будет создавать ссылку на это определение метода.)</span><span class="sxs-lookup"><span data-stu-id="113ce-133">(The `mdPrivateScope` bit means that the compiler will not emit a reference to this method definition.)</span></span>  
  
## <a name="method-implementation-information"></a><span data-ttu-id="113ce-134">Сведения о реализации метода</span><span class="sxs-lookup"><span data-stu-id="113ce-134">Method Implementation Information</span></span>  
 <span data-ttu-id="113ce-135">Сведения о реализации метода часто неизвестны во время объявления метода.</span><span class="sxs-lookup"><span data-stu-id="113ce-135">Information about the method implementation is often not known at the time the method is declared.</span></span> <span data-ttu-id="113ce-136">Поэтому при вызове не нужно передавать значения в `ulCodeRVA` `dwImplFlags` параметрах и `DefineMethod` .</span><span class="sxs-lookup"><span data-stu-id="113ce-136">Therefore, you do not need to pass values in the `ulCodeRVA` and `dwImplFlags` parameters when calling `DefineMethod`.</span></span> <span data-ttu-id="113ce-137">Значения можно указать позже с помощью [IMetaDataEmit:: сетмесодимплфлагс](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-setmethodimplflags-method.md) или [IMetaDataEmit:: SetRVA](imetadataemit-setrva-method.md).</span><span class="sxs-lookup"><span data-stu-id="113ce-137">The values can be supplied later through [IMetaDataEmit::SetMethodImplFlags](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-setmethodimplflags-method.md) or [IMetaDataEmit::SetRVA](imetadataemit-setrva-method.md), as appropriate.</span></span>  
  
 <span data-ttu-id="113ce-138">В некоторых ситуациях, например при вызове платформы (PInvoke) или в сценариях COM-взаимодействия, тело метода не будет передано и `ulCodeRVA` должно быть установлено в ноль.</span><span class="sxs-lookup"><span data-stu-id="113ce-138">In some situations, such as platform invocation (PInvoke) or COM interop scenarios, the method body will not be supplied, and `ulCodeRVA` should be set to zero.</span></span> <span data-ttu-id="113ce-139">В таких ситуациях метод не должен помечаться как абстрактный, поскольку среда выполнения обнаружит реализацию.</span><span class="sxs-lookup"><span data-stu-id="113ce-139">In these situations, the method should not be tagged as abstract, because the runtime will locate the implementation.</span></span>  
  
## <a name="defining-a-method-for-pinvoke"></a><span data-ttu-id="113ce-140">Определение метода для PInvoke</span><span class="sxs-lookup"><span data-stu-id="113ce-140">Defining a Method for PInvoke</span></span>  
 <span data-ttu-id="113ce-141">Для вызова каждой неуправляемой функции через PInvoke необходимо определить управляемый метод, представляющий целевую неуправляемую функцию.</span><span class="sxs-lookup"><span data-stu-id="113ce-141">For each unmanaged function to be called through PInvoke, you must define a managed method that represents the target unmanaged function.</span></span> <span data-ttu-id="113ce-142">Чтобы определить управляемый метод, используйте `DefineMethod` с некоторыми параметрами, заданными определенными значениями, в зависимости от способа использования PInvoke:</span><span class="sxs-lookup"><span data-stu-id="113ce-142">To define the managed method, use `DefineMethod` with some of the parameters set to certain values, depending on the way in which PInvoke is used:</span></span>  
  
- <span data-ttu-id="113ce-143">True PInvoke — включает вызов внешнего неуправляемого метода, который находится в неуправляемой библиотеке DLL.</span><span class="sxs-lookup"><span data-stu-id="113ce-143">True PInvoke - involves invocation of an external unmanaged method that resides in an unmanaged DLL.</span></span>  
  
- <span data-ttu-id="113ce-144">Локальный PInvoke — включает вызов собственного неуправляемого метода, внедренного в текущий управляемый модуль.</span><span class="sxs-lookup"><span data-stu-id="113ce-144">Local PInvoke - involves invocation of a native unmanaged method that is embedded in the current managed module.</span></span>  
  
 <span data-ttu-id="113ce-145">Параметры параметров приведены в следующей таблице.</span><span class="sxs-lookup"><span data-stu-id="113ce-145">The parameter settings are given in the following table.</span></span>  
  
|<span data-ttu-id="113ce-146">Параметр</span><span class="sxs-lookup"><span data-stu-id="113ce-146">Parameter</span></span>|<span data-ttu-id="113ce-147">Значения для истинного PInvoke</span><span class="sxs-lookup"><span data-stu-id="113ce-147">Values for true PInvoke</span></span>|<span data-ttu-id="113ce-148">Значения для локального вызова PInvoke</span><span class="sxs-lookup"><span data-stu-id="113ce-148">Values for local PInvoke</span></span>|  
|---------------|-----------------------------|------------------------------|  
|`dwMethodFlags`||<span data-ttu-id="113ce-149">Set `mdStatic` ; clear `mdSynchronized` и `mdAbstract` .</span><span class="sxs-lookup"><span data-stu-id="113ce-149">Set `mdStatic`; clear `mdSynchronized` and `mdAbstract`.</span></span>|  
|`pvSigBlob`|<span data-ttu-id="113ce-150">Допустимая сигнатура метода общеязыковой среды выполнения (CLR) с параметрами, которые являются допустимыми управляемыми типами.</span><span class="sxs-lookup"><span data-stu-id="113ce-150">A valid common language runtime (CLR) method signature with parameters that are valid managed types.</span></span>|<span data-ttu-id="113ce-151">Допустимая сигнатура метода CLR с параметрами, которые являются допустимыми управляемыми типами.</span><span class="sxs-lookup"><span data-stu-id="113ce-151">A valid CLR method signature with parameters that are valid managed types.</span></span>|  
|`ulCodeRVA`||<span data-ttu-id="113ce-152">0</span><span class="sxs-lookup"><span data-stu-id="113ce-152">0</span></span>|  
|`dwImplFlags`|<span data-ttu-id="113ce-153">Задайте значения для `miCil` и `miManaged`.</span><span class="sxs-lookup"><span data-stu-id="113ce-153">Set `miCil` and `miManaged`.</span></span>|<span data-ttu-id="113ce-154">Задайте значения для `miNative` и `miUnmanaged`.</span><span class="sxs-lookup"><span data-stu-id="113ce-154">Set `miNative` and `miUnmanaged`.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="113ce-155">Требования</span><span class="sxs-lookup"><span data-stu-id="113ce-155">Requirements</span></span>  
 <span data-ttu-id="113ce-156">**Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="113ce-156">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="113ce-157">**Заголовок:** COR. h</span><span class="sxs-lookup"><span data-stu-id="113ce-157">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="113ce-158">**Библиотека:** Используется в качестве ресурса в MSCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="113ce-158">**Library:** Used as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="113ce-159">**.NET Framework версии:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="113ce-159">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="113ce-160">См. также статью</span><span class="sxs-lookup"><span data-stu-id="113ce-160">See also</span></span>

- [<span data-ttu-id="113ce-161">Интерфейс IMetaDataEmit</span><span class="sxs-lookup"><span data-stu-id="113ce-161">IMetaDataEmit Interface</span></span>](imetadataemit-interface.md)
- [<span data-ttu-id="113ce-162">Интерфейс IMetaDataEmit2</span><span class="sxs-lookup"><span data-stu-id="113ce-162">IMetaDataEmit2 Interface</span></span>](imetadataemit2-interface.md)
