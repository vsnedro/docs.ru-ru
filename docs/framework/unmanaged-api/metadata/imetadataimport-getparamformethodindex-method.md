---
title: Метод IMetaDataImport::GetParamForMethodIndex
ms.date: 03/30/2017
api_name:
- IMetaDataImport.GetParamForMethodIndex
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataImport::GetParamForMethodIndex
helpviewer_keywords:
- IMetaDataImport::GetParamForMethodIndex method [.NET Framework metadata]
- GetParamForMethodIndex method [.NET Framework metadata]
ms.assetid: ec3bfa95-1920-4511-932e-3ff23d76fcb8
topic_type:
- apiref
ms.openlocfilehash: 21a83e404405ca9cfe301b76cb1e1591d69e747c
ms.sourcegitcommit: da21fc5a8cce1e028575acf31974681a1bc5aeed
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/08/2020
ms.locfileid: "84491125"
---
# <a name="imetadataimportgetparamformethodindex-method"></a><span data-ttu-id="c5eca-102">Метод IMetaDataImport::GetParamForMethodIndex</span><span class="sxs-lookup"><span data-stu-id="c5eca-102">IMetaDataImport::GetParamForMethodIndex Method</span></span>
<span data-ttu-id="c5eca-103">Возвращает токен, представляющий указанный параметр метода, представленного указанным токеном MethodDef.</span><span class="sxs-lookup"><span data-stu-id="c5eca-103">Gets the token that represents a specified parameter of the method represented by the specified MethodDef token.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c5eca-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="c5eca-104">Syntax</span></span>  
  
```cpp  
HRESULT GetParamForMethodIndex (  
   [in]  mdMethodDef      md,  
   [in]  ULONG            ulParamSeq,  
   [out] mdParamDef       *ppd  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="c5eca-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="c5eca-105">Parameters</span></span>  
 `md`  
 <span data-ttu-id="c5eca-106">окне Токен, представляющий метод, для которого возвращается токен параметра.</span><span class="sxs-lookup"><span data-stu-id="c5eca-106">[in] A token that represents the method to return the parameter token for.</span></span>  
  
 `ulParamSeq`  
 <span data-ttu-id="c5eca-107">окне Порядковый номер в списке параметров, в котором выполняется запрошенный параметр.</span><span class="sxs-lookup"><span data-stu-id="c5eca-107">[in] The ordinal position in the parameter list where the requested parameter occurs.</span></span> <span data-ttu-id="c5eca-108">Параметры нумеруются начиная с единицы, а возвращаемое значение метода в нулевом положении.</span><span class="sxs-lookup"><span data-stu-id="c5eca-108">Parameters are numbered starting from one, with the method's return value in position zero.</span></span>  
  
 `ppd`  
 <span data-ttu-id="c5eca-109">заполняет Указатель на токен Парамдеф, представляющий запрошенный параметр.</span><span class="sxs-lookup"><span data-stu-id="c5eca-109">[out] A pointer to a ParamDef token that represents the requested parameter.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="c5eca-110">Требования</span><span class="sxs-lookup"><span data-stu-id="c5eca-110">Requirements</span></span>  
 <span data-ttu-id="c5eca-111">**Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="c5eca-111">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c5eca-112">**Заголовок:** COR. h</span><span class="sxs-lookup"><span data-stu-id="c5eca-112">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="c5eca-113">**Библиотека:** Включается в качестве ресурса в библиотеку MsCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="c5eca-113">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="c5eca-114">**.NET Framework версии:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="c5eca-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c5eca-115">См. также</span><span class="sxs-lookup"><span data-stu-id="c5eca-115">See also</span></span>

- [<span data-ttu-id="c5eca-116">Интерфейс IMetaDataImport</span><span class="sxs-lookup"><span data-stu-id="c5eca-116">IMetaDataImport Interface</span></span>](imetadataimport-interface.md)
- [<span data-ttu-id="c5eca-117">Интерфейс IMetaDataImport2</span><span class="sxs-lookup"><span data-stu-id="c5eca-117">IMetaDataImport2 Interface</span></span>](imetadataimport2-interface.md)
