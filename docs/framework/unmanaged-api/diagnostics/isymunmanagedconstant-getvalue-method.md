---
title: Метод ISymUnmanagedConstant::GetValue
ms.date: 03/30/2017
api_name:
- ISymUnmanagedConstant.GetValue
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedConstant::GetValue
helpviewer_keywords:
- GetValue method, ISymUnmanagedConstant interface [.NET Framework debugging]
- ISymUnmanagedConstant::GetValue method [.NET Framework debugging]
ms.assetid: 0036fc10-e768-47a8-b9cf-bf47faf8d194
topic_type:
- apiref
ms.openlocfilehash: 7a1c795f4a162699078e91bcaa274253169234e7
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/24/2020
ms.locfileid: "95732844"
---
# <a name="isymunmanagedconstantgetvalue-method"></a><span data-ttu-id="3261b-102">Метод ISymUnmanagedConstant::GetValue</span><span class="sxs-lookup"><span data-stu-id="3261b-102">ISymUnmanagedConstant::GetValue Method</span></span>

<span data-ttu-id="3261b-103"> Возвращает значение константы.</span><span class="sxs-lookup"><span data-stu-id="3261b-103">Gets the value of the constant.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3261b-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="3261b-104">Syntax</span></span>  
  
```cpp  
HRESULT GetValue(  
    [out]  VARIANT* pValue  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="3261b-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="3261b-105">Parameters</span></span>  

 `pValue`  
 <span data-ttu-id="3261b-106">заполняет Указатель на переменную, которая получает значение.</span><span class="sxs-lookup"><span data-stu-id="3261b-106">[out] A pointer to a variable that receives the value.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="3261b-107">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="3261b-107">Return Value</span></span>  

 <span data-ttu-id="3261b-108">S_OK, если метод выполнен. в противном случае E_FAIL или другой код ошибки.</span><span class="sxs-lookup"><span data-stu-id="3261b-108">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="3261b-109">Требования</span><span class="sxs-lookup"><span data-stu-id="3261b-109">Requirements</span></span>  

 <span data-ttu-id="3261b-110">**Заголовок:** Корсим. idl, Корсим. h</span><span class="sxs-lookup"><span data-stu-id="3261b-110">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3261b-111">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="3261b-111">See also</span></span>

- [<span data-ttu-id="3261b-112">Интерфейс ISymUnmanagedConstant</span><span class="sxs-lookup"><span data-stu-id="3261b-112">ISymUnmanagedConstant Interface</span></span>](isymunmanagedconstant-interface.md)
- [<span data-ttu-id="3261b-113">Метод GetName</span><span class="sxs-lookup"><span data-stu-id="3261b-113">GetName Method</span></span>](isymunmanagedconstant-getname-method.md)
- [<span data-ttu-id="3261b-114">Метод GetSignature</span><span class="sxs-lookup"><span data-stu-id="3261b-114">GetSignature Method</span></span>](isymunmanagedconstant-getsignature-method.md)
