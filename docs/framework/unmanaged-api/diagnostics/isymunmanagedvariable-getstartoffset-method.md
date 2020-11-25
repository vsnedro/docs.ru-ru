---
title: Метод ISymUnmanagedVariable::GetStartOffset
ms.date: 03/30/2017
api_name:
- ISymUnmanagedVariable.GetStartOffset
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedVariable::GetStartOffset
helpviewer_keywords:
- GetStartOffset method, ISymUnmanagedVariable interface [.NET Framework debugging]
- ISymUnmanagedVariable::GetStartOffset method [.NET Framework debugging]
ms.assetid: 63021fc1-9c2d-4788-811f-fe8ca077206a
topic_type:
- apiref
ms.openlocfilehash: 68d20c33c5ccd554554cae57ee55f6f51d5d980c
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/24/2020
ms.locfileid: "95733312"
---
# <a name="isymunmanagedvariablegetstartoffset-method"></a><span data-ttu-id="df23b-102">Метод ISymUnmanagedVariable::GetStartOffset</span><span class="sxs-lookup"><span data-stu-id="df23b-102">ISymUnmanagedVariable::GetStartOffset Method</span></span>

<span data-ttu-id="df23b-103">Возвращает начальное смещение этой переменной в родительском элементе.</span><span class="sxs-lookup"><span data-stu-id="df23b-103">Gets the start offset of this variable within its parent.</span></span> <span data-ttu-id="df23b-104">Если это локальная переменная в области, начальное смещение будет находиться в пределах смещений, определенных для области.</span><span class="sxs-lookup"><span data-stu-id="df23b-104">If this is a local variable within a scope, the start offset will fall within the offsets defined for the scope.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="df23b-105">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="df23b-105">Syntax</span></span>  
  
```cpp  
HRESULT GetStartOffset(  
    [out, retval] ULONG32* pRetVal);  
```  
  
## <a name="parameters"></a><span data-ttu-id="df23b-106">Параметры</span><span class="sxs-lookup"><span data-stu-id="df23b-106">Parameters</span></span>  

 `pRetVal`  
 <span data-ttu-id="df23b-107">заполняет Указатель на объект `ULONG32` , который получает начальное смещение.</span><span class="sxs-lookup"><span data-stu-id="df23b-107">[out] A pointer to a `ULONG32` that receives the start offset.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="df23b-108">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="df23b-108">Return Value</span></span>  

 <span data-ttu-id="df23b-109">S_OK, если метод выполнен. в противном случае E_FAIL или другой код ошибки.</span><span class="sxs-lookup"><span data-stu-id="df23b-109">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="df23b-110">Требования</span><span class="sxs-lookup"><span data-stu-id="df23b-110">Requirements</span></span>  

 <span data-ttu-id="df23b-111">**Заголовок:** Корсим. idl, Корсим. h</span><span class="sxs-lookup"><span data-stu-id="df23b-111">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="df23b-112">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="df23b-112">See also</span></span>

- [<span data-ttu-id="df23b-113">Интерфейс ISymUnmanagedVariable</span><span class="sxs-lookup"><span data-stu-id="df23b-113">ISymUnmanagedVariable Interface</span></span>](isymunmanagedvariable-interface.md)
- [<span data-ttu-id="df23b-114">Метод GetEndOffset</span><span class="sxs-lookup"><span data-stu-id="df23b-114">GetEndOffset Method</span></span>](isymunmanagedvariable-getendoffset-method.md)
