---
title: Метод IMetaDataImport::GetMemberRefProps
ms.date: 03/30/2017
api_name:
- IMetaDataImport.GetMemberRefProps
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataImport::GetMemberRefProps
helpviewer_keywords:
- GetMemberRefProps method [.NET Framework metadata]
- IMetaDataImport::GetMemberRefProps method [.NET Framework metadata]
ms.assetid: 0ea73055-ece0-4151-a094-414c88ef8941
topic_type:
- apiref
ms.openlocfilehash: 3237b67f8f711e9ef213d6fc66f1513c534fbdeb
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/24/2020
ms.locfileid: "95733208"
---
# <a name="imetadataimportgetmemberrefprops-method"></a><span data-ttu-id="1d5e2-102">Метод IMetaDataImport::GetMemberRefProps</span><span class="sxs-lookup"><span data-stu-id="1d5e2-102">IMetaDataImport::GetMemberRefProps Method</span></span>

<span data-ttu-id="1d5e2-103">Возвращает метаданные, связанные с членом, на который ссылается указанный токен.</span><span class="sxs-lookup"><span data-stu-id="1d5e2-103">Gets metadata associated with the member referenced by the specified token.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="1d5e2-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="1d5e2-104">Syntax</span></span>  
  
```cpp  
HRESULT GetMemberRefProps (  
   [in]  mdMemberRef       mr,
   [out] mdToken           *ptk,
   [out] LPWSTR            szMember,
   [in]  ULONG             cchMember,
   [out] ULONG             *pchMember,
   [out] PCCOR_SIGNATURE   *ppvSigBlob,
   [out] ULONG             *pbSig
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="1d5e2-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="1d5e2-105">Parameters</span></span>  

 `mr`  
 <span data-ttu-id="1d5e2-106">окне Токен MemberRef, для которого возвращаются связанные метаданные.</span><span class="sxs-lookup"><span data-stu-id="1d5e2-106">[in] The MemberRef token to return associated metadata for.</span></span>  
  
 `ptk`  
 <span data-ttu-id="1d5e2-107">заполняет TypeDef или TypeRef, или TypeSpec-токен, представляющий класс, объявляющий член, или токен ModuleRef, представляющий класс Module, объявляющий элемент, или MethodDef, представляющий элемент.</span><span class="sxs-lookup"><span data-stu-id="1d5e2-107">[out] A TypeDef or TypeRef, or TypeSpec token that represents the class that declares the member, or a ModuleRef token that represents the module class that declares the member, or a MethodDef that represents the member.</span></span>  
  
 `szMember`  
 <span data-ttu-id="1d5e2-108">заполняет Строковый буфер для имени члена.</span><span class="sxs-lookup"><span data-stu-id="1d5e2-108">[out] A string buffer for the member's name.</span></span>  
  
 `cchMember`  
 <span data-ttu-id="1d5e2-109">окне Запрошенный размер в расширенных символах `szMember` .</span><span class="sxs-lookup"><span data-stu-id="1d5e2-109">[in] The requested size in wide characters of `szMember`.</span></span>  
  
 `pchMember`  
 <span data-ttu-id="1d5e2-110">заполняет Возвращаемый размер в расширенных символах `szMember` .</span><span class="sxs-lookup"><span data-stu-id="1d5e2-110">[out] The returned size in wide characters of `szMember`.</span></span>  
  
 `ppvSibBlob`  
 <span data-ttu-id="1d5e2-111">заполняет Указатель на сигнатуру двоичных метаданных для элемента.</span><span class="sxs-lookup"><span data-stu-id="1d5e2-111">[out] A pointer to the binary metadata signature for the member.</span></span>  
  
 `pbSig`  
 <span data-ttu-id="1d5e2-112">заполняет Размер в байтах для `ppvSigBlob` .</span><span class="sxs-lookup"><span data-stu-id="1d5e2-112">[out] The size in bytes of `ppvSigBlob`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="1d5e2-113">Требования</span><span class="sxs-lookup"><span data-stu-id="1d5e2-113">Requirements</span></span>  

 <span data-ttu-id="1d5e2-114">**Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="1d5e2-114">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="1d5e2-115">**Заголовок:** COR. h</span><span class="sxs-lookup"><span data-stu-id="1d5e2-115">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="1d5e2-116">**Библиотека:** Включается в качестве ресурса в MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="1d5e2-116">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="1d5e2-117">**.NET Framework версии:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="1d5e2-117">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1d5e2-118">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="1d5e2-118">See also</span></span>

- [<span data-ttu-id="1d5e2-119">Интерфейс IMetaDataImport</span><span class="sxs-lookup"><span data-stu-id="1d5e2-119">IMetaDataImport Interface</span></span>](imetadataimport-interface.md)
- [<span data-ttu-id="1d5e2-120">Интерфейс IMetaDataImport2</span><span class="sxs-lookup"><span data-stu-id="1d5e2-120">IMetaDataImport2 Interface</span></span>](imetadataimport2-interface.md)
