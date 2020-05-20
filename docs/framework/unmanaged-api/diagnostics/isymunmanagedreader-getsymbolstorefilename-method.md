---
title: Метод ISymUnmanagedReader::GetSymbolStoreFileName
ms.date: 03/30/2017
api_name:
- ISymUnmanagedReader.GetSymbolStoreFileName
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedReader::GetSymbolStoreFileName
helpviewer_keywords:
- GetSymbolStoreFileName method [.NET Framework debugging]
- ISymUnmanagedReader::GetSymbolStoreFileName method [.NET Framework debugging]
ms.assetid: c84f4846-9bc8-44a4-9a76-e39106d6d8b2
topic_type:
- apiref
ms.openlocfilehash: 6ffab3b2f81680404f870cfd63ae5125173a346c
ms.sourcegitcommit: 27db07ffb26f76912feefba7b884313547410db5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/19/2020
ms.locfileid: "83615518"
---
# <a name="isymunmanagedreadergetsymbolstorefilename-method"></a><span data-ttu-id="4922f-102">Метод ISymUnmanagedReader::GetSymbolStoreFileName</span><span class="sxs-lookup"><span data-stu-id="4922f-102">ISymUnmanagedReader::GetSymbolStoreFileName Method</span></span>
<span data-ttu-id="4922f-103">Предоставляет имя файла на диске для хранилища символов.</span><span class="sxs-lookup"><span data-stu-id="4922f-103">Provides the on-disk file name of the symbol store.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4922f-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="4922f-104">Syntax</span></span>  
  
```cpp  
HRESULT GetSymbolStoreFileName (  
    [in]  ULONG32 cchName,  
    [out] ULONG32 *pcchName,  
    [out, size_is (cchName),  
        length_is (*pcchName)] WCHAR szName[]);  
```  
  
## <a name="parameters"></a><span data-ttu-id="4922f-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="4922f-105">Parameters</span></span>  
 `cchName`  
 <span data-ttu-id="4922f-106">окне Размер `szName` буфера.</span><span class="sxs-lookup"><span data-stu-id="4922f-106">[in] The size of the `szName` buffer.</span></span>  
  
 `pcchName`  
 <span data-ttu-id="4922f-107">заполняет Указатель на переменную, которая получает длину имени, возвращаемого в `szName` , включая завершение значения NULL.</span><span class="sxs-lookup"><span data-stu-id="4922f-107">[out] A pointer to the variable that receives the length of the name returned in `szName`, including the null termination.</span></span>  
  
 `szName`  
 <span data-ttu-id="4922f-108">заполняет Указатель на переменную, которая получает имя файла хранилища символов.</span><span class="sxs-lookup"><span data-stu-id="4922f-108">[out] A pointer to the variable that receives the file name of the symbol store.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="4922f-109">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="4922f-109">Return Value</span></span>  
 <span data-ttu-id="4922f-110">S_OK, если метод выполнен. в противном случае E_FAIL или другой код ошибки.</span><span class="sxs-lookup"><span data-stu-id="4922f-110">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="4922f-111">Требования</span><span class="sxs-lookup"><span data-stu-id="4922f-111">Requirements</span></span>  
 <span data-ttu-id="4922f-112">**Заголовок:** Корсим. idl, Корсим. h</span><span class="sxs-lookup"><span data-stu-id="4922f-112">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4922f-113">См. также статью</span><span class="sxs-lookup"><span data-stu-id="4922f-113">See also</span></span>

- [<span data-ttu-id="4922f-114">Интерфейс ISymUnmanagedReader</span><span class="sxs-lookup"><span data-stu-id="4922f-114">ISymUnmanagedReader Interface</span></span>](isymunmanagedreader-interface.md)
