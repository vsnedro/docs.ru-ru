---
title: Метод ISymUnmanagedAsyncMethodPropertiesWriter::DefineAsyncStepInfo
ms.date: 03/30/2017
ms.assetid: f738a6ed-7cd9-4106-a5cd-355481e5771c
ms.openlocfilehash: f8c77e44183fd92704aa91ca1cfd7e3fa68aa27f
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/24/2020
ms.locfileid: "95719623"
---
# <a name="isymunmanagedasyncmethodpropertieswriterdefineasyncstepinfo-method"></a><span data-ttu-id="4057f-102">Метод ISymUnmanagedAsyncMethodPropertiesWriter::DefineAsyncStepInfo</span><span class="sxs-lookup"><span data-stu-id="4057f-102">ISymUnmanagedAsyncMethodPropertiesWriter::DefineAsyncStepInfo Method</span></span>

<span data-ttu-id="4057f-103">Определите группу асинхронных операций await в текущем методе.</span><span class="sxs-lookup"><span data-stu-id="4057f-103">Define a group of async await operations in the current method.</span></span>  
  
 <span data-ttu-id="4057f-104">Каждое значение yield Offset соответствует инструкции Return, определяющей потенциальный доход.</span><span class="sxs-lookup"><span data-stu-id="4057f-104">Each yield offset matches an await's return instruction, identifying a potential yield.</span></span> <span data-ttu-id="4057f-105">Каждая `breakpointMethod` / `breakpointOffset` пара сообщает нам, где будет возобновлена асинхронная операция, которая может быть в другом методе.</span><span class="sxs-lookup"><span data-stu-id="4057f-105">Each `breakpointMethod`/`breakpointOffset` pair tells us where the asynchronous operation will resume which could be in a different method.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4057f-106">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="4057f-106">Syntax</span></span>  
  
```idl  
HRESULT DefineAsyncStepInfo(    [in] ULONG32 count,    [in, size_is(count)] ULONG32 yieldOffsets[],    [in, size_is(count)] ULONG32 breakpointOffset[],     [in, size_is(count)] mdToken breakpointMethod[]);  
```  
  
## <a name="parameters"></a><span data-ttu-id="4057f-107">Параметры</span><span class="sxs-lookup"><span data-stu-id="4057f-107">Parameters</span></span>  
  
|<span data-ttu-id="4057f-108">Параметр</span><span class="sxs-lookup"><span data-stu-id="4057f-108">Parameter</span></span>|<span data-ttu-id="4057f-109">Описание</span><span class="sxs-lookup"><span data-stu-id="4057f-109">Description</span></span>|  
|---------------|-----------------|  
|`count`||  
|`yieldOffsets`||  
|`breakpointOffset`||  
|`breakpointMethod`||  
  
## <a name="return-value"></a><span data-ttu-id="4057f-110">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="4057f-110">Return Value</span></span>  

 <span data-ttu-id="4057f-111">Возвращает `HRESULT`.</span><span class="sxs-lookup"><span data-stu-id="4057f-111">Returns `HRESULT`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="4057f-112">Требования</span><span class="sxs-lookup"><span data-stu-id="4057f-112">Requirements</span></span>  

 <span data-ttu-id="4057f-113">**Заголовок:** Корсим. idl, Корсим. h</span><span class="sxs-lookup"><span data-stu-id="4057f-113">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4057f-114">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="4057f-114">See also</span></span>

- [<span data-ttu-id="4057f-115">Интерфейс ISymUnmanagedAsyncMethodPropertiesWriter</span><span class="sxs-lookup"><span data-stu-id="4057f-115">ISymUnmanagedAsyncMethodPropertiesWriter Interface</span></span>](isymunmanagedasyncmethodpropertieswriter-interface.md)
