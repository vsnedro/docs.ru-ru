---
title: Интерфейс ISymUnmanagedBinder
ms.date: 03/30/2017
api_name:
- ISymUnmanagedBinder
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedBinder
helpviewer_keywords:
- ISymUnmanagedBinder interface [.NET Framework debugging]
ms.assetid: b22fbe19-b30f-4696-8175-e6b91da9edab
topic_type:
- apiref
ms.openlocfilehash: 554e59484f00626726f7f024c69e93a5e6647130
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/24/2020
ms.locfileid: "95727384"
---
# <a name="isymunmanagedbinder-interface"></a><span data-ttu-id="0d2d5-102">Интерфейс ISymUnmanagedBinder</span><span class="sxs-lookup"><span data-stu-id="0d2d5-102">ISymUnmanagedBinder Interface</span></span>

<span data-ttu-id="0d2d5-103">Представляет модуль привязки символов для неуправляемого кода.</span><span class="sxs-lookup"><span data-stu-id="0d2d5-103">Represents a symbol binder for unmanaged code.</span></span>  
  
> [!IMPORTANT]
> <span data-ttu-id="0d2d5-104">При открытии файла базы данных программы (PDB) из ненадежного источника возникает угроза безопасности.</span><span class="sxs-lookup"><span data-stu-id="0d2d5-104">It is a security risk to open a program database (PDB) file from an untrusted source.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="0d2d5-105">Методы</span><span class="sxs-lookup"><span data-stu-id="0d2d5-105">Methods</span></span>  
  
|<span data-ttu-id="0d2d5-106">Метод</span><span class="sxs-lookup"><span data-stu-id="0d2d5-106">Method</span></span>|<span data-ttu-id="0d2d5-107">Описание</span><span class="sxs-lookup"><span data-stu-id="0d2d5-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="0d2d5-108">Метод GetReaderForFile</span><span class="sxs-lookup"><span data-stu-id="0d2d5-108">GetReaderForFile Method</span></span>](isymunmanagedbinder-getreaderforfile-method.md)|<span data-ttu-id="0d2d5-109">При наличии интерфейса метаданных и имени файла возвращает правильную структуру [ISymUnmanagedReader](isymunmanagedreader-interface.md) , которая будет считывать отладочные символы, связанные с модулем.</span><span class="sxs-lookup"><span data-stu-id="0d2d5-109">Given a metadata interface and a file name, returns the correct [ISymUnmanagedReader](isymunmanagedreader-interface.md) structure that will read the debugging symbols associated with the module.</span></span>|  
|[<span data-ttu-id="0d2d5-110">Метод GetReaderFromStream</span><span class="sxs-lookup"><span data-stu-id="0d2d5-110">GetReaderFromStream Method</span></span>](isymunmanagedbinder-getreaderfromstream-method.md)|<span data-ttu-id="0d2d5-111">При наличии интерфейса метаданных и потока, содержащего хранилище символов, возвращает правильную структуру [ISymUnmanagedReader](isymunmanagedreader-interface.md) , которая будет считывать отладочные символы из заданного хранилища символов.</span><span class="sxs-lookup"><span data-stu-id="0d2d5-111">Given a metadata interface and a stream that contains the symbol store, returns the correct [ISymUnmanagedReader](isymunmanagedreader-interface.md) structure that will read the debugging symbols from the given symbol store.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="0d2d5-112">Требования</span><span class="sxs-lookup"><span data-stu-id="0d2d5-112">Requirements</span></span>  

 <span data-ttu-id="0d2d5-113">**Заголовок:** Корсим. idl, Корсим. h</span><span class="sxs-lookup"><span data-stu-id="0d2d5-113">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0d2d5-114">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="0d2d5-114">See also</span></span>

- [<span data-ttu-id="0d2d5-115">Интерфейсы хранилища символов диагностики</span><span class="sxs-lookup"><span data-stu-id="0d2d5-115">Diagnostics Symbol Store Interfaces</span></span>](diagnostics-symbol-store-interfaces.md)
- [<span data-ttu-id="0d2d5-116">Интерфейс ISymUnmanagedBinder2</span><span class="sxs-lookup"><span data-stu-id="0d2d5-116">ISymUnmanagedBinder2 Interface</span></span>](isymunmanagedbinder2-interface.md)
- [<span data-ttu-id="0d2d5-117">Интерфейс ISymUnmanagedBinder3</span><span class="sxs-lookup"><span data-stu-id="0d2d5-117">ISymUnmanagedBinder3 Interface</span></span>](isymunmanagedbinder3-interface.md)
