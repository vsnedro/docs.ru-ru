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
ms.openlocfilehash: d90a55b53ba00540137e44fc190790c4710903e3
ms.sourcegitcommit: 27db07ffb26f76912feefba7b884313547410db5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/19/2020
ms.locfileid: "83610799"
---
# <a name="isymunmanagedsourceservermodule-interface"></a><span data-ttu-id="4f2dd-102">Интерфейс ISymUnmanagedSourceServerModule</span><span class="sxs-lookup"><span data-stu-id="4f2dd-102">ISymUnmanagedSourceServerModule Interface</span></span>
<span data-ttu-id="4f2dd-103">Предоставляет данные сервера-источника для модуля.</span><span class="sxs-lookup"><span data-stu-id="4f2dd-103">Provides source server data for a module.</span></span> <span data-ttu-id="4f2dd-104">Получите этот интерфейс, вызвав `QueryInterface` для объекта, который реализует интерфейс [ISymUnmanagedReader](isymunmanagedreader-interface.md) .</span><span class="sxs-lookup"><span data-stu-id="4f2dd-104">Obtain this interface by calling `QueryInterface` on an object that implements the [ISymUnmanagedReader](isymunmanagedreader-interface.md) interface.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="4f2dd-105">Методы</span><span class="sxs-lookup"><span data-stu-id="4f2dd-105">Methods</span></span>  
  
|<span data-ttu-id="4f2dd-106">Метод</span><span class="sxs-lookup"><span data-stu-id="4f2dd-106">Method</span></span>|<span data-ttu-id="4f2dd-107">Описание</span><span class="sxs-lookup"><span data-stu-id="4f2dd-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="4f2dd-108">Метод GetSourceServerData</span><span class="sxs-lookup"><span data-stu-id="4f2dd-108">GetSourceServerData Method</span></span>](isymunmanagedsourceservermodule-getsourceserverdata-method.md)|<span data-ttu-id="4f2dd-109">Возвращает данные исходного сервера для модуля.</span><span class="sxs-lookup"><span data-stu-id="4f2dd-109">Returns the source server data for the module.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="4f2dd-110">Требования</span><span class="sxs-lookup"><span data-stu-id="4f2dd-110">Requirements</span></span>  
 <span data-ttu-id="4f2dd-111">**Заголовок:** Корсим. idl, Корсим. h</span><span class="sxs-lookup"><span data-stu-id="4f2dd-111">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4f2dd-112">Дополнительно</span><span class="sxs-lookup"><span data-stu-id="4f2dd-112">See also</span></span>

- [<span data-ttu-id="4f2dd-113">Интерфейсы хранилища символов диагностики</span><span class="sxs-lookup"><span data-stu-id="4f2dd-113">Diagnostics Symbol Store Interfaces</span></span>](diagnostics-symbol-store-interfaces.md)
