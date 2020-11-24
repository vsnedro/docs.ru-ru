---
title: Метод ISymUnmanagedReader::GetMethodsFromDocumentPosition
ms.date: 03/30/2017
api_name:
- ISymUnmanagedReader.GetMethodsFromDocumentPosition
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedReader::GetMethodsFromDocumentPosition
helpviewer_keywords:
- GetMethodsFromDocumentPosition method [.NET Framework debugging]
- ISymUnmanagedReader::GetMethodsFromDocumentPosition method [.NET Framework debugging]
ms.assetid: 83605f1e-e4f3-49e6-859b-f13cad68bb54
topic_type:
- apiref
ms.openlocfilehash: 5298dd0f53693d96b748f6c839660838fdfad4ac
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/24/2020
ms.locfileid: "95689554"
---
# <a name="isymunmanagedreadergetmethodsfromdocumentposition-method"></a><span data-ttu-id="167d4-102">Метод ISymUnmanagedReader::GetMethodsFromDocumentPosition</span><span class="sxs-lookup"><span data-stu-id="167d4-102">ISymUnmanagedReader::GetMethodsFromDocumentPosition Method</span></span>

<span data-ttu-id="167d4-103">Возвращает массив методов, каждый из которых содержит точку останова в заданной позиции в документе.</span><span class="sxs-lookup"><span data-stu-id="167d4-103">Returns an array of methods, each of which contains the breakpoint at the given position in a document.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="167d4-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="167d4-104">Syntax</span></span>  
  
```cpp  
HRESULT GetMethodsFromDocumentPosition (  
    [in]  ISymUnmanagedDocument* document,  
    [in]  ULONG32 line,  
    [in]  ULONG32 column,  
    [in]  ULONG32 cMethod,  
    [out] ULONG32* pcMethod,  
    [out, size_is (cMethod),  
        length_is (*pcMethod)] ISymUnmanagedMethod* pRetVal[]);  
```  
  
## <a name="parameters"></a><span data-ttu-id="167d4-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="167d4-105">Parameters</span></span>  

 `document`  
 <span data-ttu-id="167d4-106">окне Указанный документ.</span><span class="sxs-lookup"><span data-stu-id="167d4-106">[in] The specified document.</span></span>  
  
 `line`  
 <span data-ttu-id="167d4-107">окне Строка указанного документа.</span><span class="sxs-lookup"><span data-stu-id="167d4-107">[in] The line of the specified document.</span></span>  
  
 `column`  
 <span data-ttu-id="167d4-108">окне Столбец указанного документа.</span><span class="sxs-lookup"><span data-stu-id="167d4-108">[in] The column of the specified document.</span></span>  
  
 `cMethod`  
 <span data-ttu-id="167d4-109">[in] Размер массива `pRetVal`.</span><span class="sxs-lookup"><span data-stu-id="167d4-109">[in] The size of the `pRetVal` array.</span></span>  
  
 `pcMethod`  
 <span data-ttu-id="167d4-110">заполняет Указатель на переменную, которая получает количество элементов, возвращаемых в `pRetVal` массиве.</span><span class="sxs-lookup"><span data-stu-id="167d4-110">[out] A pointer to a variable that receives the number of elements returned in the `pRetVal` array.</span></span>  
  
 `pRetVal`  
 <span data-ttu-id="167d4-111">заполняет Массив указателей, каждый из которых указывает на объект [ISymUnmanagedMethod](isymunmanagedmethod-interface.md) , представляющий метод, содержащий точку останова.</span><span class="sxs-lookup"><span data-stu-id="167d4-111">[out] An array of pointers, each of which points to an [ISymUnmanagedMethod](isymunmanagedmethod-interface.md) object that represents a method containing the breakpoint.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="167d4-112">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="167d4-112">Return Value</span></span>  

 <span data-ttu-id="167d4-113">S_OK, если метод выполнен. в противном случае E_FAIL или другой код ошибки.</span><span class="sxs-lookup"><span data-stu-id="167d4-113">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="167d4-114">Требования</span><span class="sxs-lookup"><span data-stu-id="167d4-114">Requirements</span></span>  

 <span data-ttu-id="167d4-115">**Заголовок:** Корсим. idl, Корсим. h</span><span class="sxs-lookup"><span data-stu-id="167d4-115">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="167d4-116">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="167d4-116">See also</span></span>

- [<span data-ttu-id="167d4-117">Интерфейс ISymUnmanagedReader</span><span class="sxs-lookup"><span data-stu-id="167d4-117">ISymUnmanagedReader Interface</span></span>](isymunmanagedreader-interface.md)
