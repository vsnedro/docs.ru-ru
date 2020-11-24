---
title: Метод EnumCustomAttributes
ms.date: 03/30/2017
api_name:
- EnumCustomAttributes
- IALink.EnumCustomAttributes
api_location:
- alink.dll
api_type:
- COM
f1_keywords:
- EnumCustomAttributes
helpviewer_keywords:
- EnumCustomAttributes method
ms.assetid: 08dff60c-f01b-4050-8865-ea3f95361c9f
topic_type:
- apiref
ms.openlocfilehash: 445c833d10631341ef7ad579eaff8ddd96be3428
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/24/2020
ms.locfileid: "95684854"
---
# <a name="enumcustomattributes-method"></a><span data-ttu-id="cbe2b-102">Метод EnumCustomAttributes</span><span class="sxs-lookup"><span data-stu-id="cbe2b-102">EnumCustomAttributes Method</span></span>

<span data-ttu-id="cbe2b-103">Извлекает настраиваемые атрибуты уровня сборки.</span><span class="sxs-lookup"><span data-stu-id="cbe2b-103">Retrieves assembly-level custom attributes.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="cbe2b-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="cbe2b-104">Syntax</span></span>  
  
```cpp  
HRESULT EnumCustomAttributes(  
    HALINKENUM hEnum,  
    mdToken tkType,  
    mdCustomAttribute rCustomValues[],  
    ULONG cMax,  
    ULONG* pcCustomValues  
) PURE;  
```  
  
## <a name="parameters"></a><span data-ttu-id="cbe2b-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="cbe2b-105">Parameters</span></span>  

 `hEnum`  
 <span data-ttu-id="cbe2b-106">Маркер перечислителя.</span><span class="sxs-lookup"><span data-stu-id="cbe2b-106">Handle of enumerator.</span></span>  
  
 `tkType`  
 <span data-ttu-id="cbe2b-107">Тип атрибутов для перечисления.</span><span class="sxs-lookup"><span data-stu-id="cbe2b-107">Type of attributes to be enumerated.</span></span> <span data-ttu-id="cbe2b-108">Используется `mdTokenNill` для всех атрибутов.</span><span class="sxs-lookup"><span data-stu-id="cbe2b-108">Use `mdTokenNill` for all attributes.</span></span>  
  
 `rCustomValues`  
 <span data-ttu-id="cbe2b-109">Получает маркеры настраиваемых атрибутов.</span><span class="sxs-lookup"><span data-stu-id="cbe2b-109">Receives custom attributes tokens.</span></span>  
  
 `cMax`  
 <span data-ttu-id="cbe2b-110">Задает размер `rCustomValues` массива.</span><span class="sxs-lookup"><span data-stu-id="cbe2b-110">Specifies size of `rCustomValues` array.</span></span>  
  
 `pcCustomValues`  
 <span data-ttu-id="cbe2b-111">При необходимости получает число значений токена.</span><span class="sxs-lookup"><span data-stu-id="cbe2b-111">Optionally receives count of token values.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="cbe2b-112">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="cbe2b-112">Return Value</span></span>  

 <span data-ttu-id="cbe2b-113">Возвращает S_OK, если метод завершается с ошибкой.</span><span class="sxs-lookup"><span data-stu-id="cbe2b-113">Returns S_OK if the method succeeds.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="cbe2b-114">Требования</span><span class="sxs-lookup"><span data-stu-id="cbe2b-114">Requirements</span></span>  

 <span data-ttu-id="cbe2b-115">Требуется ALink. h</span><span class="sxs-lookup"><span data-stu-id="cbe2b-115">Requires alink.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="cbe2b-116">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="cbe2b-116">See also</span></span>

- [<span data-ttu-id="cbe2b-117">Интерфейс IALink</span><span class="sxs-lookup"><span data-stu-id="cbe2b-117">IALink Interface</span></span>](ialink-interface.md)
- [<span data-ttu-id="cbe2b-118">Интерфейс IALink2</span><span class="sxs-lookup"><span data-stu-id="cbe2b-118">IALink2 Interface</span></span>](ialink2-interface.md)
- [<span data-ttu-id="cbe2b-119">API ALink</span><span class="sxs-lookup"><span data-stu-id="cbe2b-119">ALink API</span></span>](index.md)
