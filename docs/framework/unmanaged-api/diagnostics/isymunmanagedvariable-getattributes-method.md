---
title: Метод ISymUnmanagedVariable::GetAttributes
ms.date: 03/30/2017
api_name:
- ISymUnmanagedVariable.GetAttributes
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedVariable::GetAttributes
helpviewer_keywords:
- GetAttributes method [.NET Framework debugging]
- ISymUnmanagedVariable::GetAttributes method [.NET Framework debugging]
ms.assetid: 80f168af-a6a6-4c8f-b9e6-8a82dc834ed5
topic_type:
- apiref
ms.openlocfilehash: 29869abdd39f61c6c9cb51d6b2be50fa462c5b70
ms.sourcegitcommit: 27db07ffb26f76912feefba7b884313547410db5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/19/2020
ms.locfileid: "83615258"
---
# <a name="isymunmanagedvariablegetattributes-method"></a><span data-ttu-id="bf3a3-102">Метод ISymUnmanagedVariable::GetAttributes</span><span class="sxs-lookup"><span data-stu-id="bf3a3-102">ISymUnmanagedVariable::GetAttributes Method</span></span>
<span data-ttu-id="bf3a3-103">Возвращает флаги атрибута для этой переменной.</span><span class="sxs-lookup"><span data-stu-id="bf3a3-103">Gets the attribute flags for this variable.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="bf3a3-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="bf3a3-104">Syntax</span></span>  
  
```cpp  
HRESULT GetAttributes(  
    [out, retval] ULONG32* pRetVal);  
```  
  
## <a name="parameters"></a><span data-ttu-id="bf3a3-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="bf3a3-105">Parameters</span></span>  
 `pRetVal`  
 <span data-ttu-id="bf3a3-106">заполняет Указатель на объект `ULONG32` , который получает атрибуты.</span><span class="sxs-lookup"><span data-stu-id="bf3a3-106">[out] A pointer to a `ULONG32` that receives the attributes.</span></span> <span data-ttu-id="bf3a3-107">Возвращаемое значение будет одним из значений, определенных в перечислении [CorSymVarFlag](corsymvarflag-enumeration.md) .</span><span class="sxs-lookup"><span data-stu-id="bf3a3-107">The returned value will be one of the values defined in the [CorSymVarFlag](corsymvarflag-enumeration.md) enumeration.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="bf3a3-108">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="bf3a3-108">Return Value</span></span>  
 <span data-ttu-id="bf3a3-109">S_OK, если метод выполнен. в противном случае E_FAIL или другой код ошибки.</span><span class="sxs-lookup"><span data-stu-id="bf3a3-109">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="bf3a3-110">Требования</span><span class="sxs-lookup"><span data-stu-id="bf3a3-110">Requirements</span></span>  
 <span data-ttu-id="bf3a3-111">**Заголовок:** Корсим. idl, Корсим. h</span><span class="sxs-lookup"><span data-stu-id="bf3a3-111">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bf3a3-112">См. также статью</span><span class="sxs-lookup"><span data-stu-id="bf3a3-112">See also</span></span>

- [<span data-ttu-id="bf3a3-113">Интерфейс ISymUnmanagedVariable</span><span class="sxs-lookup"><span data-stu-id="bf3a3-113">ISymUnmanagedVariable Interface</span></span>](isymunmanagedvariable-interface.md)
