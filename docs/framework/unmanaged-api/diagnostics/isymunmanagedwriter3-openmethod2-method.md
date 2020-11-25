---
title: Метод ISymUnmanagedWriter3::OpenMethod2
ms.date: 03/30/2017
api_name:
- ISymUnmanagedWriter3.OpenMethod2
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedWriter3::OpenMethod2
helpviewer_keywords:
- ISymUnmanagedWriter3::OpenMethod2 method [.NET Framework debugging]
- OpenMethod2 method [.NET Framework debugging]
ms.assetid: 025e358c-448f-4423-a2f2-57acf437c8a5
topic_type:
- apiref
ms.openlocfilehash: 39235c5c26cb168dfc995de97f72b80dccb6b818
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/24/2020
ms.locfileid: "95720299"
---
# <a name="isymunmanagedwriter3openmethod2-method"></a><span data-ttu-id="ed7a8-102">Метод ISymUnmanagedWriter3::OpenMethod2</span><span class="sxs-lookup"><span data-stu-id="ed7a8-102">ISymUnmanagedWriter3::OpenMethod2 Method</span></span>

<span data-ttu-id="ed7a8-103">Открывает метод и предоставляет его фактическое смещение раздела в изображении.</span><span class="sxs-lookup"><span data-stu-id="ed7a8-103">Opens a method and provides its real section offset in the image.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ed7a8-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="ed7a8-104">Syntax</span></span>  
  
```cpp  
HRESULT OpenMethod2(
    [in] mdMethodDef method,  
    [in] ULONG32 isect,  
    [in] ULONG32 offset);  
```  
  
## <a name="parameters"></a><span data-ttu-id="ed7a8-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="ed7a8-105">Parameters</span></span>  

 `method`  
 <span data-ttu-id="ed7a8-106">окне Токен метаданных для открываемого метода.</span><span class="sxs-lookup"><span data-stu-id="ed7a8-106">[in] The metadata token for the method to be opened.</span></span>  
  
 `isect`  
 <span data-ttu-id="ed7a8-107">окне Смещение раздела в изображении.</span><span class="sxs-lookup"><span data-stu-id="ed7a8-107">[in] The section offset in the image.</span></span>  
  
 `offset`  
 <span data-ttu-id="ed7a8-108">окне Смещение в изображении.</span><span class="sxs-lookup"><span data-stu-id="ed7a8-108">[in] The offset in the image.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="ed7a8-109">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="ed7a8-109">Return Value</span></span>  

 <span data-ttu-id="ed7a8-110">S_OK, если метод выполнен. в противном случае E_FAIL или другой код ошибки.</span><span class="sxs-lookup"><span data-stu-id="ed7a8-110">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="ed7a8-111">Требования</span><span class="sxs-lookup"><span data-stu-id="ed7a8-111">Requirements</span></span>  

 <span data-ttu-id="ed7a8-112">**Заголовок:** Корсим. idl, Корсим. h</span><span class="sxs-lookup"><span data-stu-id="ed7a8-112">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ed7a8-113">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="ed7a8-113">See also</span></span>

- [<span data-ttu-id="ed7a8-114">Интерфейс ISymUnmanagedWriter3</span><span class="sxs-lookup"><span data-stu-id="ed7a8-114">ISymUnmanagedWriter3 Interface</span></span>](isymunmanagedwriter3-interface.md)
- [<span data-ttu-id="ed7a8-115">Метод OpenMethod</span><span class="sxs-lookup"><span data-stu-id="ed7a8-115">OpenMethod Method</span></span>](isymunmanagedwriter-openmethod-method.md)
