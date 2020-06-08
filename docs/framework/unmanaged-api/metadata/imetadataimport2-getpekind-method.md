---
title: Метод IMetaDataImport2::GetPEKind
ms.date: 03/30/2017
api_name:
- IMetaDataImport2.GetPEKind
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataImport2::GetPEKind
helpviewer_keywords:
- GetPEKind method [.NET Framework metadata]
- IMetaDataImport2::GetPEKind method [.NET Framework metadata]
ms.assetid: d91c3d89-8022-4a4c-a2a2-a8af2c387507
topic_type:
- apiref
ms.openlocfilehash: 3626998c456e23fb922ae45a68bedb0e45a7ccba
ms.sourcegitcommit: da21fc5a8cce1e028575acf31974681a1bc5aeed
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/08/2020
ms.locfileid: "84490436"
---
# <a name="imetadataimport2getpekind-method"></a><span data-ttu-id="4ca6b-102">Метод IMetaDataImport2::GetPEKind</span><span class="sxs-lookup"><span data-stu-id="4ca6b-102">IMetaDataImport2::GetPEKind Method</span></span>
<span data-ttu-id="4ca6b-103">Возвращает значение, определяющее природу кода в переносимом исполняемом (PE) файле (обычно это DLL или EXE-файл), который определен в текущей области метаданных.</span><span class="sxs-lookup"><span data-stu-id="4ca6b-103">Gets a value identifying the nature of the code in the portable executable (PE) file, typically a DLL or EXE file, that is defined in the current metadata scope.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4ca6b-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="4ca6b-104">Syntax</span></span>  
  
```cpp  
HRESULT GetPEKind (  
   [out] DWORD *pdwPEKind,  
   [out] DWORD *pdwMachine  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="4ca6b-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="4ca6b-105">Parameters</span></span>  
 `pdwPEKind`  
 <span data-ttu-id="4ca6b-106">заполняет Указатель на значение перечисления [CorPEKind](corpekind-enumeration.md) , ОПИСЫВАЮЩее PE-файл.</span><span class="sxs-lookup"><span data-stu-id="4ca6b-106">[out] A pointer to a value of the [CorPEKind](corpekind-enumeration.md) enumeration that describes the PE file.</span></span>  
  
 `pdwMachine`  
 <span data-ttu-id="4ca6b-107">заполняет Указатель на значение, идентифицирующее архитектуру компьютера.</span><span class="sxs-lookup"><span data-stu-id="4ca6b-107">[out] A pointer to a value that identifies the architecture of the machine.</span></span> <span data-ttu-id="4ca6b-108">Возможные значения см. в следующем разделе.</span><span class="sxs-lookup"><span data-stu-id="4ca6b-108">See the next section for possible values.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="4ca6b-109">Примечания</span><span class="sxs-lookup"><span data-stu-id="4ca6b-109">Remarks</span></span>  
 <span data-ttu-id="4ca6b-110">Значение, на которое ссылается `pdwMachine` параметр, может быть одним из следующих.</span><span class="sxs-lookup"><span data-stu-id="4ca6b-110">The value referenced by the `pdwMachine` parameter can be one of the following.</span></span>  
  
|<span data-ttu-id="4ca6b-111">Значение</span><span class="sxs-lookup"><span data-stu-id="4ca6b-111">Value</span></span>|<span data-ttu-id="4ca6b-112">Архитектура компьютера</span><span class="sxs-lookup"><span data-stu-id="4ca6b-112">Machine architecture</span></span>|  
|-----------|--------------------------|  
|<span data-ttu-id="4ca6b-113">IMAGE_FILE_MACHINE_I386</span><span class="sxs-lookup"><span data-stu-id="4ca6b-113">IMAGE_FILE_MACHINE_I386</span></span><br /><br /> <span data-ttu-id="4ca6b-114">0x014C</span><span class="sxs-lookup"><span data-stu-id="4ca6b-114">0x014C</span></span>|<span data-ttu-id="4ca6b-115">x86</span><span class="sxs-lookup"><span data-stu-id="4ca6b-115">x86</span></span>|  
|<span data-ttu-id="4ca6b-116">IMAGE_FILE_MACHINE_IA64</span><span class="sxs-lookup"><span data-stu-id="4ca6b-116">IMAGE_FILE_MACHINE_IA64</span></span><br /><br /> <span data-ttu-id="4ca6b-117">0x0200</span><span class="sxs-lookup"><span data-stu-id="4ca6b-117">0x0200</span></span>|<span data-ttu-id="4ca6b-118">Intel IPF</span><span class="sxs-lookup"><span data-stu-id="4ca6b-118">Intel IPF</span></span>|  
|<span data-ttu-id="4ca6b-119">IMAGE_FILE_MACHINE_AMD64</span><span class="sxs-lookup"><span data-stu-id="4ca6b-119">IMAGE_FILE_MACHINE_AMD64</span></span><br /><br /> <span data-ttu-id="4ca6b-120">0x8664</span><span class="sxs-lookup"><span data-stu-id="4ca6b-120">0x8664</span></span>|<span data-ttu-id="4ca6b-121">X64</span><span class="sxs-lookup"><span data-stu-id="4ca6b-121">x64</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="4ca6b-122">Требования</span><span class="sxs-lookup"><span data-stu-id="4ca6b-122">Requirements</span></span>  
 <span data-ttu-id="4ca6b-123">**Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="4ca6b-123">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="4ca6b-124">**Заголовок:** COR. h</span><span class="sxs-lookup"><span data-stu-id="4ca6b-124">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="4ca6b-125">**Библиотека:** Используется в качестве ресурса в MsCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="4ca6b-125">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="4ca6b-126">**.NET Framework версии:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="4ca6b-126">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4ca6b-127">См. также</span><span class="sxs-lookup"><span data-stu-id="4ca6b-127">See also</span></span>

- [<span data-ttu-id="4ca6b-128">Интерфейс IMetaDataImport2</span><span class="sxs-lookup"><span data-stu-id="4ca6b-128">IMetaDataImport2 Interface</span></span>](imetadataimport2-interface.md)
- [<span data-ttu-id="4ca6b-129">Интерфейс IMetaDataImport</span><span class="sxs-lookup"><span data-stu-id="4ca6b-129">IMetaDataImport Interface</span></span>](imetadataimport-interface.md)
- [<span data-ttu-id="4ca6b-130">Перечисление CorPEKind</span><span class="sxs-lookup"><span data-stu-id="4ca6b-130">CorPEKind Enumeration</span></span>](corpekind-enumeration.md)
