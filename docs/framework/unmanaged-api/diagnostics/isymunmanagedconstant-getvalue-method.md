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
ms.openlocfilehash: 8e20d2e0f3d5cb6dc7444c8e78665b6c8b82d2de
ms.sourcegitcommit: 7b1497c1927cb449cefd313bc5126ae37df30746
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/16/2020
ms.locfileid: "83441478"
---
# <a name="isymunmanagedconstantgetvalue-method"></a><span data-ttu-id="ed9bf-102">Метод ISymUnmanagedConstant::GetValue</span><span class="sxs-lookup"><span data-stu-id="ed9bf-102">ISymUnmanagedConstant::GetValue Method</span></span>
<span data-ttu-id="ed9bf-103"> Возвращает значение константы.</span><span class="sxs-lookup"><span data-stu-id="ed9bf-103">Gets the value of the constant.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ed9bf-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="ed9bf-104">Syntax</span></span>  
  
```cpp  
HRESULT GetValue(  
    [out]  VARIANT* pValue  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="ed9bf-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="ed9bf-105">Parameters</span></span>  
 `pValue`  
 <span data-ttu-id="ed9bf-106">заполняет Указатель на переменную, которая получает значение.</span><span class="sxs-lookup"><span data-stu-id="ed9bf-106">[out] A pointer to a variable that receives the value.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="ed9bf-107">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="ed9bf-107">Return Value</span></span>  
 <span data-ttu-id="ed9bf-108">S_OK, если метод выполнен. в противном случае E_FAIL или другой код ошибки.</span><span class="sxs-lookup"><span data-stu-id="ed9bf-108">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="ed9bf-109">Требования</span><span class="sxs-lookup"><span data-stu-id="ed9bf-109">Requirements</span></span>  
 <span data-ttu-id="ed9bf-110">**Заголовок:** Корсим. idl, Корсим. h</span><span class="sxs-lookup"><span data-stu-id="ed9bf-110">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ed9bf-111">Дополнительно</span><span class="sxs-lookup"><span data-stu-id="ed9bf-111">See also</span></span>

- [<span data-ttu-id="ed9bf-112">Интерфейс ISymUnmanagedConstant</span><span class="sxs-lookup"><span data-stu-id="ed9bf-112">ISymUnmanagedConstant Interface</span></span>](isymunmanagedconstant-interface.md)
- [<span data-ttu-id="ed9bf-113">Метод GetName</span><span class="sxs-lookup"><span data-stu-id="ed9bf-113">GetName Method</span></span>](isymunmanagedconstant-getname-method.md)
- [<span data-ttu-id="ed9bf-114">Метод GetSignature</span><span class="sxs-lookup"><span data-stu-id="ed9bf-114">GetSignature Method</span></span>](isymunmanagedconstant-getsignature-method.md)
