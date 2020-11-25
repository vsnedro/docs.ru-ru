---
title: Метод ISymUnmanagedScope::GetChildren
ms.date: 03/30/2017
api_name:
- ISymUnmanagedScope.GetChildren
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedScope::GetChildren
helpviewer_keywords:
- ISymUnmanagedScope::GetChildren method [.NET Framework debugging]
- GetChildren method [.NET Framework debugging]
ms.assetid: 0bed524e-cc48-4bf0-b9fa-25d665e63ddb
topic_type:
- apiref
ms.openlocfilehash: 8f3c83a7a89553ba600f3e0e368eec0ddd0350e9
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/24/2020
ms.locfileid: "95727613"
---
# <a name="isymunmanagedscopegetchildren-method"></a><span data-ttu-id="77aa6-102">Метод ISymUnmanagedScope::GetChildren</span><span class="sxs-lookup"><span data-stu-id="77aa6-102">ISymUnmanagedScope::GetChildren Method</span></span>

<span data-ttu-id="77aa6-103">Возвращает дочерние элементы этой области.</span><span class="sxs-lookup"><span data-stu-id="77aa6-103">Gets the children of this scope.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="77aa6-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="77aa6-104">Syntax</span></span>  
  
```cpp  
HRESULT GetChildren(  
    [in]  ULONG32  cChildren,  
    [out] ULONG32  *pcChildren,  
    [out, size_is(cChildren),  
        length_is(*pcChildren)] ISymUnmanagedScope* children[]);  
```  
  
## <a name="parameters"></a><span data-ttu-id="77aa6-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="77aa6-105">Parameters</span></span>  

 `cChildren`  
 <span data-ttu-id="77aa6-106">окне Значение типа `ULONG32` , указывающее размер `children` массива.</span><span class="sxs-lookup"><span data-stu-id="77aa6-106">[in] A `ULONG32` that indicates the size of the `children` array.</span></span>  
  
 `pcChildren`  
 <span data-ttu-id="77aa6-107">заполняет Указатель на объект `ULONG32` , который получает размер буфера, необходимого для хранения дочерних элементов.</span><span class="sxs-lookup"><span data-stu-id="77aa6-107">[out] A pointer to a `ULONG32` that receives the size of the buffer required to contain the children.</span></span>  
  
 `children`  
 <span data-ttu-id="77aa6-108">заполняет Возвращаемый массив дочерних элементов.</span><span class="sxs-lookup"><span data-stu-id="77aa6-108">[out] The returned array of children.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="77aa6-109">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="77aa6-109">Return Value</span></span>  

 <span data-ttu-id="77aa6-110">S_OK, если метод выполнен. в противном случае E_FAIL или другой код ошибки.</span><span class="sxs-lookup"><span data-stu-id="77aa6-110">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="77aa6-111">Требования</span><span class="sxs-lookup"><span data-stu-id="77aa6-111">Requirements</span></span>  

 <span data-ttu-id="77aa6-112">**Заголовок:** Корсим. idl, Корсим. h</span><span class="sxs-lookup"><span data-stu-id="77aa6-112">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="77aa6-113">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="77aa6-113">See also</span></span>

- [<span data-ttu-id="77aa6-114">Интерфейс ISymUnmanagedScope</span><span class="sxs-lookup"><span data-stu-id="77aa6-114">ISymUnmanagedScope Interface</span></span>](isymunmanagedscope-interface.md)
- [<span data-ttu-id="77aa6-115">Метод GetParent</span><span class="sxs-lookup"><span data-stu-id="77aa6-115">GetParent Method</span></span>](isymunmanagedscope-getparent-method.md)
