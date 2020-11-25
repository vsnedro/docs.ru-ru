---
title: Метод ISymUnmanagedWriter::OpenNamespace
ms.date: 03/30/2017
api_name:
- ISymUnmanagedWriter.OpenNamespace
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedWriter::OpenNamespace
helpviewer_keywords:
- ISymUnmanagedWriter::OpenNamespace method [.NET Framework debugging]
- OpenNamespace method [.NET Framework debugging]
ms.assetid: 426f4e4f-e60d-4ad1-b546-a10e3c55c283
topic_type:
- apiref
ms.openlocfilehash: 2f64f9f4bde3119f9f089becec5a36d69ed43596
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/24/2020
ms.locfileid: "95730065"
---
# <a name="isymunmanagedwriteropennamespace-method"></a><span data-ttu-id="37469-102">Метод ISymUnmanagedWriter::OpenNamespace</span><span class="sxs-lookup"><span data-stu-id="37469-102">ISymUnmanagedWriter::OpenNamespace Method</span></span>

<span data-ttu-id="37469-103">Открывает новое пространство имен.</span><span class="sxs-lookup"><span data-stu-id="37469-103">Opens a new namespace.</span></span> <span data-ttu-id="37469-104">Вызовите этот метод перед определением методов или переменных, которые занимают пространство имен.</span><span class="sxs-lookup"><span data-stu-id="37469-104">Call this method before defining methods or variables that occupy a namespace.</span></span> <span data-ttu-id="37469-105">Пространства имен могут быть вложенными.</span><span class="sxs-lookup"><span data-stu-id="37469-105">Namespaces can be nested.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="37469-106">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="37469-106">Syntax</span></span>  
  
```cpp  
HRESULT OpenNamespace(  
    [in] const WCHAR *name);  
```  
  
## <a name="parameters"></a><span data-ttu-id="37469-107">Параметры</span><span class="sxs-lookup"><span data-stu-id="37469-107">Parameters</span></span>  

 `name`  
 <span data-ttu-id="37469-108">окне Указатель на имя нового пространства имен.</span><span class="sxs-lookup"><span data-stu-id="37469-108">[in] A pointer to the name of the new namespace.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="37469-109">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="37469-109">Return Value</span></span>  

 <span data-ttu-id="37469-110">S_OK, если метод выполнен. в противном случае E_FAIL или другой код ошибки.</span><span class="sxs-lookup"><span data-stu-id="37469-110">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="37469-111">Требования</span><span class="sxs-lookup"><span data-stu-id="37469-111">Requirements</span></span>  

 <span data-ttu-id="37469-112">**Заголовок:** Корсим. idl, Корсим. h</span><span class="sxs-lookup"><span data-stu-id="37469-112">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="37469-113">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="37469-113">See also</span></span>

- [<span data-ttu-id="37469-114">Интерфейс ISymUnmanagedWriter</span><span class="sxs-lookup"><span data-stu-id="37469-114">ISymUnmanagedWriter Interface</span></span>](isymunmanagedwriter-interface.md)
- [<span data-ttu-id="37469-115">Метод CloseNamespace</span><span class="sxs-lookup"><span data-stu-id="37469-115">CloseNamespace Method</span></span>](isymunmanagedwriter-closenamespace-method.md)
