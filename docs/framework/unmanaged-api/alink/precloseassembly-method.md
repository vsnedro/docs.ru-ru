---
title: Метод PreCloseAssembly
ms.date: 03/30/2017
api_name:
- IALink.PreCloseAssembly
api_location:
- alink.dll
api_type:
- COM
f1_keywords:
- PreCloseAssembly
helpviewer_keywords:
- PreCloseAssembly method
ms.assetid: 6d23ac54-15ea-4027-a172-9ebef43e8f56
topic_type:
- apiref
ms.openlocfilehash: 31c0c5e23d1a985c2005693e25ca91379037482a
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/24/2020
ms.locfileid: "95728684"
---
# <a name="precloseassembly-method"></a><span data-ttu-id="4a895-102">Метод PreCloseAssembly</span><span class="sxs-lookup"><span data-stu-id="4a895-102">PreCloseAssembly Method</span></span>

<span data-ttu-id="4a895-103">Закрывает файл сборки.</span><span class="sxs-lookup"><span data-stu-id="4a895-103">Closes the assembly file.</span></span> <span data-ttu-id="4a895-104">Вызовите этот метод после закрытия всех остальных файлов, но перед закрытием файла сборки.</span><span class="sxs-lookup"><span data-stu-id="4a895-104">Call this method after closing all other files, but before closing the assembly file.</span></span> <span data-ttu-id="4a895-105">Не вызывайте этот метод для непривязанных модулей.</span><span class="sxs-lookup"><span data-stu-id="4a895-105">Do not call this method for unbound modules.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4a895-106">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="4a895-106">Syntax</span></span>  
  
```cpp  
HRESULT PreCloseAssembly(  
    mdAssembly AssemblyID  
) PURE;  
```  
  
## <a name="parameters"></a><span data-ttu-id="4a895-107">Параметры</span><span class="sxs-lookup"><span data-stu-id="4a895-107">Parameters</span></span>  

 `AssemblyID`  
 <span data-ttu-id="4a895-108">Идентификатор сборки.</span><span class="sxs-lookup"><span data-stu-id="4a895-108">ID of the assembly.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="4a895-109">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="4a895-109">Return Value</span></span>  

 <span data-ttu-id="4a895-110">Возвращает S_OK, если метод завершается с ошибкой.</span><span class="sxs-lookup"><span data-stu-id="4a895-110">Returns S_OK if the method succeeds.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="4a895-111">Требования</span><span class="sxs-lookup"><span data-stu-id="4a895-111">Requirements</span></span>  

 <span data-ttu-id="4a895-112">Требуется ALink. h.</span><span class="sxs-lookup"><span data-stu-id="4a895-112">Requires alink.h.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4a895-113">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="4a895-113">See also</span></span>

- [<span data-ttu-id="4a895-114">Интерфейс IALink</span><span class="sxs-lookup"><span data-stu-id="4a895-114">IALink Interface</span></span>](ialink-interface.md)
- [<span data-ttu-id="4a895-115">Интерфейс IALink2</span><span class="sxs-lookup"><span data-stu-id="4a895-115">IALink2 Interface</span></span>](ialink2-interface.md)
- [<span data-ttu-id="4a895-116">API ALink</span><span class="sxs-lookup"><span data-stu-id="4a895-116">ALink API</span></span>](index.md)
