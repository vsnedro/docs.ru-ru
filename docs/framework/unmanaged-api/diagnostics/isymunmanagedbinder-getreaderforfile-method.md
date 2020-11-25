---
title: Метод ISymUnmanagedBinder::GetReaderForFile
ms.date: 03/30/2017
api_name:
- ISymUnmanagedBinder.GetReaderForFile
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedBinder::GetReaderForFile
helpviewer_keywords:
- ISymUnmanagedBinder::GetReaderForFile method [.NET Framework debugging]
- GetReaderForFile method [.NET Framework debugging]
ms.assetid: 46c06258-831e-47c8-a50a-8650af6b637e
topic_type:
- apiref
ms.openlocfilehash: ac895032e70cf31532ab4c73409d6d750eae65df
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/24/2020
ms.locfileid: "95707000"
---
# <a name="isymunmanagedbindergetreaderforfile-method"></a><span data-ttu-id="0d1ce-102">Метод ISymUnmanagedBinder::GetReaderForFile</span><span class="sxs-lookup"><span data-stu-id="0d1ce-102">ISymUnmanagedBinder::GetReaderForFile Method</span></span>

<span data-ttu-id="0d1ce-103">При наличии интерфейса метаданных и имени файла возвращает правильный интерфейс [ISymUnmanagedReader](isymunmanagedreader-interface.md) , который будет считывать символы отладки, связанные с модулем.</span><span class="sxs-lookup"><span data-stu-id="0d1ce-103">Given a metadata interface and a file name, returns the correct [ISymUnmanagedReader](isymunmanagedreader-interface.md) interface that will read the debugging symbols associated with the module.</span></span>  
  
 <span data-ttu-id="0d1ce-104">Этот метод будет открывать файл базы данных программы (PDB) только в том случае, если он находится рядом с исполняемым файлом.</span><span class="sxs-lookup"><span data-stu-id="0d1ce-104">This method will open the program database (PDB) file only if it is next to the executable file.</span></span> <span data-ttu-id="0d1ce-105">Это изменение было внесено в целях безопасности.</span><span class="sxs-lookup"><span data-stu-id="0d1ce-105">This change has been made for security purposes.</span></span> <span data-ttu-id="0d1ce-106">Если требуется более широкий поиск PDB-файла, используйте метод [ISymUnmanagedBinder2:: GetReaderForFile2](isymunmanagedbinder2-getreaderforfile2-method.md) .</span><span class="sxs-lookup"><span data-stu-id="0d1ce-106">If you need a more extensive search for the PDB file, use the [ISymUnmanagedBinder2::GetReaderForFile2](isymunmanagedbinder2-getreaderforfile2-method.md) method.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0d1ce-107">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="0d1ce-107">Syntax</span></span>  
  
```cpp  
HRESULT GetReaderForFile(  
    [in]  IUnknown     *importer,  
    [in]  const WCHAR  *fileName,  
    [in]  const WCHAR  *searchPath,  
    [out, retval] ISymUnmanagedReader  **pRetVal);  
```  
  
## <a name="parameters"></a><span data-ttu-id="0d1ce-108">Параметры</span><span class="sxs-lookup"><span data-stu-id="0d1ce-108">Parameters</span></span>  

 `importer`  
 <span data-ttu-id="0d1ce-109">окне Указатель на интерфейс импорта метаданных.</span><span class="sxs-lookup"><span data-stu-id="0d1ce-109">[in] A pointer to the metadata import interface.</span></span>  
  
 `fileName`  
 <span data-ttu-id="0d1ce-110">окне Указатель на имя файла.</span><span class="sxs-lookup"><span data-stu-id="0d1ce-110">[in] A pointer to the file name.</span></span>  
  
 `searchPath`  
 <span data-ttu-id="0d1ce-111">окне Указатель на путь поиска.</span><span class="sxs-lookup"><span data-stu-id="0d1ce-111">[in] A pointer to the search path.</span></span>  
  
 `pRetVal`  
 <span data-ttu-id="0d1ce-112">заполняет Указатель, которому присваивается возвращаемый интерфейс [ISymUnmanagedReader](isymunmanagedreader-interface.md) .</span><span class="sxs-lookup"><span data-stu-id="0d1ce-112">[out] A pointer that is set to the returned [ISymUnmanagedReader](isymunmanagedreader-interface.md) interface.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="0d1ce-113">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="0d1ce-113">Return Value</span></span>  

 <span data-ttu-id="0d1ce-114">S_OK, если метод выполнен. в противном случае E_FAIL или другой код ошибки.</span><span class="sxs-lookup"><span data-stu-id="0d1ce-114">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="0d1ce-115">Требования</span><span class="sxs-lookup"><span data-stu-id="0d1ce-115">Requirements</span></span>  

 <span data-ttu-id="0d1ce-116">**Заголовок:** Корсим. idl, Корсим. h</span><span class="sxs-lookup"><span data-stu-id="0d1ce-116">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0d1ce-117">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="0d1ce-117">See also</span></span>

- [<span data-ttu-id="0d1ce-118">Интерфейс ISymUnmanagedBinder</span><span class="sxs-lookup"><span data-stu-id="0d1ce-118">ISymUnmanagedBinder Interface</span></span>](isymunmanagedbinder-interface.md)
- [<span data-ttu-id="0d1ce-119">Метод GetReaderForFile2</span><span class="sxs-lookup"><span data-stu-id="0d1ce-119">GetReaderForFile2 Method</span></span>](isymunmanagedbinder2-getreaderforfile2-method.md)
