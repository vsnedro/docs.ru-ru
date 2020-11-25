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
ms.openlocfilehash: 67abdfd8f8c67299eae757533f20df69392f25b8
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/24/2020
ms.locfileid: "95729191"
---
# <a name="imetadataimportgetsigfromtoken-method"></a><span data-ttu-id="6042e-102">Метод IMetaDataImport::GetSigFromToken</span><span class="sxs-lookup"><span data-stu-id="6042e-102">IMetaDataImport::GetSigFromToken Method</span></span>

<span data-ttu-id="6042e-103">Возвращает двоичную подпись метаданных, связанную с указанным токеном.</span><span class="sxs-lookup"><span data-stu-id="6042e-103">Gets the binary metadata signature associated with the specified token.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6042e-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="6042e-104">Syntax</span></span>  
  
```cpp  
HRESULT GetSigFromToken (
   [in]   mdSignature        mdSig,
   [out]  PCCOR_SIGNATURE    *ppvSig,
   [out]  ULONG              *pcbSig
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="6042e-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="6042e-105">Parameters</span></span>  

 `mdSig`  
 <span data-ttu-id="6042e-106">окне Токен, для которого возвращается сигнатура двоичных метаданных.</span><span class="sxs-lookup"><span data-stu-id="6042e-106">[in] The token to return the binary metadata signature for.</span></span>  
  
 `ppvSig`  
 <span data-ttu-id="6042e-107">заполняет Указатель на возвращаемую сигнатуру метаданных.</span><span class="sxs-lookup"><span data-stu-id="6042e-107">[out] A pointer to the returned metadata signature.</span></span>  
  
 `pcbSig`  
 <span data-ttu-id="6042e-108">заполняет Размер в байтах двоичной подписи метаданных.</span><span class="sxs-lookup"><span data-stu-id="6042e-108">[out] The size in bytes of the binary metadata signature.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="6042e-109">Требования</span><span class="sxs-lookup"><span data-stu-id="6042e-109">Requirements</span></span>  

 <span data-ttu-id="6042e-110">**Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="6042e-110">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="6042e-111">**Заголовок:** COR. h</span><span class="sxs-lookup"><span data-stu-id="6042e-111">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="6042e-112">**Библиотека:** Включается в качестве ресурса в MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="6042e-112">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="6042e-113">**.NET Framework версии:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="6042e-113">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6042e-114">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="6042e-114">See also</span></span>

- [<span data-ttu-id="6042e-115">Интерфейс IMetaDataImport</span><span class="sxs-lookup"><span data-stu-id="6042e-115">IMetaDataImport Interface</span></span>](imetadataimport-interface.md)
- [<span data-ttu-id="6042e-116">Интерфейс IMetaDataImport2</span><span class="sxs-lookup"><span data-stu-id="6042e-116">IMetaDataImport2 Interface</span></span>](imetadataimport2-interface.md)
