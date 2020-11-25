---
title: Интерфейс ISymUnmanagedWriter5
ms.date: 03/30/2017
ms.assetid: 15b8526e-4f5d-475c-a1e3-d8b2d145c879
ms.openlocfilehash: 894f3b0e45df2c681cbdec1f154703be64f32fc5
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/24/2020
ms.locfileid: "95725798"
---
# <a name="isymunmanagedwriter5-interface"></a><span data-ttu-id="5feea-102">Интерфейс ISymUnmanagedWriter5</span><span class="sxs-lookup"><span data-stu-id="5feea-102">ISymUnmanagedWriter5 Interface</span></span>

<span data-ttu-id="5feea-103">Интерфейс ISymUnmanagedWriter5.</span><span class="sxs-lookup"><span data-stu-id="5feea-103">ISymUnmanagedWriter5 interface.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5feea-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="5feea-104">Syntax</span></span>  
  
```idl  
[object,uuid(DCF7780D-BDE9-45DF-ACFE-21731A32000C),pointer_default(unique)]interface ISymUnmanagedWriter5 : ISymUnmanagedWriter4  
```  
  
## <a name="methods"></a><span data-ttu-id="5feea-105">Методы</span><span class="sxs-lookup"><span data-stu-id="5feea-105">Methods</span></span>  

 <span data-ttu-id="5feea-106">Этот интерфейс содержит следующие методы:</span><span class="sxs-lookup"><span data-stu-id="5feea-106">This interface contains the following methods:</span></span>  
  
|<span data-ttu-id="5feea-107">Метод</span><span class="sxs-lookup"><span data-stu-id="5feea-107">Method</span></span>|<span data-ttu-id="5feea-108">Описание</span><span class="sxs-lookup"><span data-stu-id="5feea-108">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="5feea-109">Метод CloseMapTokensToSourceSpans</span><span class="sxs-lookup"><span data-stu-id="5feea-109">CloseMapTokensToSourceSpans Method</span></span>](isymunmanagedwriter5-closemaptokenstosourcespans-method.md)|<span data-ttu-id="5feea-110">Закройте Специальный раздел настраиваемых данных, чтобы получить сведения о сопоставлении диапазона "токен-источник".</span><span class="sxs-lookup"><span data-stu-id="5feea-110">Close the special custom data section for token-to- source span mapping information.</span></span> <span data-ttu-id="5feea-111">После закрытия не удается добавить дополнительные сведения о сопоставлении.</span><span class="sxs-lookup"><span data-stu-id="5feea-111">After it is closed, no more mapping information can be added.</span></span>|  
|[<span data-ttu-id="5feea-112">Метод MapTokenToSourceSpan</span><span class="sxs-lookup"><span data-stu-id="5feea-112">MapTokenToSourceSpan Method</span></span>](isymunmanagedwriter5-maptokentosourcespan-method.md)|<span data-ttu-id="5feea-113">Сопоставляет заданный токен метаданных с заданным диапазоном исходной строки в указанном исходном файле.</span><span class="sxs-lookup"><span data-stu-id="5feea-113">Maps the given metadata token to the given source line span in the specified source file.</span></span><br /><br /> <span data-ttu-id="5feea-114">Должен вызываться между вызовами [метода OpenMapTokensToSourceSpans](isymunmanagedwriter5-openmaptokenstosourcespans-method.md) и [метода CloseMapTokensToSourceSpans](isymunmanagedwriter5-closemaptokenstosourcespans-method.md).</span><span class="sxs-lookup"><span data-stu-id="5feea-114">Must be called between calls to [OpenMapTokensToSourceSpans Method](isymunmanagedwriter5-openmaptokenstosourcespans-method.md) and [CloseMapTokensToSourceSpans Method](isymunmanagedwriter5-closemaptokenstosourcespans-method.md).</span></span>|  
|[<span data-ttu-id="5feea-115">Метод OpenMapTokensToSourceSpans</span><span class="sxs-lookup"><span data-stu-id="5feea-115">OpenMapTokensToSourceSpans Method</span></span>](isymunmanagedwriter5-openmaptokenstosourcespans-method.md)|<span data-ttu-id="5feea-116">Откройте Специальный раздел настраиваемых данных, чтобы выдать сведения о сопоставлении диапазона от токена к источнику в.</span><span class="sxs-lookup"><span data-stu-id="5feea-116">Open a special custom data section to emit token-to- source span mapping information into.</span></span> <span data-ttu-id="5feea-117">Открытие этого раздела, если метод уже открыт или наоборот, является ошибкой.</span><span class="sxs-lookup"><span data-stu-id="5feea-117">Opening this section when a method is already open, or vice versa, is an error.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="5feea-118">Требования</span><span class="sxs-lookup"><span data-stu-id="5feea-118">Requirements</span></span>  

 <span data-ttu-id="5feea-119">**Заголовок:** Корсим. idl, Корсим. h</span><span class="sxs-lookup"><span data-stu-id="5feea-119">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5feea-120">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="5feea-120">See also</span></span>

- [<span data-ttu-id="5feea-121">Интерфейсы хранилища символов диагностики</span><span class="sxs-lookup"><span data-stu-id="5feea-121">Diagnostics Symbol Store Interfaces</span></span>](diagnostics-symbol-store-interfaces.md)
- [<span data-ttu-id="5feea-122">Интерфейс ISymUnmanagedWriter4</span><span class="sxs-lookup"><span data-stu-id="5feea-122">ISymUnmanagedWriter4 Interface</span></span>](isymunmanagedwriter4-interface.md)
