---
title: Структура CorDebugEHClause
ms.date: 03/30/2017
dev_langs:
- cpp
api_name:
- CorDebugEHClause
api_location:
- mscordbi.dll
api_type:
- COM
ms.assetid: 0e350a1b-6997-46d0-bfc5-962a5011ef43
topic_type:
- apiref
ms.openlocfilehash: a889d6ba00c4a0eb96a9923a7dbe52f3b93aaba5
ms.sourcegitcommit: de7f589de07a9979b6ac28f54c3e534a617d9425
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/05/2020
ms.locfileid: "82795965"
---
# <a name="cordebugehclause-structure"></a><span data-ttu-id="ff905-102">Структура CorDebugEHClause</span><span class="sxs-lookup"><span data-stu-id="ff905-102">CorDebugEHClause Structure</span></span>
<span data-ttu-id="ff905-103">[Поддерживается в .NET Framework 4.5.2 и более поздних версиях.]</span><span class="sxs-lookup"><span data-stu-id="ff905-103">[Supported in the .NET Framework 4.5.2 and later versions]</span></span>  
  
 <span data-ttu-id="ff905-104">Представляет предложение обработки исключений для данного фрагмента кода промежуточного языка.</span><span class="sxs-lookup"><span data-stu-id="ff905-104">Represents an exception handling (EH) clause for a given piece of intermediate language (IL) code.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ff905-105">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="ff905-105">Syntax</span></span>  
  
```cpp
typedef struct _CorDebugEHClause {  
   ULONG32 Flags;  
   ULONG32 TryOffset;  
   ULONG32 TryLength;  
   ULONG32 HandlerOffset;  
   ULONG32 HandlerLength;  
   ULONG32 ClassToken;  
   ULONG32 FilterOffset;  
} CorDebugEHClause;  
```  
  
## <a name="members"></a><span data-ttu-id="ff905-106">Участники</span><span class="sxs-lookup"><span data-stu-id="ff905-106">Members</span></span>  
  
