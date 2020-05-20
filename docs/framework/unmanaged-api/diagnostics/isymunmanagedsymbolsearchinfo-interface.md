---
title: Интерфейс ISymUnmanagedSymbolSearchInfo
ms.date: 03/30/2017
api_name:
- ISymUnmanagedSymbolSearchInfo
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedSymbolSearchInfo
helpviewer_keywords:
- ISymUnmanagedSymbolSearchInfo interface [.NET Framework debugging]
ms.assetid: 30817373-0a21-49c1-a0c4-8e8daeecb8db
topic_type:
- apiref
ms.openlocfilehash: 308c501e17446719067d2dc0580d698c1770bf53
ms.sourcegitcommit: 27db07ffb26f76912feefba7b884313547410db5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/19/2020
ms.locfileid: "83610669"
---
# <a name="isymunmanagedsymbolsearchinfo-interface"></a><span data-ttu-id="c3262-102">Интерфейс ISymUnmanagedSymbolSearchInfo</span><span class="sxs-lookup"><span data-stu-id="c3262-102">ISymUnmanagedSymbolSearchInfo Interface</span></span>
<span data-ttu-id="c3262-103">Предоставляет методы, получающие сведения о пути поиска.</span><span class="sxs-lookup"><span data-stu-id="c3262-103">Provides methods that get information about the search path.</span></span> <span data-ttu-id="c3262-104">Получите этот интерфейс, вызвав `QueryInterface` для объекта, который реализует интерфейс [ISymUnmanagedReader](isymunmanagedreader-interface.md) .</span><span class="sxs-lookup"><span data-stu-id="c3262-104">Obtain this interface by calling `QueryInterface` on an object that implements the [ISymUnmanagedReader](isymunmanagedreader-interface.md) interface.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="c3262-105">Методы</span><span class="sxs-lookup"><span data-stu-id="c3262-105">Methods</span></span>  
  
|<span data-ttu-id="c3262-106">Метод</span><span class="sxs-lookup"><span data-stu-id="c3262-106">Method</span></span>|<span data-ttu-id="c3262-107">Описание</span><span class="sxs-lookup"><span data-stu-id="c3262-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="c3262-108">Метод GetHRESULT</span><span class="sxs-lookup"><span data-stu-id="c3262-108">GetHRESULT Method</span></span>](isymunmanagedsymbolsearchinfo-gethresult-method.md)|<span data-ttu-id="c3262-109">Возвращает значение HRESULT.</span><span class="sxs-lookup"><span data-stu-id="c3262-109">Gets the HRESULT.</span></span>|  
|[<span data-ttu-id="c3262-110">Метод GetSearchPath</span><span class="sxs-lookup"><span data-stu-id="c3262-110">GetSearchPath Method</span></span>](isymunmanagedsymbolsearchinfo-getsearchpath-method.md)|<span data-ttu-id="c3262-111">Возвращает путь поиска.</span><span class="sxs-lookup"><span data-stu-id="c3262-111">Gets the search path.</span></span>|  
|[<span data-ttu-id="c3262-112">Метод GetSearchPathLength</span><span class="sxs-lookup"><span data-stu-id="c3262-112">GetSearchPathLength Method</span></span>](isymunmanagedsymbolsearchinfo-getsearchpathlength-method.md)|<span data-ttu-id="c3262-113">Возвращает длину пути поиска.</span><span class="sxs-lookup"><span data-stu-id="c3262-113">Gets the search path length.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="c3262-114">Требования</span><span class="sxs-lookup"><span data-stu-id="c3262-114">Requirements</span></span>  
 <span data-ttu-id="c3262-115">**Заголовок:** Корсим. idl, Корсим. h</span><span class="sxs-lookup"><span data-stu-id="c3262-115">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c3262-116">Дополнительно</span><span class="sxs-lookup"><span data-stu-id="c3262-116">See also</span></span>

- [<span data-ttu-id="c3262-117">Интерфейсы хранилища символов диагностики</span><span class="sxs-lookup"><span data-stu-id="c3262-117">Diagnostics Symbol Store Interfaces</span></span>](diagnostics-symbol-store-interfaces.md)
