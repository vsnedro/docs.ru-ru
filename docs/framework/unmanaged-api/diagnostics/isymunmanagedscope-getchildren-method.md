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
ms.openlocfilehash: c6d21f40c260890c9c88dcdfccd7e31161024ba3
ms.sourcegitcommit: 27db07ffb26f76912feefba7b884313547410db5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/19/2020
ms.locfileid: "83614868"
---
# <a name="isymunmanagedscopegetchildren-method"></a><span data-ttu-id="dba92-102">Метод ISymUnmanagedScope::GetChildren</span><span class="sxs-lookup"><span data-stu-id="dba92-102">ISymUnmanagedScope::GetChildren Method</span></span>
<span data-ttu-id="dba92-103">Возвращает дочерние элементы этой области.</span><span class="sxs-lookup"><span data-stu-id="dba92-103">Gets the children of this scope.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="dba92-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="dba92-104">Syntax</span></span>  
  
```cpp  
HRESULT GetChildren(  
    [in]  ULONG32  cChildren,  
    [out] ULONG32  *pcChildren,  
    [out, size_is(cChildren),  
        length_is(*pcChildren)] ISymUnmanagedScope* children[]);  
```  
  
## <a name="parameters"></a><span data-ttu-id="dba92-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="dba92-105">Parameters</span></span>  
 `cChildren`  
 <span data-ttu-id="dba92-106">окне Значение типа `ULONG32` , указывающее размер `children` массива.</span><span class="sxs-lookup"><span data-stu-id="dba92-106">[in] A `ULONG32` that indicates the size of the `children` array.</span></span>  
  
 `pcChildren`  
 <span data-ttu-id="dba92-107">заполняет Указатель на объект `ULONG32` , который получает размер буфера, необходимого для хранения дочерних элементов.</span><span class="sxs-lookup"><span data-stu-id="dba92-107">[out] A pointer to a `ULONG32` that receives the size of the buffer required to contain the children.</span></span>  
  
 `children`  
 <span data-ttu-id="dba92-108">заполняет Возвращаемый массив дочерних элементов.</span><span class="sxs-lookup"><span data-stu-id="dba92-108">[out] The returned array of children.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="dba92-109">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="dba92-109">Return Value</span></span>  
 <span data-ttu-id="dba92-110">S_OK, если метод выполнен. в противном случае E_FAIL или другой код ошибки.</span><span class="sxs-lookup"><span data-stu-id="dba92-110">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="dba92-111">Требования</span><span class="sxs-lookup"><span data-stu-id="dba92-111">Requirements</span></span>  
 <span data-ttu-id="dba92-112">**Заголовок:** Корсим. idl, Корсим. h</span><span class="sxs-lookup"><span data-stu-id="dba92-112">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="dba92-113">См. также статью</span><span class="sxs-lookup"><span data-stu-id="dba92-113">See also</span></span>

- [<span data-ttu-id="dba92-114">Интерфейс ISymUnmanagedScope</span><span class="sxs-lookup"><span data-stu-id="dba92-114">ISymUnmanagedScope Interface</span></span>](isymunmanagedscope-interface.md)
- [<span data-ttu-id="dba92-115">Метод GetParent</span><span class="sxs-lookup"><span data-stu-id="dba92-115">GetParent Method</span></span>](isymunmanagedscope-getparent-method.md)
