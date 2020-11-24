---
title: Метод ISymUnmanagedWriter3::Commit
ms.date: 03/30/2017
api_name:
- ISymUnmanagedWriter3.Commit
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedWriter3::Commit
helpviewer_keywords:
- Commit method, ISymUnmanagedWriter3 interface [.NET Framework debugging]
- ISymUnmanagedWriter3::Commit method [.NET Framework debugging]
ms.assetid: f6961922-46ec-4d2c-8369-85f880731f37
topic_type:
- apiref
ms.openlocfilehash: 394832d6144509717d2f79a78afaff50ad81c01d
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/24/2020
ms.locfileid: "95683307"
---
# <a name="isymunmanagedwriter3commit-method"></a><span data-ttu-id="f91d7-102">Метод ISymUnmanagedWriter3::Commit</span><span class="sxs-lookup"><span data-stu-id="f91d7-102">ISymUnmanagedWriter3::Commit Method</span></span>

<span data-ttu-id="f91d7-103">Фиксирует изменения, записанные на данный момент в поток.</span><span class="sxs-lookup"><span data-stu-id="f91d7-103">Commits the changes written so far to the stream.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f91d7-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="f91d7-104">Syntax</span></span>  
  
```cpp  
HRESULT Commit();  
```  
  
## <a name="return-value"></a><span data-ttu-id="f91d7-105">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="f91d7-105">Return Value</span></span>  

 <span data-ttu-id="f91d7-106">S_OK, если метод выполнен. в противном случае E_FAIL или другой код ошибки.</span><span class="sxs-lookup"><span data-stu-id="f91d7-106">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="f91d7-107">Требования</span><span class="sxs-lookup"><span data-stu-id="f91d7-107">Requirements</span></span>  

 <span data-ttu-id="f91d7-108">**Заголовок:** Корсим. idl, Корсим. h</span><span class="sxs-lookup"><span data-stu-id="f91d7-108">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f91d7-109">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="f91d7-109">See also</span></span>

- [<span data-ttu-id="f91d7-110">Интерфейс ISymUnmanagedWriter3</span><span class="sxs-lookup"><span data-stu-id="f91d7-110">ISymUnmanagedWriter3 Interface</span></span>](isymunmanagedwriter3-interface.md)
