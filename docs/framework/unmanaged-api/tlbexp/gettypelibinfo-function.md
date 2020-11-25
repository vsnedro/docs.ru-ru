---
title: Функция GetTypeLibInfo
ms.date: 03/30/2017
api_name:
- GetTypeLibInfo
api_location:
- TlbRef.dll
api_type:
- DLLExport
f1_keywords:
- GetTypeLibInfo
helpviewer_keywords:
- GetTypeLibInfo function [.NET Framework]
ms.assetid: a1c4d165-9bdc-4ca8-940e-292d4ffcc338
topic_type:
- apiref
ms.openlocfilehash: e9f6ae9a0fcd6651395c54c2e44973e53668c1ac
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/24/2020
ms.locfileid: "95708326"
---
# <a name="gettypelibinfo-function"></a><span data-ttu-id="f2da0-102">Функция GetTypeLibInfo</span><span class="sxs-lookup"><span data-stu-id="f2da0-102">GetTypeLibInfo Function</span></span>

<span data-ttu-id="f2da0-103">Возвращает сведения о указанной библиотеке типов, изучая ее структуру [тлибаттр](/windows/win32/api/oaidl/ns-oaidl-tlibattr) .</span><span class="sxs-lookup"><span data-stu-id="f2da0-103">Returns information about the specified type library by examining its [TLIBATTR](/windows/win32/api/oaidl/ns-oaidl-tlibattr) structure.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f2da0-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="f2da0-104">Syntax</span></span>  
  
```cpp  
HRESULT GetTypeLibInfo(  
    [in]   LPWSTR     szFile,  
    [out]  GUID      *pTypeLibID,  
    [out]  LCID      *pTypeLibLCID,  
    [out]  SYSKIND   *pTypeLibPlatform,  
    [out]  USHORT    *pTypeLibMajorVer,  
    [out]  USHORT    *pTypeLibMinorVer  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="f2da0-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="f2da0-105">Parameters</span></span>  

 `szFile`  
 <span data-ttu-id="f2da0-106">окне Имя файла библиотеки типов.</span><span class="sxs-lookup"><span data-stu-id="f2da0-106">[in] The file name of the type library.</span></span>  
  
 `pTypeLibID`  
 <span data-ttu-id="f2da0-107">заполняет Идентификатор GUID библиотеки типов.</span><span class="sxs-lookup"><span data-stu-id="f2da0-107">[out] The GUID of the type library.</span></span>  
  
 `pTypeLibLCID`  
 <span data-ttu-id="f2da0-108">заполняет ИДЕНТИФИКАТОР локализации библиотеки типов.</span><span class="sxs-lookup"><span data-stu-id="f2da0-108">[out] The localization ID of the type library.</span></span>  
  
 `pTypeLibPlatform`  
 <span data-ttu-id="f2da0-109">заполняет Флаг [Сискинд](/windows/win32/api/oaidl/ne-oaidl-syskind) , определяющий целевую операционную систему для библиотеки типов.</span><span class="sxs-lookup"><span data-stu-id="f2da0-109">[out] A [SYSKIND](/windows/win32/api/oaidl/ne-oaidl-syskind) flag that identifies the target operating system for the type library.</span></span> <span data-ttu-id="f2da0-110">Распространенные значения: SYS_WIN32 и SYS_WIN64.</span><span class="sxs-lookup"><span data-stu-id="f2da0-110">Common values are SYS_WIN32 and SYS_WIN64.</span></span>  
  
 `pTypeLibMajorVer`  
 <span data-ttu-id="f2da0-111">заполняет Основной номер версии библиотеки типов.</span><span class="sxs-lookup"><span data-stu-id="f2da0-111">[out] The major version number of the type library.</span></span> <span data-ttu-id="f2da0-112">Например, для версии *x. y* основной номер версии — *x*.</span><span class="sxs-lookup"><span data-stu-id="f2da0-112">For example, for version *x.y*, the major version number is *x*.</span></span>  
  
 `pTypeLibMinorVer`  
 <span data-ttu-id="f2da0-113">заполняет Дополнительный номер версии библиотеки типов.</span><span class="sxs-lookup"><span data-stu-id="f2da0-113">[out] The minor version number of the type library.</span></span> <span data-ttu-id="f2da0-114">Например, для версии *x. y* дополнительный номер версии — *y*.</span><span class="sxs-lookup"><span data-stu-id="f2da0-114">For example, for version *x.y*, the minor version number is *y*.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="f2da0-115">Комментарии</span><span class="sxs-lookup"><span data-stu-id="f2da0-115">Remarks</span></span>  

 <span data-ttu-id="f2da0-116">`GetTypeLibInfo`Функция вызывается [Tlbexp.exe (программа экспорта библиотек типов)](../../tools/tlbexp-exe-type-library-exporter.md).</span><span class="sxs-lookup"><span data-stu-id="f2da0-116">The `GetTypeLibInfo` function is called by the [Tlbexp.exe (Type Library Exporter)](../../tools/tlbexp-exe-type-library-exporter.md).</span></span> <span data-ttu-id="f2da0-117">Это средство создает библиотеку типов, описывающую типы в сборке среды CLR.</span><span class="sxs-lookup"><span data-stu-id="f2da0-117">This tool generates a type library that describes the types in a common language runtime (CLR) assembly.</span></span>  
  
 <span data-ttu-id="f2da0-118">Если какой-либо из параметров имеет значение null, функция возвращает объект `HRESULT` `E_POINTER` .</span><span class="sxs-lookup"><span data-stu-id="f2da0-118">If any parameter is null, the function returns an `HRESULT` of `E_POINTER`.</span></span> <span data-ttu-id="f2da0-119">В противном случае возвращается значение `S_OK`.</span><span class="sxs-lookup"><span data-stu-id="f2da0-119">Otherwise, it returns `S_OK`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="f2da0-120">Требования</span><span class="sxs-lookup"><span data-stu-id="f2da0-120">Requirements</span></span>  

 <span data-ttu-id="f2da0-121">**Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="f2da0-121">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f2da0-122">**Заголовок:** Тлбреф. h</span><span class="sxs-lookup"><span data-stu-id="f2da0-122">**Header:** TlbRef.h</span></span>  
  
 <span data-ttu-id="f2da0-123">**Библиотека:** Тлбреф. lib</span><span class="sxs-lookup"><span data-stu-id="f2da0-123">**Library:** TlbRef.lib</span></span>  
  
 <span data-ttu-id="f2da0-124">**.NET Framework версии:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="f2da0-124">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f2da0-125">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="f2da0-125">See also</span></span>

- [<span data-ttu-id="f2da0-126">Вспомогательные функции Tlbexp</span><span class="sxs-lookup"><span data-stu-id="f2da0-126">Tlbexp Helper Functions</span></span>](index.md)
- [<span data-ttu-id="f2da0-127">Функция Лоадтипелибекс</span><span class="sxs-lookup"><span data-stu-id="f2da0-127">LoadTypeLibEx Function</span></span>](/previous-versions/windows/desktop/api/oleauto/nf-oleauto-loadtypelibex)
