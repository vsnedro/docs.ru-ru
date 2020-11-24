---
title: Функция GetRequestedRuntimeVersionForCLSID
ms.date: 03/30/2017
api_name:
- GetRequestedRuntimeVersionForCLSID
api_location:
- mscoree.dll
api_type:
- DLLExport
f1_keywords:
- GetRequestedRuntimeVersionForCLSID
helpviewer_keywords:
- GetRequestedRuntimeVersionForCLSID function [.NET Framework hosting]
ms.assetid: 5bb12f9a-0612-434b-b4ed-2db636a20bec
topic_type:
- apiref
ms.openlocfilehash: 3afb89a42d7e26c5e89e6f9458ef3406cc0102ca
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/24/2020
ms.locfileid: "95684191"
---
# <a name="getrequestedruntimeversionforclsid-function"></a><span data-ttu-id="2740e-102">Функция GetRequestedRuntimeVersionForCLSID</span><span class="sxs-lookup"><span data-stu-id="2740e-102">GetRequestedRuntimeVersionForCLSID Function</span></span>

<span data-ttu-id="2740e-103">Возвращает соответствующую информацию о версии среды CLR для класса с указанным `CLSID` .</span><span class="sxs-lookup"><span data-stu-id="2740e-103">Gets the appropriate common language runtime (CLR) version information for the class with the specified `CLSID`.</span></span>  
  
 <span data-ttu-id="2740e-104">Эта функция является устаревшей в .NET Framework 4.</span><span class="sxs-lookup"><span data-stu-id="2740e-104">This function has been deprecated in the .NET Framework 4.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2740e-105">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="2740e-105">Syntax</span></span>  
  
```cpp  
HRESULT GetRequestedRuntimeVersionForCLSID (  
    [in]  REFCLSID   rclsid,
    [out]  LPWSTR     pVersion,
    [in]  DWORD      cchBuffer,
    [out] DWORD*     dwLength,
    [in]  CLSID_RESOLUTION_FLAGS dwResolutionFlags  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="2740e-106">Параметры</span><span class="sxs-lookup"><span data-stu-id="2740e-106">Parameters</span></span>  

 `rclsid`  
 <span data-ttu-id="2740e-107">окне  `CLSID` Компонента.</span><span class="sxs-lookup"><span data-stu-id="2740e-107">[in]  The `CLSID` of the component.</span></span>  
  
 `pVersion`  
 <span data-ttu-id="2740e-108">заполняет  Буфер, содержащий строку номера версии после успешного завершения.</span><span class="sxs-lookup"><span data-stu-id="2740e-108">[out]  A buffer that contains the version number string upon successful completion.</span></span>  
  
 `cchBuffer`  
 <span data-ttu-id="2740e-109">окне  Размер буфера в расширенных символах `pVersion` .</span><span class="sxs-lookup"><span data-stu-id="2740e-109">[in]  The size, in wide characters, of the `pVersion` buffer.</span></span>  
  
 `dwLength`  
 <span data-ttu-id="2740e-110">заполняет Длина возвращенного буфера в байтах.</span><span class="sxs-lookup"><span data-stu-id="2740e-110">[out] The length, in bytes, of the returned buffer.</span></span>  
  
 `dwResolutionFlags`  
 <span data-ttu-id="2740e-111">окне  Одно из значений CLSID_RESOLUTION_FLAGS.</span><span class="sxs-lookup"><span data-stu-id="2740e-111">[in]  One of the CLSID_RESOLUTION_FLAGS values.</span></span> <span data-ttu-id="2740e-112">Поддерживаются следующие значения.</span><span class="sxs-lookup"><span data-stu-id="2740e-112">The following values are supported:</span></span>  
  
- <span data-ttu-id="2740e-113">CLSID_RESOLUTION_DEFAULT: (0x0) указывает, что следует использовать режим взаимодействия по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="2740e-113">CLSID_RESOLUTION_DEFAULT: (0x0) Specifies that default interop behavior should be used.</span></span>  
  
- <span data-ttu-id="2740e-114">CLSID_RESOLUTION_REGISTERED: (0x1) указывает, что необходимо выполнять поиск в реестре и применять политику оболочки совместимости.</span><span class="sxs-lookup"><span data-stu-id="2740e-114">CLSID_RESOLUTION_REGISTERED: (0x1) Specifies that the registry should be searched and shim policy should be applied.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="2740e-115">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="2740e-115">Return Value</span></span>  
  
|<span data-ttu-id="2740e-116">HRESULT</span><span class="sxs-lookup"><span data-stu-id="2740e-116">HRESULT</span></span>|<span data-ttu-id="2740e-117">Описание:</span><span class="sxs-lookup"><span data-stu-id="2740e-117">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="2740e-118">S_OK</span><span class="sxs-lookup"><span data-stu-id="2740e-118">S_OK</span></span>|<span data-ttu-id="2740e-119">Функция возвращена успешно.</span><span class="sxs-lookup"><span data-stu-id="2740e-119">The function returned successfully.</span></span>|  
|<span data-ttu-id="2740e-120">E_INVALIDARG</span><span class="sxs-lookup"><span data-stu-id="2740e-120">E_INVALIDARG</span></span>|<span data-ttu-id="2740e-121">Один из параметров имеет недопустимый тип или формат.</span><span class="sxs-lookup"><span data-stu-id="2740e-121">One of the parameters has an invalid type or format.</span></span>|  
|<span data-ttu-id="2740e-122">ERROR_INSUFFICIENT_BUFFER</span><span class="sxs-lookup"><span data-stu-id="2740e-122">ERROR_INSUFFICIENT_BUFFER</span></span>|<span data-ttu-id="2740e-123">`pVersion`Буфер недостаточно велик для размещения всей строки версии.</span><span class="sxs-lookup"><span data-stu-id="2740e-123">The `pVersion` buffer is not large enough to hold the entire version string.</span></span>|  
|<span data-ttu-id="2740e-124">REGDB_E_CLASSNOTREG</span><span class="sxs-lookup"><span data-stu-id="2740e-124">REGDB_E_CLASSNOTREG</span></span>|<span data-ttu-id="2740e-125">Отсутствует класс, зарегистрированный в указанном классе `CLSID` .</span><span class="sxs-lookup"><span data-stu-id="2740e-125">There is no class registered with the specified `CLSID`.</span></span>|  
|<span data-ttu-id="2740e-126">E_POINTER</span><span class="sxs-lookup"><span data-stu-id="2740e-126">E_POINTER</span></span>|<span data-ttu-id="2740e-127">`dwLength` параметр имеет значение null или `cchBuffer` достаточно велик для хранения строки версии, но `pVersion` имеет значение null.</span><span class="sxs-lookup"><span data-stu-id="2740e-127">`dwLength` is null, or `cchBuffer` is large enough to hold the version string, but `pVersion` is null.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="2740e-128">Требования</span><span class="sxs-lookup"><span data-stu-id="2740e-128">Requirements</span></span>  

 <span data-ttu-id="2740e-129">**Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="2740e-129">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="2740e-130">**Заголовок:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="2740e-130">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="2740e-131">**.NET Framework версии:**[!INCLUDE[net_current_v11plus](../../../../includes/net-current-v11plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="2740e-131">**.NET Framework Versions:** [!INCLUDE[net_current_v11plus](../../../../includes/net-current-v11plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2740e-132">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="2740e-132">See also</span></span>

- [<span data-ttu-id="2740e-133">Устаревшие функции размещения CLR</span><span class="sxs-lookup"><span data-stu-id="2740e-133">Deprecated CLR Hosting Functions</span></span>](deprecated-clr-hosting-functions.md)
