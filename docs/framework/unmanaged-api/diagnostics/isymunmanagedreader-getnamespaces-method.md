---
title: Метод ISymUnmanagedReader::GetNamespaces
ms.date: 03/30/2017
api_name:
- ISymUnmanagedReader.GetNamespaces
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedReader::GetNamespaces
helpviewer_keywords:
- ISymUnmanagedReader::GetNamespaces method [.NET Framework debugging]
- GetNamespaces method, ISymUnmanagedReader interface [.NET Framework debugging]
ms.assetid: 3feb4796-2fab-45ce-beca-6f5bc530b971
topic_type:
- apiref
ms.openlocfilehash: 44f9284f0a89f0941940cf379c48b2b138149122
ms.sourcegitcommit: 27db07ffb26f76912feefba7b884313547410db5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/19/2020
ms.locfileid: "83614946"
---
# <a name="isymunmanagedreadergetnamespaces-method"></a><span data-ttu-id="e5e60-102">Метод ISymUnmanagedReader::GetNamespaces</span><span class="sxs-lookup"><span data-stu-id="e5e60-102">ISymUnmanagedReader::GetNamespaces Method</span></span>
<span data-ttu-id="e5e60-103">Возвращает пространства имен, определенные в глобальной области в этом хранилище символов.</span><span class="sxs-lookup"><span data-stu-id="e5e60-103">Gets the namespaces defined at global scope within this symbol store.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e5e60-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="e5e60-104">Syntax</span></span>  
  
```cpp  
HRESULT GetNamespaces (  
    [in]  ULONG32  cNameSpaces,  
    [out] ULONG32  *pcNameSpaces,  
    [out, size_is (cNameSpaces),  
        length_is (*pcNameSpaces)]  
        ISymUnmanagedNamespace*  namespaces[]);  
```  
  
## <a name="parameters"></a><span data-ttu-id="e5e60-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="e5e60-105">Parameters</span></span>  
 `cNameSpaces`  
 <span data-ttu-id="e5e60-106">окне Размер массива пространств имен.</span><span class="sxs-lookup"><span data-stu-id="e5e60-106">[in] The size of the namespaces array.</span></span>  
  
 `pcNameSpaces`  
 <span data-ttu-id="e5e60-107">заполняет Указатель на переменную, которая получает длину списка пространств имен.</span><span class="sxs-lookup"><span data-stu-id="e5e60-107">[out] A pointer to a variable that receives the length of the namespace list.</span></span>  
  
 `namespaces`  
 <span data-ttu-id="e5e60-108">заполняет Указатель на переменную, которая получает список пространств имен.</span><span class="sxs-lookup"><span data-stu-id="e5e60-108">[out] A pointer to a variable that receives the namespace list.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="e5e60-109">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="e5e60-109">Return Value</span></span>  
 <span data-ttu-id="e5e60-110">S_OK, если метод выполнен. в противном случае E_FAIL или другой код ошибки.</span><span class="sxs-lookup"><span data-stu-id="e5e60-110">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="e5e60-111">Требования</span><span class="sxs-lookup"><span data-stu-id="e5e60-111">Requirements</span></span>  
 <span data-ttu-id="e5e60-112">**Заголовок:** Корсим. idl, Корсим. h</span><span class="sxs-lookup"><span data-stu-id="e5e60-112">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e5e60-113">Дополнительно</span><span class="sxs-lookup"><span data-stu-id="e5e60-113">See also</span></span>

- [<span data-ttu-id="e5e60-114">Интерфейс ISymUnmanagedReader</span><span class="sxs-lookup"><span data-stu-id="e5e60-114">ISymUnmanagedReader Interface</span></span>](isymunmanagedreader-interface.md)
