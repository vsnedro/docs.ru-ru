---
title: Метод CloseEnum
ms.date: 03/30/2017
api_name:
- CloseEnum
- IALink.CloseEnum
api_location:
- alink.dll
api_type:
- COM
f1_keywords:
- CloseEnum
helpviewer_keywords:
- CloseEnum method
ms.assetid: aa4a091e-13fe-4264-91de-e12f1c767c87
topic_type:
- apiref
ms.openlocfilehash: 59b1ec3f9ca382ef13680e3aad4d0c0c0e175f1c
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/24/2020
ms.locfileid: "95716971"
---
# <a name="closeenum-method"></a><span data-ttu-id="0da84-102">Метод CloseEnum</span><span class="sxs-lookup"><span data-stu-id="0da84-102">CloseEnum Method</span></span>

<span data-ttu-id="0da84-103">Закрывает указанное перечисление и освобождает связанные ресурсы.</span><span class="sxs-lookup"><span data-stu-id="0da84-103">Closes the indicated enumeration and frees associated resources.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0da84-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="0da84-104">Syntax</span></span>  
  
```cpp  
HRESULT CloseEnum(  
    HALINKENUM hEnum  
) PURE;  
```  
  
## <a name="parameters"></a><span data-ttu-id="0da84-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="0da84-105">Parameters</span></span>  

 `hEnum`  
 <span data-ttu-id="0da84-106">Обрабатываемый обработчик перечисления.</span><span class="sxs-lookup"><span data-stu-id="0da84-106">Handle of enumeration to be closed.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="0da84-107">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="0da84-107">Return Value</span></span>  

 <span data-ttu-id="0da84-108">Возвращает S_OK, если метод завершается с ошибкой.</span><span class="sxs-lookup"><span data-stu-id="0da84-108">Returns S_OK if the method succeeds.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="0da84-109">Требования</span><span class="sxs-lookup"><span data-stu-id="0da84-109">Requirements</span></span>  

 <span data-ttu-id="0da84-110">Требуется ALink. h</span><span class="sxs-lookup"><span data-stu-id="0da84-110">Requires alink.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0da84-111">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="0da84-111">See also</span></span>

- [<span data-ttu-id="0da84-112">Интерфейс IALink</span><span class="sxs-lookup"><span data-stu-id="0da84-112">IALink Interface</span></span>](ialink-interface.md)
- [<span data-ttu-id="0da84-113">Интерфейс IALink2</span><span class="sxs-lookup"><span data-stu-id="0da84-113">IALink2 Interface</span></span>](ialink2-interface.md)
- [<span data-ttu-id="0da84-114">API ALink</span><span class="sxs-lookup"><span data-stu-id="0da84-114">ALink API</span></span>](index.md)
