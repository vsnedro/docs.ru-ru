---
title: Метод GetAssemblyRefHash
ms.date: 03/30/2017
api_name:
- IALink.GetAssemblyRefHash
api_location:
- alink.dll
api_type:
- COM
f1_keywords:
- GetAssemblyRefHash
helpviewer_keywords:
- GetAssemblyRefHash method
ms.assetid: 091a18bd-e901-46f6-b999-74d71c8a7c41
topic_type:
- apiref
ms.openlocfilehash: af040c4a6c9b85930d2d9261f8587ba69eb204e5
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/24/2020
ms.locfileid: "95721482"
---
# <a name="getassemblyrefhash-method"></a><span data-ttu-id="b90c8-102">Метод GetAssemblyRefHash</span><span class="sxs-lookup"><span data-stu-id="b90c8-102">GetAssemblyRefHash Method</span></span>

<span data-ttu-id="b90c8-103">Извлекает хэш-объект хэша для данной сборки.</span><span class="sxs-lookup"><span data-stu-id="b90c8-103">Retrieves a hash blob for a given assembly.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b90c8-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="b90c8-104">Syntax</span></span>  
  
```cpp  
HRESULT GetAssemblyRefHash(  
    mdToken FileToken,  
    const void** ppvHash,  
    DWORD* pcbHash  
) PURE;  
```  
  
## <a name="parameters"></a><span data-ttu-id="b90c8-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="b90c8-105">Parameters</span></span>  

 `FileToken`  
 <span data-ttu-id="b90c8-106">Идентификатор сборки, на которую будет ссылаться хэш.</span><span class="sxs-lookup"><span data-stu-id="b90c8-106">ID of assembly to which the hash will refer.</span></span>  
  
 `ppvHash`  
 <span data-ttu-id="b90c8-107">Получает результирующий большой двоичный объект хэша.</span><span class="sxs-lookup"><span data-stu-id="b90c8-107">Receives the resulting hash blob.</span></span>  
  
 `pcbHash`  
 <span data-ttu-id="b90c8-108">Получает размер хэш-объекта хэша (в байтах).</span><span class="sxs-lookup"><span data-stu-id="b90c8-108">Receives size, in bytes, of hash blob.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="b90c8-109">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="b90c8-109">Return Value</span></span>  

 <span data-ttu-id="b90c8-110">Возвращает S_OK, если метод завершается с ошибкой.</span><span class="sxs-lookup"><span data-stu-id="b90c8-110">Returns S_OK if the method succeeds.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="b90c8-111">Требования</span><span class="sxs-lookup"><span data-stu-id="b90c8-111">Requirements</span></span>  

 <span data-ttu-id="b90c8-112">Требуется ALink. h</span><span class="sxs-lookup"><span data-stu-id="b90c8-112">Requires alink.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b90c8-113">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="b90c8-113">See also</span></span>

- [<span data-ttu-id="b90c8-114">Интерфейс IALink</span><span class="sxs-lookup"><span data-stu-id="b90c8-114">IALink Interface</span></span>](ialink-interface.md)
- [<span data-ttu-id="b90c8-115">Интерфейс IALink2</span><span class="sxs-lookup"><span data-stu-id="b90c8-115">IALink2 Interface</span></span>](ialink2-interface.md)
- [<span data-ttu-id="b90c8-116">API ALink</span><span class="sxs-lookup"><span data-stu-id="b90c8-116">ALink API</span></span>](index.md)
