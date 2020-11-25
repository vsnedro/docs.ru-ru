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
ms.openlocfilehash: 026ba35044bc7573dc54617dcade9cf3918a76ec
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/24/2020
ms.locfileid: "95725928"
---
# <a name="isymunmanagedscopegetnamespaces-method"></a><span data-ttu-id="cbed9-102">Метод ISymUnmanagedScope::GetNamespaces</span><span class="sxs-lookup"><span data-stu-id="cbed9-102">ISymUnmanagedScope::GetNamespaces Method</span></span>

<span data-ttu-id="cbed9-103">Возвращает пространства имен, используемые в этой области.</span><span class="sxs-lookup"><span data-stu-id="cbed9-103">Gets the namespaces that are being used within this scope.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="cbed9-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="cbed9-104">Syntax</span></span>  
  
```cpp  
HRESULT GetNamespaces(  
    [in]  ULONG32  cNameSpaces,  
    [out] ULONG32  *pcNameSpaces,  
    [out, size_is(cNameSpaces),  
        length_is(*pcNameSpaces)]  
        ISymUnmanagedNamespace* namespaces[]);  
```  
  
## <a name="parameters"></a><span data-ttu-id="cbed9-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="cbed9-105">Parameters</span></span>  

 `cNameSpaces`  
 <span data-ttu-id="cbed9-106">[in] Размер массива `namespaces`.</span><span class="sxs-lookup"><span data-stu-id="cbed9-106">[in] The size of the `namespaces` array.</span></span>  
  
 `pcNameSpaces`  
 <span data-ttu-id="cbed9-107">заполняет Указатель на объект `ULONG32` , который получает размер буфера, необходимого для хранения пространств имен.</span><span class="sxs-lookup"><span data-stu-id="cbed9-107">[out] A pointer to a `ULONG32` that receives the size of the buffer required to contain the namespaces.</span></span>  
  
 `namespaces`  
 <span data-ttu-id="cbed9-108">заполняет Массив, получающий пространства имен.</span><span class="sxs-lookup"><span data-stu-id="cbed9-108">[out] The array that receives the namespaces.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="cbed9-109">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="cbed9-109">Return Value</span></span>  

 <span data-ttu-id="cbed9-110">S_OK, если метод выполнен. в противном случае E_FAIL или другой код ошибки.</span><span class="sxs-lookup"><span data-stu-id="cbed9-110">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="cbed9-111">Требования</span><span class="sxs-lookup"><span data-stu-id="cbed9-111">Requirements</span></span>  

 <span data-ttu-id="cbed9-112">**Заголовок:** Корсим. idl, Корсим. h</span><span class="sxs-lookup"><span data-stu-id="cbed9-112">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="cbed9-113">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="cbed9-113">See also</span></span>

- [<span data-ttu-id="cbed9-114">Интерфейс ISymUnmanagedScope</span><span class="sxs-lookup"><span data-stu-id="cbed9-114">ISymUnmanagedScope Interface</span></span>](isymunmanagedscope-interface.md)
