---
title: Интерфейс ISymUnmanagedReaderSymbolSearchInfo
ms.date: 03/30/2017
api_name:
- ISymUnmanagedReaderSymbolSearchInfo
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedReaderSymbolSearchInfo
helpviewer_keywords:
- ISymUnmanagedReaderSymbolSearchInfo interface [.NET Framework debugging]
ms.assetid: fde7e21d-1169-4bed-a34d-792e69652bf9
topic_type:
- apiref
ms.openlocfilehash: 3f6cea68a4379f8769ccbdbc6911cc5c425d3369
ms.sourcegitcommit: 27db07ffb26f76912feefba7b884313547410db5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/19/2020
ms.locfileid: "83614881"
---
# <a name="isymunmanagedreadersymbolsearchinfo-interface"></a><span data-ttu-id="3dcc7-102">Интерфейс ISymUnmanagedReaderSymbolSearchInfo</span><span class="sxs-lookup"><span data-stu-id="3dcc7-102">ISymUnmanagedReaderSymbolSearchInfo Interface</span></span>
<span data-ttu-id="3dcc7-103">Предоставляет методы, которые получают сведения о поиске символов.</span><span class="sxs-lookup"><span data-stu-id="3dcc7-103">Provides methods that get symbol search information.</span></span> <span data-ttu-id="3dcc7-104">Получите этот интерфейс, вызвав `QueryInterface` для объекта, который реализует интерфейс [ISymUnmanagedReader](isymunmanagedreader-interface.md) .</span><span class="sxs-lookup"><span data-stu-id="3dcc7-104">Obtain this interface by calling `QueryInterface` on an object that implements the [ISymUnmanagedReader](isymunmanagedreader-interface.md) interface.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="3dcc7-105">Методы</span><span class="sxs-lookup"><span data-stu-id="3dcc7-105">Methods</span></span>  
  
|<span data-ttu-id="3dcc7-106">Метод</span><span class="sxs-lookup"><span data-stu-id="3dcc7-106">Method</span></span>|<span data-ttu-id="3dcc7-107">Описание</span><span class="sxs-lookup"><span data-stu-id="3dcc7-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="3dcc7-108">Метод GetSymbolSearchInfo</span><span class="sxs-lookup"><span data-stu-id="3dcc7-108">GetSymbolSearchInfo Method</span></span>](isymunmanagedreadersymbolsearchinfo-getsymbolsearchinfo-method.md)|<span data-ttu-id="3dcc7-109">Возвращает сведения о поиске символов.</span><span class="sxs-lookup"><span data-stu-id="3dcc7-109">Gets symbol search information.</span></span>|  
|[<span data-ttu-id="3dcc7-110">Метод GetSymbolSearchInfoCount</span><span class="sxs-lookup"><span data-stu-id="3dcc7-110">GetSymbolSearchInfoCount Method</span></span>](isymunmanagedreadersymbolsearchinfo-getsymbolsearchinfocount-method.md)|<span data-ttu-id="3dcc7-111">Возвращает число сведений о поиске символов.</span><span class="sxs-lookup"><span data-stu-id="3dcc7-111">Gets a count of symbol search information.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="3dcc7-112">Требования</span><span class="sxs-lookup"><span data-stu-id="3dcc7-112">Requirements</span></span>  
 <span data-ttu-id="3dcc7-113">**Заголовок:** Корсим. idl, Корсим. h</span><span class="sxs-lookup"><span data-stu-id="3dcc7-113">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3dcc7-114">Дополнительно</span><span class="sxs-lookup"><span data-stu-id="3dcc7-114">See also</span></span>

- [<span data-ttu-id="3dcc7-115">Интерфейсы хранилища символов диагностики</span><span class="sxs-lookup"><span data-stu-id="3dcc7-115">Diagnostics Symbol Store Interfaces</span></span>](diagnostics-symbol-store-interfaces.md)
