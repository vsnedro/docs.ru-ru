---
title: Метод EmitAssembly
ms.date: 03/30/2017
api_name:
- IALink2.EmitAssembly
- EmitAssembly
api_location:
- alink.dll
api_type:
- COM
f1_keywords:
- EmitAssembly
helpviewer_keywords:
- EmitAssembly method
ms.assetid: 605ff39e-e5cc-4bff-8196-e8d68a9715b9
topic_type:
- apiref
ms.openlocfilehash: b85b2576660f77eb901c504d398e8bc7909882f7
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/24/2020
ms.locfileid: "95676378"
---
# <a name="emitassembly-method"></a><span data-ttu-id="a419b-102">Метод EmitAssembly</span><span class="sxs-lookup"><span data-stu-id="a419b-102">EmitAssembly Method</span></span>

<span data-ttu-id="a419b-103">Создает сборку.</span><span class="sxs-lookup"><span data-stu-id="a419b-103">Creates the assembly.</span></span> <span data-ttu-id="a419b-104">Вызывайте этот метод после закрытия всех остальных файлов, кроме файла сборки.</span><span class="sxs-lookup"><span data-stu-id="a419b-104">Call this method after all other files are closed except for the assembly file.</span></span> <span data-ttu-id="a419b-105">Не вызывайте этот метод при создании непривязанных модулей.</span><span class="sxs-lookup"><span data-stu-id="a419b-105">Do not call this method when producing unbound modules.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a419b-106">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="a419b-106">Syntax</span></span>  
  
```cpp  
HRESULT EmitAssembly(  
    mdAssembly AssemblyID  
) PURE;  
```  
  
## <a name="parameters"></a><span data-ttu-id="a419b-107">Параметры</span><span class="sxs-lookup"><span data-stu-id="a419b-107">Parameters</span></span>  

 `AssemblyID`  
 <span data-ttu-id="a419b-108">Идентификатор сборки.</span><span class="sxs-lookup"><span data-stu-id="a419b-108">ID of the assembly.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="a419b-109">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="a419b-109">Return Value</span></span>  

 <span data-ttu-id="a419b-110">Возвращает S_OK, если метод завершается с ошибкой.</span><span class="sxs-lookup"><span data-stu-id="a419b-110">Returns S_OK if the method succeeds.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="a419b-111">Требования</span><span class="sxs-lookup"><span data-stu-id="a419b-111">Requirements</span></span>  

 <span data-ttu-id="a419b-112">Требуется ALink. h</span><span class="sxs-lookup"><span data-stu-id="a419b-112">Requires alink.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a419b-113">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="a419b-113">See also</span></span>

- [<span data-ttu-id="a419b-114">Интерфейс IALink</span><span class="sxs-lookup"><span data-stu-id="a419b-114">IALink Interface</span></span>](ialink-interface.md)
- [<span data-ttu-id="a419b-115">Интерфейс IALink2</span><span class="sxs-lookup"><span data-stu-id="a419b-115">IALink2 Interface</span></span>](ialink2-interface.md)
- [<span data-ttu-id="a419b-116">API ALink</span><span class="sxs-lookup"><span data-stu-id="a419b-116">ALink API</span></span>](index.md)
