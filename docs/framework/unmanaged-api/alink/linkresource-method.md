---
title: Метод LinkResource
ms.date: 03/30/2017
api_name:
- IALink.LinkResource
api_location:
- alink.dll
api_type:
- COM
f1_keywords:
- LinkResource
helpviewer_keywords:
- LinkResource method
ms.assetid: c404acb3-4c59-4100-9a4c-483cbdb1d736
topic_type:
- apiref
ms.openlocfilehash: 4f2f13976dfd4e5601bf8b54bed7b851884fbb9d
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/24/2020
ms.locfileid: "95690451"
---
# <a name="linkresource-method"></a><span data-ttu-id="86ce6-102">Метод LinkResource</span><span class="sxs-lookup"><span data-stu-id="86ce6-102">LinkResource Method</span></span>

<span data-ttu-id="86ce6-103">Ссылки в ресурсе.</span><span class="sxs-lookup"><span data-stu-id="86ce6-103">Links in a resource.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="86ce6-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="86ce6-104">Syntax</span></span>  
  
```cpp  
HRESULT LinkResource(  
    mdAssembly  AssemblyID,  
    LPCWSTR     pszFileName,  
    LPCWSTR     pszNewLocation,  
    LPCWSTR     pszResourceName,  
    DWORD       dwFlags  
) PURE;  
```  
  
## <a name="parameters"></a><span data-ttu-id="86ce6-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="86ce6-105">Parameters</span></span>  

 `AssemblyID`  
 <span data-ttu-id="86ce6-106">Идентификатор сборки.</span><span class="sxs-lookup"><span data-stu-id="86ce6-106">ID of the assembly.</span></span>  
  
 `pszFileName`  
 <span data-ttu-id="86ce6-107">Имя файла.</span><span class="sxs-lookup"><span data-stu-id="86ce6-107">Name of the file.</span></span>  
  
 `pszNewLocation`  
 <span data-ttu-id="86ce6-108">Необязательное новое имя файла.</span><span class="sxs-lookup"><span data-stu-id="86ce6-108">Optional new file name.</span></span> <span data-ttu-id="86ce6-109">Если значение не равно NULL, `pszFileName` будет скопировано в псзневлокатион.</span><span class="sxs-lookup"><span data-stu-id="86ce6-109">If non-NULL, `pszFileName` will be copied to pszNewLocation.</span></span>  
  
 `pszResourceName`  
 <span data-ttu-id="86ce6-110">Имя ресурса.</span><span class="sxs-lookup"><span data-stu-id="86ce6-110">Name of the resource.</span></span>  
  
 `dwFlags`  
 <span data-ttu-id="86ce6-111">Флаги специальных возможностей, такие как `mrPublic` и `mrPrivate` .</span><span class="sxs-lookup"><span data-stu-id="86ce6-111">Accessibility flags such as `mrPublic` and `mrPrivate`.</span></span> <span data-ttu-id="86ce6-112">Этот параметр может быть передан [методу DefineManifestResource](../metadata/imetadataassemblyemit-definemanifestresource-method.md).</span><span class="sxs-lookup"><span data-stu-id="86ce6-112">This parameter may be passed to [DefineManifestResource Method](../metadata/imetadataassemblyemit-definemanifestresource-method.md).</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="86ce6-113">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="86ce6-113">Return Value</span></span>  

 <span data-ttu-id="86ce6-114">Возвращает S_OK, если метод завершается с ошибкой.</span><span class="sxs-lookup"><span data-stu-id="86ce6-114">Returns S_OK if the method succeeds.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="86ce6-115">Требования</span><span class="sxs-lookup"><span data-stu-id="86ce6-115">Requirements</span></span>  

 <span data-ttu-id="86ce6-116">Требуется ALink. h.</span><span class="sxs-lookup"><span data-stu-id="86ce6-116">Requires alink.h.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="86ce6-117">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="86ce6-117">See also</span></span>

- [<span data-ttu-id="86ce6-118">Интерфейс IALink</span><span class="sxs-lookup"><span data-stu-id="86ce6-118">IALink Interface</span></span>](ialink-interface.md)
- [<span data-ttu-id="86ce6-119">Интерфейс IALink2</span><span class="sxs-lookup"><span data-stu-id="86ce6-119">IALink2 Interface</span></span>](ialink2-interface.md)
- [<span data-ttu-id="86ce6-120">API ALink</span><span class="sxs-lookup"><span data-stu-id="86ce6-120">ALink API</span></span>](index.md)
