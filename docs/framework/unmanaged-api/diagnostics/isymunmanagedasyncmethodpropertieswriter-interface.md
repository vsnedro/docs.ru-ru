---
title: Интерфейс ISymUnmanagedAsyncMethodPropertiesWriter
ms.date: 03/30/2017
ms.assetid: caa71820-8058-4b6a-93a2-25ee757d92d3
ms.openlocfilehash: 360d1150b0accd6a070fa36531e570d222787cee
ms.sourcegitcommit: 7b1497c1927cb449cefd313bc5126ae37df30746
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/16/2020
ms.locfileid: "83441764"
---
# <a name="isymunmanagedasyncmethodpropertieswriter-interface"></a><span data-ttu-id="07dc0-102">Интерфейс ISymUnmanagedAsyncMethodPropertiesWriter</span><span class="sxs-lookup"><span data-stu-id="07dc0-102">ISymUnmanagedAsyncMethodPropertiesWriter Interface</span></span>
<span data-ttu-id="07dc0-103">Позволяет определить дополнительные сведения о асинхронном методе для каждого символа метода.</span><span class="sxs-lookup"><span data-stu-id="07dc0-103">Allows you to define optional async method information for each method symbol.</span></span> <span data-ttu-id="07dc0-104">Всегда используйте с открытым методом. то есть между вызовами [метода опенмесод](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-openmethod-method.md) и [метода клосемесод](isymunmanagedwriter-closemethod-method.md).</span><span class="sxs-lookup"><span data-stu-id="07dc0-104">Always use with an opened method; that is, between calls to the [OpenMethod Method](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-openmethod-method.md) and the [CloseMethod Method](isymunmanagedwriter-closemethod-method.md).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="07dc0-105">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="07dc0-105">Syntax</span></span>  
  
```idl  
[object,uuid(FC073774-1739-4232-BD56-A027294BEC15),pointer_default(unique)]interface ISymUnmanagedAsyncMethodPropertiesWriter : IUnknown  
```  
  
## <a name="methods"></a><span data-ttu-id="07dc0-106">Методы</span><span class="sxs-lookup"><span data-stu-id="07dc0-106">Methods</span></span>  
 <span data-ttu-id="07dc0-107">Этот интерфейс содержит следующие методы:</span><span class="sxs-lookup"><span data-stu-id="07dc0-107">This interface contains the following methods:</span></span>  
  
|<span data-ttu-id="07dc0-108">Метод</span><span class="sxs-lookup"><span data-stu-id="07dc0-108">Method</span></span>|<span data-ttu-id="07dc0-109">Описание</span><span class="sxs-lookup"><span data-stu-id="07dc0-109">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="07dc0-110">Метод DefineAsyncStepInfo</span><span class="sxs-lookup"><span data-stu-id="07dc0-110">DefineAsyncStepInfo Method</span></span>](isymunmanagedasyncmethodpropertieswriter-defineasyncstepinfo-method.md)|<span data-ttu-id="07dc0-111">Определите группу асинхронных операций await в текущем методе.</span><span class="sxs-lookup"><span data-stu-id="07dc0-111">Define a group of async await operations in the current method.</span></span><br /><br /> <span data-ttu-id="07dc0-112">Каждое значение yield Offset соответствует инструкции Return, определяющей потенциальный доход.</span><span class="sxs-lookup"><span data-stu-id="07dc0-112">Each yield offset matches an await's return instruction, identifying a potential yield.</span></span> <span data-ttu-id="07dc0-113">Каждая `breakpointMethod` / `breakpointOffset` пара определяет, где будет возобновлена асинхронная операция. это может быть другой метод.</span><span class="sxs-lookup"><span data-stu-id="07dc0-113">Each `breakpointMethod`/`breakpointOffset` pair identifies where the asynchronous operation will resume; it may be in a different method.</span></span>|  
|[<span data-ttu-id="07dc0-114">Метод DefineCatchHandlerILOffset</span><span class="sxs-lookup"><span data-stu-id="07dc0-114">DefineCatchHandlerILOffset Method</span></span>](isymunmanagedasyncmethodpropertieswriter-definecatchhandleriloffset-method.md)|<span data-ttu-id="07dc0-115">Задает смещение IL для обработчика catch, созданного компилятором, который создает оболочку для асинхронного метода.</span><span class="sxs-lookup"><span data-stu-id="07dc0-115">Sets the IL offset for the compiler-generated catch handler that wraps an async method.</span></span><br /><br /> <span data-ttu-id="07dc0-116">Смещение IL созданного блока catch используется отладчиком для управления перехватом, как если бы он был непользовательским кодом, несмотря на то, что он может произойти в методе пользовательского кода.</span><span class="sxs-lookup"><span data-stu-id="07dc0-116">The IL offset of the generated catch is used by the debugger to handle the catch as if it were non-user code, even though it may occur in a user code method.</span></span> <span data-ttu-id="07dc0-117">В частности, он используется в ответ на событие исключения **катчхандлерфаунд** .</span><span class="sxs-lookup"><span data-stu-id="07dc0-117">In particular, it is used in response to a **CatchHandlerFound** exception event.</span></span>|  
|[<span data-ttu-id="07dc0-118">Метод DefineKickoffMethod</span><span class="sxs-lookup"><span data-stu-id="07dc0-118">DefineKickoffMethod Method</span></span>](isymunmanagedasyncmethodpropertieswriter-definekickoffmethod-method.md)|<span data-ttu-id="07dc0-119">Задает начальный метод, инициирующий асинхронную операцию.</span><span class="sxs-lookup"><span data-stu-id="07dc0-119">Sets the starting method that initiates the async operation.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="07dc0-120">Требования</span><span class="sxs-lookup"><span data-stu-id="07dc0-120">Requirements</span></span>  
 <span data-ttu-id="07dc0-121">**Заголовок:** Корсим. idl, Корсим. h</span><span class="sxs-lookup"><span data-stu-id="07dc0-121">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="07dc0-122">Дополнительно</span><span class="sxs-lookup"><span data-stu-id="07dc0-122">See also</span></span>

- [<span data-ttu-id="07dc0-123">Интерфейсы хранилища символов диагностики</span><span class="sxs-lookup"><span data-stu-id="07dc0-123">Diagnostics Symbol Store Interfaces</span></span>](diagnostics-symbol-store-interfaces.md)
