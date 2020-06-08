---
title: Метод IMetaDataImport::GetNameFromToken
ms.date: 03/30/2017
api_name:
- IMetaDataImport.GetNameFromToken
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataImport::GetNameFromToken
helpviewer_keywords:
- GetNameFromToken method [.NET Framework metadata]
- IMetaDataImport::GetNameFromToken method [.NET Framework metadata]
ms.assetid: 32114ecf-8916-4ab2-a201-179c017344f1
topic_type:
- apiref
ms.openlocfilehash: 6d62739148280c7333cf7cdb6002b59a145496e3
ms.sourcegitcommit: da21fc5a8cce1e028575acf31974681a1bc5aeed
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/08/2020
ms.locfileid: "84503566"
---
# <a name="imetadataimportgetnamefromtoken-method"></a><span data-ttu-id="78028-102">Метод IMetaDataImport::GetNameFromToken</span><span class="sxs-lookup"><span data-stu-id="78028-102">IMetaDataImport::GetNameFromToken Method</span></span>
<span data-ttu-id="78028-103">Возвращает имя объекта, на который ссылается указанный токен метаданных, в формате UTF-8.</span><span class="sxs-lookup"><span data-stu-id="78028-103">Gets the UTF-8 name of the object referenced by the specified metadata token.</span></span> <span data-ttu-id="78028-104">Этот метод устарел.</span><span class="sxs-lookup"><span data-stu-id="78028-104">This method is obsolete.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="78028-105">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="78028-105">Syntax</span></span>  
  
```cpp  
HRESULT GetNameFromToken (  
   [in] mdToken      tk,  
   [out] MDUTF8CSTR  *pszUtf8NamePtr  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="78028-106">Параметры</span><span class="sxs-lookup"><span data-stu-id="78028-106">Parameters</span></span>  
 `tk`  
 <span data-ttu-id="78028-107">окне Токен, представляющий объект, для которого возвращается имя.</span><span class="sxs-lookup"><span data-stu-id="78028-107">[in] The token representing the object to return the name for.</span></span>  
  
 `pszUtf8NamePtr`  
 <span data-ttu-id="78028-108">заполняет Указатель на имя объекта UTF-8 в куче.</span><span class="sxs-lookup"><span data-stu-id="78028-108">[out] A pointer to the UTF-8 object name in the heap.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="78028-109">Примечания</span><span class="sxs-lookup"><span data-stu-id="78028-109">Remarks</span></span>  
 <span data-ttu-id="78028-110">`GetNameFromToken` устарел.</span><span class="sxs-lookup"><span data-stu-id="78028-110">`GetNameFromToken` is obsolete.</span></span> <span data-ttu-id="78028-111">В качестве альтернативы можно вызвать метод, чтобы получить свойства требуемого типа токена, например `GetFieldProps` для поля или `GetMethodProps` для метода.</span><span class="sxs-lookup"><span data-stu-id="78028-111">As an alternative, call a method to get the properties of the particular type of token required, such as `GetFieldProps` for a field or `GetMethodProps` for a method.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="78028-112">Требования</span><span class="sxs-lookup"><span data-stu-id="78028-112">Requirements</span></span>  
 <span data-ttu-id="78028-113">**Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="78028-113">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="78028-114">**Заголовок:** COR. h</span><span class="sxs-lookup"><span data-stu-id="78028-114">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="78028-115">**Библиотека:** Включается в качестве ресурса в библиотеку MsCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="78028-115">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="78028-116">**.NET Framework версии:** 1,0</span><span class="sxs-lookup"><span data-stu-id="78028-116">**.NET Framework Versions:** 1.0</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="78028-117">См. также</span><span class="sxs-lookup"><span data-stu-id="78028-117">See also</span></span>

- [<span data-ttu-id="78028-118">Интерфейс IMetaDataImport</span><span class="sxs-lookup"><span data-stu-id="78028-118">IMetaDataImport Interface</span></span>](imetadataimport-interface.md)
- [<span data-ttu-id="78028-119">Интерфейс IMetaDataImport2</span><span class="sxs-lookup"><span data-stu-id="78028-119">IMetaDataImport2 Interface</span></span>](imetadataimport2-interface.md)
