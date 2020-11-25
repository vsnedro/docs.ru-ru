---
title: Метод AddFile2
ms.date: 03/30/2017
api_name:
- AddFile2
- IALink2.AddFile2
api_location:
- alink.dll
api_type:
- COM
f1_keywords:
- AddFile2
helpviewer_keywords:
- AddFile2 method
ms.assetid: 03bc49bf-a89b-4fb6-a88d-97482e061195
topic_type:
- apiref
ms.openlocfilehash: cff6707496c7d9657796deb8bf6fa9165ff295a2
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/24/2020
ms.locfileid: "95717088"
---
# <a name="addfile2-method"></a><span data-ttu-id="23323-102">Метод AddFile2</span><span class="sxs-lookup"><span data-stu-id="23323-102">AddFile2 Method</span></span>

<span data-ttu-id="23323-103">Добавляет файлы в сборку.</span><span class="sxs-lookup"><span data-stu-id="23323-103">Adds files to the assembly.</span></span> <span data-ttu-id="23323-104">Также можно использовать для создания непривязанных модулей.</span><span class="sxs-lookup"><span data-stu-id="23323-104">Can also be used to create unbound modules.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="23323-105">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="23323-105">Syntax</span></span>  
  
```cpp  
HRESULT AddFile2(  
    mdAssembly AssemblyID,  
    LPCWSTR pszFilename,  
    DWORD dwFlags,  
    IMetaDataEmit2* pEmitter,  
    mdFile* pFileToken  
) PURE;  
```  
  
## <a name="parameters"></a><span data-ttu-id="23323-106">Параметры</span><span class="sxs-lookup"><span data-stu-id="23323-106">Parameters</span></span>  

 `AssemblyID`  
 <span data-ttu-id="23323-107">Идентификатор сборки, в которую добавляется файл.</span><span class="sxs-lookup"><span data-stu-id="23323-107">ID for the assembly to which the file is added.</span></span>  
  
 `pszFilename`  
 <span data-ttu-id="23323-108">Имя добавляемого файла.</span><span class="sxs-lookup"><span data-stu-id="23323-108">Name of the file to be added.</span></span>  
  
 `dwFlags`  
 <span data-ttu-id="23323-109">`FileDef`Флаги com+, такие как `ffContainsNoMetaData` и `ffWriteable` .</span><span class="sxs-lookup"><span data-stu-id="23323-109">COM+ `FileDef` flags such as `ffContainsNoMetaData` and `ffWriteable`.</span></span> <span data-ttu-id="23323-110">`dwFlags` передается [методу дефинефиле](../metadata/imetadataassemblyemit-definefile-method.md).</span><span class="sxs-lookup"><span data-stu-id="23323-110">`dwFlags` is passed to [DefineFile Method](../metadata/imetadataassemblyemit-definefile-method.md).</span></span>  
  
 `pEmitter`  
 <span data-ttu-id="23323-111">Интерфейс для интерфейса интерфейса [IMetaDataEmit2](../metadata/imetadataemit2-interface.md) .</span><span class="sxs-lookup"><span data-stu-id="23323-111">Interface to [IMetaDataEmit2 Interface](../metadata/imetadataemit2-interface.md) interface.</span></span>  
  
 `pFileToken`  
 <span data-ttu-id="23323-112">Получает идентификатор добавляемого файла.</span><span class="sxs-lookup"><span data-stu-id="23323-112">Receives ID for the file being added.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="23323-113">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="23323-113">Return Value</span></span>  

 <span data-ttu-id="23323-114">Возвращает S_OK, если метод завершается с ошибкой.</span><span class="sxs-lookup"><span data-stu-id="23323-114">Returns S_OK if the method succeeds.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="23323-115">Требования</span><span class="sxs-lookup"><span data-stu-id="23323-115">Requirements</span></span>  

 <span data-ttu-id="23323-116">Требуется ALink. h.</span><span class="sxs-lookup"><span data-stu-id="23323-116">Requires alink.h.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="23323-117">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="23323-117">See also</span></span>

- [<span data-ttu-id="23323-118">Интерфейс IALink2</span><span class="sxs-lookup"><span data-stu-id="23323-118">IALink2 Interface</span></span>](ialink2-interface.md)
- [<span data-ttu-id="23323-119">Интерфейс IALink</span><span class="sxs-lookup"><span data-stu-id="23323-119">IALink Interface</span></span>](ialink-interface.md)
- [<span data-ttu-id="23323-120">API ALink</span><span class="sxs-lookup"><span data-stu-id="23323-120">ALink API</span></span>](index.md)
