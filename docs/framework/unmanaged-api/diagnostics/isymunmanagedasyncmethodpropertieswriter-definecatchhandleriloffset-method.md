---
title: Метод ISymUnmanagedAsyncMethodPropertiesWriter::DefineCatchHandlerILOffset
ms.date: 03/30/2017
ms.assetid: 92af7896-2201-408d-8b1b-23e28001eeac
ms.openlocfilehash: 58dde2fcce3f4bf578907171e5b575c30c678cfc
ms.sourcegitcommit: 7b1497c1927cb449cefd313bc5126ae37df30746
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/16/2020
ms.locfileid: "83441777"
---
# <a name="isymunmanagedasyncmethodpropertieswriterdefinecatchhandleriloffset-method"></a><span data-ttu-id="78bfb-102">Метод ISymUnmanagedAsyncMethodPropertiesWriter::DefineCatchHandlerILOffset</span><span class="sxs-lookup"><span data-stu-id="78bfb-102">ISymUnmanagedAsyncMethodPropertiesWriter::DefineCatchHandlerILOffset Method</span></span>
<span data-ttu-id="78bfb-103">Задает смещение IL для обработчика catch, созданного компилятором, который создает оболочку для асинхронного метода.</span><span class="sxs-lookup"><span data-stu-id="78bfb-103">Sets the IL offset for the compiler-generated catch handler that wraps an async method.</span></span>  
  
 <span data-ttu-id="78bfb-104">Смещение IL созданного блока catch используется отладчиком для управления перехватом, как если бы он был непользовательским кодом, даже если он может возникнуть в методе пользовательского кода.</span><span class="sxs-lookup"><span data-stu-id="78bfb-104">The IL offset of the generated catch is used by the debugger to handle the catch as if it were non-user code even though it might occur in a user code method.</span></span> <span data-ttu-id="78bfb-105">В частности, он используется в ответ на событие исключения **катчхандлерфаунд** .</span><span class="sxs-lookup"><span data-stu-id="78bfb-105">In particular, it is used in response to a **CatchHandlerFound** exception event.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="78bfb-106">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="78bfb-106">Syntax</span></span>  
  
```idl  
HRESULT DefineCatchHandlerILOffset(    [in] ULONG32 catchHandlerOffset);  
```  
  
## <a name="parameters"></a><span data-ttu-id="78bfb-107">Параметры</span><span class="sxs-lookup"><span data-stu-id="78bfb-107">Parameters</span></span>  
  
|<span data-ttu-id="78bfb-108">Параметр</span><span class="sxs-lookup"><span data-stu-id="78bfb-108">Parameter</span></span>|<span data-ttu-id="78bfb-109">Описание</span><span class="sxs-lookup"><span data-stu-id="78bfb-109">Description</span></span>|  
|---------------|-----------------|  
|`catchHandlerOffset`||  
  
## <a name="return-value"></a><span data-ttu-id="78bfb-110">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="78bfb-110">Return Value</span></span>  
 <span data-ttu-id="78bfb-111">Возвращает `HRESULT`.</span><span class="sxs-lookup"><span data-stu-id="78bfb-111">Returns `HRESULT`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="78bfb-112">Требования</span><span class="sxs-lookup"><span data-stu-id="78bfb-112">Requirements</span></span>  
 <span data-ttu-id="78bfb-113">**Заголовок:** Корсим. idl, Корсим. h</span><span class="sxs-lookup"><span data-stu-id="78bfb-113">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="78bfb-114">Дополнительно</span><span class="sxs-lookup"><span data-stu-id="78bfb-114">See also</span></span>

- [<span data-ttu-id="78bfb-115">Интерфейс ISymUnmanagedAsyncMethodPropertiesWriter</span><span class="sxs-lookup"><span data-stu-id="78bfb-115">ISymUnmanagedAsyncMethodPropertiesWriter Interface</span></span>](isymunmanagedasyncmethodpropertieswriter-interface.md)
