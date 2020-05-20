---
title: Метод ISymUnmanagedWriter::CloseMethod
ms.date: 03/30/2017
api_name:
- ISymUnmanagedWriter.CloseMethod
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedWriter::CloseMethod
helpviewer_keywords:
- ISymUnmanagedWriter::CloseMethod method [.NET Framework debugging]
- CloseMethod method [.NET Framework debugging]
ms.assetid: b8025e04-f0e5-40c8-849c-8cd51323420e
topic_type:
- apiref
ms.openlocfilehash: fdf24bb8533da7914128f9477987c427442383bb
ms.sourcegitcommit: 27db07ffb26f76912feefba7b884313547410db5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/19/2020
ms.locfileid: "83610123"
---
# <a name="isymunmanagedwriterclosemethod-method"></a><span data-ttu-id="604f2-102">Метод ISymUnmanagedWriter::CloseMethod</span><span class="sxs-lookup"><span data-stu-id="604f2-102">ISymUnmanagedWriter::CloseMethod Method</span></span>
<span data-ttu-id="604f2-103">Закрывает текущий метод.</span><span class="sxs-lookup"><span data-stu-id="604f2-103">Closes the current method.</span></span> <span data-ttu-id="604f2-104">После закрытия метода в нем нельзя определять символы.</span><span class="sxs-lookup"><span data-stu-id="604f2-104">Once a method is closed, no more symbols can be defined within it.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="604f2-105">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="604f2-105">Syntax</span></span>  
  
```cpp  
HRESULT CloseMethod();  
```  
  
## <a name="return-value"></a><span data-ttu-id="604f2-106">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="604f2-106">Return Value</span></span>  
 <span data-ttu-id="604f2-107">S_OK, если метод выполнен. в противном случае E_FAIL или другой код ошибки.</span><span class="sxs-lookup"><span data-stu-id="604f2-107">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="604f2-108">Требования</span><span class="sxs-lookup"><span data-stu-id="604f2-108">Requirements</span></span>  
 <span data-ttu-id="604f2-109">**Заголовок:** Корсим. idl, Корсим. h</span><span class="sxs-lookup"><span data-stu-id="604f2-109">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="604f2-110">Дополнительно</span><span class="sxs-lookup"><span data-stu-id="604f2-110">See also</span></span>

- [<span data-ttu-id="604f2-111">Интерфейс ISymUnmanagedWriter</span><span class="sxs-lookup"><span data-stu-id="604f2-111">ISymUnmanagedWriter Interface</span></span>](isymunmanagedwriter-interface.md)
- [<span data-ttu-id="604f2-112">Метод OpenMethod</span><span class="sxs-lookup"><span data-stu-id="604f2-112">OpenMethod Method</span></span>](isymunmanagedwriter-openmethod-method.md)
