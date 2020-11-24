---
title: Метод EmitInternalExportedTypes
ms.date: 03/30/2017
api_name:
- EmitInternalExportedTypes
- IALink2.EmitInternalExportedTypes
api_location:
- alink.dll
api_type:
- COM
f1_keywords:
- EmitInternalExportedTypes
helpviewer_keywords:
- EmitInternalExportedTypes method
ms.assetid: 28c8b00d-2c14-40b4-aed5-a1db0e2428eb
topic_type:
- apiref
ms.openlocfilehash: faf1438f56cd49b235ffbb18a0154e3e20c202b9
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/24/2020
ms.locfileid: "95684971"
---
# <a name="emitinternalexportedtypes-method"></a><span data-ttu-id="e00dd-102">Метод EmitInternalExportedTypes</span><span class="sxs-lookup"><span data-stu-id="e00dd-102">EmitInternalExportedTypes Method</span></span>

<span data-ttu-id="e00dd-103">Выдает типы, добавленные в сборку.</span><span class="sxs-lookup"><span data-stu-id="e00dd-103">Emits types added to the assembly.</span></span> <span data-ttu-id="e00dd-104">Вызовите этот метод после добавления известных внутренних типов.</span><span class="sxs-lookup"><span data-stu-id="e00dd-104">Call this method after known internal types have been added.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e00dd-105">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="e00dd-105">Syntax</span></span>  
  
```cpp  
HRESULT EmitInternalExportedTypes(  
    mdAssembly AssemblyID  
) PURE;  
```  
  
## <a name="parameters"></a><span data-ttu-id="e00dd-106">Параметры</span><span class="sxs-lookup"><span data-stu-id="e00dd-106">Parameters</span></span>  

 `AssemblyID`  
 <span data-ttu-id="e00dd-107">Идентификатор сборки.</span><span class="sxs-lookup"><span data-stu-id="e00dd-107">ID of assembly.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="e00dd-108">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="e00dd-108">Return Value</span></span>  

 <span data-ttu-id="e00dd-109">Возвращает S_OK, если метод завершается с ошибкой.</span><span class="sxs-lookup"><span data-stu-id="e00dd-109">Returns S_OK if the method succeeds.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="e00dd-110">Требования</span><span class="sxs-lookup"><span data-stu-id="e00dd-110">Requirements</span></span>  

 <span data-ttu-id="e00dd-111">Требуется ALink. h</span><span class="sxs-lookup"><span data-stu-id="e00dd-111">Requires alink.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e00dd-112">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="e00dd-112">See also</span></span>

- [<span data-ttu-id="e00dd-113">Интерфейс IALink2</span><span class="sxs-lookup"><span data-stu-id="e00dd-113">IALink2 Interface</span></span>](ialink2-interface.md)
- [<span data-ttu-id="e00dd-114">Интерфейс IALink</span><span class="sxs-lookup"><span data-stu-id="e00dd-114">IALink Interface</span></span>](ialink-interface.md)
- [<span data-ttu-id="e00dd-115">API ALink</span><span class="sxs-lookup"><span data-stu-id="e00dd-115">ALink API</span></span>](index.md)
