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
ms.openlocfilehash: 6feb48b7c78dda64ba372e470b83ffb14f21f2f9
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/24/2020
ms.locfileid: "95683333"
---
# <a name="isymunmanagedwriter2-interface"></a><span data-ttu-id="c3700-102">Интерфейс ISymUnmanagedWriter2</span><span class="sxs-lookup"><span data-stu-id="c3700-102">ISymUnmanagedWriter2 Interface</span></span>

<span data-ttu-id="c3700-103">Представляет средство записи символов и предоставляет методы для определения документов, точек следования, лексических областей и переменных.</span><span class="sxs-lookup"><span data-stu-id="c3700-103">Represents a symbol writer, and provides methods to define documents, sequence points, lexical scopes, and variables.</span></span> <span data-ttu-id="c3700-104">Этот интерфейс расширяет интерфейс [ISymUnmanagedWriter](isymunmanagedwriter-interface.md) .</span><span class="sxs-lookup"><span data-stu-id="c3700-104">This interface extends the [ISymUnmanagedWriter](isymunmanagedwriter-interface.md) interface.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="c3700-105">Методы</span><span class="sxs-lookup"><span data-stu-id="c3700-105">Methods</span></span>  
  
|<span data-ttu-id="c3700-106">Метод</span><span class="sxs-lookup"><span data-stu-id="c3700-106">Method</span></span>|<span data-ttu-id="c3700-107">Описание</span><span class="sxs-lookup"><span data-stu-id="c3700-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="c3700-108">Метод DefineConstant2</span><span class="sxs-lookup"><span data-stu-id="c3700-108">DefineConstant2 Method</span></span>](isymunmanagedwriter2-defineconstant2-method.md)|<span data-ttu-id="c3700-109">Определяет имя для постоянного значения.</span><span class="sxs-lookup"><span data-stu-id="c3700-109">Defines a name for a constant value.</span></span>|  
|[<span data-ttu-id="c3700-110">Метод DefineGlobalVariable2</span><span class="sxs-lookup"><span data-stu-id="c3700-110">DefineGlobalVariable2 Method</span></span>](isymunmanagedwriter2-defineglobalvariable2-method.md)|<span data-ttu-id="c3700-111">Определяет одну глобальную переменную.</span><span class="sxs-lookup"><span data-stu-id="c3700-111">Defines a single global variable.</span></span>|  
|[<span data-ttu-id="c3700-112">Метод DefineLocalVariable2</span><span class="sxs-lookup"><span data-stu-id="c3700-112">DefineLocalVariable2 Method</span></span>](isymunmanagedwriter2-definelocalvariable2-method.md)|<span data-ttu-id="c3700-113">Определяет одну переменную в текущей лексической области видимости.</span><span class="sxs-lookup"><span data-stu-id="c3700-113">Defines a single variable in the current lexical scope.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="c3700-114">Требования</span><span class="sxs-lookup"><span data-stu-id="c3700-114">Requirements</span></span>  

 <span data-ttu-id="c3700-115">**Заголовок:** Корсим. idl, Корсим. h</span><span class="sxs-lookup"><span data-stu-id="c3700-115">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c3700-116">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="c3700-116">See also</span></span>

- [<span data-ttu-id="c3700-117">Интерфейсы хранилища символов диагностики</span><span class="sxs-lookup"><span data-stu-id="c3700-117">Diagnostics Symbol Store Interfaces</span></span>](diagnostics-symbol-store-interfaces.md)
- [<span data-ttu-id="c3700-118">Интерфейс ISymUnmanagedWriter</span><span class="sxs-lookup"><span data-stu-id="c3700-118">ISymUnmanagedWriter Interface</span></span>](isymunmanagedwriter-interface.md)
- [<span data-ttu-id="c3700-119">Интерфейс ISymUnmanagedWriter3</span><span class="sxs-lookup"><span data-stu-id="c3700-119">ISymUnmanagedWriter3 Interface</span></span>](isymunmanagedwriter3-interface.md)
