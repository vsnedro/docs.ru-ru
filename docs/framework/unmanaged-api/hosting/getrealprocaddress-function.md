---
title: Функция GetRealProcAddress
ms.date: 03/30/2017
api_name:
- GetRealProcAddress
api_location:
- mscoree.dll
api_type:
- DLLExport
f1_keywords:
- GetRealProcAddress
helpviewer_keywords:
- GetRealProcAddress function [.NET Framework hosting]
ms.assetid: f1f2fab1-400b-488f-95f2-d49c4fca3556
topic_type:
- apiref
ms.openlocfilehash: d48106fca6008955409581ad9ac202aebe785cb4
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/24/2020
ms.locfileid: "95733234"
---
# <a name="getrealprocaddress-function"></a><span data-ttu-id="d3efe-102">Функция GetRealProcAddress</span><span class="sxs-lookup"><span data-stu-id="d3efe-102">GetRealProcAddress Function</span></span>

<span data-ttu-id="d3efe-103">Возвращает адрес указанной функции, которая экспортируется из последней установленной версии среды CLR.</span><span class="sxs-lookup"><span data-stu-id="d3efe-103">Gets the address of the specified function that is exported from the latest installed version of the common language runtime (CLR).</span></span>  
  
 <span data-ttu-id="d3efe-104">Эта функция является устаревшей в .NET Framework 4.</span><span class="sxs-lookup"><span data-stu-id="d3efe-104">This function has been deprecated in the .NET Framework 4.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d3efe-105">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="d3efe-105">Syntax</span></span>  
  
```cpp  
HRESULT GetRealProcAddress (  
    [in]  LPCSTR  pwszProcName,
    [out] VOID  **ppv  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="d3efe-106">Параметры</span><span class="sxs-lookup"><span data-stu-id="d3efe-106">Parameters</span></span>  

 `pwszProcName`  
 <span data-ttu-id="d3efe-107">окне Имя функции.</span><span class="sxs-lookup"><span data-stu-id="d3efe-107">[in] The name of the function.</span></span>  
  
 `ppv`  
 <span data-ttu-id="d3efe-108">заполняет Расположение, которое получает указатель на адрес функции.</span><span class="sxs-lookup"><span data-stu-id="d3efe-108">[out] The location that receives a pointer to the address of the function.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="d3efe-109">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="d3efe-109">Return Value</span></span>  

 <span data-ttu-id="d3efe-110">Этот метод возвращает коды стандартных ошибок модели COM, как определено в файле WinError. h, в дополнение к следующим значениям, определенным в CorError. h.</span><span class="sxs-lookup"><span data-stu-id="d3efe-110">This method returns standard Component Object Model (COM) error codes, as defined in WinError.h, in addition to the following values defined in CorError.h.</span></span>  
  
|<span data-ttu-id="d3efe-111">Код возврата</span><span class="sxs-lookup"><span data-stu-id="d3efe-111">Return code</span></span>|<span data-ttu-id="d3efe-112">Описание</span><span class="sxs-lookup"><span data-stu-id="d3efe-112">Description</span></span>|  
|-----------------|-----------------|  
|<span data-ttu-id="d3efe-113">S_OK</span><span class="sxs-lookup"><span data-stu-id="d3efe-113">S_OK</span></span>|<span data-ttu-id="d3efe-114">Метод завершился успешно.</span><span class="sxs-lookup"><span data-stu-id="d3efe-114">The method completed successfully.</span></span>|  
|<span data-ttu-id="d3efe-115">E_POINTER</span><span class="sxs-lookup"><span data-stu-id="d3efe-115">E_POINTER</span></span>|<span data-ttu-id="d3efe-116">Недопустимый параметр `ppv`.</span><span class="sxs-lookup"><span data-stu-id="d3efe-116">`ppv` is not valid.</span></span>|  
|<span data-ttu-id="d3efe-117">CLR_E_SHIM_RUNTIMEEXPORT</span><span class="sxs-lookup"><span data-stu-id="d3efe-117">CLR_E_SHIM_RUNTIMEEXPORT</span></span>|<span data-ttu-id="d3efe-118">Функция не экспортируется из среды выполнения.</span><span class="sxs-lookup"><span data-stu-id="d3efe-118">The function is not exported from the runtime.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="d3efe-119">Требования</span><span class="sxs-lookup"><span data-stu-id="d3efe-119">Requirements</span></span>  

 <span data-ttu-id="d3efe-120">**Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="d3efe-120">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="d3efe-121">**Заголовок:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="d3efe-121">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="d3efe-122">**Библиотека:** MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="d3efe-122">**Library:** MSCorEE.dll</span></span>  
  
 <span data-ttu-id="d3efe-123">**.NET Framework версии:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="d3efe-123">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d3efe-124">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="d3efe-124">See also</span></span>

- [<span data-ttu-id="d3efe-125">Устаревшие функции размещения CLR</span><span class="sxs-lookup"><span data-stu-id="d3efe-125">Deprecated CLR Hosting Functions</span></span>](deprecated-clr-hosting-functions.md)
