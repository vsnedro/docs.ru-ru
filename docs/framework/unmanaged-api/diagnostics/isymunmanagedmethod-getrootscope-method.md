---
title: Метод ISymUnmanagedMethod::GetRootScope
ms.date: 03/30/2017
api_name:
- ISymUnmanagedMethod.GetRootScope
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedMethod::GetRootScope
helpviewer_keywords:
- ISymUnmanagedMethod::GetRootScope method [.NET Framework debugging]
- GetRootScope method [.NET Framework debugging]
ms.assetid: 7d58caac-2e75-4dfa-9249-32d8a624b247
topic_type:
- apiref
ms.openlocfilehash: 650a64e72b410cddfbee7dce676ddbb5a3b8b3d3
ms.sourcegitcommit: 27db07ffb26f76912feefba7b884313547410db5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/19/2020
ms.locfileid: "83614452"
---
# <a name="isymunmanagedmethodgetrootscope-method"></a><span data-ttu-id="82569-102">Метод ISymUnmanagedMethod::GetRootScope</span><span class="sxs-lookup"><span data-stu-id="82569-102">ISymUnmanagedMethod::GetRootScope Method</span></span>
<span data-ttu-id="82569-103">Возвращает корневую лексическую область внутри этого метода.</span><span class="sxs-lookup"><span data-stu-id="82569-103">Gets the root lexical scope within this method.</span></span> <span data-ttu-id="82569-104">Эта область включает весь метод.</span><span class="sxs-lookup"><span data-stu-id="82569-104">This scope encloses the entire method.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="82569-105">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="82569-105">Syntax</span></span>  
  
```cpp  
HRESULT GetRootScope(  
    [out, retval] ISymUnmanagedScope** pRetVal);  
```  
  
## <a name="parameters"></a><span data-ttu-id="82569-106">Параметры</span><span class="sxs-lookup"><span data-stu-id="82569-106">Parameters</span></span>  
 `pRetVal`  
 <span data-ttu-id="82569-107">заполняет Указатель, которому присваивается возвращаемый интерфейс [исимунманажедскопе](isymunmanagedscope-interface.md) .</span><span class="sxs-lookup"><span data-stu-id="82569-107">[out] A pointer that is set to the returned [ISymUnmanagedScope](isymunmanagedscope-interface.md) interface.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="82569-108">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="82569-108">Return Value</span></span>  
 <span data-ttu-id="82569-109">S_OK, если метод выполнен. в противном случае E_FAIL или другой код ошибки.</span><span class="sxs-lookup"><span data-stu-id="82569-109">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="82569-110">Требования</span><span class="sxs-lookup"><span data-stu-id="82569-110">Requirements</span></span>  
 <span data-ttu-id="82569-111">**Заголовок:** Корсим. idl, Корсим. h</span><span class="sxs-lookup"><span data-stu-id="82569-111">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="82569-112">См. также статью</span><span class="sxs-lookup"><span data-stu-id="82569-112">See also</span></span>

- [<span data-ttu-id="82569-113">Интерфейс ISymUnmanagedMethod</span><span class="sxs-lookup"><span data-stu-id="82569-113">ISymUnmanagedMethod Interface</span></span>](isymunmanagedmethod-interface.md)
