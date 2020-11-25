---
title: Структура DacpMethodDescData
ms.date: 02/01/2019
api.name:
- DacpMethodDescData Structure
api.location:
- mscordacwks.dll
api.type:
- COM
f1.keywords:
- DacpMethodDescData Structure
helpviewer.keywords:
- DacpMethodDescData Structure [.NET Framework debugging]
topic_type:
- apiref
author: hoyosjs
ms.author: juhoyosa
ms.openlocfilehash: dcf01c00a106c131646a16597dca4092a06c5983
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/24/2020
ms.locfileid: "95723068"
---
# <a name="dacpmethoddescdata-structure"></a><span data-ttu-id="ed44a-102">Структура DacpMethodDescData</span><span class="sxs-lookup"><span data-stu-id="ed44a-102">DacpMethodDescData Structure</span></span>

<span data-ttu-id="ed44a-103">Определяет транспортный буфер для сведений о среде выполнения метода.</span><span class="sxs-lookup"><span data-stu-id="ed44a-103">Defines a transport buffer for a method's runtime information.</span></span>

[!INCLUDE[debugging-api-recommended-note](../../../../includes/debugging-api-recommended-note.md)]

## <a name="syntax"></a><span data-ttu-id="ed44a-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="ed44a-104">Syntax</span></span>

```cpp
struct DacpMethodDescData
{
    int             bHasNativeCode;
    int             bIsDynamic;
    unsigned short  wSlotNumber;
    CLRDATA_ADDRESS NativeCodeAddr;
    CLRDATA_ADDRESS data;
    CLRDATA_ADDRESS MethodDescPtr;
    CLRDATA_ADDRESS nativeCodeInfo;
    CLRDATA_ADDRESS moduleInfo;
    mdToken         MDToken;
    CLRDATA_ADDRESS payloadGC;
    CLRDATA_ADDRESS payloadGC2;
    CLRDATA_ADDRESS managedDynamicMethodObject;
    CLRDATA_ADDRESS requestedIP;
    DacpReJitData   rejitDataCurrent;
    DacpReJitData   rejitDataRequested;
    unsigned long   cJittedRejitVersions;
};
```

## <a name="members"></a><span data-ttu-id="ed44a-105">Члены</span><span class="sxs-lookup"><span data-stu-id="ed44a-105">Members</span></span>

