---
title: Метод GetScope
ms.date: 03/30/2017
api_name:
- IALink.GetScope
api_location:
- alink.dll
api_type:
- COM
f1_keywords:
- GetScope
helpviewer_keywords:
- GetScope method
ms.assetid: e1555328-2c71-4ece-b357-9eb6d3a8efc4
topic_type:
- apiref
ms.openlocfilehash: fd5ae6ef40cb171c33132df0f640acbef96d69b5
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/24/2020
ms.locfileid: "95684682"
---
# <a name="getscope-method"></a><span data-ttu-id="940a0-102">Метод GetScope</span><span class="sxs-lookup"><span data-stu-id="940a0-102">GetScope Method</span></span>

<span data-ttu-id="940a0-103">Возвращает область импорта.</span><span class="sxs-lookup"><span data-stu-id="940a0-103">Gets an import scope.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="940a0-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="940a0-104">Syntax</span></span>  
  
```cpp  
HRESULT GetScope(  
    mdAssembly AssemblyID,  
    mdToken FileToken,  
    DWORD dwScope,  
    IMetaDataImport** ppImportScope  
) PURE;  
```  
  
## <a name="parameters"></a><span data-ttu-id="940a0-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="940a0-105">Parameters</span></span>  

 `AssemblyID`  
 <span data-ttu-id="940a0-106">Уникальный идентификатор сборки для импорта.</span><span class="sxs-lookup"><span data-stu-id="940a0-106">Unique ID of assembly to import to.</span></span>  
  
 `FileToken`  
 <span data-ttu-id="940a0-107">Уникальный идентификатор файла для импорта.</span><span class="sxs-lookup"><span data-stu-id="940a0-107">Unique ID of the file to import from.</span></span>  
  
 `dwScope`  
 <span data-ttu-id="940a0-108">Отсчитываемая от нуля область для импорта.</span><span class="sxs-lookup"><span data-stu-id="940a0-108">Zero-based scope to import.</span></span>  
  
 `ppImportScope`  
 <span data-ttu-id="940a0-109">Получает интерфейс [интерфейса IMetaDataImport](../metadata/imetadataimport-interface.md) для области.</span><span class="sxs-lookup"><span data-stu-id="940a0-109">Receives [IMetaDataImport Interface](../metadata/imetadataimport-interface.md) interface for the scope.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="940a0-110">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="940a0-110">Return Value</span></span>  

 <span data-ttu-id="940a0-111">Возвращает S_OK, если метод завершается с ошибкой.</span><span class="sxs-lookup"><span data-stu-id="940a0-111">Returns S_OK if the method succeeds.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="940a0-112">Требования</span><span class="sxs-lookup"><span data-stu-id="940a0-112">Requirements</span></span>  

 <span data-ttu-id="940a0-113">Требуется ALink. h</span><span class="sxs-lookup"><span data-stu-id="940a0-113">Requires alink.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="940a0-114">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="940a0-114">See also</span></span>

- [<span data-ttu-id="940a0-115">Интерфейс IALink</span><span class="sxs-lookup"><span data-stu-id="940a0-115">IALink Interface</span></span>](ialink-interface.md)
- [<span data-ttu-id="940a0-116">Интерфейс IALink2</span><span class="sxs-lookup"><span data-stu-id="940a0-116">IALink2 Interface</span></span>](ialink2-interface.md)
- [<span data-ttu-id="940a0-117">API ALink</span><span class="sxs-lookup"><span data-stu-id="940a0-117">ALink API</span></span>](index.md)
