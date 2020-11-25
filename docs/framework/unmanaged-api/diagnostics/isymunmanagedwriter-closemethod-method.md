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
ms.openlocfilehash: fcf250f10baf4c65cd1c8c918655e4b9f4f5cc4b
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/24/2020
ms.locfileid: "95731739"
---
# <a name="isymunmanagedwriterclosemethod-method"></a><span data-ttu-id="affd4-102">Метод ISymUnmanagedWriter::CloseMethod</span><span class="sxs-lookup"><span data-stu-id="affd4-102">ISymUnmanagedWriter::CloseMethod Method</span></span>

<span data-ttu-id="affd4-103">Закрывает текущий метод.</span><span class="sxs-lookup"><span data-stu-id="affd4-103">Closes the current method.</span></span> <span data-ttu-id="affd4-104">После закрытия метода в нем нельзя определять символы.</span><span class="sxs-lookup"><span data-stu-id="affd4-104">Once a method is closed, no more symbols can be defined within it.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="affd4-105">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="affd4-105">Syntax</span></span>  
  
```cpp  
HRESULT CloseMethod();  
```  
  
## <a name="return-value"></a><span data-ttu-id="affd4-106">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="affd4-106">Return Value</span></span>  

 <span data-ttu-id="affd4-107">S_OK, если метод выполнен. в противном случае E_FAIL или другой код ошибки.</span><span class="sxs-lookup"><span data-stu-id="affd4-107">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="affd4-108">Требования</span><span class="sxs-lookup"><span data-stu-id="affd4-108">Requirements</span></span>  

 <span data-ttu-id="affd4-109">**Заголовок:** Корсим. idl, Корсим. h</span><span class="sxs-lookup"><span data-stu-id="affd4-109">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="affd4-110">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="affd4-110">See also</span></span>

- [<span data-ttu-id="affd4-111">Интерфейс ISymUnmanagedWriter</span><span class="sxs-lookup"><span data-stu-id="affd4-111">ISymUnmanagedWriter Interface</span></span>](isymunmanagedwriter-interface.md)
- [<span data-ttu-id="affd4-112">Метод OpenMethod</span><span class="sxs-lookup"><span data-stu-id="affd4-112">OpenMethod Method</span></span>](isymunmanagedwriter-openmethod-method.md)
