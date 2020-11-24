---
title: Интерфейс ISymUnmanagedDocument
ms.date: 03/30/2017
api_name:
- ISymUnmanagedDocument
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedDocument
helpviewer_keywords:
- ISymUnmanagedDocument interface [.NET Framework debugging]
ms.assetid: 5c26b366-6e81-467c-9dd0-02dd26fee0a3
topic_type:
- apiref
ms.openlocfilehash: 83c683e1f60f13f7cee4ddc6fe5af5a94e36eb93
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/24/2020
ms.locfileid: "95692180"
---
# <a name="isymunmanageddocument-interface"></a><span data-ttu-id="5fa8b-102">Интерфейс ISymUnmanagedDocument</span><span class="sxs-lookup"><span data-stu-id="5fa8b-102">ISymUnmanagedDocument Interface</span></span>

<span data-ttu-id="5fa8b-103">Представляет документ, на который ссылается хранилище символов.</span><span class="sxs-lookup"><span data-stu-id="5fa8b-103">Represents a document referenced by a symbol store.</span></span> <span data-ttu-id="5fa8b-104">Документ определяется по универсальному указателю ресурсов (URL-адрес) и GUID типа документа.</span><span class="sxs-lookup"><span data-stu-id="5fa8b-104">A document is defined by a uniform resource locator (URL) and a document type GUID.</span></span> <span data-ttu-id="5fa8b-105">Документ можно разместить независимо от того, как он хранится, используя URL-адрес и GUID типа документа.</span><span class="sxs-lookup"><span data-stu-id="5fa8b-105">You can locate the document regardless of how it is stored by using the URL and document type GUID.</span></span> <span data-ttu-id="5fa8b-106">Вы можете сохранить источник документа в хранилище символов и получить его через этот интерфейс.</span><span class="sxs-lookup"><span data-stu-id="5fa8b-106">You can store the document source in the symbol store and retrieve it through this interface.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="5fa8b-107">Методы</span><span class="sxs-lookup"><span data-stu-id="5fa8b-107">Methods</span></span>  
  
