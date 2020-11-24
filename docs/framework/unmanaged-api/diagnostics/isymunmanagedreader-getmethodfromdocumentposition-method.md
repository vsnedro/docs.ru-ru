---
title: Метод ISymUnmanagedReader::GetMethodFromDocumentPosition
ms.date: 03/30/2017
api_name:
- ISymUnmanagedReader.GetMethodFromDocumentPosition
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedReader::GetMethodFromDocumentPosition
helpviewer_keywords:
- GetMethodFromDocumentPosition method [.NET Framework debugging]
- ISymUnmanagedReader::GetMethodFromDocumentPosition method [.NET Framework debugging]
ms.assetid: 55773dbc-9053-46e3-8a3c-86caa9d91fb4
topic_type:
- apiref
ms.openlocfilehash: 417644e5d0c7af802d5266bd1825efa83c181597
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/24/2020
ms.locfileid: "95689606"
---
# <a name="isymunmanagedreadergetmethodfromdocumentposition-method"></a><span data-ttu-id="24e7d-102">Метод ISymUnmanagedReader::GetMethodFromDocumentPosition</span><span class="sxs-lookup"><span data-stu-id="24e7d-102">ISymUnmanagedReader::GetMethodFromDocumentPosition Method</span></span>

<span data-ttu-id="24e7d-103">Возвращает метод, содержащий точку останова в заданной позиции в документе.</span><span class="sxs-lookup"><span data-stu-id="24e7d-103">Returns the method that contains the breakpoint at the given position in a document.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="24e7d-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="24e7d-104">Syntax</span></span>  
  
```cpp  
HRESULT GetMethodFromDocumentPosition (  
    [in]  ISymUnmanagedDocument*  document,  
    [in]  ULONG32  line,  
    [in]  ULONG32  column,  
    [out, retval] ISymUnmanagedMethod**  pRetVal);  
```  
  
## <a name="parameters"></a><span data-ttu-id="24e7d-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="24e7d-105">Parameters</span></span>  

 `document`  
 <span data-ttu-id="24e7d-106">окне Указанный документ.</span><span class="sxs-lookup"><span data-stu-id="24e7d-106">[in] The specified document.</span></span>  
  
 `line`  
 <span data-ttu-id="24e7d-107">окне Строка указанного документа.</span><span class="sxs-lookup"><span data-stu-id="24e7d-107">[in] The line of the specified document.</span></span>  
  
 `column`  
 <span data-ttu-id="24e7d-108">окне Столбец указанного документа.</span><span class="sxs-lookup"><span data-stu-id="24e7d-108">[in] The column of the specified document.</span></span>  
  
 `pRetVal`  
 <span data-ttu-id="24e7d-109">заполняет Указатель на адрес объекта [интерфейса ISymUnmanagedMethod](isymunmanagedmethod-interface.md) , который представляет метод, содержащий точку останова.</span><span class="sxs-lookup"><span data-stu-id="24e7d-109">[out] A pointer to the address of a [ISymUnmanagedMethod Interface](isymunmanagedmethod-interface.md) object that represents the method containing the breakpoint.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="24e7d-110">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="24e7d-110">Return Value</span></span>  

 <span data-ttu-id="24e7d-111">S_OK, если метод выполнен. в противном случае E_FAIL или другой код ошибки.</span><span class="sxs-lookup"><span data-stu-id="24e7d-111">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="24e7d-112">Требования</span><span class="sxs-lookup"><span data-stu-id="24e7d-112">Requirements</span></span>  

 <span data-ttu-id="24e7d-113">**Заголовок:** Корсим. idl, Корсим. h</span><span class="sxs-lookup"><span data-stu-id="24e7d-113">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="24e7d-114">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="24e7d-114">See also</span></span>

- [<span data-ttu-id="24e7d-115">Интерфейс ISymUnmanagedReader</span><span class="sxs-lookup"><span data-stu-id="24e7d-115">ISymUnmanagedReader Interface</span></span>](isymunmanagedreader-interface.md)
