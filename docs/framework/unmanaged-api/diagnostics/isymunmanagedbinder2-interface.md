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
ms.openlocfilehash: 8a4fbb40ec2426d000628fbd6d5f0241d3152c18
ms.sourcegitcommit: 7b1497c1927cb449cefd313bc5126ae37df30746
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/16/2020
ms.locfileid: "83441673"
---
# <a name="isymunmanagedbinder2-interface"></a><span data-ttu-id="a63d9-102">Интерфейс ISymUnmanagedBinder2</span><span class="sxs-lookup"><span data-stu-id="a63d9-102">ISymUnmanagedBinder2 Interface</span></span>
<span data-ttu-id="a63d9-103">Представляет связыватель символов для неуправляемого кода и расширяет интерфейс [ISymUnmanagedBinder](isymunmanagedbinder-interface.md) .</span><span class="sxs-lookup"><span data-stu-id="a63d9-103">Represents a symbol binder for unmanaged code, and extends the [ISymUnmanagedBinder](isymunmanagedbinder-interface.md) interface.</span></span>  
  
> [!IMPORTANT]
> <span data-ttu-id="a63d9-104">При открытии файла базы данных программы (PDB) из ненадежного источника возникает угроза безопасности.</span><span class="sxs-lookup"><span data-stu-id="a63d9-104">It is a security risk to open a program database (PDB) file from an untrusted source.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="a63d9-105">Методы</span><span class="sxs-lookup"><span data-stu-id="a63d9-105">Methods</span></span>  
  
|<span data-ttu-id="a63d9-106">Метод</span><span class="sxs-lookup"><span data-stu-id="a63d9-106">Method</span></span>|<span data-ttu-id="a63d9-107">Описание</span><span class="sxs-lookup"><span data-stu-id="a63d9-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="a63d9-108">Метод GetReaderForFile2</span><span class="sxs-lookup"><span data-stu-id="a63d9-108">GetReaderForFile2 Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedbinder2-getreaderforfile2-method.md)|<span data-ttu-id="a63d9-109">При наличии интерфейса метаданных и имени файла возвращает правильный интерфейс [ISymUnmanagedReader](isymunmanagedreader-interface.md) , который будет считывать символы отладки, связанные с модулем.</span><span class="sxs-lookup"><span data-stu-id="a63d9-109">Given a metadata interface and a file name, returns the correct [ISymUnmanagedReader](isymunmanagedreader-interface.md) interface that will read the debugging symbols associated with the module.</span></span> <span data-ttu-id="a63d9-110">Предоставляет более широкие возможности поиска, чем метод [ISymUnmanagedBinder:: getreaderforfile:](isymunmanagedbinder-getreaderforfile-method.md) .</span><span class="sxs-lookup"><span data-stu-id="a63d9-110">Provides a more extensive search than the [ISymUnmanagedBinder::GetReaderForFile](isymunmanagedbinder-getreaderforfile-method.md) method.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="a63d9-111">Требования</span><span class="sxs-lookup"><span data-stu-id="a63d9-111">Requirements</span></span>  
 <span data-ttu-id="a63d9-112">**Заголовок:** Корсим. idl, Корсим. h</span><span class="sxs-lookup"><span data-stu-id="a63d9-112">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a63d9-113">Дополнительно</span><span class="sxs-lookup"><span data-stu-id="a63d9-113">See also</span></span>

- [<span data-ttu-id="a63d9-114">Интерфейсы хранилища символов диагностики</span><span class="sxs-lookup"><span data-stu-id="a63d9-114">Diagnostics Symbol Store Interfaces</span></span>](diagnostics-symbol-store-interfaces.md)
- [<span data-ttu-id="a63d9-115">Интерфейс ISymUnmanagedBinder</span><span class="sxs-lookup"><span data-stu-id="a63d9-115">ISymUnmanagedBinder Interface</span></span>](isymunmanagedbinder-interface.md)
- [<span data-ttu-id="a63d9-116">Интерфейс ISymUnmanagedBinder3</span><span class="sxs-lookup"><span data-stu-id="a63d9-116">ISymUnmanagedBinder3 Interface</span></span>](isymunmanagedbinder3-interface.md)
