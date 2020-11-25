---
title: Метод ISymUnmanagedReader::GetDocumentVersion
ms.date: 03/30/2017
api_name:
- ISymUnmanagedReader.GetDocumentVersion
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedReader::GetDocumentVersion
helpviewer_keywords:
- GetDocumentVersion method [.NET Framework debugging]
- ISymUnmanagedReader::GetDocumentVersion method [.NET Framework debugging]
ms.assetid: a51f1f64-e084-44c5-830c-2222da5a6bbf
topic_type:
- apiref
ms.openlocfilehash: fc38c167b47ea72c7bc7ad81074f9cb1a0d217d8
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/24/2020
ms.locfileid: "95707572"
---
# <a name="isymunmanagedreadergetdocumentversion-method"></a><span data-ttu-id="4dda5-102">Метод ISymUnmanagedReader::GetDocumentVersion</span><span class="sxs-lookup"><span data-stu-id="4dda5-102">ISymUnmanagedReader::GetDocumentVersion Method</span></span>

<span data-ttu-id="4dda5-103">Возвращает указанную версию указанного документа.</span><span class="sxs-lookup"><span data-stu-id="4dda5-103">Gets the specified version of the specified document.</span></span> <span data-ttu-id="4dda5-104">Версия документа начинается с 1 и увеличивается каждый раз при обновлении документа с помощью метода [UpdateSymbolStore](isymunmanagedreader-updatesymbolstore-method.md) .</span><span class="sxs-lookup"><span data-stu-id="4dda5-104">The document version starts at 1 and is incremented each time the document is updated using the [UpdateSymbolStore](isymunmanagedreader-updatesymbolstore-method.md) method.</span></span> <span data-ttu-id="4dda5-105">Если `pbCurrent` параметр имеет значение `true` , это последняя версия документа.</span><span class="sxs-lookup"><span data-stu-id="4dda5-105">If the `pbCurrent` parameter is `true`, this is the latest version of the document.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4dda5-106">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="4dda5-106">Syntax</span></span>  
  
```cpp  
HRESULT GetDocumentVersion (  
    [in]  ISymUnmanagedDocument *pDoc,  
    [out] int* version,  
    [out] BOOL* pbCurrent);  
```  
  
## <a name="parameters"></a><span data-ttu-id="4dda5-107">Параметры</span><span class="sxs-lookup"><span data-stu-id="4dda5-107">Parameters</span></span>  

 `pDoc`  
 <span data-ttu-id="4dda5-108">окне Указанный документ.</span><span class="sxs-lookup"><span data-stu-id="4dda5-108">[in] The specified document.</span></span>  
  
 `version`  
 <span data-ttu-id="4dda5-109">заполняет Указатель на переменную, которая получает версию указанного документа.</span><span class="sxs-lookup"><span data-stu-id="4dda5-109">[out] A pointer to a variable that receives the version of the specified document.</span></span>  
  
 `pbCurrent`  
 <span data-ttu-id="4dda5-110">заполняет Указатель на переменную, которая получает, `true` если это последняя версия документа, или `false` если это не последняя версия.</span><span class="sxs-lookup"><span data-stu-id="4dda5-110">[out] A pointer to a variable that receives `true` if this is the latest version of the document, or `false` if it isn't the latest version.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="4dda5-111">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="4dda5-111">Return Value</span></span>  

 <span data-ttu-id="4dda5-112">S_OK, если метод выполнен. в противном случае E_FAIL или другой код ошибки.</span><span class="sxs-lookup"><span data-stu-id="4dda5-112">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="4dda5-113">Требования</span><span class="sxs-lookup"><span data-stu-id="4dda5-113">Requirements</span></span>  

 <span data-ttu-id="4dda5-114">**Заголовок:** Корсим. idl, Корсим. h</span><span class="sxs-lookup"><span data-stu-id="4dda5-114">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4dda5-115">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="4dda5-115">See also</span></span>

- [<span data-ttu-id="4dda5-116">Интерфейс ISymUnmanagedReader</span><span class="sxs-lookup"><span data-stu-id="4dda5-116">ISymUnmanagedReader Interface</span></span>](isymunmanagedreader-interface.md)
