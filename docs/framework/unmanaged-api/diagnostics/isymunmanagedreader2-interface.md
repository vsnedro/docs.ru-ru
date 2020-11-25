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
ms.openlocfilehash: 3f34be833d3ccb5c636d2c5f18ccb6e216ef2c49
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/24/2020
ms.locfileid: "95709080"
---
# <a name="isymunmanagedreader2-interface"></a><span data-ttu-id="45ae4-102">Интерфейс ISymUnmanagedReader2</span><span class="sxs-lookup"><span data-stu-id="45ae4-102">ISymUnmanagedReader2 Interface</span></span>

<span data-ttu-id="45ae4-103">Представляет средство чтения символов, которое предоставляет доступ к документам, методам и переменным в хранилище символов.</span><span class="sxs-lookup"><span data-stu-id="45ae4-103">Represents a symbol reader that provides access to documents, methods, and variables within a symbol store.</span></span> <span data-ttu-id="45ae4-104">Этот интерфейс расширяет интерфейс [ISymUnmanagedReader](isymunmanagedreader-interface.md) .</span><span class="sxs-lookup"><span data-stu-id="45ae4-104">This interface extends the [ISymUnmanagedReader](isymunmanagedreader-interface.md) interface.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="45ae4-105">Методы</span><span class="sxs-lookup"><span data-stu-id="45ae4-105">Methods</span></span>  
  
|<span data-ttu-id="45ae4-106">Метод</span><span class="sxs-lookup"><span data-stu-id="45ae4-106">Method</span></span>|<span data-ttu-id="45ae4-107">Описание</span><span class="sxs-lookup"><span data-stu-id="45ae4-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="45ae4-108">Метод GetMethodByVersionPreRemap</span><span class="sxs-lookup"><span data-stu-id="45ae4-108">GetMethodByVersionPreRemap Method</span></span>](isymunmanagedreader2-getmethodbyversionpreremap-method.md)|<span data-ttu-id="45ae4-109">Получение метода чтения символов по заданному маркеру метода и номеру версии "изменить и продолжить".</span><span class="sxs-lookup"><span data-stu-id="45ae4-109">Get a symbol reader method, given a method token and an edit-and-continue version number.</span></span>|  
|[<span data-ttu-id="45ae4-110">Метод GetMethodsInDocument</span><span class="sxs-lookup"><span data-stu-id="45ae4-110">GetMethodsInDocument Method</span></span>](isymunmanagedreader2-getmethodsindocument-method.md)|<span data-ttu-id="45ae4-111">Возвращает каждый метод, имеющий сведения о строке в указанном документе.</span><span class="sxs-lookup"><span data-stu-id="45ae4-111">Gets every method that has line information in the provided document.</span></span>|  
|[<span data-ttu-id="45ae4-112">Метод GetSymAttributePreRemap</span><span class="sxs-lookup"><span data-stu-id="45ae4-112">GetSymAttributePreRemap Method</span></span>](isymunmanagedreader2-getsymattributepreremap-method.md)|<span data-ttu-id="45ae4-113">Возвращает настраиваемый атрибут на основе его имени.</span><span class="sxs-lookup"><span data-stu-id="45ae4-113">Gets a custom attribute based upon its name.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="45ae4-114">Требования</span><span class="sxs-lookup"><span data-stu-id="45ae4-114">Requirements</span></span>  

 <span data-ttu-id="45ae4-115">**Заголовок:** Корсим. idl, Корсим. h</span><span class="sxs-lookup"><span data-stu-id="45ae4-115">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="45ae4-116">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="45ae4-116">See also</span></span>

- [<span data-ttu-id="45ae4-117">Интерфейсы хранилища символов диагностики</span><span class="sxs-lookup"><span data-stu-id="45ae4-117">Diagnostics Symbol Store Interfaces</span></span>](diagnostics-symbol-store-interfaces.md)
- [<span data-ttu-id="45ae4-118">Интерфейс ISymUnmanagedReader</span><span class="sxs-lookup"><span data-stu-id="45ae4-118">ISymUnmanagedReader Interface</span></span>](isymunmanagedreader-interface.md)
