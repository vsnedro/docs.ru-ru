---
title: Метод IMetaDataImport::GetPinvokeMap
ms.date: 03/30/2017
api_name:
- IMetaDataImport.GetPinvokeMap
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataImport::GetPinvokeMap
helpviewer_keywords:
- IMetaDataImport::GetPinvokeMap method [.NET Framework metadata]
- GetPinvokeMap method [.NET Framework metadata]
ms.assetid: b8685c1e-b80c-4198-8eb3-748d6f48a99e
topic_type:
- apiref
ms.openlocfilehash: 8409e56b5ec4dbe47035a0555b6b7ce175b517ee
ms.sourcegitcommit: da21fc5a8cce1e028575acf31974681a1bc5aeed
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/08/2020
ms.locfileid: "84490982"
---
# <a name="imetadataimportgetpinvokemap-method"></a><span data-ttu-id="1931b-102">Метод IMetaDataImport::GetPinvokeMap</span><span class="sxs-lookup"><span data-stu-id="1931b-102">IMetaDataImport::GetPinvokeMap Method</span></span>
<span data-ttu-id="1931b-103">Возвращает токен ModuleRef, представляющий целевую сборку вызова PInvoke.</span><span class="sxs-lookup"><span data-stu-id="1931b-103">Gets a ModuleRef token to represent the target assembly of a PInvoke call.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="1931b-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="1931b-104">Syntax</span></span>  
  
```cpp  
HRESULT GetPinvokeMap (  
   [in]  mdToken       tk,  
   [out] DWORD         *pdwMappingFlags,  
   [out] LPWSTR        szImportName,  
   [in]  ULONG         cchImportName,  
   [out] ULONG         *pchImportName,  
   [out] mdModuleRef   *pmrImportDLL  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="1931b-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="1931b-105">Parameters</span></span>  
 `tk`  
 <span data-ttu-id="1931b-106">окне Токен FieldDef или MethodDef для получения метаданных сопоставления PInvoke для.</span><span class="sxs-lookup"><span data-stu-id="1931b-106">[in] A FieldDef or MethodDef token to get the PInvoke mapping metadata for.</span></span>  
  
 `pdwMappingFlags`  
 <span data-ttu-id="1931b-107">заполняет Указатель на флаги, используемые для сопоставления.</span><span class="sxs-lookup"><span data-stu-id="1931b-107">[out] A pointer to flags used for mapping.</span></span> <span data-ttu-id="1931b-108">Это значение является битовой маской из перечисления [CorPinvokeMap](corpinvokemap-enumeration.md) .</span><span class="sxs-lookup"><span data-stu-id="1931b-108">This value is a bitmask from the [CorPinvokeMap](corpinvokemap-enumeration.md) enumeration.</span></span>  
  
 `szImportName`  
 <span data-ttu-id="1931b-109">заполняет Имя неуправляемой целевой библиотеки DLL.</span><span class="sxs-lookup"><span data-stu-id="1931b-109">[out] The name of the unmanaged target DLL.</span></span>  
  
 `cchImportName`  
 <span data-ttu-id="1931b-110">окне Размер в расширенных символах `szImportName` .</span><span class="sxs-lookup"><span data-stu-id="1931b-110">[in] The size in wide characters of `szImportName`.</span></span>  
  
 `pchImportName`  
 <span data-ttu-id="1931b-111">заполняет Число расширенных символов, возвращаемых в `szImportName` .</span><span class="sxs-lookup"><span data-stu-id="1931b-111">[out] The number of wide characters returned in `szImportName`.</span></span>  
  
 `pmrImportDLL`  
 <span data-ttu-id="1931b-112">заполняет Указатель на токен ModuleRef, представляющий неуправляемую библиотеку целевых объектов.</span><span class="sxs-lookup"><span data-stu-id="1931b-112">[out] A pointer to a ModuleRef token that represents the unmanaged target object library.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="1931b-113">Требования</span><span class="sxs-lookup"><span data-stu-id="1931b-113">Requirements</span></span>  
 <span data-ttu-id="1931b-114">**Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="1931b-114">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="1931b-115">**Заголовок:** COR. h</span><span class="sxs-lookup"><span data-stu-id="1931b-115">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="1931b-116">**Библиотека:** Включается в качестве ресурса в библиотеку MsCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="1931b-116">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="1931b-117">**.NET Framework версии:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="1931b-117">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1931b-118">См. также</span><span class="sxs-lookup"><span data-stu-id="1931b-118">See also</span></span>

- [<span data-ttu-id="1931b-119">Интерфейс IMetaDataImport</span><span class="sxs-lookup"><span data-stu-id="1931b-119">IMetaDataImport Interface</span></span>](imetadataimport-interface.md)
- [<span data-ttu-id="1931b-120">Интерфейс IMetaDataImport2</span><span class="sxs-lookup"><span data-stu-id="1931b-120">IMetaDataImport2 Interface</span></span>](imetadataimport2-interface.md)
