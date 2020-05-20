---
title: Метод ISymUnmanagedScope::GetMethod
ms.date: 03/30/2017
api_name:
- ISymUnmanagedScope.GetMethod
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedScope::GetMethod
helpviewer_keywords:
- GetMethod method, ISymUnmanagedScope interface [.NET Framework debugging]
- ISymUnmanagedScope::GetMethod method [.NET Framework debugging]
ms.assetid: a61866ee-221a-45b9-a1b7-395825b77872
topic_type:
- apiref
ms.openlocfilehash: cdbffe71540b51ff539a45861546efd761761892
ms.sourcegitcommit: 27db07ffb26f76912feefba7b884313547410db5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/19/2020
ms.locfileid: "83615375"
---
# <a name="isymunmanagedscopegetmethod-method"></a><span data-ttu-id="4c36f-102">Метод ISymUnmanagedScope::GetMethod</span><span class="sxs-lookup"><span data-stu-id="4c36f-102">ISymUnmanagedScope::GetMethod Method</span></span>
<span data-ttu-id="4c36f-103">Возвращает метод, содержащий эту область.</span><span class="sxs-lookup"><span data-stu-id="4c36f-103">Gets the method that contains this scope.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4c36f-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="4c36f-104">Syntax</span></span>  
  
```cpp  
HRESULT GetMethod(  
    [out, retval] ISymUnmanagedMethod** pRetVal);  
```  
  
## <a name="parameters"></a><span data-ttu-id="4c36f-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="4c36f-105">Parameters</span></span>  
 `pRetVal`  
 <span data-ttu-id="4c36f-106">заполняет Указатель на возвращаемый интерфейс [ISymUnmanagedMethod](isymunmanagedmethod-interface.md) .</span><span class="sxs-lookup"><span data-stu-id="4c36f-106">[out] A pointer to the returned [ISymUnmanagedMethod](isymunmanagedmethod-interface.md) interface.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="4c36f-107">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="4c36f-107">Return Value</span></span>  
 <span data-ttu-id="4c36f-108">S_OK, если метод выполнен. в противном случае E_FAIL или другой код ошибки.</span><span class="sxs-lookup"><span data-stu-id="4c36f-108">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="4c36f-109">Требования</span><span class="sxs-lookup"><span data-stu-id="4c36f-109">Requirements</span></span>  
 <span data-ttu-id="4c36f-110">**Заголовок:** Корсим. idl, Корсим. h</span><span class="sxs-lookup"><span data-stu-id="4c36f-110">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4c36f-111">См. также статью</span><span class="sxs-lookup"><span data-stu-id="4c36f-111">See also</span></span>

- [<span data-ttu-id="4c36f-112">Интерфейс ISymUnmanagedScope</span><span class="sxs-lookup"><span data-stu-id="4c36f-112">ISymUnmanagedScope Interface</span></span>](isymunmanagedscope-interface.md)
