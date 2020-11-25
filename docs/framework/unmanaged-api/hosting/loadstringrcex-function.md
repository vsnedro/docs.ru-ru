---
title: Функция LoadStringRCEx
ms.date: 03/30/2017
api_name:
- LoadStringRCEx
api_location:
- mscoree.dll
api_type:
- DLLExport
f1_keywords:
- LoadStringRCEx
helpviewer_keywords:
- LoadStringRCEx function [.NET Framework hosting]
ms.assetid: bc789636-ca14-4f07-8f77-9305874d7495
topic_type:
- apiref
ms.openlocfilehash: 1aa5c9f5dd7dd63e69c2eed1f6dd8ad6f007f01f
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/24/2020
ms.locfileid: "95727540"
---
# <a name="loadstringrcex-function"></a><span data-ttu-id="51bee-102">Функция LoadStringRCEx</span><span class="sxs-lookup"><span data-stu-id="51bee-102">LoadStringRCEx Function</span></span>

<span data-ttu-id="51bee-103">Преобразует значение HRESULT в соответствующее сообщение об ошибке для указанного языка и региональных параметров.</span><span class="sxs-lookup"><span data-stu-id="51bee-103">Translates an HRESULT value to an appropriate error message for the specified culture.</span></span>  
  
 <span data-ttu-id="51bee-104">Эта функция является устаревшей в .NET Framework 4.</span><span class="sxs-lookup"><span data-stu-id="51bee-104">This function has been deprecated in the .NET Framework 4.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="51bee-105">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="51bee-105">Syntax</span></span>  
  
```cpp  
HRESULT LoadStringRCEx (  
    [in]  LCID    lcid,
    [in]  UINT    iResouceID,
    [out] LPWSTR  szBuffer,
    [in]  int     iMax,
    [in]  int     bQuiet,
    [out] int    *pcwchUsed  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="51bee-106">Параметры</span><span class="sxs-lookup"><span data-stu-id="51bee-106">Parameters</span></span>  

 `lcid`  
 <span data-ttu-id="51bee-107">окне Идентификатор языка и региональных параметров.</span><span class="sxs-lookup"><span data-stu-id="51bee-107">[in] A culture identifier.</span></span> <span data-ttu-id="51bee-108">Pass-1 для `lcid` для использования языка и региональных параметров по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="51bee-108">Pass -1 for `lcid` to use the default culture.</span></span>  
  
 `iResourceID`  
 <span data-ttu-id="51bee-109">[in] Значение HRESULT.</span><span class="sxs-lookup"><span data-stu-id="51bee-109">[in] An HRESULT.</span></span>  
  
 `szBuffer`  
 <span data-ttu-id="51bee-110">заполняет Буфер, содержащий сообщение об ошибке после успешного завершения.</span><span class="sxs-lookup"><span data-stu-id="51bee-110">[out] A buffer that contains the error message upon successful completion.</span></span>  
  
 `iMax`  
 <span data-ttu-id="51bee-111">окне Размер буфера сообщений об ошибках.</span><span class="sxs-lookup"><span data-stu-id="51bee-111">[in] The size of the error message buffer.</span></span>  
  
 `bQuiet`  
 <span data-ttu-id="51bee-112">окне Игнорируют.</span><span class="sxs-lookup"><span data-stu-id="51bee-112">[in] Ignored.</span></span>  
  
 `pcwchUsed`  
 <span data-ttu-id="51bee-113">заполняет Указатель на длину сообщения об ошибке.</span><span class="sxs-lookup"><span data-stu-id="51bee-113">[out] A pointer to the length of the error message.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="51bee-114">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="51bee-114">Return Value</span></span>  

 <span data-ttu-id="51bee-115">Этот метод возвращает стандартные коды ошибок COM, как определено в файле WinError. h, а также следующие значения.</span><span class="sxs-lookup"><span data-stu-id="51bee-115">This method returns standard COM error codes, as defined in WinError.h, in addition to the following values.</span></span>  
  
|<span data-ttu-id="51bee-116">Код возврата</span><span class="sxs-lookup"><span data-stu-id="51bee-116">Return code</span></span>|<span data-ttu-id="51bee-117">Описание</span><span class="sxs-lookup"><span data-stu-id="51bee-117">Description</span></span>|  
|-----------------|-----------------|  
|<span data-ttu-id="51bee-118">S_OK</span><span class="sxs-lookup"><span data-stu-id="51bee-118">S_OK</span></span>|<span data-ttu-id="51bee-119">Метод завершился успешно.</span><span class="sxs-lookup"><span data-stu-id="51bee-119">The method completed successfully.</span></span>|  
|<span data-ttu-id="51bee-120">E_INVALIDARG</span><span class="sxs-lookup"><span data-stu-id="51bee-120">E_INVALIDARG</span></span>|<span data-ttu-id="51bee-121">`szBuffer` имеет значение null или `iMax` равно нулю (0).</span><span class="sxs-lookup"><span data-stu-id="51bee-121">`szBuffer` is null, or `iMax` is zero (0).</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="51bee-122">Комментарии</span><span class="sxs-lookup"><span data-stu-id="51bee-122">Remarks</span></span>  

 <span data-ttu-id="51bee-123">Если метод не завершается успешно, `szBuffer` содержит пустую строку.</span><span class="sxs-lookup"><span data-stu-id="51bee-123">If the method does not complete successfully, `szBuffer` contains an empty string.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="51bee-124">Требования</span><span class="sxs-lookup"><span data-stu-id="51bee-124">Requirements</span></span>  

 <span data-ttu-id="51bee-125">**Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="51bee-125">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="51bee-126">**Заголовок:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="51bee-126">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="51bee-127">**Библиотека:** MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="51bee-127">**Library:** MSCorEE.dll</span></span>  
  
 <span data-ttu-id="51bee-128">**.NET Framework версии:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="51bee-128">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="51bee-129">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="51bee-129">See also</span></span>

- <xref:System.Globalization.CultureInfo.LCID%2A?displayProperty=nameWithType>
- [<span data-ttu-id="51bee-130">Функция LoadStringRC</span><span class="sxs-lookup"><span data-stu-id="51bee-130">LoadStringRC Function</span></span>](loadstringrc-function.md)
- [<span data-ttu-id="51bee-131">Устаревшие функции размещения CLR</span><span class="sxs-lookup"><span data-stu-id="51bee-131">Deprecated CLR Hosting Functions</span></span>](deprecated-clr-hosting-functions.md)
