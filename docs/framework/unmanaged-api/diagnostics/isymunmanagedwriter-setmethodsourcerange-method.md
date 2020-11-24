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
ms.openlocfilehash: a918b5c2334683348adc6a7382527faedb52d7b6
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/24/2020
ms.locfileid: "95683541"
---
# <a name="isymunmanagedwritersetmethodsourcerange-method"></a><span data-ttu-id="67304-102">Метод ISymUnmanagedWriter::SetMethodSourceRange</span><span class="sxs-lookup"><span data-stu-id="67304-102">ISymUnmanagedWriter::SetMethodSourceRange Method</span></span>

<span data-ttu-id="67304-103">Указывает истинные начало и конец метода в исходном файле.</span><span class="sxs-lookup"><span data-stu-id="67304-103">Specifies the true start and end of a method within a source file.</span></span> <span data-ttu-id="67304-104">Этот метод используется для указания экстента метода независимо от точек следования, которые существуют в методе.</span><span class="sxs-lookup"><span data-stu-id="67304-104">Use this method to specify the extent of a method independently of the sequence points that exist within the method.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="67304-105">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="67304-105">Syntax</span></span>  
  
```cpp  
HRESULT SetMethodSourceRange(  
    [in] ISymUnmanagedDocumentWriter  *startDoc,  
    [in] ULONG32                      startLine,  
    [in] ULONG32                      startColumn,  
    [in] ISymUnmanagedDocumentWriter  *endDoc,  
    [in] ULONG32                      endLine,  
    [in] ULONG32                      endColumn);  
```  
  
## <a name="parameters"></a><span data-ttu-id="67304-106">Параметры</span><span class="sxs-lookup"><span data-stu-id="67304-106">Parameters</span></span>  

 `startDoc`  
 <span data-ttu-id="67304-107">окне Указатель на документ, содержащий начальную точку.</span><span class="sxs-lookup"><span data-stu-id="67304-107">[in] A pointer to the document containing the starting position.</span></span>  
  
 `startLine`  
 <span data-ttu-id="67304-108">окне Номер начальной строки.</span><span class="sxs-lookup"><span data-stu-id="67304-108">[in] The starting line number.</span></span>  
  
 `startColumn`  
 <span data-ttu-id="67304-109">окне Начальный столбец.</span><span class="sxs-lookup"><span data-stu-id="67304-109">[in] The starting column.</span></span>  
  
 `endDoc`  
 <span data-ttu-id="67304-110">окне Указатель на документ, содержащий конечную точку.</span><span class="sxs-lookup"><span data-stu-id="67304-110">[in] A pointer to the document containing the ending position.</span></span>  
  
 `endLine`  
 <span data-ttu-id="67304-111">окне Номер конечной строки.</span><span class="sxs-lookup"><span data-stu-id="67304-111">[in] The ending line number.</span></span>  
  
 `endColumn`  
 <span data-ttu-id="67304-112">окне Номер конечного столбца.</span><span class="sxs-lookup"><span data-stu-id="67304-112">[in] The ending column number.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="67304-113">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="67304-113">Return Value</span></span>  

 <span data-ttu-id="67304-114">S_OK, если метод выполнен. в противном случае E_FAIL или другой код ошибки.</span><span class="sxs-lookup"><span data-stu-id="67304-114">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="67304-115">Требования</span><span class="sxs-lookup"><span data-stu-id="67304-115">Requirements</span></span>  

 <span data-ttu-id="67304-116">**Заголовок:** Корсим. idl, Корсим. h</span><span class="sxs-lookup"><span data-stu-id="67304-116">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="67304-117">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="67304-117">See also</span></span>

- [<span data-ttu-id="67304-118">Интерфейс ISymUnmanagedWriter</span><span class="sxs-lookup"><span data-stu-id="67304-118">ISymUnmanagedWriter Interface</span></span>](isymunmanagedwriter-interface.md)
