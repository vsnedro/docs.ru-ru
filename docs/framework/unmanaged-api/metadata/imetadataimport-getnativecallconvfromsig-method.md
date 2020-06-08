---
title: Метод IMetaDataImport::GetNativeCallConvFromSig
ms.date: 03/30/2017
api_name:
- IMetaDataImport.GetNativeCallConvFromSig
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataImport::GetNativeCallConvFromSig
helpviewer_keywords:
- GetNativeCallConvFromSig method [.NET Framework metadata]
- IMetaDataImport::GetNativeCallConvFromSig method [.NET Framework metadata]
ms.assetid: 50e04026-4d4a-47d9-96c1-f4677d6d938b
topic_type:
- apiref
ms.openlocfilehash: 44439eda62f85c32893b73f17bd057195cf6b2e1
ms.sourcegitcommit: da21fc5a8cce1e028575acf31974681a1bc5aeed
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/08/2020
ms.locfileid: "84503553"
---
# <a name="imetadataimportgetnativecallconvfromsig-method"></a><span data-ttu-id="b6441-102">Метод IMetaDataImport::GetNativeCallConvFromSig</span><span class="sxs-lookup"><span data-stu-id="b6441-102">IMetaDataImport::GetNativeCallConvFromSig Method</span></span>
<span data-ttu-id="b6441-103">Возвращает собственное соглашение о вызовах для метода, представленного заданным указателем на подпись.</span><span class="sxs-lookup"><span data-stu-id="b6441-103">Gets the native calling convention for the method that is represented by the specified signature pointer.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b6441-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="b6441-104">Syntax</span></span>  
  
```cpp  
HRESULT GetNativeCallConvFromSig (  
   [in]  void const  *pvSig,  
   [in]  ULONG       cbSig,  
   [out] ULONG       *pCallConv  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="b6441-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="b6441-105">Parameters</span></span>  
 `pvSig`  
 <span data-ttu-id="b6441-106">окне Указатель на сигнатуру метаданных метода, для которого возвращается соглашение о вызовах.</span><span class="sxs-lookup"><span data-stu-id="b6441-106">[in] A pointer to the metadata signature of the method to return the calling convention for.</span></span>  
  
 `cbSig`  
 <span data-ttu-id="b6441-107">окне Размер в байтах для `pvSig` .</span><span class="sxs-lookup"><span data-stu-id="b6441-107">[in] The size in bytes of `pvSig`.</span></span>  
  
 `pCallConv`  
 <span data-ttu-id="b6441-108">заполняет Указатель на собственное соглашение о вызовах.</span><span class="sxs-lookup"><span data-stu-id="b6441-108">[out] A pointer to the native calling convention.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="b6441-109">Требования</span><span class="sxs-lookup"><span data-stu-id="b6441-109">Requirements</span></span>  
 <span data-ttu-id="b6441-110">**Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="b6441-110">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="b6441-111">**Заголовок:** COR. h</span><span class="sxs-lookup"><span data-stu-id="b6441-111">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="b6441-112">**Библиотека:** Включается в качестве ресурса в библиотеку MsCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="b6441-112">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="b6441-113">**.NET Framework версии:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="b6441-113">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b6441-114">См. также</span><span class="sxs-lookup"><span data-stu-id="b6441-114">See also</span></span>

- <xref:System.Runtime.InteropServices.CallingConvention>
- [<span data-ttu-id="b6441-115">Интерфейс IMetaDataImport</span><span class="sxs-lookup"><span data-stu-id="b6441-115">IMetaDataImport Interface</span></span>](imetadataimport-interface.md)
- [<span data-ttu-id="b6441-116">Интерфейс IMetaDataImport2</span><span class="sxs-lookup"><span data-stu-id="b6441-116">IMetaDataImport2 Interface</span></span>](imetadataimport2-interface.md)
