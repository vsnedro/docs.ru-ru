---
title: Метод IMetaDataImport2::GetVersionString
ms.date: 03/30/2017
api_name:
- IMetaDataImport2.GetVersionString
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataImport2::GetVersionString
helpviewer_keywords:
- GetVersionString method, IMetaDataImport2 interface [.NET Framework metadata]
- IMetaDataImport2::GetVersionString method [.NET Framework metadata]
ms.assetid: 308183ee-fd44-4432-9d86-ef00d181b49b
topic_type:
- apiref
ms.openlocfilehash: 84cf5ac9eab5749d3bdc63670fe5c31bfb62abcd
ms.sourcegitcommit: da21fc5a8cce1e028575acf31974681a1bc5aeed
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/08/2020
ms.locfileid: "84490411"
---
# <a name="imetadataimport2getversionstring-method"></a><span data-ttu-id="bd905-102">Метод IMetaDataImport2::GetVersionString</span><span class="sxs-lookup"><span data-stu-id="bd905-102">IMetaDataImport2::GetVersionString Method</span></span>
<span data-ttu-id="bd905-103">Возвращает номер версии среды выполнения, которая использовалась для построения сборки.</span><span class="sxs-lookup"><span data-stu-id="bd905-103">Gets the version number of the runtime that was used to build the assembly.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="bd905-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="bd905-104">Syntax</span></span>  
  
```cpp  
HRESULT GetVersionString (  
   [out] LPWSTR      pwzBuf,  
   [in]  DWORD       ccBufSize,  
   [out] DWORD       *pccBufSize  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="bd905-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="bd905-105">Parameters</span></span>  
 `pwzBuf`  
 <span data-ttu-id="bd905-106">заполняет Массив для хранения строки, указывающей версию.</span><span class="sxs-lookup"><span data-stu-id="bd905-106">[out] An array to store the string that specifies the version.</span></span>  
  
 `ccBufSize`  
 <span data-ttu-id="bd905-107">окне Размер массива в расширенных символах `pwzBuf` .</span><span class="sxs-lookup"><span data-stu-id="bd905-107">[in] The size, in wide characters, of the `pwzBuf` array.</span></span>  
  
 `pccBufSize`  
 <span data-ttu-id="bd905-108">заполняет Число расширенных символов, включая знак завершения null, возвращаемый в `pwzBuf` массиве.</span><span class="sxs-lookup"><span data-stu-id="bd905-108">[out] The number of wide characters, including a null terminator, returned in the `pwzBuf` array.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="bd905-109">Примечания</span><span class="sxs-lookup"><span data-stu-id="bd905-109">Remarks</span></span>  
 <span data-ttu-id="bd905-110">`GetVersionString`Метод получает встроенную версию текущей области метаданных.</span><span class="sxs-lookup"><span data-stu-id="bd905-110">The `GetVersionString` method gets the built-for version of the current metadata scope.</span></span> <span data-ttu-id="bd905-111">Если область не была сохранена, она не будет иметь встроенной версии и будет возвращена пустая строка.</span><span class="sxs-lookup"><span data-stu-id="bd905-111">If the scope has never been saved, it will not have a built-for version, and an empty string will be returned.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="bd905-112">Требования</span><span class="sxs-lookup"><span data-stu-id="bd905-112">Requirements</span></span>  
 <span data-ttu-id="bd905-113">**Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="bd905-113">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="bd905-114">**Заголовок:** COR. h</span><span class="sxs-lookup"><span data-stu-id="bd905-114">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="bd905-115">**Библиотека:** Используется в качестве ресурса в MsCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="bd905-115">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="bd905-116">**.NET Framework версии:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="bd905-116">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bd905-117">См. также</span><span class="sxs-lookup"><span data-stu-id="bd905-117">See also</span></span>

- [<span data-ttu-id="bd905-118">Интерфейс IMetaDataImport2</span><span class="sxs-lookup"><span data-stu-id="bd905-118">IMetaDataImport2 Interface</span></span>](imetadataimport2-interface.md)
- [<span data-ttu-id="bd905-119">Интерфейс IMetaDataImport</span><span class="sxs-lookup"><span data-stu-id="bd905-119">IMetaDataImport Interface</span></span>](imetadataimport-interface.md)
