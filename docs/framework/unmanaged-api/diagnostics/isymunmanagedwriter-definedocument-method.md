---
title: Метод ISymUnmanagedWriter::DefineDocument
ms.date: 03/30/2017
api_name:
- ISymUnmanagedWriter.DefineDocument
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedWriter::DefineDocument
helpviewer_keywords:
- ISymUnmanagedWriter::DefineDocument method [.NET Framework debugging]
- DefineDocument method [.NET Framework debugging]
ms.assetid: c3bf15b0-3250-4bbe-b9b5-c5d695289b6f
topic_type:
- apiref
ms.openlocfilehash: fdcfb0c4f9c21eb516f4196d0c8f682669468219
ms.sourcegitcommit: 27db07ffb26f76912feefba7b884313547410db5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/19/2020
ms.locfileid: "83615232"
---
# <a name="isymunmanagedwriterdefinedocument-method"></a><span data-ttu-id="f7d97-102">Метод ISymUnmanagedWriter::DefineDocument</span><span class="sxs-lookup"><span data-stu-id="f7d97-102">ISymUnmanagedWriter::DefineDocument Method</span></span>
<span data-ttu-id="f7d97-103">Определяет исходный документ.</span><span class="sxs-lookup"><span data-stu-id="f7d97-103">Defines a source document.</span></span> <span data-ttu-id="f7d97-104">Идентификаторы GUID предоставляются для известных языков, поставщиков и типов документов.</span><span class="sxs-lookup"><span data-stu-id="f7d97-104">GUIDs are provided for known languages, vendors, and document types.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f7d97-105">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="f7d97-105">Syntax</span></span>  
  
```cpp  
HRESULT DefineDocument(  
    [in]  const WCHAR  *url,  
    [in]  const GUID   *language,  
    [in]  const GUID   *languageVendor,  
    [in]  const GUID   *documentType,  
    [out, retval] ISymUnmanagedDocumentWriter**  pRetVal);  
```  
  
## <a name="parameters"></a><span data-ttu-id="f7d97-106">Параметры</span><span class="sxs-lookup"><span data-stu-id="f7d97-106">Parameters</span></span>  
 `url`  
 <span data-ttu-id="f7d97-107">окне Указатель на объект `WCHAR` , который определяет универсальный указатель ресурсов (URL-адрес), определяющий документ.</span><span class="sxs-lookup"><span data-stu-id="f7d97-107">[in] A pointer to a `WCHAR` that defines the uniform resource locator (URL) that identifies the document.</span></span>  
  
 `language`  
 <span data-ttu-id="f7d97-108">окне Указатель на идентификатор GUID, определяющий язык документа.</span><span class="sxs-lookup"><span data-stu-id="f7d97-108">[in] A pointer to a GUID that defines the document language.</span></span>  
  
 `languageVendor`  
 <span data-ttu-id="f7d97-109">окне Указатель на идентификатор GUID, определяющий удостоверение поставщика для языка документа.</span><span class="sxs-lookup"><span data-stu-id="f7d97-109">[in] A pointer to a GUID that defines the identity of the vendor for the document language.</span></span>  
  
 `documentType`  
 <span data-ttu-id="f7d97-110">окне Указатель на идентификатор GUID, определяющий тип документа.</span><span class="sxs-lookup"><span data-stu-id="f7d97-110">[in] A pointer to a GUID that defines the type of the document.</span></span>  
  
 `pRetVal`  
 <span data-ttu-id="f7d97-111">заполняет Указатель на возвращаемый интерфейс [ISymUnmanagedWriter](isymunmanagedwriter-interface.md) .</span><span class="sxs-lookup"><span data-stu-id="f7d97-111">[out] A pointer to the returned [ISymUnmanagedWriter](isymunmanagedwriter-interface.md) interface.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="f7d97-112">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="f7d97-112">Return Value</span></span>  
 <span data-ttu-id="f7d97-113">S_OK, если метод выполнен. в противном случае E_FAIL или другой код ошибки.</span><span class="sxs-lookup"><span data-stu-id="f7d97-113">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="f7d97-114">Требования</span><span class="sxs-lookup"><span data-stu-id="f7d97-114">Requirements</span></span>  
 <span data-ttu-id="f7d97-115">**Заголовок:** Корсим. idl, Корсим. h</span><span class="sxs-lookup"><span data-stu-id="f7d97-115">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f7d97-116">Дополнительно</span><span class="sxs-lookup"><span data-stu-id="f7d97-116">See also</span></span>

- [<span data-ttu-id="f7d97-117">Интерфейс ISymUnmanagedWriter</span><span class="sxs-lookup"><span data-stu-id="f7d97-117">ISymUnmanagedWriter Interface</span></span>](isymunmanagedwriter-interface.md)