|<span data-ttu-id="5fa8b-108">Метод</span><span class="sxs-lookup"><span data-stu-id="5fa8b-108">Method</span></span>|<span data-ttu-id="5fa8b-109">Описание</span><span class="sxs-lookup"><span data-stu-id="5fa8b-109">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="5fa8b-110">Метод FindClosestLine</span><span class="sxs-lookup"><span data-stu-id="5fa8b-110">FindClosestLine Method</span></span>](isymunmanageddocument-findclosestline-method.md)|<span data-ttu-id="5fa8b-111">Возвращает ближайшую строку, которая является точкой последовательности, с учетом строки в этом документе, которая может быть или не являться точкой последовательности.</span><span class="sxs-lookup"><span data-stu-id="5fa8b-111">Returns the closest line that is a sequence point, given a line in this document that may or may not be a sequence point.</span></span>|  
|[<span data-ttu-id="5fa8b-112">Метод GetCheckSum</span><span class="sxs-lookup"><span data-stu-id="5fa8b-112">GetCheckSum Method</span></span>](isymunmanageddocument-getchecksum-method.md)|<span data-ttu-id="5fa8b-113">Возвращает контрольную сумму.</span><span class="sxs-lookup"><span data-stu-id="5fa8b-113">Gets the checksum.</span></span>|  
|[<span data-ttu-id="5fa8b-114">Метод GetCheckSumAlgorithmId</span><span class="sxs-lookup"><span data-stu-id="5fa8b-114">GetCheckSumAlgorithmId Method</span></span>](isymunmanageddocument-getchecksumalgorithmid-method.md)|<span data-ttu-id="5fa8b-115">Возвращает идентификатор алгоритма контрольной суммы или возвращает идентификатор GUID всех нулей, если контрольная сумма отсутствует.</span><span class="sxs-lookup"><span data-stu-id="5fa8b-115">Gets the checksum algorithm identifier, or returns a GUID of all zeros if there is no checksum.</span></span>|  
|[<span data-ttu-id="5fa8b-116">Метод GetDocumentType</span><span class="sxs-lookup"><span data-stu-id="5fa8b-116">GetDocumentType Method</span></span>](isymunmanageddocument-getdocumenttype-method.md)|<span data-ttu-id="5fa8b-117">Возвращает тип документа этого документа.</span><span class="sxs-lookup"><span data-stu-id="5fa8b-117">Gets the document type of this document.</span></span>|  
|[<span data-ttu-id="5fa8b-118">Метод GetLanguage</span><span class="sxs-lookup"><span data-stu-id="5fa8b-118">GetLanguage Method</span></span>](isymunmanageddocument-getlanguage-method.md)|<span data-ttu-id="5fa8b-119">Возвращает идентификатор языка этого документа.</span><span class="sxs-lookup"><span data-stu-id="5fa8b-119">Gets the language identifier of this document.</span></span>|  
|[<span data-ttu-id="5fa8b-120">Метод GetLanguageVendor</span><span class="sxs-lookup"><span data-stu-id="5fa8b-120">GetLanguageVendor Method</span></span>](isymunmanageddocument-getlanguagevendor-method.md)|<span data-ttu-id="5fa8b-121">Получает поставщика языка этого документа.</span><span class="sxs-lookup"><span data-stu-id="5fa8b-121">Gets the language vendor of this document.</span></span>|  
|[<span data-ttu-id="5fa8b-122">Метод GetSourceLength</span><span class="sxs-lookup"><span data-stu-id="5fa8b-122">GetSourceLength Method</span></span>](isymunmanageddocument-getsourcelength-method.md)|<span data-ttu-id="5fa8b-123">Возвращает длину внедренного источника в байтах.</span><span class="sxs-lookup"><span data-stu-id="5fa8b-123">Gets the length, in bytes, of the embedded source.</span></span>|  
|[<span data-ttu-id="5fa8b-124">Метод GetSourceRange</span><span class="sxs-lookup"><span data-stu-id="5fa8b-124">GetSourceRange Method</span></span>](isymunmanageddocument-getsourcerange-method.md)|<span data-ttu-id="5fa8b-125">Возвращает указанный диапазон внедренного источника в заданный буфер.</span><span class="sxs-lookup"><span data-stu-id="5fa8b-125">Returns the specified range of the embedded source into the given buffer.</span></span>|  
|[<span data-ttu-id="5fa8b-126">Метод GetURL</span><span class="sxs-lookup"><span data-stu-id="5fa8b-126">GetURL Method</span></span>](isymunmanageddocument-geturl-method.md)|<span data-ttu-id="5fa8b-127">Возвращает URL-адрес для этого документа.</span><span class="sxs-lookup"><span data-stu-id="5fa8b-127">Returns the URL for this document.</span></span>|  
|[<span data-ttu-id="5fa8b-128">Метод HasEmbeddedSource</span><span class="sxs-lookup"><span data-stu-id="5fa8b-128">HasEmbeddedSource Method</span></span>](isymunmanageddocument-hasembeddedsource-method.md)|<span data-ttu-id="5fa8b-129">Возвращает `true` , если документ имеет исходный код, внедренный в отладочные символы; в противном случае возвращает `false` .</span><span class="sxs-lookup"><span data-stu-id="5fa8b-129">Returns `true` if the document has source embedded in the debugging symbols; otherwise, returns `false`.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="5fa8b-130">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="5fa8b-130">See also</span></span>

- [<span data-ttu-id="5fa8b-131">Интерфейсы хранилища символов диагностики</span><span class="sxs-lookup"><span data-stu-id="5fa8b-131">Diagnostics Symbol Store Interfaces</span></span>](diagnostics-symbol-store-interfaces.md)
