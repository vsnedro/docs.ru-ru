---
title: Интерфейс ISymUnmanagedWriter2
ms.date: 03/30/2017
api_name:
- ISymUnmanagedWriter2
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedWriter2
helpviewer_keywords:
- ISymUnmanagedWriter2 interface [.NET Framework debugging]
ms.assetid: 8e78faa4-cf43-44fb-a91d-94d6df692a25
topic_type:
- apiref
ms.openlocfilehash: 1fe6055d930c6d30e947d6bc774d0520a9e175ae
ms.sourcegitcommit: 27db07ffb26f76912feefba7b884313547410db5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/19/2020
ms.locfileid: "83614686"
---
# <a name="isymunmanagedwriter2-interface"></a><span data-ttu-id="38b74-102">Интерфейс ISymUnmanagedWriter2</span><span class="sxs-lookup"><span data-stu-id="38b74-102">ISymUnmanagedWriter2 Interface</span></span>
<span data-ttu-id="38b74-103">Представляет средство записи символов и предоставляет методы для определения документов, точек следования, лексических областей и переменных.</span><span class="sxs-lookup"><span data-stu-id="38b74-103">Represents a symbol writer, and provides methods to define documents, sequence points, lexical scopes, and variables.</span></span> <span data-ttu-id="38b74-104">Этот интерфейс расширяет интерфейс [ISymUnmanagedWriter](isymunmanagedwriter-interface.md) .</span><span class="sxs-lookup"><span data-stu-id="38b74-104">This interface extends the [ISymUnmanagedWriter](isymunmanagedwriter-interface.md) interface.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="38b74-105">Методы</span><span class="sxs-lookup"><span data-stu-id="38b74-105">Methods</span></span>  
  
|<span data-ttu-id="38b74-106">Метод</span><span class="sxs-lookup"><span data-stu-id="38b74-106">Method</span></span>|<span data-ttu-id="38b74-107">Описание</span><span class="sxs-lookup"><span data-stu-id="38b74-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="38b74-108">Метод DefineConstant2</span><span class="sxs-lookup"><span data-stu-id="38b74-108">DefineConstant2 Method</span></span>](isymunmanagedwriter2-defineconstant2-method.md)|<span data-ttu-id="38b74-109">Определяет имя для постоянного значения.</span><span class="sxs-lookup"><span data-stu-id="38b74-109">Defines a name for a constant value.</span></span>|  
|[<span data-ttu-id="38b74-110">Метод DefineGlobalVariable2</span><span class="sxs-lookup"><span data-stu-id="38b74-110">DefineGlobalVariable2 Method</span></span>](isymunmanagedwriter2-defineglobalvariable2-method.md)|<span data-ttu-id="38b74-111">Определяет одну глобальную переменную.</span><span class="sxs-lookup"><span data-stu-id="38b74-111">Defines a single global variable.</span></span>|  
|[<span data-ttu-id="38b74-112">Метод DefineLocalVariable2</span><span class="sxs-lookup"><span data-stu-id="38b74-112">DefineLocalVariable2 Method</span></span>](isymunmanagedwriter2-definelocalvariable2-method.md)|<span data-ttu-id="38b74-113">Определяет одну переменную в текущей лексической области видимости.</span><span class="sxs-lookup"><span data-stu-id="38b74-113">Defines a single variable in the current lexical scope.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="38b74-114">Требования</span><span class="sxs-lookup"><span data-stu-id="38b74-114">Requirements</span></span>  
 <span data-ttu-id="38b74-115">**Заголовок:** Корсим. idl, Корсим. h</span><span class="sxs-lookup"><span data-stu-id="38b74-115">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="38b74-116">Дополнительно</span><span class="sxs-lookup"><span data-stu-id="38b74-116">See also</span></span>

- [<span data-ttu-id="38b74-117">Интерфейсы хранилища символов диагностики</span><span class="sxs-lookup"><span data-stu-id="38b74-117">Diagnostics Symbol Store Interfaces</span></span>](diagnostics-symbol-store-interfaces.md)
- [<span data-ttu-id="38b74-118">Интерфейс ISymUnmanagedWriter</span><span class="sxs-lookup"><span data-stu-id="38b74-118">ISymUnmanagedWriter Interface</span></span>](isymunmanagedwriter-interface.md)
- [<span data-ttu-id="38b74-119">Интерфейс ISymUnmanagedWriter3</span><span class="sxs-lookup"><span data-stu-id="38b74-119">ISymUnmanagedWriter3 Interface</span></span>](isymunmanagedwriter3-interface.md)
