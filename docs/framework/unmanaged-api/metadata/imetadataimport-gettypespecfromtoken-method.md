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
ms.openlocfilehash: 43e9671afa92d36966e51bbdc630db4a9d9083b7
ms.sourcegitcommit: da21fc5a8cce1e028575acf31974681a1bc5aeed
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/08/2020
ms.locfileid: "84503512"
---
# <a name="imetadataimportgettypespecfromtoken-method"></a><span data-ttu-id="85696-102">Метод IMetaDataImport::GetTypeSpecFromToken</span><span class="sxs-lookup"><span data-stu-id="85696-102">IMetaDataImport::GetTypeSpecFromToken Method</span></span>
<span data-ttu-id="85696-103">Возвращает двоичную подпись метаданных для спецификации типа, представленного указанным токеном.</span><span class="sxs-lookup"><span data-stu-id="85696-103">Gets the binary metadata signature of the type specification represented by the specified token.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="85696-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="85696-104">Syntax</span></span>  
  
```cpp  
HRESULT GetTypeSpecFromToken (
   [in]  mdTypeSpec            typespec,
   [out] PCCOR_SIGNATURE       *ppvSig,
   [out] ULONG                 *pcbSig  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="85696-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="85696-105">Parameters</span></span>  
 `typespec`  
 <span data-ttu-id="85696-106">окне Токен TypeSpec, связанный с запрошенной сигнатурой метаданных.</span><span class="sxs-lookup"><span data-stu-id="85696-106">[in] The TypeSpec token associated with the requested metadata signature.</span></span>  
  
 `ppvSig`  
 <span data-ttu-id="85696-107">заполняет Указатель на сигнатуру двоичных метаданных.</span><span class="sxs-lookup"><span data-stu-id="85696-107">[out] A pointer to the binary metadata signature.</span></span>  
  
 `pcbSig`  
 <span data-ttu-id="85696-108">заполняет Размер подписи метаданных в байтах.</span><span class="sxs-lookup"><span data-stu-id="85696-108">[out] The size, in bytes, of the metadata signature.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="85696-109">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="85696-109">Return Value</span></span>  
 <span data-ttu-id="85696-110">Значение HRESULT, указывающее на успешное выполнение или сбой.</span><span class="sxs-lookup"><span data-stu-id="85696-110">An HRESULT that indicates success or failure.</span></span> <span data-ttu-id="85696-111">Сбои можно проверить с помощью макроса FAILed.</span><span class="sxs-lookup"><span data-stu-id="85696-111">Failures can be tested with the FAILED macro.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="85696-112">Требования</span><span class="sxs-lookup"><span data-stu-id="85696-112">Requirements</span></span>  
 <span data-ttu-id="85696-113">**Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="85696-113">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="85696-114">**Заголовок:** COR. h</span><span class="sxs-lookup"><span data-stu-id="85696-114">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="85696-115">**Библиотека:** Включается в качестве ресурса в библиотеку MsCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="85696-115">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="85696-116">**.NET Framework версии:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="85696-116">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="85696-117">См. также</span><span class="sxs-lookup"><span data-stu-id="85696-117">See also</span></span>

- [<span data-ttu-id="85696-118">Интерфейс IMetaDataImport</span><span class="sxs-lookup"><span data-stu-id="85696-118">IMetaDataImport Interface</span></span>](imetadataimport-interface.md)
- [<span data-ttu-id="85696-119">Интерфейс IMetaDataImport2</span><span class="sxs-lookup"><span data-stu-id="85696-119">IMetaDataImport2 Interface</span></span>](imetadataimport2-interface.md)
