---
title: Метод ISymUnmanagedReader::GetUserEntryPoint
ms.date: 03/30/2017
api_name:
- ISymUnmanagedReader.GetUserEntryPoint
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedReader::GetUserEntryPoint
helpviewer_keywords:
- GetUserEntryPoint method [.NET Framework debugging]
- ISymUnmanagedReader::GetUserEntryPoint method [.NET Framework debugging]
ms.assetid: 3fd3a34c-d176-46e9-9996-fb1646cff9b0
topic_type:
- apiref
ms.openlocfilehash: d465f830fa73016c3cf3f7df3a4a4d0c42bc0980
ms.sourcegitcommit: 27db07ffb26f76912feefba7b884313547410db5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/19/2020
ms.locfileid: "83615505"
---
# <a name="isymunmanagedreadergetuserentrypoint-method"></a><span data-ttu-id="fd164-102">Метод ISymUnmanagedReader::GetUserEntryPoint</span><span class="sxs-lookup"><span data-stu-id="fd164-102">ISymUnmanagedReader::GetUserEntryPoint Method</span></span>
<span data-ttu-id="fd164-103">Возвращает метод, указанный в качестве точки входа пользователя для модуля, если он есть.</span><span class="sxs-lookup"><span data-stu-id="fd164-103">Returns the method that was specified as the user entry point for the module, if any.</span></span> <span data-ttu-id="fd164-104">Например, этот метод может быть основным методом пользователя вместо заглушек, созданных компилятором, перед методом Main.</span><span class="sxs-lookup"><span data-stu-id="fd164-104">For example, this method could be the user's main method rather than compiler-generated stubs before the main method.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="fd164-105">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="fd164-105">Syntax</span></span>  
  
```cpp  
HRESULT GetUserEntryPoint (  
    [out, retval]  mdMethodDef  *pToken);  
```  
  
## <a name="parameters"></a><span data-ttu-id="fd164-106">Параметры</span><span class="sxs-lookup"><span data-stu-id="fd164-106">Parameters</span></span>  
 `pToken`  
 <span data-ttu-id="fd164-107">заполняет Указатель на переменную, которая получает точку входа.</span><span class="sxs-lookup"><span data-stu-id="fd164-107">[out] A pointer to a variable that receives the entry point.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="fd164-108">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="fd164-108">Return Value</span></span>  
 <span data-ttu-id="fd164-109">S_OK, если метод выполнен. в противном случае E_FAIL или другой код ошибки.</span><span class="sxs-lookup"><span data-stu-id="fd164-109">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="fd164-110">Требования</span><span class="sxs-lookup"><span data-stu-id="fd164-110">Requirements</span></span>  
 <span data-ttu-id="fd164-111">**Заголовок:** Корсим. idl, Корсим. h</span><span class="sxs-lookup"><span data-stu-id="fd164-111">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fd164-112">См. также статью</span><span class="sxs-lookup"><span data-stu-id="fd164-112">See also</span></span>

- [<span data-ttu-id="fd164-113">Интерфейс ISymUnmanagedReader</span><span class="sxs-lookup"><span data-stu-id="fd164-113">ISymUnmanagedReader Interface</span></span>](isymunmanagedreader-interface.md)
