---
title: Метод ISymUnmanagedScope::GetNamespaces
ms.date: 03/30/2017
api_name:
- ISymUnmanagedScope.GetNamespaces
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedScope::GetNamespaces
helpviewer_keywords:
- GetNamespaces method, ISymUnmanagedScope interface [.NET Framework debugging]
- ISymUnmanagedScope::GetNamespaces method [.NET Framework debugging]
ms.assetid: c44b0440-04bd-460a-84fb-41afecf44503
topic_type:
- apiref
ms.openlocfilehash: 6f11a69671864ba4627c2bb8c86e0c9beb27eeb1
ms.sourcegitcommit: 27db07ffb26f76912feefba7b884313547410db5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/19/2020
ms.locfileid: "83611124"
---
# <a name="isymunmanagedscopegetnamespaces-method"></a><span data-ttu-id="2de99-102">Метод ISymUnmanagedScope::GetNamespaces</span><span class="sxs-lookup"><span data-stu-id="2de99-102">ISymUnmanagedScope::GetNamespaces Method</span></span>
<span data-ttu-id="2de99-103">Возвращает пространства имен, используемые в этой области.</span><span class="sxs-lookup"><span data-stu-id="2de99-103">Gets the namespaces that are being used within this scope.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2de99-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="2de99-104">Syntax</span></span>  
  
```cpp  
HRESULT GetNamespaces(  
    [in]  ULONG32  cNameSpaces,  
    [out] ULONG32  *pcNameSpaces,  
    [out, size_is(cNameSpaces),  
        length_is(*pcNameSpaces)]  
        ISymUnmanagedNamespace* namespaces[]);  
```  
  
## <a name="parameters"></a><span data-ttu-id="2de99-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="2de99-105">Parameters</span></span>  
 `cNameSpaces`  
 <span data-ttu-id="2de99-106">[in] Размер массива `namespaces`.</span><span class="sxs-lookup"><span data-stu-id="2de99-106">[in] The size of the `namespaces` array.</span></span>  
  
 `pcNameSpaces`  
 <span data-ttu-id="2de99-107">заполняет Указатель на объект `ULONG32` , который получает размер буфера, необходимого для хранения пространств имен.</span><span class="sxs-lookup"><span data-stu-id="2de99-107">[out] A pointer to a `ULONG32` that receives the size of the buffer required to contain the namespaces.</span></span>  
  
 `namespaces`  
 <span data-ttu-id="2de99-108">заполняет Массив, получающий пространства имен.</span><span class="sxs-lookup"><span data-stu-id="2de99-108">[out] The array that receives the namespaces.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="2de99-109">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="2de99-109">Return Value</span></span>  
 <span data-ttu-id="2de99-110">S_OK, если метод выполнен. в противном случае E_FAIL или другой код ошибки.</span><span class="sxs-lookup"><span data-stu-id="2de99-110">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="2de99-111">Требования</span><span class="sxs-lookup"><span data-stu-id="2de99-111">Requirements</span></span>  
 <span data-ttu-id="2de99-112">**Заголовок:** Корсим. idl, Корсим. h</span><span class="sxs-lookup"><span data-stu-id="2de99-112">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2de99-113">Дополнительно</span><span class="sxs-lookup"><span data-stu-id="2de99-113">See also</span></span>

- [<span data-ttu-id="2de99-114">Интерфейс ISymUnmanagedScope</span><span class="sxs-lookup"><span data-stu-id="2de99-114">ISymUnmanagedScope Interface</span></span>](isymunmanagedscope-interface.md)
