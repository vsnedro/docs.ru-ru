---
title: Метод ISymUnmanagedDocument::GetCheckSum
ms.date: 03/30/2017
api_name:
- ISymUnmanagedDocument.GetCheckSum
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedDocument::GetCheckSum
helpviewer_keywords:
- ISymUnmanagedDocument::GetCheckSum method [.NET Framework debugging]
- GetCheckSum method [.NET Framework debugging]
ms.assetid: 9bc881b3-e2ce-48a7-ad69-17eaaa304120
topic_type:
- apiref
ms.openlocfilehash: 543bd208e5492460435663c32f276472a763f613
ms.sourcegitcommit: 7b1497c1927cb449cefd313bc5126ae37df30746
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/16/2020
ms.locfileid: "83441101"
---
# <a name="isymunmanageddocumentgetchecksum-method"></a><span data-ttu-id="af78c-102">Метод ISymUnmanagedDocument::GetCheckSum</span><span class="sxs-lookup"><span data-stu-id="af78c-102">ISymUnmanagedDocument::GetCheckSum Method</span></span>
<span data-ttu-id="af78c-103">Возвращает контрольную сумму.</span><span class="sxs-lookup"><span data-stu-id="af78c-103">Gets the checksum.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="af78c-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="af78c-104">Syntax</span></span>  
  
```cpp  
HRESULT GetCheckSum(  
    [in]  ULONG32  cData,  
    [out] ULONG32  *pcData,  
    [out, size_is(cData), length_is(*pcData)] BYTE data[]);  
```  
  
## <a name="parameters"></a><span data-ttu-id="af78c-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="af78c-105">Parameters</span></span>  
 `cData`  
 <span data-ttu-id="af78c-106">окне Длина буфера, предоставленного `data` параметром</span><span class="sxs-lookup"><span data-stu-id="af78c-106">[in] The length of the buffer provided by the `data` parameter</span></span>  
  
 `pcData`  
 <span data-ttu-id="af78c-107">заполняет Размер и длина контрольной суммы в байтах.</span><span class="sxs-lookup"><span data-stu-id="af78c-107">[out] The size and length of the checksum, in bytes.</span></span>  
  
 `data`  
 <span data-ttu-id="af78c-108">заполняет Буфер, получающий контрольную сумму.</span><span class="sxs-lookup"><span data-stu-id="af78c-108">[out] The buffer that receives the checksum.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="af78c-109">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="af78c-109">Return Value</span></span>  
 <span data-ttu-id="af78c-110">S_OK, если метод выполнен. в противном случае — код ошибки.</span><span class="sxs-lookup"><span data-stu-id="af78c-110">S_OK if the method succeeds; otherwise, an error code.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="af78c-111">См. также статью</span><span class="sxs-lookup"><span data-stu-id="af78c-111">See also</span></span>

- [<span data-ttu-id="af78c-112">Интерфейс ISymUnmanagedDocument</span><span class="sxs-lookup"><span data-stu-id="af78c-112">ISymUnmanagedDocument Interface</span></span>](isymunmanageddocument-interface.md)
