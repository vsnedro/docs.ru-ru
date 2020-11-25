---
title: Метод ImportFile
ms.date: 03/30/2017
api_name:
- IALink.ImportFile
api_location:
- alink.dll
api_type:
- COM
f1_keywords:
- ImportFile
helpviewer_keywords:
- ImportFile method
ms.assetid: bcbe321f-b83a-4e9a-9f10-8d913e244dc9
topic_type:
- apiref
ms.openlocfilehash: f30307884a268008fd4d1a8de31ec5a49b6ab92d
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/24/2020
ms.locfileid: "95705245"
---
# <a name="importfile-method"></a><span data-ttu-id="74e45-102">Метод ImportFile</span><span class="sxs-lookup"><span data-stu-id="74e45-102">ImportFile Method</span></span>

<span data-ttu-id="74e45-103">Импортирует сборки и непривязанные модули.</span><span class="sxs-lookup"><span data-stu-id="74e45-103">Imports assemblies and unbound modules.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="74e45-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="74e45-104">Syntax</span></span>  
  
```cpp  
HRESULT ImportFile(  
    LPCWSTR pszFilename,  
    LPCWSTR pszTargetName,  
    BOOL fSmartImport,  
    mdToken* pImportToken,  
    IMetaDataAssemblyImport** ppAssemblyScope,  
    DWORD* pdwCountOfScopes  
) PURE;  
```  
  
## <a name="parameters"></a><span data-ttu-id="74e45-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="74e45-105">Parameters</span></span>  

 `pszFilename`  
 <span data-ttu-id="74e45-106">Полное имя импортируемого файла.</span><span class="sxs-lookup"><span data-stu-id="74e45-106">Fully qualified name of file to be imported.</span></span>  
  
 `pszTargetName`  
 <span data-ttu-id="74e45-107">Необязательное имя выходного файла, которое можно использовать для переименования файла, так как он связан с сборкой.</span><span class="sxs-lookup"><span data-stu-id="74e45-107">Optional output file name that can be used to rename the file as it is linked into the assembly.</span></span>  
  
 `fSmartImport`  
 <span data-ttu-id="74e45-108">Если значение равно TRUE, используется ImportTypes, в противном случае импорт должен выполняться вручную.</span><span class="sxs-lookup"><span data-stu-id="74e45-108">If TRUE, ImportTypes is used, otherwise importing must be performed manually.</span></span>  
  
 `pImportToken`  
 <span data-ttu-id="74e45-109">Указатель на маркер, где будет храниться уникальный идентификатор файла.</span><span class="sxs-lookup"><span data-stu-id="74e45-109">Pointer to token where a unique file ID will be stored.</span></span> <span data-ttu-id="74e45-110">Файл может быть сборкой или файлом.</span><span class="sxs-lookup"><span data-stu-id="74e45-110">The file can be an assembly or a file.</span></span>  
  
 `ppAssemblyScope`  
 <span data-ttu-id="74e45-111">Получает указатель на [интерфейс IMetaDataAssemblyImport](../metadata/imetadataassemblyimport-interface.md).</span><span class="sxs-lookup"><span data-stu-id="74e45-111">Receives pointer to [IMetaDataAssemblyImport Interface](../metadata/imetadataassemblyimport-interface.md).</span></span> <span data-ttu-id="74e45-112">Может иметь значение NULL, если файл не является сборкой.</span><span class="sxs-lookup"><span data-stu-id="74e45-112">Can be NULL if the file is not an assembly.</span></span>  
  
 `pdwCountOfScopes`  
 <span data-ttu-id="74e45-113">Указатель на число импортированных файлов и (или) областей.</span><span class="sxs-lookup"><span data-stu-id="74e45-113">Pointer to the count of files and/or scopes that have been imported.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="74e45-114">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="74e45-114">Return Value</span></span>  

 <span data-ttu-id="74e45-115">Возвращает S_OK, если метод завершается с ошибкой.</span><span class="sxs-lookup"><span data-stu-id="74e45-115">Returns S_OK if the method succeeds.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="74e45-116">Требования</span><span class="sxs-lookup"><span data-stu-id="74e45-116">Requirements</span></span>  

 <span data-ttu-id="74e45-117">Требуется ALink. h</span><span class="sxs-lookup"><span data-stu-id="74e45-117">Requires alink.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="74e45-118">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="74e45-118">See also</span></span>

- [<span data-ttu-id="74e45-119">Интерфейс IALink</span><span class="sxs-lookup"><span data-stu-id="74e45-119">IALink Interface</span></span>](ialink-interface.md)
- [<span data-ttu-id="74e45-120">Интерфейс IALink2</span><span class="sxs-lookup"><span data-stu-id="74e45-120">IALink2 Interface</span></span>](ialink2-interface.md)
- [<span data-ttu-id="74e45-121">API ALink</span><span class="sxs-lookup"><span data-stu-id="74e45-121">ALink API</span></span>](index.md)
