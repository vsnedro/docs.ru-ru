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
ms.openlocfilehash: 07c41e9d80b1703e86ae06525d64bf166ef2cf8e
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/24/2020
ms.locfileid: "95717556"
---
# <a name="isymunmanagedscopegetlocalcount-method"></a><span data-ttu-id="06b63-102">Метод ISymUnmanagedScope::GetLocalCount</span><span class="sxs-lookup"><span data-stu-id="06b63-102">ISymUnmanagedScope::GetLocalCount Method</span></span>

<span data-ttu-id="06b63-103">Возвращает число локальных переменных, определенных в этой области.</span><span class="sxs-lookup"><span data-stu-id="06b63-103">Gets a count of the local variables defined within this scope.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="06b63-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="06b63-104">Syntax</span></span>  
  
```cpp  
HRESULT GetLocalCount(  
    [out, retval] ULONG32 *pRetVal);  
```  
  
## <a name="parameters"></a><span data-ttu-id="06b63-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="06b63-105">Parameters</span></span>  

 `pRetVal`  
 <span data-ttu-id="06b63-106">заполняет Указатель на объект `ULONG32` , который получает число локальных переменных.</span><span class="sxs-lookup"><span data-stu-id="06b63-106">[out] A pointer to a `ULONG32` that receives the count of local variables.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="06b63-107">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="06b63-107">Return Value</span></span>  

 <span data-ttu-id="06b63-108">S_OK, если метод выполнен. в противном случае E_FAIL или другой код ошибки.</span><span class="sxs-lookup"><span data-stu-id="06b63-108">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="06b63-109">Требования</span><span class="sxs-lookup"><span data-stu-id="06b63-109">Requirements</span></span>  

 <span data-ttu-id="06b63-110">**Заголовок:** Корсим. idl, Корсим. h</span><span class="sxs-lookup"><span data-stu-id="06b63-110">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="06b63-111">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="06b63-111">See also</span></span>

- [<span data-ttu-id="06b63-112">Интерфейс ISymUnmanagedScope</span><span class="sxs-lookup"><span data-stu-id="06b63-112">ISymUnmanagedScope Interface</span></span>](isymunmanagedscope-interface.md)
