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
ms.openlocfilehash: d623fe862eaf5902fd89d0e512dd07f73a03246f
ms.sourcegitcommit: d9c7ac5d06735a01c1fafe34efe9486734841a72
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/06/2020
ms.locfileid: "82860819"
---
# <a name="dacpmethoddescdata-structure"></a><span data-ttu-id="e960e-102">Структура DacpMethodDescData</span><span class="sxs-lookup"><span data-stu-id="e960e-102">DacpMethodDescData Structure</span></span>

<span data-ttu-id="e960e-103">Определяет транспортный буфер для сведений о среде выполнения метода.</span><span class="sxs-lookup"><span data-stu-id="e960e-103">Defines a transport buffer for a method's runtime information.</span></span>

[!INCLUDE[debugging-api-recommended-note](../../../../includes/debugging-api-recommended-note.md)]

## <a name="syntax"></a><span data-ttu-id="e960e-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="e960e-104">Syntax</span></span>

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

## <a name="members"></a><span data-ttu-id="e960e-105">Члены</span><span class="sxs-lookup"><span data-stu-id="e960e-105">Members</span></span>

| <span data-ttu-id="e960e-106">Участник</span><span class="sxs-lookup"><span data-stu-id="e960e-106">Member</span></span>                       | <span data-ttu-id="e960e-107">Описание</span><span class="sxs-lookup"><span data-stu-id="e960e-107">Description</span></span>                                                                                     |
| ---------------------------- | ----------------------------------------------------------------------------------------------- |
| `bHasNativeCode`             | <span data-ttu-id="e960e-108">Указывает, доступен ли в среде выполнения машинный код для данного экземпляра метода.</span><span class="sxs-lookup"><span data-stu-id="e960e-108">Indicates if the runtime has native code available for the given instantiation of the method.</span></span> |
| `bIsDynamic`                 | <span data-ttu-id="e960e-109">Указывает, создается ли метод динамически с помощью создания упрощенного кода.</span><span class="sxs-lookup"><span data-stu-id="e960e-109">Indicates if the method is generated dynamically through lightweight code generation.</span></span>           |
| `wSlotNumber`                | <span data-ttu-id="e960e-110">Номер слота метода в таблице методов.</span><span class="sxs-lookup"><span data-stu-id="e960e-110">The method's slot number in the method table.</span></span>                                                   |
| `NativeCodeAddr`             | <span data-ttu-id="e960e-111">Начальный собственный адрес метода.</span><span class="sxs-lookup"><span data-stu-id="e960e-111">The method's initial native address.</span></span>                                                            |
| `data`                       | <span data-ttu-id="e960e-112">Указатель на буфер, который используется средой выполнения для внутренних целей.</span><span class="sxs-lookup"><span data-stu-id="e960e-112">Pointer to a buffer used internally by the runtime.</span></span>                                             |
| `MethodDescPtr`              | <span data-ttu-id="e960e-113">Указатель на объект `MethodDesc` в среде выполнения.</span><span class="sxs-lookup"><span data-stu-id="e960e-113">Pointer to the `MethodDesc` in the runtime.</span></span>                                                     |
| `nativeCodeInfo`             | <span data-ttu-id="e960e-114">Указатель на буфер, используемый средой выполнения для трассировки методов.</span><span class="sxs-lookup"><span data-stu-id="e960e-114">Pointer to a buffer used internally by the runtime to track methods.</span></span>                            |
| `moduleInfo`                 | <span data-ttu-id="e960e-115">Указатель на буфер, используемый средой выполнения для сведений о модуле.</span><span class="sxs-lookup"><span data-stu-id="e960e-115">Pointer to a buffer used internally by the runtime for module information.</span></span>                      |
| `MDToken`                    | <span data-ttu-id="e960e-116">Токен, связанный с данным методом.</span><span class="sxs-lookup"><span data-stu-id="e960e-116">Token associated with the given method.</span></span>                                                         |
| `payloadGC`                  | <span data-ttu-id="e960e-117">Указатель на буфер сборки мусора, который используется средой выполнения для внутренних целей.</span><span class="sxs-lookup"><span data-stu-id="e960e-117">Pointer to a garbage collection buffer used internally by the runtime.</span></span>                          |
| `payloadGC2`                 | <span data-ttu-id="e960e-118">Указатель на буфер сборки мусора, который используется средой выполнения для внутренних целей.</span><span class="sxs-lookup"><span data-stu-id="e960e-118">Pointer to a garbage collection buffer used internally by the runtime.</span></span>                          |
| `managedDynamicMethodObject` | <span data-ttu-id="e960e-119">Если метод является динамическим, среда выполнения использует этот буфер для внутреннего отслеживания сведений.</span><span class="sxs-lookup"><span data-stu-id="e960e-119">If the method is dynamic, the runtime uses this buffer internally for information tracking.</span></span>     |
| `requestedIP`                | <span data-ttu-id="e960e-120">Используется для заполнения структуры на запрос при наличии адреса машинного кода.</span><span class="sxs-lookup"><span data-stu-id="e960e-120">Used to populate the structure per request when given a native code address.</span></span>                    |
| `rejitDataCurrent`           | <span data-ttu-id="e960e-121">Сведения о последней инструментированной версии метода.</span><span class="sxs-lookup"><span data-stu-id="e960e-121">Information about the latest instrumented version of the method.</span></span>                                   |
| `rejitDataRequested`         | <span data-ttu-id="e960e-122">Rejit сведения для запрошенного собственного адреса.</span><span class="sxs-lookup"><span data-stu-id="e960e-122">Rejit information for the requested native address.</span></span>                                             |
| `cJittedRejitVersions`       | <span data-ttu-id="e960e-123">Сколько раз метод был режиттед с помощью инструментирования.</span><span class="sxs-lookup"><span data-stu-id="e960e-123">Number of times the method has been rejitted through instrumentation.</span></span>                           |

