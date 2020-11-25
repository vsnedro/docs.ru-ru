---
title: Метод ISymUnmanagedScope::GetStartOffset
ms.date: 03/30/2017
api_name:
- ISymUnmanagedScope.GetStartOffset
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedScope::GetStartOffset
helpviewer_keywords:
- GetStartOffset method, ISymUnmanagedScope interface [.NET Framework debugging]
- ISymUnmanagedScope::GetStartOffset method [.NET Framework debugging]
ms.assetid: da6bbc75-94d1-4354-9722-0d455b4428fb
topic_type:
- apiref
ms.openlocfilehash: 69b72ce66a203f403fcfe0fd4b4e728ece7397e4
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/24/2020
ms.locfileid: "95725876"
---
# <a name="isymunmanagedscopegetstartoffset-method"></a><span data-ttu-id="7278f-102">Метод ISymUnmanagedScope::GetStartOffset</span><span class="sxs-lookup"><span data-stu-id="7278f-102">ISymUnmanagedScope::GetStartOffset Method</span></span>

<span data-ttu-id="7278f-103">Возвращает начальное смещение для этой области.</span><span class="sxs-lookup"><span data-stu-id="7278f-103">Gets the start offset for this scope.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7278f-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="7278f-104">Syntax</span></span>  
  
```cpp  
HRESULT GetStartOffset(  
    [out, retval] ULONG32* pRetVal);  
```  
  
## <a name="parameters"></a><span data-ttu-id="7278f-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="7278f-105">Parameters</span></span>  

 `pRetVal`  
 <span data-ttu-id="7278f-106">заполняет Указатель на объект `ULONG32` , содержащий начальное смещение.</span><span class="sxs-lookup"><span data-stu-id="7278f-106">[out] A pointer to a `ULONG32` that contains the starting offset.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="7278f-107">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="7278f-107">Return Value</span></span>  

 <span data-ttu-id="7278f-108">S_OK, если метод выполнен. в противном случае E_FAIL или другой код ошибки.</span><span class="sxs-lookup"><span data-stu-id="7278f-108">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="7278f-109">Требования</span><span class="sxs-lookup"><span data-stu-id="7278f-109">Requirements</span></span>  

 <span data-ttu-id="7278f-110">**Заголовок:** Корсим. idl, Корсим. h</span><span class="sxs-lookup"><span data-stu-id="7278f-110">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7278f-111">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="7278f-111">See also</span></span>

- [<span data-ttu-id="7278f-112">Интерфейс ISymUnmanagedScope</span><span class="sxs-lookup"><span data-stu-id="7278f-112">ISymUnmanagedScope Interface</span></span>](isymunmanagedscope-interface.md)
- [<span data-ttu-id="7278f-113">Метод GetEndOffset</span><span class="sxs-lookup"><span data-stu-id="7278f-113">GetEndOffset Method</span></span>](isymunmanagedscope-getendoffset-method.md)
