---
title: Интерфейс ISymUnmanagedReader2
ms.date: 03/30/2017
api_name:
- ISymUnmanagedReader2
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedReader2
helpviewer_keywords:
- ISymUnmanagedReader2 interface [.NET Framework debugging]
ms.assetid: a01a881b-82a3-4b3e-a3a9-9dc305c2e5f7
topic_type:
- apiref
ms.openlocfilehash: d4c5ff46d37b1292059b18920abd8042c18bbf31
ms.sourcegitcommit: 27db07ffb26f76912feefba7b884313547410db5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/19/2020
ms.locfileid: "83615401"
---
# <a name="isymunmanagedreader2-interface"></a><span data-ttu-id="dee6c-102">Интерфейс ISymUnmanagedReader2</span><span class="sxs-lookup"><span data-stu-id="dee6c-102">ISymUnmanagedReader2 Interface</span></span>
<span data-ttu-id="dee6c-103">Представляет средство чтения символов, предоставляющее доступ к документам, методам и переменным в хранилище символов.</span><span class="sxs-lookup"><span data-stu-id="dee6c-103">Represents a symbol reader that provides access to documents, methods, and variables within a symbol store.</span></span> <span data-ttu-id="dee6c-104">Этот интерфейс расширяет интерфейс [ISymUnmanagedReader](isymunmanagedreader-interface.md) .</span><span class="sxs-lookup"><span data-stu-id="dee6c-104">This interface extends the [ISymUnmanagedReader](isymunmanagedreader-interface.md) interface.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="dee6c-105">Методы</span><span class="sxs-lookup"><span data-stu-id="dee6c-105">Methods</span></span>  
  
|<span data-ttu-id="dee6c-106">Метод</span><span class="sxs-lookup"><span data-stu-id="dee6c-106">Method</span></span>|<span data-ttu-id="dee6c-107">Описание</span><span class="sxs-lookup"><span data-stu-id="dee6c-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="dee6c-108">Метод GetMethodByVersionPreRemap</span><span class="sxs-lookup"><span data-stu-id="dee6c-108">GetMethodByVersionPreRemap Method</span></span>](isymunmanagedreader2-getmethodbyversionpreremap-method.md)|<span data-ttu-id="dee6c-109">Получение метода чтения символов по заданному маркеру метода и номеру версии "изменить и продолжить".</span><span class="sxs-lookup"><span data-stu-id="dee6c-109">Get a symbol reader method, given a method token and an edit-and-continue version number.</span></span>|  
|[<span data-ttu-id="dee6c-110">Метод GetMethodsInDocument</span><span class="sxs-lookup"><span data-stu-id="dee6c-110">GetMethodsInDocument Method</span></span>](isymunmanagedreader2-getmethodsindocument-method.md)|<span data-ttu-id="dee6c-111">Возвращает каждый метод, имеющий сведения о строке в указанном документе.</span><span class="sxs-lookup"><span data-stu-id="dee6c-111">Gets every method that has line information in the provided document.</span></span>|  
|[<span data-ttu-id="dee6c-112">Метод GetSymAttributePreRemap</span><span class="sxs-lookup"><span data-stu-id="dee6c-112">GetSymAttributePreRemap Method</span></span>](isymunmanagedreader2-getsymattributepreremap-method.md)|<span data-ttu-id="dee6c-113">Возвращает настраиваемый атрибут на основе его имени.</span><span class="sxs-lookup"><span data-stu-id="dee6c-113">Gets a custom attribute based upon its name.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="dee6c-114">Требования</span><span class="sxs-lookup"><span data-stu-id="dee6c-114">Requirements</span></span>  
 <span data-ttu-id="dee6c-115">**Заголовок:** Корсим. idl, Корсим. h</span><span class="sxs-lookup"><span data-stu-id="dee6c-115">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="dee6c-116">См. также статью</span><span class="sxs-lookup"><span data-stu-id="dee6c-116">See also</span></span>

- [<span data-ttu-id="dee6c-117">Интерфейсы хранилища символов диагностики</span><span class="sxs-lookup"><span data-stu-id="dee6c-117">Diagnostics Symbol Store Interfaces</span></span>](diagnostics-symbol-store-interfaces.md)
- [<span data-ttu-id="dee6c-118">Интерфейс ISymUnmanagedReader</span><span class="sxs-lookup"><span data-stu-id="dee6c-118">ISymUnmanagedReader Interface</span></span>](isymunmanagedreader-interface.md)
