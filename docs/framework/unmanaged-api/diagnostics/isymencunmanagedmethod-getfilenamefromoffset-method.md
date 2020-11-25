---
title: Метод ISymENCUnmanagedMethod::GetFileNameFromOffset
ms.date: 03/30/2017
api_name:
- ISymENCUnmanagedMethod.GetFileNameFromOffset
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymENCUnmanagedMethod::GetFileNameFromOffset
helpviewer_keywords:
- GetFileNameFromOffset method [.NET Framework debugging]
- ISymENCUnmanagedMethod::GetFileNameFromOffset method [.NET Framework debugging]
ms.assetid: 00e2e194-12f5-436e-a997-2b9d3e844d4f
topic_type:
- apiref
ms.openlocfilehash: ad9631039c8d032e7ffdba1e6098b66398f82277
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/24/2020
ms.locfileid: "95707390"
---
# <a name="isymencunmanagedmethodgetfilenamefromoffset-method"></a><span data-ttu-id="0c4e4-102">Метод ISymENCUnmanagedMethod::GetFileNameFromOffset</span><span class="sxs-lookup"><span data-stu-id="0c4e4-102">ISymENCUnmanagedMethod::GetFileNameFromOffset Method</span></span>

<span data-ttu-id="0c4e4-103">Возвращает имя файла для строки, связанной со смещением.</span><span class="sxs-lookup"><span data-stu-id="0c4e4-103">Gets the file name for the line associated with an offset.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0c4e4-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="0c4e4-104">Syntax</span></span>  
  
```cpp  
HRESULT GetFileNameFromOffset(  
    [in]  ULONG32  dwOffset,  
    [in]  ULONG32  cchName,  
    [out] ULONG32  *pcchName,  
    [out, size_is(cchName),  
       length_is(*pcchName)] WCHAR szName[]);  
```  
  
## <a name="parameters"></a><span data-ttu-id="0c4e4-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="0c4e4-105">Parameters</span></span>  

 `dwOffset`  
 <span data-ttu-id="0c4e4-106">окне Значение типа `ULONG32` , содержащее смещение.</span><span class="sxs-lookup"><span data-stu-id="0c4e4-106">[in] A `ULONG32` that contains the offset.</span></span>  
  
 `cchName`  
 <span data-ttu-id="0c4e4-107">окне Значение типа `ULONG32` , указывающее размер `szName` буфера.</span><span class="sxs-lookup"><span data-stu-id="0c4e4-107">[in] A `ULONG32` that indicates the size of the `szName` buffer.</span></span>  
  
 `pcchName`  
 <span data-ttu-id="0c4e4-108">заполняет Указатель на объект `ULONG32` , который получает размер (в символах) буфера, необходимого для хранения имен файлов.</span><span class="sxs-lookup"><span data-stu-id="0c4e4-108">[out] A pointer to a `ULONG32` that receives the size, in characters, of the buffer required to contain the file names.</span></span>  
  
 `szName`  
 <span data-ttu-id="0c4e4-109">заполняет Буфер, содержащий имена файлов.</span><span class="sxs-lookup"><span data-stu-id="0c4e4-109">[out] The buffer that contains the file names.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="0c4e4-110">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="0c4e4-110">Return Value</span></span>  

 <span data-ttu-id="0c4e4-111">S_OK, если метод выполнен. в противном случае E_FAIL или другой код ошибки.</span><span class="sxs-lookup"><span data-stu-id="0c4e4-111">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="0c4e4-112">Требования</span><span class="sxs-lookup"><span data-stu-id="0c4e4-112">Requirements</span></span>  

 <span data-ttu-id="0c4e4-113">**Заголовок:** Корсим. idl, Корсим. h</span><span class="sxs-lookup"><span data-stu-id="0c4e4-113">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0c4e4-114">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="0c4e4-114">See also</span></span>

- [<span data-ttu-id="0c4e4-115">Интерфейс ISymENCUnmanagedMethod</span><span class="sxs-lookup"><span data-stu-id="0c4e4-115">ISymENCUnmanagedMethod Interface</span></span>](isymencunmanagedmethod-interface.md)
