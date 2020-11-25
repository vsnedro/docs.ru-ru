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
ms.openlocfilehash: c5a43f6c277f582f9f14cefe5bfba6f5300c09d8
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/24/2020
ms.locfileid: "95727358"
---
# <a name="isymunmanagedbinder2-interface"></a><span data-ttu-id="fdb5f-102">Интерфейс ISymUnmanagedBinder2</span><span class="sxs-lookup"><span data-stu-id="fdb5f-102">ISymUnmanagedBinder2 Interface</span></span>

<span data-ttu-id="fdb5f-103">Представляет связыватель символов для неуправляемого кода и расширяет интерфейс [ISymUnmanagedBinder](isymunmanagedbinder-interface.md) .</span><span class="sxs-lookup"><span data-stu-id="fdb5f-103">Represents a symbol binder for unmanaged code, and extends the [ISymUnmanagedBinder](isymunmanagedbinder-interface.md) interface.</span></span>  
  
> [!IMPORTANT]
> <span data-ttu-id="fdb5f-104">При открытии файла базы данных программы (PDB) из ненадежного источника возникает угроза безопасности.</span><span class="sxs-lookup"><span data-stu-id="fdb5f-104">It is a security risk to open a program database (PDB) file from an untrusted source.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="fdb5f-105">Методы</span><span class="sxs-lookup"><span data-stu-id="fdb5f-105">Methods</span></span>  
  
|<span data-ttu-id="fdb5f-106">Метод</span><span class="sxs-lookup"><span data-stu-id="fdb5f-106">Method</span></span>|<span data-ttu-id="fdb5f-107">Описание</span><span class="sxs-lookup"><span data-stu-id="fdb5f-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="fdb5f-108">Метод GetReaderForFile2</span><span class="sxs-lookup"><span data-stu-id="fdb5f-108">GetReaderForFile2 Method</span></span>](isymunmanagedbinder2-getreaderforfile2-method.md)|<span data-ttu-id="fdb5f-109">При наличии интерфейса метаданных и имени файла возвращает правильный интерфейс [ISymUnmanagedReader](isymunmanagedreader-interface.md) , который будет считывать символы отладки, связанные с модулем.</span><span class="sxs-lookup"><span data-stu-id="fdb5f-109">Given a metadata interface and a file name, returns the correct [ISymUnmanagedReader](isymunmanagedreader-interface.md) interface that will read the debugging symbols associated with the module.</span></span> <span data-ttu-id="fdb5f-110">Предоставляет более широкие возможности поиска, чем метод [ISymUnmanagedBinder:: getreaderforfile:](isymunmanagedbinder-getreaderforfile-method.md) .</span><span class="sxs-lookup"><span data-stu-id="fdb5f-110">Provides a more extensive search than the [ISymUnmanagedBinder::GetReaderForFile](isymunmanagedbinder-getreaderforfile-method.md) method.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="fdb5f-111">Требования</span><span class="sxs-lookup"><span data-stu-id="fdb5f-111">Requirements</span></span>  

 <span data-ttu-id="fdb5f-112">**Заголовок:** Корсим. idl, Корсим. h</span><span class="sxs-lookup"><span data-stu-id="fdb5f-112">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fdb5f-113">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="fdb5f-113">See also</span></span>

- [<span data-ttu-id="fdb5f-114">Интерфейсы хранилища символов диагностики</span><span class="sxs-lookup"><span data-stu-id="fdb5f-114">Diagnostics Symbol Store Interfaces</span></span>](diagnostics-symbol-store-interfaces.md)
- [<span data-ttu-id="fdb5f-115">Интерфейс ISymUnmanagedBinder</span><span class="sxs-lookup"><span data-stu-id="fdb5f-115">ISymUnmanagedBinder Interface</span></span>](isymunmanagedbinder-interface.md)
- [<span data-ttu-id="fdb5f-116">Интерфейс ISymUnmanagedBinder3</span><span class="sxs-lookup"><span data-stu-id="fdb5f-116">ISymUnmanagedBinder3 Interface</span></span>](isymunmanagedbinder3-interface.md)
