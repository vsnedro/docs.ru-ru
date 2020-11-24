---
title: Метод ExportNestedTypeForwarder
ms.date: 03/30/2017
api_name:
- IALink.ExportNestedTypeForwarder
api_location:
- alink.dll
api_type:
- COM
f1_keywords:
- ExportNestedTypeForwarder
helpviewer_keywords:
- ExportNestedTypeForwarder method
ms.assetid: 886ea6c5-6b26-4b88-8bf6-448d6d191950
topic_type:
- apiref
ms.openlocfilehash: 45adda6551e1cec994f59acbb0e8d2b5c56c4df6
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/24/2020
ms.locfileid: "95684815"
---
# <a name="exportnestedtypeforwarder-method"></a><span data-ttu-id="a413e-102">Метод ExportNestedTypeForwarder</span><span class="sxs-lookup"><span data-stu-id="a413e-102">ExportNestedTypeForwarder Method</span></span>

<span data-ttu-id="a413e-103">Добавляет сервер пересылки типа для вложенного типа в таблицу типов данной сборки.</span><span class="sxs-lookup"><span data-stu-id="a413e-103">Adds a type forwarder for a nested type to the type table of the given assembly.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a413e-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="a413e-104">Syntax</span></span>  
  
```cpp  
HRESULT ExportNestedTypeForwarder(  
    mdAssembly      AssemblyID,  
    mdToken         FileToken,  
    mdTypeDef       TypeToken,  
    mdExportedType  ParentType,  
    LPCWSTR         pszTypename,  
    DWORD           dwFlags,  
    mdExportedType* pType  
) PURE;  
```  
  
## <a name="parameters"></a><span data-ttu-id="a413e-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="a413e-105">Parameters</span></span>  

 `AssemblyID`  
 <span data-ttu-id="a413e-106">Идентификатор сборки, из которой необходимо выполнить экспорт.</span><span class="sxs-lookup"><span data-stu-id="a413e-106">ID of the assembly to export from.</span></span>  
  
 `FileToken`  
 <span data-ttu-id="a413e-107">Маркер файла или идентификатор сборки файла, который определяет тип.</span><span class="sxs-lookup"><span data-stu-id="a413e-107">File token or assembly ID of file that defines the type.</span></span>  
  
 `TypeToken`  
 <span data-ttu-id="a413e-108">Токен для типа.</span><span class="sxs-lookup"><span data-stu-id="a413e-108">Token for the type.</span></span>  
  
 `ParentType`  
 <span data-ttu-id="a413e-109">Токен родительского типа.</span><span class="sxs-lookup"><span data-stu-id="a413e-109">Token of parent type.</span></span>  
  
 `pszTypename`  
 <span data-ttu-id="a413e-110">Полное имя типа для экспорта.</span><span class="sxs-lookup"><span data-stu-id="a413e-110">Fully qualified type name to export.</span></span>  
  
 `dwFlags`  
 <span data-ttu-id="a413e-111">`ComType` Флаги, такие как `tdPublic` или `tdNested` .</span><span class="sxs-lookup"><span data-stu-id="a413e-111">`ComType` flags such as `tdPublic` or `tdNested`.</span></span>  
  
 `pType`  
 <span data-ttu-id="a413e-112">Получает маркер типа экспорта.</span><span class="sxs-lookup"><span data-stu-id="a413e-112">Receives token of export type.</span></span> <span data-ttu-id="a413e-113">Это необходимо только для выпуска вложенных типов.</span><span class="sxs-lookup"><span data-stu-id="a413e-113">This is necessary only for emitting nested types.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="a413e-114">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="a413e-114">Return Value</span></span>  

 <span data-ttu-id="a413e-115">Возвращает S_OK, если метод завершается с ошибкой.</span><span class="sxs-lookup"><span data-stu-id="a413e-115">Returns S_OK if the method succeeds.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="a413e-116">Требования</span><span class="sxs-lookup"><span data-stu-id="a413e-116">Requirements</span></span>  

 <span data-ttu-id="a413e-117">Требуется ALink. h</span><span class="sxs-lookup"><span data-stu-id="a413e-117">Requires alink.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a413e-118">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="a413e-118">See also</span></span>

- [<span data-ttu-id="a413e-119">Интерфейс IALink</span><span class="sxs-lookup"><span data-stu-id="a413e-119">IALink Interface</span></span>](ialink-interface.md)
- [<span data-ttu-id="a413e-120">Интерфейс IALink2</span><span class="sxs-lookup"><span data-stu-id="a413e-120">IALink2 Interface</span></span>](ialink2-interface.md)
- [<span data-ttu-id="a413e-121">API ALink</span><span class="sxs-lookup"><span data-stu-id="a413e-121">ALink API</span></span>](index.md)
