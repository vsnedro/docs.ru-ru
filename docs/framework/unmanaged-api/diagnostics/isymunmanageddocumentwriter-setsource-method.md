---
title: Метод ISymUnmanagedDocumentWriter::SetSource
ms.date: 03/30/2017
api_name:
- ISymUnmanagedDocumentWriter.SetSource
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedDocumentWriter::SetSource
helpviewer_keywords:
- ISymUnmanagedDocumentWriter::SetSource method [.NET Framework debugging]
- SetSource method [.NET Framework debugging]
ms.assetid: ea5b9d9f-ff06-4bd3-8de5-6435343aba59
topic_type:
- apiref
ms.openlocfilehash: 31475b08b569b925aab9cab869545f0912c4ecf8
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/24/2020
ms.locfileid: "95691595"
---
# <a name="isymunmanageddocumentwritersetsource-method"></a><span data-ttu-id="3803c-102">Метод ISymUnmanagedDocumentWriter::SetSource</span><span class="sxs-lookup"><span data-stu-id="3803c-102">ISymUnmanagedDocumentWriter::SetSource Method</span></span>

<span data-ttu-id="3803c-103">Задает внедренный источник для записываемого документа.</span><span class="sxs-lookup"><span data-stu-id="3803c-103">Sets embedded source for a document that is being written.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3803c-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="3803c-104">Syntax</span></span>  
  
```cpp  
HRESULT SetSource(  
    [in]  ULONG32  sourceSize,  
    [in, size_is(sourceSize)] BYTE  source[]);  
```  
  
## <a name="parameters"></a><span data-ttu-id="3803c-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="3803c-105">Parameters</span></span>  

 `sourceSize`  
 <span data-ttu-id="3803c-106">окне Значение типа `ULONG32` , содержащее размер `source` буфера.</span><span class="sxs-lookup"><span data-stu-id="3803c-106">[in] A `ULONG32` that contains the size of the `source` buffer.</span></span>  
  
 `source`  
 <span data-ttu-id="3803c-107">окне Буфер, в котором хранится внедренный источник.</span><span class="sxs-lookup"><span data-stu-id="3803c-107">[in] The buffer that stores the embedded source.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="3803c-108">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="3803c-108">Return Value</span></span>  

 <span data-ttu-id="3803c-109">S_OK, если метод выполнен. в противном случае E_FAIL или другой код ошибки.</span><span class="sxs-lookup"><span data-stu-id="3803c-109">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="3803c-110">Требования</span><span class="sxs-lookup"><span data-stu-id="3803c-110">Requirements</span></span>  

 <span data-ttu-id="3803c-111">**Заголовок:** Корсим. idl, Корсим. h</span><span class="sxs-lookup"><span data-stu-id="3803c-111">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3803c-112">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="3803c-112">See also</span></span>

- [<span data-ttu-id="3803c-113">Интерфейс ISymUnmanagedDocumentWriter</span><span class="sxs-lookup"><span data-stu-id="3803c-113">ISymUnmanagedDocumentWriter Interface</span></span>](isymunmanageddocumentwriter-interface.md)
