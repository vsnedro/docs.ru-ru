---
title: Метод ISymUnmanagedWriter::SetMethodSourceRange
ms.date: 03/30/2017
api_name:
- ISymUnmanagedWriter.SetMethodSourceRange
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedWriter::SetMethodSourceRange
helpviewer_keywords:
- SetMethodSourceRange method [.NET Framework debugging]
- ISymUnmanagedWriter::SetMethodSourceRange method [.NET Framework debugging]
ms.assetid: c698b86e-ace7-4b21-9549-f52d6a034959
topic_type:
- apiref
ms.openlocfilehash: 4ba3f31ae6d6b67d7beaa2f709bf6174b721136d
ms.sourcegitcommit: 27db07ffb26f76912feefba7b884313547410db5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/19/2020
ms.locfileid: "83609525"
---
# <a name="isymunmanagedwritersetmethodsourcerange-method"></a><span data-ttu-id="bfc25-102">Метод ISymUnmanagedWriter::SetMethodSourceRange</span><span class="sxs-lookup"><span data-stu-id="bfc25-102">ISymUnmanagedWriter::SetMethodSourceRange Method</span></span>
<span data-ttu-id="bfc25-103">Указывает истинные начало и конец метода в исходном файле.</span><span class="sxs-lookup"><span data-stu-id="bfc25-103">Specifies the true start and end of a method within a source file.</span></span> <span data-ttu-id="bfc25-104">Этот метод используется для указания экстента метода независимо от точек следования, которые существуют в методе.</span><span class="sxs-lookup"><span data-stu-id="bfc25-104">Use this method to specify the extent of a method independently of the sequence points that exist within the method.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="bfc25-105">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="bfc25-105">Syntax</span></span>  
  
```cpp  
HRESULT SetMethodSourceRange(  
    [in] ISymUnmanagedDocumentWriter  *startDoc,  
    [in] ULONG32                      startLine,  
    [in] ULONG32                      startColumn,  
    [in] ISymUnmanagedDocumentWriter  *endDoc,  
    [in] ULONG32                      endLine,  
    [in] ULONG32                      endColumn);  
```  
  
## <a name="parameters"></a><span data-ttu-id="bfc25-106">Параметры</span><span class="sxs-lookup"><span data-stu-id="bfc25-106">Parameters</span></span>  
 `startDoc`  
 <span data-ttu-id="bfc25-107">окне Указатель на документ, содержащий начальную точку.</span><span class="sxs-lookup"><span data-stu-id="bfc25-107">[in] A pointer to the document containing the starting position.</span></span>  
  
 `startLine`  
 <span data-ttu-id="bfc25-108">окне Номер начальной строки.</span><span class="sxs-lookup"><span data-stu-id="bfc25-108">[in] The starting line number.</span></span>  
  
 `startColumn`  
 <span data-ttu-id="bfc25-109">окне Начальный столбец.</span><span class="sxs-lookup"><span data-stu-id="bfc25-109">[in] The starting column.</span></span>  
  
 `endDoc`  
 <span data-ttu-id="bfc25-110">окне Указатель на документ, содержащий конечную точку.</span><span class="sxs-lookup"><span data-stu-id="bfc25-110">[in] A pointer to the document containing the ending position.</span></span>  
  
 `endLine`  
 <span data-ttu-id="bfc25-111">окне Номер конечной строки.</span><span class="sxs-lookup"><span data-stu-id="bfc25-111">[in] The ending line number.</span></span>  
  
 `endColumn`  
 <span data-ttu-id="bfc25-112">окне Номер конечного столбца.</span><span class="sxs-lookup"><span data-stu-id="bfc25-112">[in] The ending column number.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="bfc25-113">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="bfc25-113">Return Value</span></span>  
 <span data-ttu-id="bfc25-114">S_OK, если метод выполнен. в противном случае E_FAIL или другой код ошибки.</span><span class="sxs-lookup"><span data-stu-id="bfc25-114">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="bfc25-115">Требования</span><span class="sxs-lookup"><span data-stu-id="bfc25-115">Requirements</span></span>  
 <span data-ttu-id="bfc25-116">**Заголовок:** Корсим. idl, Корсим. h</span><span class="sxs-lookup"><span data-stu-id="bfc25-116">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bfc25-117">Дополнительно</span><span class="sxs-lookup"><span data-stu-id="bfc25-117">See also</span></span>

- [<span data-ttu-id="bfc25-118">Интерфейс ISymUnmanagedWriter</span><span class="sxs-lookup"><span data-stu-id="bfc25-118">ISymUnmanagedWriter Interface</span></span>](isymunmanagedwriter-interface.md)
