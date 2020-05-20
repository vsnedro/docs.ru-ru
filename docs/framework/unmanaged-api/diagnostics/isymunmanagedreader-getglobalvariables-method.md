---
title: Метод ISymUnmanagedReader::GetGlobalVariables
ms.date: 03/30/2017
api_name:
- ISymUnmanagedReader.GetGlobalVariables
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedReader::GetGlobalVariables
helpviewer_keywords:
- GetGlobalVariables method [.NET Framework debugging]
- ISymUnmanagedReader::GetGlobalVariables method [.NET Framework debugging]
ms.assetid: a2dd5098-3e58-4be5-b7a2-e4160b3b505a
topic_type:
- apiref
ms.openlocfilehash: 20bfb3e48f411524bd4d9798f17dd935595a12bb
ms.sourcegitcommit: 27db07ffb26f76912feefba7b884313547410db5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/19/2020
ms.locfileid: "83615024"
---
# <a name="isymunmanagedreadergetglobalvariables-method"></a><span data-ttu-id="e883d-102">Метод ISymUnmanagedReader::GetGlobalVariables</span><span class="sxs-lookup"><span data-stu-id="e883d-102">ISymUnmanagedReader::GetGlobalVariables Method</span></span>
<span data-ttu-id="e883d-103">Возвращает все глобальные переменные.</span><span class="sxs-lookup"><span data-stu-id="e883d-103">Returns all global variables.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e883d-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="e883d-104">Syntax</span></span>  
  
```cpp  
HRESULT GetGlobalVariables(  
    [in]  ULONG32  cVars,  
    [out] ULONG32  *pcVars,  
    [out, size_is(cVars),  
        length_is(*pcVars)] ISymUnmanagedVariable *pVars[]);  
```  
  
## <a name="parameters"></a><span data-ttu-id="e883d-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="e883d-105">Parameters</span></span>  
 `cVars`  
 <span data-ttu-id="e883d-106">окне Длина буфера, на который указывает `pcVars` .</span><span class="sxs-lookup"><span data-stu-id="e883d-106">[in] The length of the buffer pointed to by `pcVars`.</span></span>  
  
 `pcVars`  
 <span data-ttu-id="e883d-107">заполняет Указатель на объект `ULONG32` , который получает размер буфера, необходимого для хранения переменных.</span><span class="sxs-lookup"><span data-stu-id="e883d-107">[out] A pointer to a `ULONG32` that receives the size of the buffer required to contain the variables.</span></span>  
  
 `pVars`  
 <span data-ttu-id="e883d-108">заполняет Буфер, содержащий переменные.</span><span class="sxs-lookup"><span data-stu-id="e883d-108">[out] A buffer that contains the variables.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="e883d-109">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="e883d-109">Return Value</span></span>  
 <span data-ttu-id="e883d-110">S_OK, если метод выполнен. в противном случае E_FAIL или другой код ошибки.</span><span class="sxs-lookup"><span data-stu-id="e883d-110">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="e883d-111">Требования</span><span class="sxs-lookup"><span data-stu-id="e883d-111">Requirements</span></span>  
 <span data-ttu-id="e883d-112">**Заголовок:** Корсим. idl, Корсим. h</span><span class="sxs-lookup"><span data-stu-id="e883d-112">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e883d-113">Дополнительно</span><span class="sxs-lookup"><span data-stu-id="e883d-113">See also</span></span>

- [<span data-ttu-id="e883d-114">Интерфейс ISymUnmanagedReader</span><span class="sxs-lookup"><span data-stu-id="e883d-114">ISymUnmanagedReader Interface</span></span>](isymunmanagedreader-interface.md)
