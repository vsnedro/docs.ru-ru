---
title: Интерфейс ISymUnmanagedMethod
ms.date: 03/30/2017
api_name:
- ISymUnmanagedMethod
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedMethod
helpviewer_keywords:
- ISymUnmanagedMethod interface [.NET Framework debugging]
ms.assetid: f204d74c-cc79-4092-83bb-60654be95649
topic_type:
- apiref
ms.openlocfilehash: b72a77fecd15a43efbddd9dfd4618897c3372f88
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/24/2020
ms.locfileid: "95699278"
---
# <a name="isymunmanagedmethod-interface"></a><span data-ttu-id="c7c06-102">Интерфейс ISymUnmanagedMethod</span><span class="sxs-lookup"><span data-stu-id="c7c06-102">ISymUnmanagedMethod Interface</span></span>

<span data-ttu-id="c7c06-103">Представляет метод в хранилище символов.</span><span class="sxs-lookup"><span data-stu-id="c7c06-103">Represents a method within the symbol store.</span></span> <span data-ttu-id="c7c06-104">Этот интерфейс предоставляет доступ только к атрибутам метода, относящимся к символам, а не к атрибутам, связанным с типом.</span><span class="sxs-lookup"><span data-stu-id="c7c06-104">This interface provides access to only the symbol-related attributes of a method, instead of the type-related attributes.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="c7c06-105">Методы</span><span class="sxs-lookup"><span data-stu-id="c7c06-105">Methods</span></span>  
  
|<span data-ttu-id="c7c06-106">Метод</span><span class="sxs-lookup"><span data-stu-id="c7c06-106">Method</span></span>|<span data-ttu-id="c7c06-107">Описание</span><span class="sxs-lookup"><span data-stu-id="c7c06-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="c7c06-108">Метод GetNamespace</span><span class="sxs-lookup"><span data-stu-id="c7c06-108">GetNamespace Method</span></span>](isymunmanagedmethod-getnamespace-method.md)|<span data-ttu-id="c7c06-109">Возвращает пространство имен, в котором определен этот метод.</span><span class="sxs-lookup"><span data-stu-id="c7c06-109">Gets the namespace within which this method is defined.</span></span>|  
|[<span data-ttu-id="c7c06-110">Метод GetOffset</span><span class="sxs-lookup"><span data-stu-id="c7c06-110">GetOffset Method</span></span>](isymunmanagedmethod-getoffset-method.md)|<span data-ttu-id="c7c06-111">Возвращает смещение в этом методе, соответствующее заданной позиции в документе.</span><span class="sxs-lookup"><span data-stu-id="c7c06-111">Returns the offset within this method that corresponds to a given position within a document.</span></span>|  
|[<span data-ttu-id="c7c06-112">Метод GetParameters</span><span class="sxs-lookup"><span data-stu-id="c7c06-112">GetParameters Method</span></span>](isymunmanagedmethod-getparameters-method.md)|<span data-ttu-id="c7c06-113">Возвращает параметры для этого метода.</span><span class="sxs-lookup"><span data-stu-id="c7c06-113">Gets the parameters for this method.</span></span>|  
|[<span data-ttu-id="c7c06-114">Метод GetRanges</span><span class="sxs-lookup"><span data-stu-id="c7c06-114">GetRanges Method</span></span>](isymunmanagedmethod-getranges-method.md)|<span data-ttu-id="c7c06-115">При наличии позиции в документе возвращает массив пар начального и конечного смещения, соответствующих диапазонам промежуточного языка MSIL, которые находятся в этом методе.</span><span class="sxs-lookup"><span data-stu-id="c7c06-115">Given a position in a document, returns an array of start and end offset pairs that correspond to the ranges of Microsoft intermediate language (MSIL) that the position covers within this method.</span></span>|  
|[<span data-ttu-id="c7c06-116">Метод GetRootScope</span><span class="sxs-lookup"><span data-stu-id="c7c06-116">GetRootScope Method</span></span>](isymunmanagedmethod-getrootscope-method.md)|<span data-ttu-id="c7c06-117">Возвращает корневую лексическую область внутри этого метода.</span><span class="sxs-lookup"><span data-stu-id="c7c06-117">Gets the root lexical scope within this method.</span></span> <span data-ttu-id="c7c06-118">Эта область включает весь метод.</span><span class="sxs-lookup"><span data-stu-id="c7c06-118">This scope encloses the entire method.</span></span>|  
|[<span data-ttu-id="c7c06-119">Метод GetScopeFromOffset</span><span class="sxs-lookup"><span data-stu-id="c7c06-119">GetScopeFromOffset Method</span></span>](isymunmanagedmethod-getscopefromoffset-method.md)|<span data-ttu-id="c7c06-120">Возвращает наиболее окружающую лексическую область внутри этого метода, которая заключает заданное смещение.</span><span class="sxs-lookup"><span data-stu-id="c7c06-120">Gets the most enclosing lexical scope within this method that encloses the given offset.</span></span>|  
|[<span data-ttu-id="c7c06-121">Метод GetSequencePointCount</span><span class="sxs-lookup"><span data-stu-id="c7c06-121">GetSequencePointCount Method</span></span>](isymunmanagedmethod-getsequencepointcount-method.md)|<span data-ttu-id="c7c06-122">Возвращает число точек следования в этом методе.</span><span class="sxs-lookup"><span data-stu-id="c7c06-122">Gets the count of sequence points within this method.</span></span>|  
|[<span data-ttu-id="c7c06-123">Метод GetSequencePoints</span><span class="sxs-lookup"><span data-stu-id="c7c06-123">GetSequencePoints Method</span></span>](isymunmanagedmethod-getsequencepoints-method.md)|<span data-ttu-id="c7c06-124">Возвращает все точки следования в этом методе.</span><span class="sxs-lookup"><span data-stu-id="c7c06-124">Gets all the sequence points within this method.</span></span>|  
|[<span data-ttu-id="c7c06-125">Метод GetSourceStartEnd</span><span class="sxs-lookup"><span data-stu-id="c7c06-125">GetSourceStartEnd Method</span></span>](isymunmanagedmethod-getsourcestartend-method.md)|<span data-ttu-id="c7c06-126">Возвращает начальную и конечную позиции документа для источника данного метода.</span><span class="sxs-lookup"><span data-stu-id="c7c06-126">Gets the start and end document positions for the source of this method.</span></span>|  
|[<span data-ttu-id="c7c06-127">Метод GetToken</span><span class="sxs-lookup"><span data-stu-id="c7c06-127">GetToken Method</span></span>](isymunmanagedmethod-gettoken-method.md)|<span data-ttu-id="c7c06-128">Возвращает маркер метаданных для данного метода.</span><span class="sxs-lookup"><span data-stu-id="c7c06-128">Returns the metadata token for this method.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="c7c06-129">Требования</span><span class="sxs-lookup"><span data-stu-id="c7c06-129">Requirements</span></span>  

 <span data-ttu-id="c7c06-130">**Заголовок:** Корсим. idl, Корсим. h</span><span class="sxs-lookup"><span data-stu-id="c7c06-130">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c7c06-131">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="c7c06-131">See also</span></span>

- [<span data-ttu-id="c7c06-132">Интерфейсы хранилища символов диагностики</span><span class="sxs-lookup"><span data-stu-id="c7c06-132">Diagnostics Symbol Store Interfaces</span></span>](diagnostics-symbol-store-interfaces.md)
