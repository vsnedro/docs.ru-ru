---
title: Метод ExportNestedType
ms.date: 03/30/2017
api_name:
- IALink.ExportNestedType
- ExportNestedType
api_location:
- alink.dll
api_type:
- COM
f1_keywords:
- ExportNestedType
helpviewer_keywords:
- ExportNestedType method
ms.assetid: dec7df60-4d30-47c8-99db-72e0419e5f76
topic_type:
- apiref
ms.openlocfilehash: 69c99e2facfcb9077c3fc4131186ba3882c7cef6
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/24/2020
ms.locfileid: "95684841"
---
# <a name="exportnestedtype-method"></a><span data-ttu-id="a8089-102">Метод ExportNestedType</span><span class="sxs-lookup"><span data-stu-id="a8089-102">ExportNestedType Method</span></span>

<span data-ttu-id="a8089-103">Указывает вложенные типы как экспортируемые.</span><span class="sxs-lookup"><span data-stu-id="a8089-103">Specifies nested types as exportable.</span></span> <span data-ttu-id="a8089-104">[Метод ExportType](exporttype-method.md) также может экспортировать вложенные типы, но этот метод выполняется быстрее.</span><span class="sxs-lookup"><span data-stu-id="a8089-104">The [ExportType Method](exporttype-method.md) can also export nested types, but this method is faster.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a8089-105">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="a8089-105">Syntax</span></span>  
  
```cpp  
HRESULT ExportNestedType(  
    mdAssembly      AssemblyID,  
    mdToken         FileToken,  
    mdTypeDef       TypeToken,  
    mdExportedType  ParentType,  
    LPCWSTR         pszTypename,  
    DWORD           dwFlags,  
    mdExportedType* pType  
) PURE;
```  
  
## <a name="parameters"></a><span data-ttu-id="a8089-106">Параметры</span><span class="sxs-lookup"><span data-stu-id="a8089-106">Parameters</span></span>  

 `AssemblyID`  
 <span data-ttu-id="a8089-107">Идентификатор сборки, из которой производится экспорт.</span><span class="sxs-lookup"><span data-stu-id="a8089-107">ID of assembly to export from.</span></span>  
  
 `FileToken`  
 <span data-ttu-id="a8089-108">Маркер файла или сборка файла, определяющая тип, который должен быть сделан экспортируемым.</span><span class="sxs-lookup"><span data-stu-id="a8089-108">File token or Assembly of file that defines the type to be made exportable.</span></span>  
  
 `TypeToken`  
 <span data-ttu-id="a8089-109">Токен типа, который должен быть доступен для экспорта.</span><span class="sxs-lookup"><span data-stu-id="a8089-109">Type token of type to be made exportable.</span></span>  
  
 `ParentType`  
 <span data-ttu-id="a8089-110">Токен родительского типа.</span><span class="sxs-lookup"><span data-stu-id="a8089-110">Token of parent type.</span></span>  
  
 `pszTypename`  
 <span data-ttu-id="a8089-111">Полное имя типа для экспорта.</span><span class="sxs-lookup"><span data-stu-id="a8089-111">Fully qualified type name to export.</span></span>  
  
 `dwFlags`  
 <span data-ttu-id="a8089-112">`ComType` Флаги, такие как `tdPublic` или `tdNested` .</span><span class="sxs-lookup"><span data-stu-id="a8089-112">`ComType` flags such as `tdPublic` or `tdNested`.</span></span> <span data-ttu-id="a8089-113">Это значение может быть передано [методу дефиникспортедтипе](../metadata/imetadataassemblyemit-defineexportedtype-method.md).</span><span class="sxs-lookup"><span data-stu-id="a8089-113">This value may be passed to [DefineExportedType Method](../metadata/imetadataassemblyemit-defineexportedtype-method.md).</span></span>  
  
 `pType`  
 <span data-ttu-id="a8089-114">Получает токен для экспортируемого типа.</span><span class="sxs-lookup"><span data-stu-id="a8089-114">Receives token for exported type.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="a8089-115">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="a8089-115">Return Value</span></span>  

 <span data-ttu-id="a8089-116">Возвращает S_OK, если метод завершается с ошибкой.</span><span class="sxs-lookup"><span data-stu-id="a8089-116">Returns S_OK if the method succeeds.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="a8089-117">Требования</span><span class="sxs-lookup"><span data-stu-id="a8089-117">Requirements</span></span>  

 <span data-ttu-id="a8089-118">Требуется ALink. h</span><span class="sxs-lookup"><span data-stu-id="a8089-118">Requires alink.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a8089-119">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="a8089-119">See also</span></span>

- [<span data-ttu-id="a8089-120">Интерфейс IALink</span><span class="sxs-lookup"><span data-stu-id="a8089-120">IALink Interface</span></span>](ialink-interface.md)
- [<span data-ttu-id="a8089-121">Интерфейс IALink2</span><span class="sxs-lookup"><span data-stu-id="a8089-121">IALink2 Interface</span></span>](ialink2-interface.md)
- [<span data-ttu-id="a8089-122">API ALink</span><span class="sxs-lookup"><span data-stu-id="a8089-122">ALink API</span></span>](index.md)
