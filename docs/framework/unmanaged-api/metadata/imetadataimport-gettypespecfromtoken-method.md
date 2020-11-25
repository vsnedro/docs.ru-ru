---
title: Метод IMetaDataImport::GetTypeSpecFromToken
ms.date: 03/30/2017
api_name:
- IMetaDataImport.GetTypeSpecFromToken
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataImport::GetTypeSpecFromToken
helpviewer_keywords:
- GetTypeSpecFromToken method [.NET Framework metadata]
- IMetaDataImport::GetTypeSpecFromToken method [.NET Framework metadata]
ms.assetid: ee518bda-3296-482e-a7b7-e9d51dd1a181
topic_type:
- apiref
ms.openlocfilehash: 62495aa4280bb1799af09fea2e550ae6107e09e9
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/24/2020
ms.locfileid: "95729152"
---
# <a name="imetadataimportgettypespecfromtoken-method"></a><span data-ttu-id="bb674-102">Метод IMetaDataImport::GetTypeSpecFromToken</span><span class="sxs-lookup"><span data-stu-id="bb674-102">IMetaDataImport::GetTypeSpecFromToken Method</span></span>

<span data-ttu-id="bb674-103">Возвращает двоичную подпись метаданных для спецификации типа, представленного указанным токеном.</span><span class="sxs-lookup"><span data-stu-id="bb674-103">Gets the binary metadata signature of the type specification represented by the specified token.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="bb674-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="bb674-104">Syntax</span></span>  
  
```cpp  
HRESULT GetTypeSpecFromToken (
   [in]  mdTypeSpec            typespec,
   [out] PCCOR_SIGNATURE       *ppvSig,
   [out] ULONG                 *pcbSig  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="bb674-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="bb674-105">Parameters</span></span>  

 `typespec`  
 <span data-ttu-id="bb674-106">окне Токен TypeSpec, связанный с запрошенной сигнатурой метаданных.</span><span class="sxs-lookup"><span data-stu-id="bb674-106">[in] The TypeSpec token associated with the requested metadata signature.</span></span>  
  
 `ppvSig`  
 <span data-ttu-id="bb674-107">заполняет Указатель на сигнатуру двоичных метаданных.</span><span class="sxs-lookup"><span data-stu-id="bb674-107">[out] A pointer to the binary metadata signature.</span></span>  
  
 `pcbSig`  
 <span data-ttu-id="bb674-108">заполняет Размер подписи метаданных в байтах.</span><span class="sxs-lookup"><span data-stu-id="bb674-108">[out] The size, in bytes, of the metadata signature.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="bb674-109">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="bb674-109">Return Value</span></span>  

 <span data-ttu-id="bb674-110">Значение HRESULT, указывающее на успешное выполнение или сбой.</span><span class="sxs-lookup"><span data-stu-id="bb674-110">An HRESULT that indicates success or failure.</span></span> <span data-ttu-id="bb674-111">Сбои можно проверить с помощью макроса FAILed.</span><span class="sxs-lookup"><span data-stu-id="bb674-111">Failures can be tested with the FAILED macro.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="bb674-112">Требования</span><span class="sxs-lookup"><span data-stu-id="bb674-112">Requirements</span></span>  

 <span data-ttu-id="bb674-113">**Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="bb674-113">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="bb674-114">**Заголовок:** COR. h</span><span class="sxs-lookup"><span data-stu-id="bb674-114">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="bb674-115">**Библиотека:** Включается в качестве ресурса в MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="bb674-115">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="bb674-116">**.NET Framework версии:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="bb674-116">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bb674-117">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="bb674-117">See also</span></span>

- [<span data-ttu-id="bb674-118">Интерфейс IMetaDataImport</span><span class="sxs-lookup"><span data-stu-id="bb674-118">IMetaDataImport Interface</span></span>](imetadataimport-interface.md)
- [<span data-ttu-id="bb674-119">Интерфейс IMetaDataImport2</span><span class="sxs-lookup"><span data-stu-id="bb674-119">IMetaDataImport2 Interface</span></span>](imetadataimport2-interface.md)
