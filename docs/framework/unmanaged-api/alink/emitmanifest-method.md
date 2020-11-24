---
title: Метод EmitManifest
ms.date: 03/30/2017
api_name:
- EmitManifest
- IALink.EmitManifest
api_location:
- alink.dll
api_type:
- COM
f1_keywords:
- EmitManifest
helpviewer_keywords:
- EmitManifest method
ms.assetid: fdebc1f3-b62e-4d9e-b775-8ccaa8ecb250
topic_type:
- apiref
ms.openlocfilehash: b1c005e58f18b03a7da5f3836f719b95c41bca95
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/24/2020
ms.locfileid: "95684945"
---
# <a name="emitmanifest-method"></a><span data-ttu-id="e6015-102">Метод EmitManifest</span><span class="sxs-lookup"><span data-stu-id="e6015-102">EmitManifest Method</span></span>

<span data-ttu-id="e6015-103">Выдает окончательный манифест.</span><span class="sxs-lookup"><span data-stu-id="e6015-103">Emits the final manifest.</span></span> <span data-ttu-id="e6015-104">Вызовите этот метод после импорта всех остальных файлов и настройки всех параметров.</span><span class="sxs-lookup"><span data-stu-id="e6015-104">Call this method after importing all other files and setting all options.</span></span> <span data-ttu-id="e6015-105">Не вызывайте этот метод для непривязанных модулей.</span><span class="sxs-lookup"><span data-stu-id="e6015-105">Do not call this method for unbound modules.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e6015-106">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="e6015-106">Syntax</span></span>  
  
```cpp  
HRESULT EmitManifest(  
    mdAssembly   AssemblyID,  
    DWORD*       pdwReserveSize,  
    mdAssembly*  ptkManifest  
) PURE;  
```  
  
## <a name="parameters"></a><span data-ttu-id="e6015-107">Параметры</span><span class="sxs-lookup"><span data-stu-id="e6015-107">Parameters</span></span>  

 `AssemblyID`  
 <span data-ttu-id="e6015-108">Идентификатор сборки.</span><span class="sxs-lookup"><span data-stu-id="e6015-108">ID of the assembly.</span></span>  
  
 `pdwReserveSize`  
 <span data-ttu-id="e6015-109">Получает размер для резервирования в файле сборки, полученный из [функции StrongNameSignatureSize](../strong-naming/strongnamesignaturesize-function.md).</span><span class="sxs-lookup"><span data-stu-id="e6015-109">Receives the size to reserve in the assembly file, retrieved from [StrongNameSignatureSize Function](../strong-naming/strongnamesignaturesize-function.md).</span></span>  
  
 `ptkManifest`  
 <span data-ttu-id="e6015-110">При необходимости получает маркер манифеста сборки.</span><span class="sxs-lookup"><span data-stu-id="e6015-110">Optionally receives the assembly manifest token.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="e6015-111">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="e6015-111">Return Value</span></span>  

 <span data-ttu-id="e6015-112">Возвращает S_OK, если метод завершается с ошибкой.</span><span class="sxs-lookup"><span data-stu-id="e6015-112">Returns S_OK if the method succeeds.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="e6015-113">Требования</span><span class="sxs-lookup"><span data-stu-id="e6015-113">Requirements</span></span>  

 <span data-ttu-id="e6015-114">Требуется ALink. h.</span><span class="sxs-lookup"><span data-stu-id="e6015-114">Requires alink.h.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e6015-115">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="e6015-115">See also</span></span>

- [<span data-ttu-id="e6015-116">Интерфейс IALink</span><span class="sxs-lookup"><span data-stu-id="e6015-116">IALink Interface</span></span>](ialink-interface.md)
- [<span data-ttu-id="e6015-117">Интерфейс IALink2</span><span class="sxs-lookup"><span data-stu-id="e6015-117">IALink2 Interface</span></span>](ialink2-interface.md)
- [<span data-ttu-id="e6015-118">API ALink</span><span class="sxs-lookup"><span data-stu-id="e6015-118">ALink API</span></span>](index.md)
