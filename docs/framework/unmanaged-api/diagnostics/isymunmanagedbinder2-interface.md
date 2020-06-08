---
title: Интерфейс ISymUnmanagedBinder2
ms.date: 03/30/2017
api_name:
- ISymUnmanagedBinder2
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedBinder2 Interface
helpviewer_keywords:
- ISymUnmanagedBinder2 interface [.NET Framework debugging]
ms.assetid: 7a59f405-73e8-4434-8bcc-a9dc45ea08e6
topic_type:
- apiref
ms.openlocfilehash: f6155eb777b5071ff522af4f27d5fb2d73aa25ef
ms.sourcegitcommit: da21fc5a8cce1e028575acf31974681a1bc5aeed
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/08/2020
ms.locfileid: "84501837"
---
# <a name="isymunmanagedbinder2-interface"></a><span data-ttu-id="4d1eb-102">Интерфейс ISymUnmanagedBinder2</span><span class="sxs-lookup"><span data-stu-id="4d1eb-102">ISymUnmanagedBinder2 Interface</span></span>
<span data-ttu-id="4d1eb-103">Представляет связыватель символов для неуправляемого кода и расширяет интерфейс [ISymUnmanagedBinder](isymunmanagedbinder-interface.md) .</span><span class="sxs-lookup"><span data-stu-id="4d1eb-103">Represents a symbol binder for unmanaged code, and extends the [ISymUnmanagedBinder](isymunmanagedbinder-interface.md) interface.</span></span>  
  
> [!IMPORTANT]
> <span data-ttu-id="4d1eb-104">При открытии файла базы данных программы (PDB) из ненадежного источника возникает угроза безопасности.</span><span class="sxs-lookup"><span data-stu-id="4d1eb-104">It is a security risk to open a program database (PDB) file from an untrusted source.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="4d1eb-105">Методы</span><span class="sxs-lookup"><span data-stu-id="4d1eb-105">Methods</span></span>  
  
|<span data-ttu-id="4d1eb-106">Метод</span><span class="sxs-lookup"><span data-stu-id="4d1eb-106">Method</span></span>|<span data-ttu-id="4d1eb-107">Описание</span><span class="sxs-lookup"><span data-stu-id="4d1eb-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="4d1eb-108">Метод GetReaderForFile2</span><span class="sxs-lookup"><span data-stu-id="4d1eb-108">GetReaderForFile2 Method</span></span>](isymunmanagedbinder2-getreaderforfile2-method.md)|<span data-ttu-id="4d1eb-109">При наличии интерфейса метаданных и имени файла возвращает правильный интерфейс [ISymUnmanagedReader](isymunmanagedreader-interface.md) , который будет считывать символы отладки, связанные с модулем.</span><span class="sxs-lookup"><span data-stu-id="4d1eb-109">Given a metadata interface and a file name, returns the correct [ISymUnmanagedReader](isymunmanagedreader-interface.md) interface that will read the debugging symbols associated with the module.</span></span> <span data-ttu-id="4d1eb-110">Предоставляет более широкие возможности поиска, чем метод [ISymUnmanagedBinder:: getreaderforfile:](isymunmanagedbinder-getreaderforfile-method.md) .</span><span class="sxs-lookup"><span data-stu-id="4d1eb-110">Provides a more extensive search than the [ISymUnmanagedBinder::GetReaderForFile](isymunmanagedbinder-getreaderforfile-method.md) method.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="4d1eb-111">Требования</span><span class="sxs-lookup"><span data-stu-id="4d1eb-111">Requirements</span></span>  
 <span data-ttu-id="4d1eb-112">**Заголовок:** Корсим. idl, Корсим. h</span><span class="sxs-lookup"><span data-stu-id="4d1eb-112">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4d1eb-113">См. также</span><span class="sxs-lookup"><span data-stu-id="4d1eb-113">See also</span></span>

- [<span data-ttu-id="4d1eb-114">Интерфейсы хранилища символов диагностики</span><span class="sxs-lookup"><span data-stu-id="4d1eb-114">Diagnostics Symbol Store Interfaces</span></span>](diagnostics-symbol-store-interfaces.md)
- [<span data-ttu-id="4d1eb-115">Интерфейс ISymUnmanagedBinder</span><span class="sxs-lookup"><span data-stu-id="4d1eb-115">ISymUnmanagedBinder Interface</span></span>](isymunmanagedbinder-interface.md)
- [<span data-ttu-id="4d1eb-116">Интерфейс ISymUnmanagedBinder3</span><span class="sxs-lookup"><span data-stu-id="4d1eb-116">ISymUnmanagedBinder3 Interface</span></span>](isymunmanagedbinder3-interface.md)
