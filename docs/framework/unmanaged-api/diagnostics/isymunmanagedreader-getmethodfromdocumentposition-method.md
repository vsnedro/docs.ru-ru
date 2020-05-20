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
ms.openlocfilehash: 8015056b110fe8a5b5122b1bc81143980b780047
ms.sourcegitcommit: 27db07ffb26f76912feefba7b884313547410db5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/19/2020
ms.locfileid: "83614985"
---
# <a name="isymunmanagedreadergetmethodfromdocumentposition-method"></a><span data-ttu-id="093bc-102">Метод ISymUnmanagedReader::GetMethodFromDocumentPosition</span><span class="sxs-lookup"><span data-stu-id="093bc-102">ISymUnmanagedReader::GetMethodFromDocumentPosition Method</span></span>
<span data-ttu-id="093bc-103">Возвращает метод, содержащий точку останова в заданной позиции в документе.</span><span class="sxs-lookup"><span data-stu-id="093bc-103">Returns the method that contains the breakpoint at the given position in a document.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="093bc-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="093bc-104">Syntax</span></span>  
  
```cpp  
HRESULT GetMethodFromDocumentPosition (  
    [in]  ISymUnmanagedDocument*  document,  
    [in]  ULONG32  line,  
    [in]  ULONG32  column,  
    [out, retval] ISymUnmanagedMethod**  pRetVal);  
```  
  
## <a name="parameters"></a><span data-ttu-id="093bc-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="093bc-105">Parameters</span></span>  
 `document`  
 <span data-ttu-id="093bc-106">окне Указанный документ.</span><span class="sxs-lookup"><span data-stu-id="093bc-106">[in] The specified document.</span></span>  
  
 `line`  
 <span data-ttu-id="093bc-107">окне Строка указанного документа.</span><span class="sxs-lookup"><span data-stu-id="093bc-107">[in] The line of the specified document.</span></span>  
  
 `column`  
 <span data-ttu-id="093bc-108">окне Столбец указанного документа.</span><span class="sxs-lookup"><span data-stu-id="093bc-108">[in] The column of the specified document.</span></span>  
  
 `pRetVal`  
 <span data-ttu-id="093bc-109">заполняет Указатель на адрес объекта [интерфейса ISymUnmanagedMethod](isymunmanagedmethod-interface.md) , который представляет метод, содержащий точку останова.</span><span class="sxs-lookup"><span data-stu-id="093bc-109">[out] A pointer to the address of a [ISymUnmanagedMethod Interface](isymunmanagedmethod-interface.md) object that represents the method containing the breakpoint.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="093bc-110">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="093bc-110">Return Value</span></span>  
 <span data-ttu-id="093bc-111">S_OK, если метод выполнен. в противном случае E_FAIL или другой код ошибки.</span><span class="sxs-lookup"><span data-stu-id="093bc-111">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="093bc-112">Требования</span><span class="sxs-lookup"><span data-stu-id="093bc-112">Requirements</span></span>  
 <span data-ttu-id="093bc-113">**Заголовок:** Корсим. idl, Корсим. h</span><span class="sxs-lookup"><span data-stu-id="093bc-113">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="093bc-114">Дополнительно</span><span class="sxs-lookup"><span data-stu-id="093bc-114">See also</span></span>

- [<span data-ttu-id="093bc-115">Интерфейс ISymUnmanagedReader</span><span class="sxs-lookup"><span data-stu-id="093bc-115">ISymUnmanagedReader Interface</span></span>](isymunmanagedreader-interface.md)
