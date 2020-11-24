---
title: Метод SetPEKind
ms.date: 03/30/2017
api_name:
- IALink2.SetPEKind
api_location:
- alink.dll
api_type:
- COM
f1_keywords:
- SetPEKind
helpviewer_keywords:
- SetPEKind method
ms.assetid: 050e77ee-3014-45c0-9e29-2ebe29347b0d
topic_type:
- apiref
ms.openlocfilehash: be8a11cbf70e2c6f19ace67648b124515c1fb3c3
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/24/2020
ms.locfileid: "95680044"
---
# <a name="setpekind-method"></a><span data-ttu-id="80920-102">Метод SetPEKind</span><span class="sxs-lookup"><span data-stu-id="80920-102">SetPEKind Method</span></span>

<span data-ttu-id="80920-103">Определяет тип переносимого исполняемого файла, который зависит от компьютера или компьютера.</span><span class="sxs-lookup"><span data-stu-id="80920-103">Determines the portable executable type, either machine-specific or machine-agnostic.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="80920-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="80920-104">Syntax</span></span>  
  
```cpp  
HRESULT SetPEKind(  
    mdAssembly AssemblyID,  
    mdToken FileToken,  
    DWORD dwPEKind,  
    DWORD dwMachine  
) PURE;
```  
  
## <a name="parameters"></a><span data-ttu-id="80920-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="80920-105">Parameters</span></span>  

 `AssemblyID`  
 <span data-ttu-id="80920-106">Идентификатор сборки.</span><span class="sxs-lookup"><span data-stu-id="80920-106">ID of the assembly.</span></span>  
  
 `FileToken`  
 <span data-ttu-id="80920-107">Токен файла, для которого задается тип PE.</span><span class="sxs-lookup"><span data-stu-id="80920-107">Token of file for which the PE type is to be set.</span></span> <span data-ttu-id="80920-108">Может иметь значение NULL `AssemblyID` , если не указывает на непривязанный netmodule.</span><span class="sxs-lookup"><span data-stu-id="80920-108">Can be NULL if `AssemblyID` does not indicate an unbound netmodule.</span></span>  
  
 `dwPEKind`  
 <span data-ttu-id="80920-109">Тип PE, как указано в [перечислении CorPEKind](../metadata/corpekind-enumeration.md).</span><span class="sxs-lookup"><span data-stu-id="80920-109">The type of PE, as indicated by the [CorPEKind Enumeration](../metadata/corpekind-enumeration.md).</span></span>  
  
 `dwMachine`  
 <span data-ttu-id="80920-110">Архитектура целевого компьютера, как указано в заголовке NT.</span><span class="sxs-lookup"><span data-stu-id="80920-110">The target machine architecture, as indicated in the NT header.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="80920-111">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="80920-111">Return Value</span></span>  

 <span data-ttu-id="80920-112">Возвращает S_OK, если метод завершается с ошибкой.</span><span class="sxs-lookup"><span data-stu-id="80920-112">Returns S_OK if the method succeeds.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="80920-113">Требования</span><span class="sxs-lookup"><span data-stu-id="80920-113">Requirements</span></span>  

 <span data-ttu-id="80920-114">Требуется ALink. h.</span><span class="sxs-lookup"><span data-stu-id="80920-114">Requires alink.h.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="80920-115">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="80920-115">See also</span></span>

- [<span data-ttu-id="80920-116">Метод GetPEKind</span><span class="sxs-lookup"><span data-stu-id="80920-116">GetPEKind Method</span></span>](../metadata/imetadataimport2-getpekind-method.md)
- [<span data-ttu-id="80920-117">Интерфейс IALink2</span><span class="sxs-lookup"><span data-stu-id="80920-117">IALink2 Interface</span></span>](ialink2-interface.md)
- [<span data-ttu-id="80920-118">Интерфейс IALink</span><span class="sxs-lookup"><span data-stu-id="80920-118">IALink Interface</span></span>](ialink-interface.md)
- [<span data-ttu-id="80920-119">API ALink</span><span class="sxs-lookup"><span data-stu-id="80920-119">ALink API</span></span>](index.md)
