---
title: Метод ISymUnmanagedReader::GetDocument
ms.date: 03/30/2017
api_name:
- ISymUnmanagedReader.GetDocument
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedReader::GetDocument
helpviewer_keywords:
- ISymUnmanagedReader::GetDocument method [.NET Framework debugging]
- GetDocument method [.NET Framework debugging]
ms.assetid: bb203853-6a6d-4027-b9e9-603a7f28b9d3
topic_type:
- apiref
ms.openlocfilehash: 950fb3b9c51ae2c9470b5aadd31c877d7aa6b6f6
ms.sourcegitcommit: 27db07ffb26f76912feefba7b884313547410db5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/19/2020
ms.locfileid: "83615063"
---
# <a name="isymunmanagedreadergetdocument-method"></a><span data-ttu-id="dad71-102">Метод ISymUnmanagedReader::GetDocument</span><span class="sxs-lookup"><span data-stu-id="dad71-102">ISymUnmanagedReader::GetDocument Method</span></span>
<span data-ttu-id="dad71-103">Находит документ.</span><span class="sxs-lookup"><span data-stu-id="dad71-103">Finds a document.</span></span> <span data-ttu-id="dad71-104">Язык документа, поставщик и тип являются необязательными.</span><span class="sxs-lookup"><span data-stu-id="dad71-104">The document language, vendor, and type are optional.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="dad71-105">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="dad71-105">Syntax</span></span>  
  
```cpp  
HRESULT GetDocument (  
    [in]  WCHAR  *url,  
    [in]  GUID   language,  
    [in]  GUID   languageVendor,  
    [in]  GUID   documentType,  
    [out, retval] ISymUnmanagedDocument** pRetVal);  
```  
  
## <a name="parameters"></a><span data-ttu-id="dad71-106">Параметры</span><span class="sxs-lookup"><span data-stu-id="dad71-106">Parameters</span></span>  
 `url`  
 <span data-ttu-id="dad71-107">окне URL-адрес, определяющий документ.</span><span class="sxs-lookup"><span data-stu-id="dad71-107">[in] The URL that identifies the document.</span></span>  
  
 `language`  
 <span data-ttu-id="dad71-108">окне Язык документа.</span><span class="sxs-lookup"><span data-stu-id="dad71-108">[in] The document language.</span></span> <span data-ttu-id="dad71-109">Этот параметр необязателен.</span><span class="sxs-lookup"><span data-stu-id="dad71-109">This parameter is optional.</span></span>  
  
 `languageVendor`  
 <span data-ttu-id="dad71-110">окне Удостоверение поставщика для языка документа.</span><span class="sxs-lookup"><span data-stu-id="dad71-110">[in] The identity of the vendor for the document language.</span></span> <span data-ttu-id="dad71-111">Этот параметр необязателен.</span><span class="sxs-lookup"><span data-stu-id="dad71-111">This parameter is optional.</span></span>  
  
 `documentType`  
 <span data-ttu-id="dad71-112">окне Тип документа.</span><span class="sxs-lookup"><span data-stu-id="dad71-112">[in] The type of the document.</span></span> <span data-ttu-id="dad71-113">Этот параметр необязателен.</span><span class="sxs-lookup"><span data-stu-id="dad71-113">This parameter is optional.</span></span>  
  
 `pRetVal`  
 <span data-ttu-id="dad71-114">заполняет Указатель на возвращаемый интерфейс.</span><span class="sxs-lookup"><span data-stu-id="dad71-114">[out] A pointer to the returned interface.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="dad71-115">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="dad71-115">Return Value</span></span>  
 <span data-ttu-id="dad71-116">S_OK, если метод выполнен. в противном случае E_FAIL или другой код ошибки.</span><span class="sxs-lookup"><span data-stu-id="dad71-116">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="dad71-117">Требования</span><span class="sxs-lookup"><span data-stu-id="dad71-117">Requirements</span></span>  
 <span data-ttu-id="dad71-118">**Заголовок:** Корсим. idl, Корсим. h</span><span class="sxs-lookup"><span data-stu-id="dad71-118">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="dad71-119">Дополнительно</span><span class="sxs-lookup"><span data-stu-id="dad71-119">See also</span></span>

- [<span data-ttu-id="dad71-120">Интерфейс ISymUnmanagedReader</span><span class="sxs-lookup"><span data-stu-id="dad71-120">ISymUnmanagedReader Interface</span></span>](isymunmanagedreader-interface.md)
