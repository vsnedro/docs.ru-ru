---
title: Метод ISymUnmanagedReader::GetVariables
ms.date: 03/30/2017
api_name:
- ISymUnmanagedReader.GetVariables
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedReader::GetVariables
helpviewer_keywords:
- ISymUnmanagedReader::GetVariables method [.NET Framework debugging]
- GetVariables method, ISymUnmanagedReader interface [.NET Framework debugging]
ms.assetid: 16dc49cb-2c60-4ac8-9c35-020e9afba3f8
topic_type:
- apiref
ms.openlocfilehash: 637e1aed003e211654141ab397c9c0b4724753c2
ms.sourcegitcommit: 27db07ffb26f76912feefba7b884313547410db5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/19/2020
ms.locfileid: "83615492"
---
# <a name="isymunmanagedreadergetvariables-method"></a><span data-ttu-id="9301b-102">Метод ISymUnmanagedReader::GetVariables</span><span class="sxs-lookup"><span data-stu-id="9301b-102">ISymUnmanagedReader::GetVariables Method</span></span>
<span data-ttu-id="9301b-103">Возвращает нелокальную переменную с учетом ее родителя и имени.</span><span class="sxs-lookup"><span data-stu-id="9301b-103">Returns a non-local variable, given its parent and name.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9301b-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="9301b-104">Syntax</span></span>  
  
```cpp  
HRESULT GetVariables (  
    [in]  mdToken  parent,  
    [in]  ULONG32  cVars,  
    [out] ULONG32  *pcVars,  
    [out, size_is (cVars),  
        length_is (*pcVars)] ISymUnmanagedVariable *pVars[]);  
```  
  
## <a name="parameters"></a><span data-ttu-id="9301b-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="9301b-105">Parameters</span></span>  
 `parent`  
 <span data-ttu-id="9301b-106">окне Родительский объект переменной.</span><span class="sxs-lookup"><span data-stu-id="9301b-106">[in] The parent of the variable.</span></span>  
  
 `cVars`  
 <span data-ttu-id="9301b-107">[in] Размер массива `pVars`.</span><span class="sxs-lookup"><span data-stu-id="9301b-107">[in] The size of the `pVars` array.</span></span>  
  
 `pcVars`  
 <span data-ttu-id="9301b-108">заполняет Указатель на переменную, которая получает количество переменных, возвращаемых в `pVars` .</span><span class="sxs-lookup"><span data-stu-id="9301b-108">[out] A pointer to the variable that receives the number of variables returned in `pVars`.</span></span>  
  
 `pVars`  
 <span data-ttu-id="9301b-109">заполняет Указатель на переменную, которая получает переменные.</span><span class="sxs-lookup"><span data-stu-id="9301b-109">[out] A pointer to the variable that receives the variables.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="9301b-110">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="9301b-110">Return Value</span></span>  
 <span data-ttu-id="9301b-111">S_OK, если метод выполнен. в противном случае E_FAIL или другой код ошибки.</span><span class="sxs-lookup"><span data-stu-id="9301b-111">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="9301b-112">Требования</span><span class="sxs-lookup"><span data-stu-id="9301b-112">Requirements</span></span>  
 <span data-ttu-id="9301b-113">**Заголовок:** Корсим. idl, Корсим. h</span><span class="sxs-lookup"><span data-stu-id="9301b-113">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9301b-114">Дополнительно</span><span class="sxs-lookup"><span data-stu-id="9301b-114">See also</span></span>

- [<span data-ttu-id="9301b-115">Интерфейс ISymUnmanagedReader</span><span class="sxs-lookup"><span data-stu-id="9301b-115">ISymUnmanagedReader Interface</span></span>](isymunmanagedreader-interface.md)
