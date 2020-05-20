---
title: Метод ISymUnmanagedSourceServerModule::GetSourceServerData
ms.date: 03/30/2017
api_name:
- ISymUnmanagedSourceServerModule.GetSourceServerData
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedSourceServerModule::GetSourceServerData
helpviewer_keywords:
- ISymUnmanagedSourceServerModule::GetSourceServerData method [.NET Framework debugging]
- GetSourceServerData method [.NET Framework debugging]
ms.assetid: 20bdf8ff-2d15-4c64-8950-6888f642d6c0
topic_type:
- apiref
ms.openlocfilehash: 9a3a6c07a9cace0ac9834cdb05925a301285204c
ms.sourcegitcommit: 27db07ffb26f76912feefba7b884313547410db5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/19/2020
ms.locfileid: "83615323"
---
# <a name="isymunmanagedsourceservermodulegetsourceserverdata-method"></a><span data-ttu-id="30eac-102">Метод ISymUnmanagedSourceServerModule::GetSourceServerData</span><span class="sxs-lookup"><span data-stu-id="30eac-102">ISymUnmanagedSourceServerModule::GetSourceServerData Method</span></span>
<span data-ttu-id="30eac-103">Возвращает данные исходного сервера для модуля.</span><span class="sxs-lookup"><span data-stu-id="30eac-103">Returns the source server data for the module.</span></span> <span data-ttu-id="30eac-104">Вызывающий объект должен освободить ресурсы с помощью `CoTaskMemFree` .</span><span class="sxs-lookup"><span data-stu-id="30eac-104">The caller must free resources by using `CoTaskMemFree`.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="30eac-105">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="30eac-105">Syntax</span></span>  
  
```cpp  
HRESULT GetSourceServerData(  
    [out] ULONG* pDataByteCount,
    [out, size_is (, *pDataByteCount)] BYTE** ppData);  
```  
  
## <a name="parameters"></a><span data-ttu-id="30eac-106">Параметры</span><span class="sxs-lookup"><span data-stu-id="30eac-106">Parameters</span></span>  
 `pDataByteCount`  
 <span data-ttu-id="30eac-107">заполняет Указатель на объект `ULONG32` , который получает размер (в байтах) данных сервера-источника.</span><span class="sxs-lookup"><span data-stu-id="30eac-107">[out] A pointer to a `ULONG32` that receives the size, in bytes, of the source server data.</span></span>  
  
 `ppData`  
 <span data-ttu-id="30eac-108">заполняет Указатель на возвращаемое `pDataByteCount` значение.</span><span class="sxs-lookup"><span data-stu-id="30eac-108">[out] A pointer to the returned `pDataByteCount` value.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="30eac-109">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="30eac-109">Return Value</span></span>  
 <span data-ttu-id="30eac-110">S_OK, если метод выполнен. в противном случае E_FAIL или другой код ошибки.</span><span class="sxs-lookup"><span data-stu-id="30eac-110">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="30eac-111">Требования</span><span class="sxs-lookup"><span data-stu-id="30eac-111">Requirements</span></span>  
 <span data-ttu-id="30eac-112">**Заголовок:** Корсим. idl, Корсим. h</span><span class="sxs-lookup"><span data-stu-id="30eac-112">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="30eac-113">См. также статью</span><span class="sxs-lookup"><span data-stu-id="30eac-113">See also</span></span>

- [<span data-ttu-id="30eac-114">Интерфейс ISymUnmanagedSourceServerModule</span><span class="sxs-lookup"><span data-stu-id="30eac-114">ISymUnmanagedSourceServerModule Interface</span></span>](isymunmanagedsourceservermodule-interface.md)
