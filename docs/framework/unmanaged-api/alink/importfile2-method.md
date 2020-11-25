---
title: Метод ImportFile2
ms.date: 03/30/2017
api_name:
- IALink.ImportFile2
api_location:
- alink.dll
api_type:
- COM
f1_keywords:
- ImportFile2
helpviewer_keywords:
- ImportFile2 method
ms.assetid: 9a6be861-c260-4a35-acea-3372ea515a0f
topic_type:
- apiref
ms.openlocfilehash: d02bc53676dd5afb0222a1ea366a8f2bd1f94f62
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/24/2020
ms.locfileid: "95705232"
---
# <a name="importfile2-method"></a><span data-ttu-id="87db8-102">Метод ImportFile2</span><span class="sxs-lookup"><span data-stu-id="87db8-102">ImportFile2 Method</span></span>

<span data-ttu-id="87db8-103">Импортирует сборки и непривязанные модули.</span><span class="sxs-lookup"><span data-stu-id="87db8-103">Imports assemblies and unbound modules.</span></span> <span data-ttu-id="87db8-104">Этот метод похож на [Метод ImportFile](importfile-method.md), но работает даже в том случае, если импортируемый файл не существует на диске.</span><span class="sxs-lookup"><span data-stu-id="87db8-104">This method is like [ImportFile Method](importfile-method.md), but works even if the file being imported does not exist on disk.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="87db8-105">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="87db8-105">Syntax</span></span>  
  
```cpp  
HRESULT ImportFile2(  
    LPCWSTR         pszFilename,  
    LPCWSTR         pszTargetName,  
    IMetaDataAssemblyImport* pAssemblyScopeIn,  
    BOOL            fSmartImport,  
    mdToken*        pImportToken,  
    IMetaDataAssemblyImport** ppAssemblyScope,  
    DWORD*          pdwCountOfScopes  
) PURE;  
```  
  
## <a name="parameters"></a><span data-ttu-id="87db8-106">Параметры</span><span class="sxs-lookup"><span data-stu-id="87db8-106">Parameters</span></span>  

 `pszFilename`  
 <span data-ttu-id="87db8-107">Имя импортируемого файла.</span><span class="sxs-lookup"><span data-stu-id="87db8-107">Name of file to be imported.</span></span>  
  
 `pszTargetName`  
 <span data-ttu-id="87db8-108">Необязательное имя выходного файла, которое можно использовать для переименования файла, так как он связан с сборкой.</span><span class="sxs-lookup"><span data-stu-id="87db8-108">Optional output file name that can be used to rename the file as it is linked into the assembly.</span></span>  
  
 `pAssemblyScopeIn`  
 <span data-ttu-id="87db8-109">Необязательный интерфейс интерфейса [IMetaDataAssemblyImport](../metadata/imetadataassemblyimport-interface.md) с областью действия.</span><span class="sxs-lookup"><span data-stu-id="87db8-109">Optional scope [IMetaDataAssemblyImport Interface](../metadata/imetadataassemblyimport-interface.md) interface.</span></span>  
  
 `fSmartImport`  
 <span data-ttu-id="87db8-110">Если значение равно TRUE, используется ImportTypes, в противном случае импорт должен выполняться вручную.</span><span class="sxs-lookup"><span data-stu-id="87db8-110">If TRUE, ImportTypes is used, otherwise importing must be performed manually.</span></span>  
  
 `pImportToken`  
 <span data-ttu-id="87db8-111">Получает идентификатор для файла или сборки.</span><span class="sxs-lookup"><span data-stu-id="87db8-111">Receives the ID for the file or assembly.</span></span>  
  
 `ppAssemblyScope`  
 <span data-ttu-id="87db8-112">Получает интерфейс [интерфейса IMetaDataAssemblyImport](../metadata/imetadataassemblyimport-interface.md) .</span><span class="sxs-lookup"><span data-stu-id="87db8-112">Receives the [IMetaDataAssemblyImport Interface](../metadata/imetadataassemblyimport-interface.md) interface.</span></span> <span data-ttu-id="87db8-113">Значение NULL, если файл не является сборкой.</span><span class="sxs-lookup"><span data-stu-id="87db8-113">NULL if the file is not an assembly.</span></span>  
  
 `pdwCountOfScopes`  
 <span data-ttu-id="87db8-114">Получает найденные файлы и/или импортированные области.</span><span class="sxs-lookup"><span data-stu-id="87db8-114">Receives the found of files and/or scopes imported.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="87db8-115">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="87db8-115">Return Value</span></span>  

 <span data-ttu-id="87db8-116">Возвращает S_OK, если метод завершается с ошибкой.</span><span class="sxs-lookup"><span data-stu-id="87db8-116">Returns S_OK if the method succeeds.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="87db8-117">Требования</span><span class="sxs-lookup"><span data-stu-id="87db8-117">Requirements</span></span>  

 <span data-ttu-id="87db8-118">Требуется ALink. h.</span><span class="sxs-lookup"><span data-stu-id="87db8-118">Requires alink.h.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="87db8-119">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="87db8-119">See also</span></span>

- [<span data-ttu-id="87db8-120">Интерфейс IALink</span><span class="sxs-lookup"><span data-stu-id="87db8-120">IALink Interface</span></span>](ialink-interface.md)
- [<span data-ttu-id="87db8-121">Интерфейс IALink2</span><span class="sxs-lookup"><span data-stu-id="87db8-121">IALink2 Interface</span></span>](ialink2-interface.md)
- [<span data-ttu-id="87db8-122">API ALink</span><span class="sxs-lookup"><span data-stu-id="87db8-122">ALink API</span></span>](index.md)
