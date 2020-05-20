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
ms.openlocfilehash: 857410187edf1c712865626a3327dd4c92cc211f
ms.sourcegitcommit: 7b1497c1927cb449cefd313bc5126ae37df30746
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/16/2020
ms.locfileid: "83441933"
---
# <a name="isymencunmanagedmethodgetfilenamefromoffset-method"></a><span data-ttu-id="4f384-102">Метод ISymENCUnmanagedMethod::GetFileNameFromOffset</span><span class="sxs-lookup"><span data-stu-id="4f384-102">ISymENCUnmanagedMethod::GetFileNameFromOffset Method</span></span>
<span data-ttu-id="4f384-103">Возвращает имя файла для строки, связанной со смещением.</span><span class="sxs-lookup"><span data-stu-id="4f384-103">Gets the file name for the line associated with an offset.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4f384-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="4f384-104">Syntax</span></span>  
  
```cpp  
HRESULT GetFileNameFromOffset(  
    [in]  ULONG32  dwOffset,  
    [in]  ULONG32  cchName,  
    [out] ULONG32  *pcchName,  
    [out, size_is(cchName),  
       length_is(*pcchName)] WCHAR szName[]);  
```  
  
## <a name="parameters"></a><span data-ttu-id="4f384-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="4f384-105">Parameters</span></span>  
 `dwOffset`  
 <span data-ttu-id="4f384-106">окне Значение типа `ULONG32` , содержащее смещение.</span><span class="sxs-lookup"><span data-stu-id="4f384-106">[in] A `ULONG32` that contains the offset.</span></span>  
  
 `cchName`  
 <span data-ttu-id="4f384-107">окне Значение типа `ULONG32` , указывающее размер `szName` буфера.</span><span class="sxs-lookup"><span data-stu-id="4f384-107">[in] A `ULONG32` that indicates the size of the `szName` buffer.</span></span>  
  
 `pcchName`  
 <span data-ttu-id="4f384-108">заполняет Указатель на объект `ULONG32` , который получает размер (в символах) буфера, необходимого для хранения имен файлов.</span><span class="sxs-lookup"><span data-stu-id="4f384-108">[out] A pointer to a `ULONG32` that receives the size, in characters, of the buffer required to contain the file names.</span></span>  
  
 `szName`  
 <span data-ttu-id="4f384-109">заполняет Буфер, содержащий имена файлов.</span><span class="sxs-lookup"><span data-stu-id="4f384-109">[out] The buffer that contains the file names.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="4f384-110">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="4f384-110">Return Value</span></span>  
 <span data-ttu-id="4f384-111">S_OK, если метод выполнен. в противном случае E_FAIL или другой код ошибки.</span><span class="sxs-lookup"><span data-stu-id="4f384-111">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="4f384-112">Требования</span><span class="sxs-lookup"><span data-stu-id="4f384-112">Requirements</span></span>  
 <span data-ttu-id="4f384-113">**Заголовок:** Корсим. idl, Корсим. h</span><span class="sxs-lookup"><span data-stu-id="4f384-113">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4f384-114">Дополнительно</span><span class="sxs-lookup"><span data-stu-id="4f384-114">See also</span></span>

- [<span data-ttu-id="4f384-115">Интерфейс ISymENCUnmanagedMethod</span><span class="sxs-lookup"><span data-stu-id="4f384-115">ISymENCUnmanagedMethod Interface</span></span>](isymencunmanagedmethod-interface.md)
