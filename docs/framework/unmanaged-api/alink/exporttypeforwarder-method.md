---
title: Метод ExportTypeForwarder
ms.date: 03/30/2017
api_name:
- IALink.ExportTypeForwarder
api_location:
- alink.dll
api_type:
- COM
f1_keywords:
- ExportTypeForwarder
helpviewer_keywords:
- ExportTypeForwarder method
ms.assetid: 55989fa9-ab43-4f08-8eb6-2eb56fa7ca76
topic_type:
- apiref
ms.openlocfilehash: 4e6ceabf37056bfc25247266be2c7801cb0e13e1
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/24/2020
ms.locfileid: "95684776"
---
# <a name="exporttypeforwarder-method"></a><span data-ttu-id="d76ef-102">Метод ExportTypeForwarder</span><span class="sxs-lookup"><span data-stu-id="d76ef-102">ExportTypeForwarder Method</span></span>

<span data-ttu-id="d76ef-103">Добавляет сервер пересылки типа в таблицу типов данной сборки.</span><span class="sxs-lookup"><span data-stu-id="d76ef-103">Adds a type forwarder to the type table of the given assembly.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d76ef-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="d76ef-104">Syntax</span></span>  
  
```cpp  
HRESULT ExportTypeForwarder(  
    mdAssemblyRef   tkAssemblyRef,  
    LPCWSTR         pszTypename,  
    DWORD           dwFlags,  
    mdExportedType* pType  
) PURE;  
```  
  
## <a name="parameters"></a><span data-ttu-id="d76ef-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="d76ef-105">Parameters</span></span>  

 `tkAssemblyRef`  
 <span data-ttu-id="d76ef-106">Ссылка на сборку, к которой относится перенаправитель типа.</span><span class="sxs-lookup"><span data-stu-id="d76ef-106">Reference to the assembly to which the type forwarder refers.</span></span>  
  
 `pszTypename`  
 <span data-ttu-id="d76ef-107">Полное имя типа для экспорта.</span><span class="sxs-lookup"><span data-stu-id="d76ef-107">Fully qualified type name to export.</span></span>  
  
 `dwFlags`  
 <span data-ttu-id="d76ef-108">`ComType` Флаги, такие как `tdPublic` или `tdNested` .</span><span class="sxs-lookup"><span data-stu-id="d76ef-108">`ComType` flags such as `tdPublic` or `tdNested`.</span></span> <span data-ttu-id="d76ef-109">Это значение может быть передано [методу дефиникспортедтипе](../metadata/imetadataassemblyemit-defineexportedtype-method.md).</span><span class="sxs-lookup"><span data-stu-id="d76ef-109">This value may be passed to [DefineExportedType Method](../metadata/imetadataassemblyemit-defineexportedtype-method.md).</span></span>  
  
 `pType`  
 <span data-ttu-id="d76ef-110">Получает токен экспортируемого типа.</span><span class="sxs-lookup"><span data-stu-id="d76ef-110">Receives the token of the exported type.</span></span> <span data-ttu-id="d76ef-111">Это необходимо только для выпуска вложенных типов.</span><span class="sxs-lookup"><span data-stu-id="d76ef-111">This is necessary only for emitting nested types.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="d76ef-112">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="d76ef-112">Return Value</span></span>  

 <span data-ttu-id="d76ef-113">Возвращает S_OK, если метод завершается с ошибкой.</span><span class="sxs-lookup"><span data-stu-id="d76ef-113">Returns S_OK if the method succeeds.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="d76ef-114">Требования</span><span class="sxs-lookup"><span data-stu-id="d76ef-114">Requirements</span></span>  

 <span data-ttu-id="d76ef-115">Требуется ALink. h</span><span class="sxs-lookup"><span data-stu-id="d76ef-115">Requires alink.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d76ef-116">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="d76ef-116">See also</span></span>

- [<span data-ttu-id="d76ef-117">Интерфейс IALink</span><span class="sxs-lookup"><span data-stu-id="d76ef-117">IALink Interface</span></span>](ialink-interface.md)
- [<span data-ttu-id="d76ef-118">Интерфейс IALink2</span><span class="sxs-lookup"><span data-stu-id="d76ef-118">IALink2 Interface</span></span>](ialink2-interface.md)
- [<span data-ttu-id="d76ef-119">API ALink</span><span class="sxs-lookup"><span data-stu-id="d76ef-119">ALink API</span></span>](index.md)
