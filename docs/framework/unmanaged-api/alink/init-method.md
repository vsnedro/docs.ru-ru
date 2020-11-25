---
title: Метод Init
ms.date: 03/30/2017
api_name:
- IALink.Init
api_location:
- alink.dll
api_type:
- COM
f1_keywords:
- Init
helpviewer_keywords:
- Init method
ms.assetid: e48b5c64-049f-4f93-ad87-d07ae9cd5845
topic_type:
- apiref
ms.openlocfilehash: 25a1c29ab94a785304b83d5b1bcb2d7176742a68
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/24/2020
ms.locfileid: "95726022"
---
# <a name="init-method"></a><span data-ttu-id="8cfb6-102">Метод Init</span><span class="sxs-lookup"><span data-stu-id="8cfb6-102">Init Method</span></span>

<span data-ttu-id="8cfb6-103">Подготавливает объекты, реализующие [интерфейс иалинк](ialink-interface.md) для использования.</span><span class="sxs-lookup"><span data-stu-id="8cfb6-103">Prepares objects implementing the [IALink Interface](ialink-interface.md) for use.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8cfb6-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="8cfb6-104">Syntax</span></span>  
  
```cpp  
HRESULT Init(  
    IMetaDataDispenserEx* pDispenser,  
    IMetaDataError* pErrorHandler  
) PURE;  
```  
  
## <a name="parameters"></a><span data-ttu-id="8cfb6-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="8cfb6-105">Parameters</span></span>  

 `pDispenser`  
 <span data-ttu-id="8cfb6-106">Указатель [интерфейса IMetaDataDispenserEx](../metadata/imetadatadispenserex-interface.md) на распределитель метаданных.</span><span class="sxs-lookup"><span data-stu-id="8cfb6-106">[IMetaDataDispenserEx Interface](../metadata/imetadatadispenserex-interface.md) pointer to the metadata dispenser.</span></span>  
  
 `pErrorHandler`  
 <span data-ttu-id="8cfb6-107">Указатель [интерфейса IMetaDataError](../metadata/imetadataerror-interface.md) на необязательный интерфейс обработки ошибок.</span><span class="sxs-lookup"><span data-stu-id="8cfb6-107">[IMetaDataError Interface](../metadata/imetadataerror-interface.md) pointer to an optional error handling interface.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="8cfb6-108">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="8cfb6-108">Return Value</span></span>  

 <span data-ttu-id="8cfb6-109">Возвращает S_OK, если метод завершается с ошибкой.</span><span class="sxs-lookup"><span data-stu-id="8cfb6-109">Returns S_OK if the method succeeds.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="8cfb6-110">Требования</span><span class="sxs-lookup"><span data-stu-id="8cfb6-110">Requirements</span></span>  

 <span data-ttu-id="8cfb6-111">Требуется ALink. h</span><span class="sxs-lookup"><span data-stu-id="8cfb6-111">Requires alink.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8cfb6-112">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="8cfb6-112">See also</span></span>

- [<span data-ttu-id="8cfb6-113">Интерфейс IALink</span><span class="sxs-lookup"><span data-stu-id="8cfb6-113">IALink Interface</span></span>](ialink-interface.md)
- [<span data-ttu-id="8cfb6-114">Интерфейс IALink2</span><span class="sxs-lookup"><span data-stu-id="8cfb6-114">IALink2 Interface</span></span>](ialink2-interface.md)
- [<span data-ttu-id="8cfb6-115">API ALink</span><span class="sxs-lookup"><span data-stu-id="8cfb6-115">ALink API</span></span>](index.md)
