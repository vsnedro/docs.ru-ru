---
title: Метод ISymUnmanagedScope::GetEndOffset
ms.date: 03/30/2017
api_name:
- ISymUnmanagedScope.GetEndOffset
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedScope::GetEndOffset
helpviewer_keywords:
- ISymUnmanagedScope::GetEndOffset method [.NET Framework debugging]
- GetEndOffset method, ISymUnmanagedScope interface [.NET Framework debugging]
ms.assetid: 1d0b15c9-8059-435f-9fce-346a08b9bd36
topic_type:
- apiref
ms.openlocfilehash: 14e747e81e467019d464212e75513bdf98344916
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/24/2020
ms.locfileid: "95678367"
---
# <a name="isymunmanagedscopegetendoffset-method"></a><span data-ttu-id="1e610-102">Метод ISymUnmanagedScope::GetEndOffset</span><span class="sxs-lookup"><span data-stu-id="1e610-102">ISymUnmanagedScope::GetEndOffset Method</span></span>

<span data-ttu-id="1e610-103">Возвращает конечное смещение для данной области.</span><span class="sxs-lookup"><span data-stu-id="1e610-103">Gets the end offset for this scope.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="1e610-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="1e610-104">Syntax</span></span>  
  
```cpp  
HRESULT GetEndOffset(  
    [out, retval] ULONG32* pRetVal);  
```  
  
## <a name="parameters"></a><span data-ttu-id="1e610-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="1e610-105">Parameters</span></span>  

 `pRetVal`  
 <span data-ttu-id="1e610-106">заполняет Указатель на объект `ULONG32` , который получает конечное смещение.</span><span class="sxs-lookup"><span data-stu-id="1e610-106">[out] A pointer to a `ULONG32` that receives the end offset.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="1e610-107">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="1e610-107">Return Value</span></span>  

 <span data-ttu-id="1e610-108">S_OK, если метод выполнен. в противном случае E_FAIL или другой код ошибки.</span><span class="sxs-lookup"><span data-stu-id="1e610-108">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="1e610-109">Требования</span><span class="sxs-lookup"><span data-stu-id="1e610-109">Requirements</span></span>  

 <span data-ttu-id="1e610-110">**Заголовок:** Корсим. idl, Корсим. h</span><span class="sxs-lookup"><span data-stu-id="1e610-110">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1e610-111">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="1e610-111">See also</span></span>

- [<span data-ttu-id="1e610-112">Интерфейс ISymUnmanagedScope</span><span class="sxs-lookup"><span data-stu-id="1e610-112">ISymUnmanagedScope Interface</span></span>](isymunmanagedscope-interface.md)
- [<span data-ttu-id="1e610-113">Метод GetStartOffset</span><span class="sxs-lookup"><span data-stu-id="1e610-113">GetStartOffset Method</span></span>](isymunmanagedscope-getstartoffset-method.md)
