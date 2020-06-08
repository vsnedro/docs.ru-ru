---
title: Метод IMetaDataImport::GetSigFromToken
ms.date: 03/30/2017
api_name:
- IMetaDataImport.GetSigFromToken
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataImport::GetSigFromToken
helpviewer_keywords:
- IMetaDataImport::GetSigFromToken method [.NET Framework metadata]
- GetSigFromToken method [.NET Framework metadata]
ms.assetid: ab894dc4-f7b6-4afc-bfcb-582a4b7e53a2
topic_type:
- apiref
ms.openlocfilehash: d795f90c458b7fcf1a191b2763ac5f5bb55fb438
ms.sourcegitcommit: da21fc5a8cce1e028575acf31974681a1bc5aeed
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/08/2020
ms.locfileid: "84490905"
---
# <a name="imetadataimportgetsigfromtoken-method"></a><span data-ttu-id="a03f6-102">Метод IMetaDataImport::GetSigFromToken</span><span class="sxs-lookup"><span data-stu-id="a03f6-102">IMetaDataImport::GetSigFromToken Method</span></span>
<span data-ttu-id="a03f6-103">Возвращает двоичную подпись метаданных, связанную с указанным токеном.</span><span class="sxs-lookup"><span data-stu-id="a03f6-103">Gets the binary metadata signature associated with the specified token.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a03f6-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="a03f6-104">Syntax</span></span>  
  
```cpp  
HRESULT GetSigFromToken (
   [in]   mdSignature        mdSig,
   [out]  PCCOR_SIGNATURE    *ppvSig,
   [out]  ULONG              *pcbSig
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="a03f6-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="a03f6-105">Parameters</span></span>  
 `mdSig`  
 <span data-ttu-id="a03f6-106">окне Токен, для которого возвращается сигнатура двоичных метаданных.</span><span class="sxs-lookup"><span data-stu-id="a03f6-106">[in] The token to return the binary metadata signature for.</span></span>  
  
 `ppvSig`  
 <span data-ttu-id="a03f6-107">заполняет Указатель на возвращаемую сигнатуру метаданных.</span><span class="sxs-lookup"><span data-stu-id="a03f6-107">[out] A pointer to the returned metadata signature.</span></span>  
  
 `pcbSig`  
 <span data-ttu-id="a03f6-108">заполняет Размер в байтах двоичной подписи метаданных.</span><span class="sxs-lookup"><span data-stu-id="a03f6-108">[out] The size in bytes of the binary metadata signature.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="a03f6-109">Требования</span><span class="sxs-lookup"><span data-stu-id="a03f6-109">Requirements</span></span>  
 <span data-ttu-id="a03f6-110">**Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="a03f6-110">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="a03f6-111">**Заголовок:** COR. h</span><span class="sxs-lookup"><span data-stu-id="a03f6-111">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="a03f6-112">**Библиотека:** Включается в качестве ресурса в библиотеку MsCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="a03f6-112">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="a03f6-113">**.NET Framework версии:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="a03f6-113">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a03f6-114">См. также</span><span class="sxs-lookup"><span data-stu-id="a03f6-114">See also</span></span>

- [<span data-ttu-id="a03f6-115">Интерфейс IMetaDataImport</span><span class="sxs-lookup"><span data-stu-id="a03f6-115">IMetaDataImport Interface</span></span>](imetadataimport-interface.md)
- [<span data-ttu-id="a03f6-116">Интерфейс IMetaDataImport2</span><span class="sxs-lookup"><span data-stu-id="a03f6-116">IMetaDataImport2 Interface</span></span>](imetadataimport2-interface.md)
