---
title: Метод ISymUnmanagedENCUpdate::GetLocalVariableCount
ms.date: 03/30/2017
api_name:
- ISymUnmanagedENCUpdate.GetLocalVariableCount
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedENCUpdate::GetLocalVariableCount
helpviewer_keywords:
- ISymUnmanagedENCUpdate::GetLocalVariableCount method [.NET Framework debugging]
- GetLocalVariableCount method [.NET Framework debugging]
ms.assetid: 9777d8bb-4abc-4be8-aa7c-34f853eceb9c
topic_type:
- apiref
ms.openlocfilehash: 19e07fb181f631335a0c56bd59b6fc8e14e2f36d
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/24/2020
ms.locfileid: "95726929"
---
# <a name="isymunmanagedencupdategetlocalvariablecount-method"></a><span data-ttu-id="e49fd-102">Метод ISymUnmanagedENCUpdate::GetLocalVariableCount</span><span class="sxs-lookup"><span data-stu-id="e49fd-102">ISymUnmanagedENCUpdate::GetLocalVariableCount Method</span></span>

<span data-ttu-id="e49fd-103">Возвращает число локальных переменных.</span><span class="sxs-lookup"><span data-stu-id="e49fd-103">Gets the number of local variables.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e49fd-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="e49fd-104">Syntax</span></span>  
  
```cpp  
HRESULT GetLocalVariableCount(  
    [in]  mdMethodDef  mdMethodToken,  
    [out] ULONG        *pcLocals);  
```  
  
## <a name="parameters"></a><span data-ttu-id="e49fd-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="e49fd-105">Parameters</span></span>  

 `mdMethodToken`  
 <span data-ttu-id="e49fd-106">окне Маркер метаданных методов.</span><span class="sxs-lookup"><span data-stu-id="e49fd-106">[in] The metadata token of methods.</span></span>  
  
 `pcLocals`  
 <span data-ttu-id="e49fd-107">заполняет Указатель на объект `ULONG32` , который получает размер буфера (в символах), необходимого для хранения числа локальных переменных.</span><span class="sxs-lookup"><span data-stu-id="e49fd-107">[out] A pointer to a `ULONG32` that receives the size, in characters, of the buffer required to contain the number of local variables.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="e49fd-108">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="e49fd-108">Return Value</span></span>  

 <span data-ttu-id="e49fd-109">S_OK, если метод выполнен. в противном случае E_FAIL или другой код ошибки.</span><span class="sxs-lookup"><span data-stu-id="e49fd-109">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="e49fd-110">Требования</span><span class="sxs-lookup"><span data-stu-id="e49fd-110">Requirements</span></span>  

 <span data-ttu-id="e49fd-111">**Заголовок:** Корсим. idl, Корсим. h</span><span class="sxs-lookup"><span data-stu-id="e49fd-111">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e49fd-112">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="e49fd-112">See also</span></span>

- [<span data-ttu-id="e49fd-113">Интерфейс ISymUnmanagedENCUpdate</span><span class="sxs-lookup"><span data-stu-id="e49fd-113">ISymUnmanagedENCUpdate Interface</span></span>](isymunmanagedencupdate-interface.md)
