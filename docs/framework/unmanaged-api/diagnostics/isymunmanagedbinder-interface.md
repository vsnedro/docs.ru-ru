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
ms.openlocfilehash: f4f925282d65cd9cbc8eb1c8825f358602de68ed
ms.sourcegitcommit: 7b1497c1927cb449cefd313bc5126ae37df30746
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/16/2020
ms.locfileid: "83441699"
---
# <a name="isymunmanagedbinder-interface"></a><span data-ttu-id="f1afb-102">Интерфейс ISymUnmanagedBinder</span><span class="sxs-lookup"><span data-stu-id="f1afb-102">ISymUnmanagedBinder Interface</span></span>
<span data-ttu-id="f1afb-103">Представляет связыватель символов для неуправляемого кода.</span><span class="sxs-lookup"><span data-stu-id="f1afb-103">Represents a symbol binder for unmanaged code.</span></span>  
  
> [!IMPORTANT]
> <span data-ttu-id="f1afb-104">При открытии файла базы данных программы (PDB) из ненадежного источника возникает угроза безопасности.</span><span class="sxs-lookup"><span data-stu-id="f1afb-104">It is a security risk to open a program database (PDB) file from an untrusted source.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="f1afb-105">Методы</span><span class="sxs-lookup"><span data-stu-id="f1afb-105">Methods</span></span>  
  
|<span data-ttu-id="f1afb-106">Метод</span><span class="sxs-lookup"><span data-stu-id="f1afb-106">Method</span></span>|<span data-ttu-id="f1afb-107">Описание</span><span class="sxs-lookup"><span data-stu-id="f1afb-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="f1afb-108">Метод GetReaderForFile</span><span class="sxs-lookup"><span data-stu-id="f1afb-108">GetReaderForFile Method</span></span>](isymunmanagedbinder-getreaderforfile-method.md)|<span data-ttu-id="f1afb-109">При наличии интерфейса метаданных и имени файла возвращает правильную структуру [ISymUnmanagedReader](isymunmanagedreader-interface.md) , которая будет считывать отладочные символы, связанные с модулем.</span><span class="sxs-lookup"><span data-stu-id="f1afb-109">Given a metadata interface and a file name, returns the correct [ISymUnmanagedReader](isymunmanagedreader-interface.md) structure that will read the debugging symbols associated with the module.</span></span>|  
|[<span data-ttu-id="f1afb-110">Метод GetReaderFromStream</span><span class="sxs-lookup"><span data-stu-id="f1afb-110">GetReaderFromStream Method</span></span>](isymunmanagedbinder-getreaderfromstream-method.md)|<span data-ttu-id="f1afb-111">При наличии интерфейса метаданных и потока, содержащего хранилище символов, возвращает правильную структуру [ISymUnmanagedReader](isymunmanagedreader-interface.md) , которая будет считывать отладочные символы из заданного хранилища символов.</span><span class="sxs-lookup"><span data-stu-id="f1afb-111">Given a metadata interface and a stream that contains the symbol store, returns the correct [ISymUnmanagedReader](isymunmanagedreader-interface.md) structure that will read the debugging symbols from the given symbol store.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="f1afb-112">Требования</span><span class="sxs-lookup"><span data-stu-id="f1afb-112">Requirements</span></span>  
 <span data-ttu-id="f1afb-113">**Заголовок:** Корсим. idl, Корсим. h</span><span class="sxs-lookup"><span data-stu-id="f1afb-113">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f1afb-114">Дополнительно</span><span class="sxs-lookup"><span data-stu-id="f1afb-114">See also</span></span>

- [<span data-ttu-id="f1afb-115">Интерфейсы хранилища символов диагностики</span><span class="sxs-lookup"><span data-stu-id="f1afb-115">Diagnostics Symbol Store Interfaces</span></span>](diagnostics-symbol-store-interfaces.md)
- [<span data-ttu-id="f1afb-116">Интерфейс ISymUnmanagedBinder2</span><span class="sxs-lookup"><span data-stu-id="f1afb-116">ISymUnmanagedBinder2 Interface</span></span>](isymunmanagedbinder2-interface.md)
- [<span data-ttu-id="f1afb-117">Интерфейс ISymUnmanagedBinder3</span><span class="sxs-lookup"><span data-stu-id="f1afb-117">ISymUnmanagedBinder3 Interface</span></span>](isymunmanagedbinder3-interface.md)
