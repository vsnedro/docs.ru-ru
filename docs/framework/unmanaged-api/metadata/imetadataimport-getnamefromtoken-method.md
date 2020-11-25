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
ms.openlocfilehash: 867fb0ee4bc1a093eb7fd46e25497d585c4d9b6b
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/24/2020
ms.locfileid: "95727501"
---
# <a name="imetadataimportgetnamefromtoken-method"></a><span data-ttu-id="c5a85-102">Метод IMetaDataImport::GetNameFromToken</span><span class="sxs-lookup"><span data-stu-id="c5a85-102">IMetaDataImport::GetNameFromToken Method</span></span>

<span data-ttu-id="c5a85-103">Возвращает имя объекта, на который ссылается указанный токен метаданных, в формате UTF-8.</span><span class="sxs-lookup"><span data-stu-id="c5a85-103">Gets the UTF-8 name of the object referenced by the specified metadata token.</span></span> <span data-ttu-id="c5a85-104">Этот метод устарел.</span><span class="sxs-lookup"><span data-stu-id="c5a85-104">This method is obsolete.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c5a85-105">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="c5a85-105">Syntax</span></span>  
  
```cpp  
HRESULT GetNameFromToken (  
   [in] mdToken      tk,  
   [out] MDUTF8CSTR  *pszUtf8NamePtr  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="c5a85-106">Параметры</span><span class="sxs-lookup"><span data-stu-id="c5a85-106">Parameters</span></span>  

 `tk`  
 <span data-ttu-id="c5a85-107">окне Токен, представляющий объект, для которого возвращается имя.</span><span class="sxs-lookup"><span data-stu-id="c5a85-107">[in] The token representing the object to return the name for.</span></span>  
  
 `pszUtf8NamePtr`  
 <span data-ttu-id="c5a85-108">заполняет Указатель на имя объекта UTF-8 в куче.</span><span class="sxs-lookup"><span data-stu-id="c5a85-108">[out] A pointer to the UTF-8 object name in the heap.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="c5a85-109">Комментарии</span><span class="sxs-lookup"><span data-stu-id="c5a85-109">Remarks</span></span>  

 <span data-ttu-id="c5a85-110">`GetNameFromToken` устарел.</span><span class="sxs-lookup"><span data-stu-id="c5a85-110">`GetNameFromToken` is obsolete.</span></span> <span data-ttu-id="c5a85-111">В качестве альтернативы можно вызвать метод, чтобы получить свойства требуемого типа токена, например `GetFieldProps` для поля или `GetMethodProps` для метода.</span><span class="sxs-lookup"><span data-stu-id="c5a85-111">As an alternative, call a method to get the properties of the particular type of token required, such as `GetFieldProps` for a field or `GetMethodProps` for a method.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="c5a85-112">Требования</span><span class="sxs-lookup"><span data-stu-id="c5a85-112">Requirements</span></span>  

 <span data-ttu-id="c5a85-113">**Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="c5a85-113">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c5a85-114">**Заголовок:** COR. h</span><span class="sxs-lookup"><span data-stu-id="c5a85-114">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="c5a85-115">**Библиотека:** Включается в качестве ресурса в MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="c5a85-115">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="c5a85-116">**.NET Framework версии:** 1,0</span><span class="sxs-lookup"><span data-stu-id="c5a85-116">**.NET Framework Versions:** 1.0</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c5a85-117">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="c5a85-117">See also</span></span>

- [<span data-ttu-id="c5a85-118">Интерфейс IMetaDataImport</span><span class="sxs-lookup"><span data-stu-id="c5a85-118">IMetaDataImport Interface</span></span>](imetadataimport-interface.md)
- [<span data-ttu-id="c5a85-119">Интерфейс IMetaDataImport2</span><span class="sxs-lookup"><span data-stu-id="c5a85-119">IMetaDataImport2 Interface</span></span>](imetadataimport2-interface.md)
