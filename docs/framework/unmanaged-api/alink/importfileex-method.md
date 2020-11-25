---
title: Метод ImportFileEx
ms.date: 03/30/2017
api_name:
- IALink2.ImportFileEx
api_location:
- alink.dll
api_type:
- COM
f1_keywords:
- ImportFileEx
helpviewer_keywords:
- ImportFileEx method
ms.assetid: ad276f3f-b303-46ac-97e0-66a377adaa4f
topic_type:
- apiref
ms.openlocfilehash: 9e373f133830a5bc1f3cf7bdc8034cb67725d797
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/24/2020
ms.locfileid: "95705206"
---
# <a name="importfileex-method"></a><span data-ttu-id="768e5-102">Метод ImportFileEx</span><span class="sxs-lookup"><span data-stu-id="768e5-102">ImportFileEx Method</span></span>

<span data-ttu-id="768e5-103">Импортирует указанную сборку или непривязанный модуль.</span><span class="sxs-lookup"><span data-stu-id="768e5-103">Imports indicated assembly or unbound module.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="768e5-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="768e5-104">Syntax</span></span>  
  
```cpp  
HRESULT ImportFileEx(  
    LPCWSTR pszFilename,  
    LPCWSTR pszTargetName,  
    BOOL fSmartImport,  
    DWORD dwOpenFlags,  
    mdToken* pImportToken,  
    IMetaDataAssemblyImport** ppAssemblyScope,  
    DWORD* pdwCountOfScopes  
) PURE;  
```  
  
## <a name="parameters"></a><span data-ttu-id="768e5-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="768e5-105">Parameters</span></span>  

 `pszFilename`  
 <span data-ttu-id="768e5-106">Полное имя файла, из которого необходимо выполнить импорт.</span><span class="sxs-lookup"><span data-stu-id="768e5-106">Fully qualified name of file from which to import.</span></span>  
  
 `pszTargetName`  
 <span data-ttu-id="768e5-107">Необязательное имя целевого файла.</span><span class="sxs-lookup"><span data-stu-id="768e5-107">Optional name of target file.</span></span>  
  
 `fSmartImport`  
 <span data-ttu-id="768e5-108">Если значение равно TRUE, используется ImportTypes, в противном случае импорт должен выполняться вручную.</span><span class="sxs-lookup"><span data-stu-id="768e5-108">If TRUE, ImportTypes is used, otherwise importing must be performed manually.</span></span>  
  
 `dwOpenFlags`  
 <span data-ttu-id="768e5-109">Флаги, передаваемые в [метод OpenScope](../metadata/imetadatadispenser-openscope-method.md).</span><span class="sxs-lookup"><span data-stu-id="768e5-109">Flags to be passed along to [OpenScope Method](../metadata/imetadatadispenser-openscope-method.md).</span></span>  
  
 `pImportToken`  
 <span data-ttu-id="768e5-110">Получает идентификатор импортируемого файла.</span><span class="sxs-lookup"><span data-stu-id="768e5-110">Receives ID of the file being imported.</span></span>  
  
 `ppAssemblyScope`  
 <span data-ttu-id="768e5-111">Получает интерфейс [интерфейса IMetaDataAssemblyImport](../metadata/imetadataassemblyimport-interface.md) для области импорта сборки.</span><span class="sxs-lookup"><span data-stu-id="768e5-111">Receives assembly import scope [IMetaDataAssemblyImport Interface](../metadata/imetadataassemblyimport-interface.md) interface.</span></span> <span data-ttu-id="768e5-112">Имеет значение NULL, если файл не является сборкой.</span><span class="sxs-lookup"><span data-stu-id="768e5-112">Is set to NULL if file is not an assembly.</span></span>  
  
 `pdwCountOfScopes`  
 <span data-ttu-id="768e5-113">Получает число импортированных файлов и (или) областей.</span><span class="sxs-lookup"><span data-stu-id="768e5-113">Receives count of imported files and/or scopes.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="768e5-114">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="768e5-114">Return Value</span></span>  

 <span data-ttu-id="768e5-115">Возвращает S_OK, если метод завершается с ошибкой.</span><span class="sxs-lookup"><span data-stu-id="768e5-115">Returns S_OK if the method succeeds.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="768e5-116">Требования</span><span class="sxs-lookup"><span data-stu-id="768e5-116">Requirements</span></span>  

 <span data-ttu-id="768e5-117">Требуется ALink. h.</span><span class="sxs-lookup"><span data-stu-id="768e5-117">Requires alink.h.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="768e5-118">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="768e5-118">See also</span></span>

- [<span data-ttu-id="768e5-119">Интерфейс IALink2</span><span class="sxs-lookup"><span data-stu-id="768e5-119">IALink2 Interface</span></span>](ialink2-interface.md)
- [<span data-ttu-id="768e5-120">Интерфейс IALink</span><span class="sxs-lookup"><span data-stu-id="768e5-120">IALink Interface</span></span>](ialink-interface.md)
- [<span data-ttu-id="768e5-121">API ALink</span><span class="sxs-lookup"><span data-stu-id="768e5-121">ALink API</span></span>](index.md)
