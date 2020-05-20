---
title: Метод ISymUnmanagedNamespace::GetVariables
ms.date: 03/30/2017
api_name:
- ISymUnmanagedNamespace.GetVariables
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedNamespace::GetVariables
helpviewer_keywords:
- ISymUnmanagedNamespace::GetVariables method [.NET Framework debugging]
- GetVariables method, ISymUnmanagedNamespace interface [.NET Framework debugging]
ms.assetid: ea7c1617-f3ce-4220-8288-f2b50eaf0f0f
topic_type:
- apiref
ms.openlocfilehash: 091f497024b48589953456e1ea6daf6635738240
ms.sourcegitcommit: 27db07ffb26f76912feefba7b884313547410db5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/19/2020
ms.locfileid: "83615089"
---
# <a name="isymunmanagednamespacegetvariables-method"></a><span data-ttu-id="19d57-102">Метод ISymUnmanagedNamespace::GetVariables</span><span class="sxs-lookup"><span data-stu-id="19d57-102">ISymUnmanagedNamespace::GetVariables Method</span></span>
<span data-ttu-id="19d57-103">Возвращает все переменные, определенные в глобальной области видимости в этом пространстве имен.</span><span class="sxs-lookup"><span data-stu-id="19d57-103">Returns all variables defined at global scope within this namespace.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="19d57-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="19d57-104">Syntax</span></span>  
  
```cpp
HRESULT GetVariables(  
    [in]  ULONG32  cVars,  
    [out] ULONG32  *pcVars,  
    [out, size_is(cVars), length_is(*pcVars)]  
        ISymUnmanagedVariable *pVars[]);  
```  
  
## <a name="parameters"></a><span data-ttu-id="19d57-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="19d57-105">Parameters</span></span>  
 `cVars`  
 <span data-ttu-id="19d57-106">окне Значение типа `ULONG32` , указывающее размер `pVars` массива.</span><span class="sxs-lookup"><span data-stu-id="19d57-106">[in] A `ULONG32` that indicates the size of the `pVars` array.</span></span>  
  
 `pcVars`  
 <span data-ttu-id="19d57-107">заполняет Указатель на объект `ULONG32` , который получает размер буфера, необходимого для хранения пространств имен.</span><span class="sxs-lookup"><span data-stu-id="19d57-107">[out] A pointer to a `ULONG32` that receives the size of the buffer required to contain the namespaces.</span></span>  
  
 `pVars`  
 <span data-ttu-id="19d57-108">заполняет Указатель на буфер, содержащий пространства имен.</span><span class="sxs-lookup"><span data-stu-id="19d57-108">[out] A pointer to a buffer that contains the namespaces.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="19d57-109">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="19d57-109">Return Value</span></span>  
 <span data-ttu-id="19d57-110">S_OK, если метод выполнен. в противном случае E_FAIL или другой код ошибки.</span><span class="sxs-lookup"><span data-stu-id="19d57-110">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="19d57-111">Требования</span><span class="sxs-lookup"><span data-stu-id="19d57-111">Requirements</span></span>  
 <span data-ttu-id="19d57-112">**Заголовок:** Корсим. idl, Корсим. h</span><span class="sxs-lookup"><span data-stu-id="19d57-112">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="19d57-113">Дополнительно</span><span class="sxs-lookup"><span data-stu-id="19d57-113">See also</span></span>

- [<span data-ttu-id="19d57-114">Интерфейс ISymUnmanagedNamespace</span><span class="sxs-lookup"><span data-stu-id="19d57-114">ISymUnmanagedNamespace Interface</span></span>](isymunmanagednamespace-interface.md)
