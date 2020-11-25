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
ms.openlocfilehash: 40c437e109eaa4352a83c5566185593cbc6b0eba
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/24/2020
ms.locfileid: "95725837"
---
# <a name="isymunmanagedscope2-interface"></a><span data-ttu-id="d3732-102">Интерфейс ISymUnmanagedScope2</span><span class="sxs-lookup"><span data-stu-id="d3732-102">ISymUnmanagedScope2 Interface</span></span>

<span data-ttu-id="d3732-103">Представляет лексическую область внутри метода.</span><span class="sxs-lookup"><span data-stu-id="d3732-103">Represents a lexical scope within a method.</span></span> <span data-ttu-id="d3732-104">Этот интерфейс расширяет интерфейс [исимунманажедскопе](isymunmanagedscope-interface.md) с помощью методов, которые получают сведения о константах, определенных в области.</span><span class="sxs-lookup"><span data-stu-id="d3732-104">This interface extends the [ISymUnmanagedScope](isymunmanagedscope-interface.md) interface with methods that get information about constants defined within the scope.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="d3732-105">Методы</span><span class="sxs-lookup"><span data-stu-id="d3732-105">Methods</span></span>  
  
|<span data-ttu-id="d3732-106">Метод</span><span class="sxs-lookup"><span data-stu-id="d3732-106">Method</span></span>|<span data-ttu-id="d3732-107">Описание</span><span class="sxs-lookup"><span data-stu-id="d3732-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="d3732-108">Метод GetConstantCount</span><span class="sxs-lookup"><span data-stu-id="d3732-108">GetConstantCount Method</span></span>](isymunmanagedscope2-getconstantcount-method.md)|<span data-ttu-id="d3732-109">Возвращает число констант, определенных в этой области.</span><span class="sxs-lookup"><span data-stu-id="d3732-109">Gets a count of the constants defined within this scope.</span></span>|  
|[<span data-ttu-id="d3732-110">Метод GetConstants</span><span class="sxs-lookup"><span data-stu-id="d3732-110">GetConstants Method</span></span>](isymunmanagedscope2-getconstants-method.md)|<span data-ttu-id="d3732-111">Возвращает локальные константы, определенные в этой области.</span><span class="sxs-lookup"><span data-stu-id="d3732-111">Gets the local constants defined within this scope.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="d3732-112">Требования</span><span class="sxs-lookup"><span data-stu-id="d3732-112">Requirements</span></span>  

 <span data-ttu-id="d3732-113">**Заголовок:** Корсим. idl, Корсим. h</span><span class="sxs-lookup"><span data-stu-id="d3732-113">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d3732-114">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="d3732-114">See also</span></span>

- [<span data-ttu-id="d3732-115">Интерфейсы хранилища символов диагностики</span><span class="sxs-lookup"><span data-stu-id="d3732-115">Diagnostics Symbol Store Interfaces</span></span>](diagnostics-symbol-store-interfaces.md)
- [<span data-ttu-id="d3732-116">Интерфейс ISymUnmanagedScope</span><span class="sxs-lookup"><span data-stu-id="d3732-116">ISymUnmanagedScope Interface</span></span>](isymunmanagedscope-interface.md)