## <a name="remarks"></a><span data-ttu-id="e960e-124">Примечания</span><span class="sxs-lookup"><span data-stu-id="e960e-124">Remarks</span></span>

<span data-ttu-id="e960e-125">Эта структура находится внутри среды выполнения и не предоставляется через все файлы заголовков или библиотек.</span><span class="sxs-lookup"><span data-stu-id="e960e-125">This structure lives inside the runtime and is not exposed through any headers or library files.</span></span> <span data-ttu-id="e960e-126">Чтобы использовать его, определите структуру, как указано выше.</span><span class="sxs-lookup"><span data-stu-id="e960e-126">To use it, define the structure as specified above.</span></span>

## <a name="requirements"></a><span data-ttu-id="e960e-127">Требования</span><span class="sxs-lookup"><span data-stu-id="e960e-127">Requirements</span></span>
<span data-ttu-id="e960e-128">**Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="e960e-128">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
<span data-ttu-id="e960e-129">**Заголовок:** None</span><span class="sxs-lookup"><span data-stu-id="e960e-129">**Header:** None</span></span>  
<span data-ttu-id="e960e-130">**Библиотека:** None</span><span class="sxs-lookup"><span data-stu-id="e960e-130">**Library:** None</span></span>  
<span data-ttu-id="e960e-131">**.NET Framework версии:**[!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]</span><span class="sxs-lookup"><span data-stu-id="e960e-131">**.NET Framework Versions:** [!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]</span></span>  

## <a name="see-also"></a><span data-ttu-id="e960e-132">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="e960e-132">See also</span></span>

- [<span data-ttu-id="e960e-133">Отладка</span><span class="sxs-lookup"><span data-stu-id="e960e-133">Debugging</span></span>](index.md)
- [<span data-ttu-id="e960e-134">Структуры отладки</span><span class="sxs-lookup"><span data-stu-id="e960e-134">Debugging Structures</span></span>](debugging-structures.md)
- [<span data-ttu-id="e960e-135">Общие типы данных</span><span class="sxs-lookup"><span data-stu-id="e960e-135">Common Data Types</span></span>](../common-data-types-unmanaged-api-reference.md)
