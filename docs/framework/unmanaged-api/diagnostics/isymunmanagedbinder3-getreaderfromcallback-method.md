---
title: Метод ISymUnmanagedBinder3::GetReaderFromCallback
ms.date: 03/30/2017
api_name:
- ISymUnmanagedBinder3.GetReaderFromCallback
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedBinder3::GetReaderFromCallback
helpviewer_keywords:
- GetReaderFromCallback method [.NET Framework debugging]
- ISymUnmanagedBinder3::GetReaderFromCallback method [.NET Framework debugging]
ms.assetid: 4ef83bd2-3d8e-499e-8a12-d9d6fd6ced30
topic_type:
- apiref
ms.openlocfilehash: 4a23e9aa259f430c0d0579657952fc6aba4c307c
ms.sourcegitcommit: 7b1497c1927cb449cefd313bc5126ae37df30746
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/16/2020
ms.locfileid: "83441660"
---
# <a name="isymunmanagedbinder3getreaderfromcallback-method"></a><span data-ttu-id="5bce7-102">Метод ISymUnmanagedBinder3::GetReaderFromCallback</span><span class="sxs-lookup"><span data-stu-id="5bce7-102">ISymUnmanagedBinder3::GetReaderFromCallback Method</span></span>
<span data-ttu-id="5bce7-103">Позволяет пользователю реализовать или предоставить через обратный вызов либо `IID_IDiaReadExeAtRVACallback` `IID_IDiaReadExeAtOffsetCallback` для получения сведений о каталоге отладки из памяти.</span><span class="sxs-lookup"><span data-stu-id="5bce7-103">Allows the user to implement or supply via callback either an `IID_IDiaReadExeAtRVACallback` or `IID_IDiaReadExeAtOffsetCallback` to obtain the debug directory information from memory.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5bce7-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="5bce7-104">Syntax</span></span>  
  
```cpp  
HRESULT GetReaderFromCallback(  
    [in]  IUnknown     *importer,  
    [in]  const WCHAR  *fileName,  
    [in]  const WCHAR  *searchPath,  
    [in]  ULONG32      searchPolicy,  
    [in]  IUnknown     *callback,  
    [out,retval] ISymUnmanagedReader  **pRetVal);  
```  
  
## <a name="parameters"></a><span data-ttu-id="5bce7-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="5bce7-105">Parameters</span></span>  
 `importer`  
 <span data-ttu-id="5bce7-106">окне Указатель на интерфейс импорта метаданных.</span><span class="sxs-lookup"><span data-stu-id="5bce7-106">[in] A pointer to the metadata import interface.</span></span>  
  
 `fileName`  
 <span data-ttu-id="5bce7-107">окне Указатель на имя файла.</span><span class="sxs-lookup"><span data-stu-id="5bce7-107">[in] A pointer to the file name.</span></span>  
  
 `searchPath`  
 <span data-ttu-id="5bce7-108">окне Указатель на путь поиска.</span><span class="sxs-lookup"><span data-stu-id="5bce7-108">[in] A pointer to the search path.</span></span>  
  
 `searchPolicy`  
 <span data-ttu-id="5bce7-109">окне Значение перечисления [корсимсеарчполициаттрибутес](corsymsearchpolicyattributes-enumeration.md) , указывающее политику, используемую при поиске средства чтения символов.</span><span class="sxs-lookup"><span data-stu-id="5bce7-109">[in] A value of the [CorSymSearchPolicyAttributes](corsymsearchpolicyattributes-enumeration.md) enumeration that specifies the policy to be used when doing a search for a symbol reader.</span></span>  
  
 `callback`  
 <span data-ttu-id="5bce7-110">окне Указатель на функцию обратного вызова.</span><span class="sxs-lookup"><span data-stu-id="5bce7-110">[in] A pointer to the callback function.</span></span>  
  
 `pRetVal`  
 <span data-ttu-id="5bce7-111">заполняет Указатель, которому присваивается возвращаемый интерфейс [ISymUnmanagedReader](isymunmanagedreader-interface.md) .</span><span class="sxs-lookup"><span data-stu-id="5bce7-111">[out] A pointer that is set to the returned [ISymUnmanagedReader](isymunmanagedreader-interface.md) interface.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="5bce7-112">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="5bce7-112">Return Value</span></span>  
 <span data-ttu-id="5bce7-113">S_OK, если метод выполнен. в противном случае E_FAIL или другой код ошибки.</span><span class="sxs-lookup"><span data-stu-id="5bce7-113">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="5bce7-114">Требования</span><span class="sxs-lookup"><span data-stu-id="5bce7-114">Requirements</span></span>  
 <span data-ttu-id="5bce7-115">**Заголовок:** Корсим. idl</span><span class="sxs-lookup"><span data-stu-id="5bce7-115">**Header:** CorSym.idl</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5bce7-116">Дополнительно</span><span class="sxs-lookup"><span data-stu-id="5bce7-116">See also</span></span>

- [<span data-ttu-id="5bce7-117">Интерфейс ISymUnmanagedBinder3</span><span class="sxs-lookup"><span data-stu-id="5bce7-117">ISymUnmanagedBinder3 Interface</span></span>](isymunmanagedbinder3-interface.md)
