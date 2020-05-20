---
title: Интерфейс ISymUnmanagedScope2
ms.date: 03/30/2017
api_name:
- ISymUnmanagedScope2
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedScope2
helpviewer_keywords:
- ISymUnmanagedScope2 interface [.NET Framework debugging]
ms.assetid: 2ed6a387-ba45-483e-9a1e-b0c69f67998b
topic_type:
- apiref
ms.openlocfilehash: 886ba693183a6b99eb03635e95a9661d105de40e
ms.sourcegitcommit: 27db07ffb26f76912feefba7b884313547410db5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/19/2020
ms.locfileid: "83610864"
---
# <a name="isymunmanagedscope2-interface"></a><span data-ttu-id="52fc5-102">Интерфейс ISymUnmanagedScope2</span><span class="sxs-lookup"><span data-stu-id="52fc5-102">ISymUnmanagedScope2 Interface</span></span>
<span data-ttu-id="52fc5-103">Представляет лексическую область внутри метода.</span><span class="sxs-lookup"><span data-stu-id="52fc5-103">Represents a lexical scope within a method.</span></span> <span data-ttu-id="52fc5-104">Этот интерфейс расширяет интерфейс [исимунманажедскопе](isymunmanagedscope-interface.md) с помощью методов, которые получают сведения о константах, определенных в области.</span><span class="sxs-lookup"><span data-stu-id="52fc5-104">This interface extends the [ISymUnmanagedScope](isymunmanagedscope-interface.md) interface with methods that get information about constants defined within the scope.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="52fc5-105">Методы</span><span class="sxs-lookup"><span data-stu-id="52fc5-105">Methods</span></span>  
  
|<span data-ttu-id="52fc5-106">Метод</span><span class="sxs-lookup"><span data-stu-id="52fc5-106">Method</span></span>|<span data-ttu-id="52fc5-107">Описание</span><span class="sxs-lookup"><span data-stu-id="52fc5-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="52fc5-108">Метод GetConstantCount</span><span class="sxs-lookup"><span data-stu-id="52fc5-108">GetConstantCount Method</span></span>](isymunmanagedscope2-getconstantcount-method.md)|<span data-ttu-id="52fc5-109">Возвращает число констант, определенных в этой области.</span><span class="sxs-lookup"><span data-stu-id="52fc5-109">Gets a count of the constants defined within this scope.</span></span>|  
|[<span data-ttu-id="52fc5-110">Метод GetConstants</span><span class="sxs-lookup"><span data-stu-id="52fc5-110">GetConstants Method</span></span>](isymunmanagedscope2-getconstants-method.md)|<span data-ttu-id="52fc5-111">Возвращает локальные константы, определенные в этой области.</span><span class="sxs-lookup"><span data-stu-id="52fc5-111">Gets the local constants defined within this scope.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="52fc5-112">Требования</span><span class="sxs-lookup"><span data-stu-id="52fc5-112">Requirements</span></span>  
 <span data-ttu-id="52fc5-113">**Заголовок:** Корсим. idl, Корсим. h</span><span class="sxs-lookup"><span data-stu-id="52fc5-113">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="52fc5-114">Дополнительно</span><span class="sxs-lookup"><span data-stu-id="52fc5-114">See also</span></span>

- [<span data-ttu-id="52fc5-115">Интерфейсы хранилища символов диагностики</span><span class="sxs-lookup"><span data-stu-id="52fc5-115">Diagnostics Symbol Store Interfaces</span></span>](diagnostics-symbol-store-interfaces.md)
- [<span data-ttu-id="52fc5-116">Интерфейс ISymUnmanagedScope</span><span class="sxs-lookup"><span data-stu-id="52fc5-116">ISymUnmanagedScope Interface</span></span>](isymunmanagedscope-interface.md)