|<span data-ttu-id="ff905-107">Участник</span><span class="sxs-lookup"><span data-stu-id="ff905-107">Member</span></span>|<span data-ttu-id="ff905-108">Описание</span><span class="sxs-lookup"><span data-stu-id="ff905-108">Description</span></span>|  
|------------|-----------------|  
|`Flags`|<span data-ttu-id="ff905-109">Битовое поле, описывающее информацию об исключениях в предложении обработки исключений.</span><span class="sxs-lookup"><span data-stu-id="ff905-109">A bit field that describes the exception information in the EH clause.</span></span> <span data-ttu-id="ff905-110">Дополнительные сведения см. в разделе «Примечания».</span><span class="sxs-lookup"><span data-stu-id="ff905-110">For more information, see the Remarks section.</span></span>|  
|`TryOffset`|<span data-ttu-id="ff905-111">Смещение блока `try` в байтах от начала тела метода.</span><span class="sxs-lookup"><span data-stu-id="ff905-111">The offset, in bytes, of the `try` block from the start of the method body.</span></span>|  
|`TryLength`|<span data-ttu-id="ff905-112">Длина блока `try` в байтах.</span><span class="sxs-lookup"><span data-stu-id="ff905-112">The length, in bytes, of the `try` block.</span></span>|  
|`HandlerOffset`|<span data-ttu-id="ff905-113">Расположение обработчика для этого блока `try`.</span><span class="sxs-lookup"><span data-stu-id="ff905-113">The location of the handler for this `try` block.</span></span>|  
|`HandlerLength`|<span data-ttu-id="ff905-114">Размер кода обработчика в байтах.</span><span class="sxs-lookup"><span data-stu-id="ff905-114">The size of the handler code in bytes.</span></span>|  
|`ClassToken`|<span data-ttu-id="ff905-115">Токен метаданных для обработчика исключений на основе типа.</span><span class="sxs-lookup"><span data-stu-id="ff905-115">The metadata token for a type-based exception handler.</span></span>|  
|`FilterOffset`|<span data-ttu-id="ff905-116">Смещение в байтах от начала тела метода для обработчика исключений на основе фильтра.</span><span class="sxs-lookup"><span data-stu-id="ff905-116">The offset, in bytes, from the start of the method body for a filter-based exception handler.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="ff905-117">Remarks</span><span class="sxs-lookup"><span data-stu-id="ff905-117">Remarks</span></span>  
 <span data-ttu-id="ff905-118">Массив `CoreDebugEHClause` значений возвращается методом [GetEHClauses](icordebugilcode-getehclauses-method.md) .</span><span class="sxs-lookup"><span data-stu-id="ff905-118">An array of `CoreDebugEHClause` values is returned by the [GetEHClauses](icordebugilcode-getehclauses-method.md) method.</span></span>  
  
 <span data-ttu-id="ff905-119">Информация о предложении обработки исключений определяется спецификацией CLI.</span><span class="sxs-lookup"><span data-stu-id="ff905-119">The EH clause information is defined by the CLI specification.</span></span> <span data-ttu-id="ff905-120">Дополнительные сведения см. в разделе [Standard ECMA-355: Common Language Infrastructure (CLI), 6-й выпуск](https://www.ecma-international.org/publications/standards/Ecma-335.htm).</span><span class="sxs-lookup"><span data-stu-id="ff905-120">For more information, see [Standard ECMA-355: Common Language Infrastructure (CLI), 6th Edition](https://www.ecma-international.org/publications/standards/Ecma-335.htm).</span></span>  
  
 <span data-ttu-id="ff905-121">Поле `flags` может содержать следующие флаги.</span><span class="sxs-lookup"><span data-stu-id="ff905-121">The `flags` field can contain the following flags.</span></span> <span data-ttu-id="ff905-122">Обратите внимание, что они не определены в CorDebug.idl или CorDebug.h.</span><span class="sxs-lookup"><span data-stu-id="ff905-122">Note that they are not defined in CorDebug.idl or CorDebug.h.</span></span>  
  
|<span data-ttu-id="ff905-123">Флаг</span><span class="sxs-lookup"><span data-stu-id="ff905-123">Flag</span></span>|<span data-ttu-id="ff905-124">Применение</span><span class="sxs-lookup"><span data-stu-id="ff905-124">Value</span></span>|<span data-ttu-id="ff905-125">Описание</span><span class="sxs-lookup"><span data-stu-id="ff905-125">Description</span></span>|  
|----------|-----------|-----------------|  
|`COR_ILEXCEPTION_CLAUSE_EXCEPTION`|<span data-ttu-id="ff905-126">0x00000000</span><span class="sxs-lookup"><span data-stu-id="ff905-126">0x00000000</span></span>|<span data-ttu-id="ff905-127">Введенное предложение исключений.</span><span class="sxs-lookup"><span data-stu-id="ff905-127">A typed exception clause.</span></span>|  
|`COR_ILEXCEPTION_CLAUSE_FILTER`|<span data-ttu-id="ff905-128">0x00000001</span><span class="sxs-lookup"><span data-stu-id="ff905-128">0x00000001</span></span>|<span data-ttu-id="ff905-129">Фильтр исключений и предложение обработчика.</span><span class="sxs-lookup"><span data-stu-id="ff905-129">An exception filter and handler clause.</span></span>|  
|`COR_ILEXCEPTION_CLAUSE_FINALLY`|<span data-ttu-id="ff905-130">0x00000002</span><span class="sxs-lookup"><span data-stu-id="ff905-130">0x00000002</span></span>|<span data-ttu-id="ff905-131">Предложение `finally`.</span><span class="sxs-lookup"><span data-stu-id="ff905-131">A `finally` clause.</span></span>|  
|`COR_ILEXCEPTION_CLAUSE_FAULT`|<span data-ttu-id="ff905-132">0x00000004</span><span class="sxs-lookup"><span data-stu-id="ff905-132">0x00000004</span></span>|<span data-ttu-id="ff905-133">Неправильное предложение (предложение `finally`, которое вызывается только при возникновении исключения).</span><span class="sxs-lookup"><span data-stu-id="ff905-133">A fault clause (a `finally` clause that is called only when an exception is thrown).</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="ff905-134">Требования</span><span class="sxs-lookup"><span data-stu-id="ff905-134">Requirements</span></span>  
 <span data-ttu-id="ff905-135">**Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="ff905-135">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ff905-136">**Заголовок:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="ff905-136">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="ff905-137">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="ff905-137">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="ff905-138">**.NET Framework версии:**[!INCLUDE[net_current_v452plus](../../../../includes/net-current-v452plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="ff905-138">**.NET Framework Versions:** [!INCLUDE[net_current_v452plus](../../../../includes/net-current-v452plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ff905-139">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="ff905-139">See also</span></span>

- [<span data-ttu-id="ff905-140">Метод GetEHClauses</span><span class="sxs-lookup"><span data-stu-id="ff905-140">GetEHClauses Method</span></span>](icordebugilcode-getehclauses-method.md)
- [<span data-ttu-id="ff905-141">Структуры отладки</span><span class="sxs-lookup"><span data-stu-id="ff905-141">Debugging Structures</span></span>](debugging-structures.md)
