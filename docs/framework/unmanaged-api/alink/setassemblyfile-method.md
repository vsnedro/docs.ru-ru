---
title: Метод SetAssemblyFile
ms.date: 03/30/2017
api_name:
- IALink.SetAssemblyFile
api_location:
- alink.dll
api_type:
- COM
f1_keywords:
- SetAssemblyFile
helpviewer_keywords:
- SetAssemblyFile method
ms.assetid: 3a912787-f139-43ca-a841-8bbda3107ecf
topic_type:
- apiref
ms.openlocfilehash: 45eed17b91f70d4188d1d89fc91a41455f3e845b
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/24/2020
ms.locfileid: "95732649"
---
# <a name="setassemblyfile-method"></a><span data-ttu-id="3bc0f-102">Метод SetAssemblyFile</span><span class="sxs-lookup"><span data-stu-id="3bc0f-102">SetAssemblyFile Method</span></span>

<span data-ttu-id="3bc0f-103">Присваивает имя сборки, которая должна быть построена.</span><span class="sxs-lookup"><span data-stu-id="3bc0f-103">Assigns the name of the assembly to be built.</span></span> <span data-ttu-id="3bc0f-104">Не предназначен для использования при создании непривязанных модулей.</span><span class="sxs-lookup"><span data-stu-id="3bc0f-104">Not for use when producing unbound modules.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3bc0f-105">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="3bc0f-105">Syntax</span></span>  
  
```cpp  
HRESULT SetAssemblyFile(  
    LPCWSTR pszFilename,  
    IMetaDataEmit* pEmitter,  
    AssemblyFlags afFlags,  
    mdAssembly* pAssemblyID  
) PURE;  
```  
  
## <a name="parameters"></a><span data-ttu-id="3bc0f-106">Параметры</span><span class="sxs-lookup"><span data-stu-id="3bc0f-106">Parameters</span></span>  

 `pszFilename`  
 <span data-ttu-id="3bc0f-107">Полное имя файла манифеста.</span><span class="sxs-lookup"><span data-stu-id="3bc0f-107">Fully qualified name of the manifest file.</span></span>  
  
 `pEmitter`  
 <span data-ttu-id="3bc0f-108">Указатель на интерфейс [интерфейса IMetaDataEmit](../metadata/imetadataemit-interface.md) .</span><span class="sxs-lookup"><span data-stu-id="3bc0f-108">Pointer to [IMetaDataEmit Interface](../metadata/imetadataemit-interface.md) interface.</span></span>  
  
 `afFlags`  
 <span data-ttu-id="3bc0f-109">Флаги, определенные в [перечислении AssemblyFlags](../metadata/assemblyflags-enumeration.md).</span><span class="sxs-lookup"><span data-stu-id="3bc0f-109">Flags as defined in [AssemblyFlags Enumeration](../metadata/assemblyflags-enumeration.md).</span></span>  
  
 `pAssemblyID`  
 <span data-ttu-id="3bc0f-110">Указатель на идентификатор результирующей сборки.</span><span class="sxs-lookup"><span data-stu-id="3bc0f-110">Pointer to ID of resulting assembly.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="3bc0f-111">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="3bc0f-111">Return Value</span></span>  

 <span data-ttu-id="3bc0f-112">Возвращает S_OK, если метод завершается с ошибкой.</span><span class="sxs-lookup"><span data-stu-id="3bc0f-112">Returns S_OK if the method succeeds.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="3bc0f-113">Требования</span><span class="sxs-lookup"><span data-stu-id="3bc0f-113">Requirements</span></span>  

 <span data-ttu-id="3bc0f-114">Требуется ALink. h.</span><span class="sxs-lookup"><span data-stu-id="3bc0f-114">Requires alink.h.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3bc0f-115">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="3bc0f-115">See also</span></span>

- [<span data-ttu-id="3bc0f-116">Интерфейс IALink</span><span class="sxs-lookup"><span data-stu-id="3bc0f-116">IALink Interface</span></span>](ialink-interface.md)
- [<span data-ttu-id="3bc0f-117">Интерфейс IALink2</span><span class="sxs-lookup"><span data-stu-id="3bc0f-117">IALink2 Interface</span></span>](ialink2-interface.md)
- [<span data-ttu-id="3bc0f-118">API ALink</span><span class="sxs-lookup"><span data-stu-id="3bc0f-118">ALink API</span></span>](index.md)
