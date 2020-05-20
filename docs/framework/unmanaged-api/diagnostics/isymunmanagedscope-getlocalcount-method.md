---
title: Метод ISymUnmanagedScope::GetLocalCount
ms.date: 03/30/2017
api_name:
- ISymUnmanagedScope.GetLocalCount
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedScope::GetLocalCount
helpviewer_keywords:
- GetLocalCount method [.NET Framework debugging]
- ISymUnmanagedScope::GetLocalCount method [.NET Framework debugging]
ms.assetid: 3ede8fb5-f655-4088-8e19-9c53812588a8
topic_type:
- apiref
ms.openlocfilehash: 9ffba23e3821c48c9b0708e4b6b617db4ddc5959
ms.sourcegitcommit: 27db07ffb26f76912feefba7b884313547410db5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/19/2020
ms.locfileid: "83611267"
---
# <a name="isymunmanagedscopegetlocalcount-method"></a><span data-ttu-id="00e24-102">Метод ISymUnmanagedScope::GetLocalCount</span><span class="sxs-lookup"><span data-stu-id="00e24-102">ISymUnmanagedScope::GetLocalCount Method</span></span>
<span data-ttu-id="00e24-103">Возвращает число локальных переменных, определенных в этой области.</span><span class="sxs-lookup"><span data-stu-id="00e24-103">Gets a count of the local variables defined within this scope.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="00e24-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="00e24-104">Syntax</span></span>  
  
```cpp  
HRESULT GetLocalCount(  
    [out, retval] ULONG32 *pRetVal);  
```  
  
## <a name="parameters"></a><span data-ttu-id="00e24-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="00e24-105">Parameters</span></span>  
 `pRetVal`  
 <span data-ttu-id="00e24-106">заполняет Указатель на объект `ULONG32` , который получает число локальных переменных.</span><span class="sxs-lookup"><span data-stu-id="00e24-106">[out] A pointer to a `ULONG32` that receives the count of local variables.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="00e24-107">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="00e24-107">Return Value</span></span>  
 <span data-ttu-id="00e24-108">S_OK, если метод выполнен. в противном случае E_FAIL или другой код ошибки.</span><span class="sxs-lookup"><span data-stu-id="00e24-108">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="00e24-109">Требования</span><span class="sxs-lookup"><span data-stu-id="00e24-109">Requirements</span></span>  
 <span data-ttu-id="00e24-110">**Заголовок:** Корсим. idl, Корсим. h</span><span class="sxs-lookup"><span data-stu-id="00e24-110">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="00e24-111">Дополнительно</span><span class="sxs-lookup"><span data-stu-id="00e24-111">See also</span></span>

- [<span data-ttu-id="00e24-112">Интерфейс ISymUnmanagedScope</span><span class="sxs-lookup"><span data-stu-id="00e24-112">ISymUnmanagedScope Interface</span></span>](isymunmanagedscope-interface.md)