| <span data-ttu-id="ed44a-106">Член</span><span class="sxs-lookup"><span data-stu-id="ed44a-106">Member</span></span>                       | <span data-ttu-id="ed44a-107">Описание</span><span class="sxs-lookup"><span data-stu-id="ed44a-107">Description</span></span>                                                                                     |
| ---------------------------- | ----------------------------------------------------------------------------------------------- |
| `bHasNativeCode`             | <span data-ttu-id="ed44a-108">Указывает, доступен ли в среде выполнения машинный код для данного экземпляра метода.</span><span class="sxs-lookup"><span data-stu-id="ed44a-108">Indicates if the runtime has native code available for the given instantiation of the method.</span></span> |
| `bIsDynamic`                 | <span data-ttu-id="ed44a-109">Указывает, создается ли метод динамически с помощью создания упрощенного кода.</span><span class="sxs-lookup"><span data-stu-id="ed44a-109">Indicates if the method is generated dynamically through lightweight code generation.</span></span>           |
| `wSlotNumber`                | <span data-ttu-id="ed44a-110">Номер слота метода в таблице методов.</span><span class="sxs-lookup"><span data-stu-id="ed44a-110">The method's slot number in the method table.</span></span>                                                   |
| `NativeCodeAddr`             | <span data-ttu-id="ed44a-111">Начальный собственный адрес метода.</span><span class="sxs-lookup"><span data-stu-id="ed44a-111">The method's initial native address.</span></span>                                                            |
| `data`                       | <span data-ttu-id="ed44a-112">Указатель на буфер, который используется средой выполнения для внутренних целей.</span><span class="sxs-lookup"><span data-stu-id="ed44a-112">Pointer to a buffer used internally by the runtime.</span></span>                                             |
| `MethodDescPtr`              | <span data-ttu-id="ed44a-113">Указатель на объект `MethodDesc` в среде выполнения.</span><span class="sxs-lookup"><span data-stu-id="ed44a-113">Pointer to the `MethodDesc` in the runtime.</span></span>                                                     |
| `nativeCodeInfo`             | <span data-ttu-id="ed44a-114">Указатель на буфер, используемый средой выполнения для трассировки методов.</span><span class="sxs-lookup"><span data-stu-id="ed44a-114">Pointer to a buffer used internally by the runtime to track methods.</span></span>                            |
| `moduleInfo`                 | <span data-ttu-id="ed44a-115">Указатель на буфер, используемый средой выполнения для сведений о модуле.</span><span class="sxs-lookup"><span data-stu-id="ed44a-115">Pointer to a buffer used internally by the runtime for module information.</span></span>                      |
| `MDToken`                    | <span data-ttu-id="ed44a-116">Токен, связанный с данным методом.</span><span class="sxs-lookup"><span data-stu-id="ed44a-116">Token associated with the given method.</span></span>                                                         |
| `payloadGC`                  | <span data-ttu-id="ed44a-117">Указатель на буфер сборки мусора, который используется средой выполнения для внутренних целей.</span><span class="sxs-lookup"><span data-stu-id="ed44a-117">Pointer to a garbage collection buffer used internally by the runtime.</span></span>                          |
| `payloadGC2`                 | <span data-ttu-id="ed44a-118">Указатель на буфер сборки мусора, который используется средой выполнения для внутренних целей.</span><span class="sxs-lookup"><span data-stu-id="ed44a-118">Pointer to a garbage collection buffer used internally by the runtime.</span></span>                          |
| `managedDynamicMethodObject` | <span data-ttu-id="ed44a-119">Если метод является динамическим, среда выполнения использует этот буфер для внутреннего отслеживания сведений.</span><span class="sxs-lookup"><span data-stu-id="ed44a-119">If the method is dynamic, the runtime uses this buffer internally for information tracking.</span></span>     |
| `requestedIP`                | <span data-ttu-id="ed44a-120">Используется для заполнения структуры на запрос при наличии адреса машинного кода.</span><span class="sxs-lookup"><span data-stu-id="ed44a-120">Used to populate the structure per request when given a native code address.</span></span>                    |
| `rejitDataCurrent`           | <span data-ttu-id="ed44a-121">Сведения о последней инструментированной версии метода.</span><span class="sxs-lookup"><span data-stu-id="ed44a-121">Information about the latest instrumented version of the method.</span></span>                                   |
| `rejitDataRequested`         | <span data-ttu-id="ed44a-122">Rejit сведения для запрошенного собственного адреса.</span><span class="sxs-lookup"><span data-stu-id="ed44a-122">Rejit information for the requested native address.</span></span>                                             |
| `cJittedRejitVersions`       | <span data-ttu-id="ed44a-123">Сколько раз метод был режиттед с помощью инструментирования.</span><span class="sxs-lookup"><span data-stu-id="ed44a-123">Number of times the method has been rejitted through instrumentation.</span></span>                           |

## <a name="remarks"></a><span data-ttu-id="ed44a-124">Комментарии</span><span class="sxs-lookup"><span data-stu-id="ed44a-124">Remarks</span></span>

<span data-ttu-id="ed44a-125">Эта структура находится внутри среды выполнения и не предоставляется через все файлы заголовков или библиотек.</span><span class="sxs-lookup"><span data-stu-id="ed44a-125">This structure lives inside the runtime and is not exposed through any headers or library files.</span></span> <span data-ttu-id="ed44a-126">Чтобы использовать его, определите структуру, как указано выше.</span><span class="sxs-lookup"><span data-stu-id="ed44a-126">To use it, define the structure as specified above.</span></span>

## <a name="requirements"></a><span data-ttu-id="ed44a-127">Требования</span><span class="sxs-lookup"><span data-stu-id="ed44a-127">Requirements</span></span>

<span data-ttu-id="ed44a-128">**Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="ed44a-128">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
<span data-ttu-id="ed44a-129">**Заголовок:** None</span><span class="sxs-lookup"><span data-stu-id="ed44a-129">**Header:** None</span></span>  
<span data-ttu-id="ed44a-130">**Библиотека:** None</span><span class="sxs-lookup"><span data-stu-id="ed44a-130">**Library:** None</span></span>  
<span data-ttu-id="ed44a-131">**.NET Framework версии:**[!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]</span><span class="sxs-lookup"><span data-stu-id="ed44a-131">**.NET Framework Versions:** [!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]</span></span>  

## <a name="see-also"></a><span data-ttu-id="ed44a-132">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="ed44a-132">See also</span></span>

- [<span data-ttu-id="ed44a-133">Отладка</span><span class="sxs-lookup"><span data-stu-id="ed44a-133">Debugging</span></span>](index.md)
- [<span data-ttu-id="ed44a-134">Структуры отладки</span><span class="sxs-lookup"><span data-stu-id="ed44a-134">Debugging Structures</span></span>](debugging-structures.md)
- [<span data-ttu-id="ed44a-135">Общие типы данных</span><span class="sxs-lookup"><span data-stu-id="ed44a-135">Common Data Types</span></span>](../common-data-types-unmanaged-api-reference.md)
