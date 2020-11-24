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
ms.openlocfilehash: af4124aed823a0a2475a181efe3fa68e1fae0bfe
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/24/2020
ms.locfileid: "95678393"
---
# <a name="isymunmanagedreadersymbolsearchinfo-interface"></a><span data-ttu-id="0e051-102">Интерфейс ISymUnmanagedReaderSymbolSearchInfo</span><span class="sxs-lookup"><span data-stu-id="0e051-102">ISymUnmanagedReaderSymbolSearchInfo Interface</span></span>

<span data-ttu-id="0e051-103">Предоставляет методы, которые получают сведения о поиске символов.</span><span class="sxs-lookup"><span data-stu-id="0e051-103">Provides methods that get symbol search information.</span></span> <span data-ttu-id="0e051-104">Получите этот интерфейс, вызвав `QueryInterface` для объекта, который реализует интерфейс [ISymUnmanagedReader](isymunmanagedreader-interface.md) .</span><span class="sxs-lookup"><span data-stu-id="0e051-104">Obtain this interface by calling `QueryInterface` on an object that implements the [ISymUnmanagedReader](isymunmanagedreader-interface.md) interface.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="0e051-105">Методы</span><span class="sxs-lookup"><span data-stu-id="0e051-105">Methods</span></span>  
  
|<span data-ttu-id="0e051-106">Метод</span><span class="sxs-lookup"><span data-stu-id="0e051-106">Method</span></span>|<span data-ttu-id="0e051-107">Описание</span><span class="sxs-lookup"><span data-stu-id="0e051-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="0e051-108">Метод GetSymbolSearchInfo</span><span class="sxs-lookup"><span data-stu-id="0e051-108">GetSymbolSearchInfo Method</span></span>](isymunmanagedreadersymbolsearchinfo-getsymbolsearchinfo-method.md)|<span data-ttu-id="0e051-109">Возвращает сведения о поиске символов.</span><span class="sxs-lookup"><span data-stu-id="0e051-109">Gets symbol search information.</span></span>|  
|[<span data-ttu-id="0e051-110">Метод GetSymbolSearchInfoCount</span><span class="sxs-lookup"><span data-stu-id="0e051-110">GetSymbolSearchInfoCount Method</span></span>](isymunmanagedreadersymbolsearchinfo-getsymbolsearchinfocount-method.md)|<span data-ttu-id="0e051-111">Возвращает число сведений о поиске символов.</span><span class="sxs-lookup"><span data-stu-id="0e051-111">Gets a count of symbol search information.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="0e051-112">Требования</span><span class="sxs-lookup"><span data-stu-id="0e051-112">Requirements</span></span>  

 <span data-ttu-id="0e051-113">**Заголовок:** Корсим. idl, Корсим. h</span><span class="sxs-lookup"><span data-stu-id="0e051-113">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0e051-114">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="0e051-114">See also</span></span>

- [<span data-ttu-id="0e051-115">Интерфейсы хранилища символов диагностики</span><span class="sxs-lookup"><span data-stu-id="0e051-115">Diagnostics Symbol Store Interfaces</span></span>](diagnostics-symbol-store-interfaces.md)
