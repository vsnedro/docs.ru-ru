---
title: Интерфейс ISymUnmanagedSourceServerModule
ms.date: 03/30/2017
api_name:
- ISymUnmanagedSourceServerModule
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedSourceServerModule
helpviewer_keywords:
- ISymUnmanagedSourceServerModule interface [.NET Framework debugging]
ms.assetid: a19b23bd-2061-476e-b67d-252f57404f8b
topic_type:
- apiref
ms.openlocfilehash: 5e438c75a29984e9200dc240f389f079a4eecfd7
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/24/2020
ms.locfileid: "95733958"
---
# <a name="isymunmanagedsourceservermodule-interface"></a><span data-ttu-id="25a2d-102">Интерфейс ISymUnmanagedSourceServerModule</span><span class="sxs-lookup"><span data-stu-id="25a2d-102">ISymUnmanagedSourceServerModule Interface</span></span>

<span data-ttu-id="25a2d-103">Предоставляет данные сервера-источника для модуля.</span><span class="sxs-lookup"><span data-stu-id="25a2d-103">Provides source server data for a module.</span></span> <span data-ttu-id="25a2d-104">Получите этот интерфейс, вызвав `QueryInterface` для объекта, который реализует интерфейс [ISymUnmanagedReader](isymunmanagedreader-interface.md) .</span><span class="sxs-lookup"><span data-stu-id="25a2d-104">Obtain this interface by calling `QueryInterface` on an object that implements the [ISymUnmanagedReader](isymunmanagedreader-interface.md) interface.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="25a2d-105">Методы</span><span class="sxs-lookup"><span data-stu-id="25a2d-105">Methods</span></span>  
  
|<span data-ttu-id="25a2d-106">Метод</span><span class="sxs-lookup"><span data-stu-id="25a2d-106">Method</span></span>|<span data-ttu-id="25a2d-107">Описание</span><span class="sxs-lookup"><span data-stu-id="25a2d-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="25a2d-108">Метод GetSourceServerData</span><span class="sxs-lookup"><span data-stu-id="25a2d-108">GetSourceServerData Method</span></span>](isymunmanagedsourceservermodule-getsourceserverdata-method.md)|<span data-ttu-id="25a2d-109">Возвращает данные исходного сервера для модуля.</span><span class="sxs-lookup"><span data-stu-id="25a2d-109">Returns the source server data for the module.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="25a2d-110">Требования</span><span class="sxs-lookup"><span data-stu-id="25a2d-110">Requirements</span></span>  

 <span data-ttu-id="25a2d-111">**Заголовок:** Корсим. idl, Корсим. h</span><span class="sxs-lookup"><span data-stu-id="25a2d-111">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="25a2d-112">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="25a2d-112">See also</span></span>

- [<span data-ttu-id="25a2d-113">Интерфейсы хранилища символов диагностики</span><span class="sxs-lookup"><span data-stu-id="25a2d-113">Diagnostics Symbol Store Interfaces</span></span>](diagnostics-symbol-store-interfaces.md)
