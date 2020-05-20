---
title: Метод ISymUnmanagedENCUpdate::InitializeForEnc
ms.date: 03/30/2017
api_name:
- ISymUnmanagedENCUpdate.InitializeForEnc
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedENCUpdate::InitializeForEnc
helpviewer_keywords:
- ISymUnmanagedENCUpdate::InitializeForEnc method [.NET Framework debugging]
- InitializeForEnc method [.NET Framework debugging]
ms.assetid: 796b2154-b53c-4d07-9e67-80fd6064725a
topic_type:
- apiref
ms.openlocfilehash: f612e38398f8c1320ba87722498400d70ec8bff0
ms.sourcegitcommit: 27db07ffb26f76912feefba7b884313547410db5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/19/2020
ms.locfileid: "83614543"
---
# <a name="isymunmanagedencupdateinitializeforenc-method"></a><span data-ttu-id="f22d3-102">Метод ISymUnmanagedENCUpdate::InitializeForEnc</span><span class="sxs-lookup"><span data-stu-id="f22d3-102">ISymUnmanagedENCUpdate::InitializeForEnc Method</span></span>
<span data-ttu-id="f22d3-103">Позволяет вычислять границы методов перед первым вызовом метода [ISymUnmanagedENCUpdate:: UpdateSymbolStore2](isymunmanagedencupdate-updatesymbolstore2-method.md) .</span><span class="sxs-lookup"><span data-stu-id="f22d3-103">Allows method boundaries to be computed before the first call to the [ISymUnmanagedENCUpdate::UpdateSymbolStore2](isymunmanagedencupdate-updatesymbolstore2-method.md) method.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f22d3-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="f22d3-104">Syntax</span></span>  
  
```cpp  
HRESULT InitializeForEnc();  
```  
  
## <a name="return-value"></a><span data-ttu-id="f22d3-105">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="f22d3-105">Return Value</span></span>  
 <span data-ttu-id="f22d3-106">S_OK, если метод выполнен. в противном случае E_FAIL или другой код ошибки.</span><span class="sxs-lookup"><span data-stu-id="f22d3-106">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="f22d3-107">Требования</span><span class="sxs-lookup"><span data-stu-id="f22d3-107">Requirements</span></span>  
 <span data-ttu-id="f22d3-108">**Заголовок:** Корсим. idl, Корсим. h</span><span class="sxs-lookup"><span data-stu-id="f22d3-108">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f22d3-109">Дополнительно</span><span class="sxs-lookup"><span data-stu-id="f22d3-109">See also</span></span>

- [<span data-ttu-id="f22d3-110">Интерфейс ISymUnmanagedENCUpdate</span><span class="sxs-lookup"><span data-stu-id="f22d3-110">ISymUnmanagedENCUpdate Interface</span></span>](isymunmanagedencupdate-interface.md)
