---
title: Интерфейс ISymUnmanagedWriter3
ms.date: 03/30/2017
api_name:
- ISymUnmanagedWriter3
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedWriter3
helpviewer_keywords:
- ISymUnmanagedWriter3 interface [.NET Framework debugging]
ms.assetid: a034c21e-e371-4360-b470-29e88288948f
topic_type:
- apiref
ms.openlocfilehash: dfc2e39a6a39e7386bd7358d422d5c6978ec42ec
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/24/2020
ms.locfileid: "95683294"
---
# <a name="isymunmanagedwriter3-interface"></a><span data-ttu-id="69da5-102">Интерфейс ISymUnmanagedWriter3</span><span class="sxs-lookup"><span data-stu-id="69da5-102">ISymUnmanagedWriter3 Interface</span></span>

<span data-ttu-id="69da5-103">Представляет средство записи символов и предоставляет методы для определения документов, точек следования, лексических областей и переменных.</span><span class="sxs-lookup"><span data-stu-id="69da5-103">Represents a symbol writer, and provides methods to define documents, sequence points, lexical scopes, and variables.</span></span> <span data-ttu-id="69da5-104">Этот интерфейс расширяет интерфейс [ISymUnmanagedWriter](isymunmanagedwriter-interface.md) .</span><span class="sxs-lookup"><span data-stu-id="69da5-104">This interface extends the [ISymUnmanagedWriter](isymunmanagedwriter-interface.md) interface.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="69da5-105">Методы</span><span class="sxs-lookup"><span data-stu-id="69da5-105">Methods</span></span>  
  
|<span data-ttu-id="69da5-106">Метод</span><span class="sxs-lookup"><span data-stu-id="69da5-106">Method</span></span>|<span data-ttu-id="69da5-107">Описание</span><span class="sxs-lookup"><span data-stu-id="69da5-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="69da5-108">Метод Commit</span><span class="sxs-lookup"><span data-stu-id="69da5-108">Commit Method</span></span>](isymunmanagedwriter3-commit-method.md)|<span data-ttu-id="69da5-109">Фиксирует изменения, записанные на данный момент в поток.</span><span class="sxs-lookup"><span data-stu-id="69da5-109">Commits the changes written so far to the stream.</span></span>|  
|[<span data-ttu-id="69da5-110">Метод OpenMethod2</span><span class="sxs-lookup"><span data-stu-id="69da5-110">OpenMethod2 Method</span></span>](isymunmanagedwriter3-openmethod2-method.md)|<span data-ttu-id="69da5-111">Открывает метод и предоставляет его фактическое смещение раздела в изображении.</span><span class="sxs-lookup"><span data-stu-id="69da5-111">Opens a method and provides its real section offset in the image.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="69da5-112">Требования</span><span class="sxs-lookup"><span data-stu-id="69da5-112">Requirements</span></span>  

 <span data-ttu-id="69da5-113">**Заголовок:** Корсим. idl, Корсим. h</span><span class="sxs-lookup"><span data-stu-id="69da5-113">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="69da5-114">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="69da5-114">See also</span></span>

- [<span data-ttu-id="69da5-115">Интерфейсы хранилища символов диагностики</span><span class="sxs-lookup"><span data-stu-id="69da5-115">Diagnostics Symbol Store Interfaces</span></span>](diagnostics-symbol-store-interfaces.md)
- [<span data-ttu-id="69da5-116">Интерфейс ISymUnmanagedWriter</span><span class="sxs-lookup"><span data-stu-id="69da5-116">ISymUnmanagedWriter Interface</span></span>](isymunmanagedwriter-interface.md)
- [<span data-ttu-id="69da5-117">Интерфейс ISymUnmanagedWriter2</span><span class="sxs-lookup"><span data-stu-id="69da5-117">ISymUnmanagedWriter2 Interface</span></span>](isymunmanagedwriter2-interface.md)
