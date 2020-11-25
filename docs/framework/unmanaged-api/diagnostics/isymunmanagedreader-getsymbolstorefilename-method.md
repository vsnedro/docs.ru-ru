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
ms.openlocfilehash: df503e44f20a0b1f02e2c609cc4b52712520faea
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/24/2020
ms.locfileid: "95720572"
---
# <a name="isymunmanagedreadergetsymbolstorefilename-method"></a><span data-ttu-id="79b2e-102">Метод ISymUnmanagedReader::GetSymbolStoreFileName</span><span class="sxs-lookup"><span data-stu-id="79b2e-102">ISymUnmanagedReader::GetSymbolStoreFileName Method</span></span>

<span data-ttu-id="79b2e-103">Предоставляет имя файла на диске для хранилища символов.</span><span class="sxs-lookup"><span data-stu-id="79b2e-103">Provides the on-disk file name of the symbol store.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="79b2e-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="79b2e-104">Syntax</span></span>  
  
```cpp  
HRESULT GetSymbolStoreFileName (  
    [in]  ULONG32 cchName,  
    [out] ULONG32 *pcchName,  
    [out, size_is (cchName),  
        length_is (*pcchName)] WCHAR szName[]);  
```  
  
## <a name="parameters"></a><span data-ttu-id="79b2e-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="79b2e-105">Parameters</span></span>  

 `cchName`  
 <span data-ttu-id="79b2e-106">окне Размер `szName` буфера.</span><span class="sxs-lookup"><span data-stu-id="79b2e-106">[in] The size of the `szName` buffer.</span></span>  
  
 `pcchName`  
 <span data-ttu-id="79b2e-107">заполняет Указатель на переменную, которая получает длину имени, возвращаемого в `szName` , включая завершение значения NULL.</span><span class="sxs-lookup"><span data-stu-id="79b2e-107">[out] A pointer to the variable that receives the length of the name returned in `szName`, including the null termination.</span></span>  
  
 `szName`  
 <span data-ttu-id="79b2e-108">заполняет Указатель на переменную, которая получает имя файла хранилища символов.</span><span class="sxs-lookup"><span data-stu-id="79b2e-108">[out] A pointer to the variable that receives the file name of the symbol store.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="79b2e-109">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="79b2e-109">Return Value</span></span>  

 <span data-ttu-id="79b2e-110">S_OK, если метод выполнен. в противном случае E_FAIL или другой код ошибки.</span><span class="sxs-lookup"><span data-stu-id="79b2e-110">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="79b2e-111">Требования</span><span class="sxs-lookup"><span data-stu-id="79b2e-111">Requirements</span></span>  

 <span data-ttu-id="79b2e-112">**Заголовок:** Корсим. idl, Корсим. h</span><span class="sxs-lookup"><span data-stu-id="79b2e-112">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="79b2e-113">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="79b2e-113">See also</span></span>

- [<span data-ttu-id="79b2e-114">Интерфейс ISymUnmanagedReader</span><span class="sxs-lookup"><span data-stu-id="79b2e-114">ISymUnmanagedReader Interface</span></span>](isymunmanagedreader-interface.md)
