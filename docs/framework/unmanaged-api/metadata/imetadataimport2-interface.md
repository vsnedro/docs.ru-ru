---
title: Интерфейс IMetaDataImport2
ms.date: 03/30/2017
api_name:
- IMetaDataImport2
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataImport2
helpviewer_keywords:
- IMetaDataImport2 interface [.NET Framework metadata]
ms.assetid: d39b2b87-ba53-4771-ae53-952a68452511
topic_type:
- apiref
ms.openlocfilehash: a845ecfde6583d625d2a8f165443344ff9e40d05
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/24/2020
ms.locfileid: "95702555"
---
# <a name="imetadataimport2-interface"></a><span data-ttu-id="700ab-102">Интерфейс IMetaDataImport2</span><span class="sxs-lookup"><span data-stu-id="700ab-102">IMetaDataImport2 Interface</span></span>

<span data-ttu-id="700ab-103">Расширяет интерфейс [IMetaDataImport](imetadataimport-interface.md) для обеспечения возможности работы с универсальными типами.</span><span class="sxs-lookup"><span data-stu-id="700ab-103">Extends the [IMetaDataImport](imetadataimport-interface.md) interface to provide the capability of working with generic types.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="700ab-104">Методы</span><span class="sxs-lookup"><span data-stu-id="700ab-104">Methods</span></span>  
  
|<span data-ttu-id="700ab-105">Метод</span><span class="sxs-lookup"><span data-stu-id="700ab-105">Method</span></span>|<span data-ttu-id="700ab-106">Описание</span><span class="sxs-lookup"><span data-stu-id="700ab-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="700ab-107">Метод EnumGenericParamConstraints</span><span class="sxs-lookup"><span data-stu-id="700ab-107">EnumGenericParamConstraints Method</span></span>](imetadataimport2-enumgenericparamconstraints-method.md)|<span data-ttu-id="700ab-108">Возвращает перечислитель для массива ограничений универсальных параметров, связанных с универсальным параметром, представленным указанным токеном.</span><span class="sxs-lookup"><span data-stu-id="700ab-108">Gets an enumerator for an array of generic parameter constraints associated with the generic parameter represented by the specified token.</span></span>|  
|[<span data-ttu-id="700ab-109">Метод EnumGenericParams</span><span class="sxs-lookup"><span data-stu-id="700ab-109">EnumGenericParams Method</span></span>](imetadataimport2-enumgenericparams-method.md)|<span data-ttu-id="700ab-110">Возвращает перечислитель для массива маркеров универсальных параметров, связанных с указанным маркером TypeDef или MethodDef.</span><span class="sxs-lookup"><span data-stu-id="700ab-110">Gets an enumerator for an array of generic parameter tokens associated with the specified TypeDef or MethodDef token.</span></span>|  
|[<span data-ttu-id="700ab-111">Метод EnumMethodSpecs</span><span class="sxs-lookup"><span data-stu-id="700ab-111">EnumMethodSpecs Method</span></span>](imetadataimport2-enummethodspecs-method.md)|<span data-ttu-id="700ab-112">Возвращает перечислитель для массива токенов MethodSpec, связанных с указанным токеном MethodDef или MemberRef.</span><span class="sxs-lookup"><span data-stu-id="700ab-112">Gets an enumerator for an array of MethodSpec tokens associated with the specified MethodDef or MemberRef token.</span></span>|  
|[<span data-ttu-id="700ab-113">Метод GetGenericParamConstraintProps</span><span class="sxs-lookup"><span data-stu-id="700ab-113">GetGenericParamConstraintProps Method</span></span>](imetadataimport2-getgenericparamconstraintprops-method.md)|<span data-ttu-id="700ab-114">Возвращает метаданные, связанные с ограничением универсального параметра, представленного указанным маркером ограничения.</span><span class="sxs-lookup"><span data-stu-id="700ab-114">Gets the metadata associated with the generic parameter constraint represented by the specified constraint token.</span></span>|  
|[<span data-ttu-id="700ab-115">Метод GetGenericParamProps</span><span class="sxs-lookup"><span data-stu-id="700ab-115">GetGenericParamProps Method</span></span>](imetadataimport2-getgenericparamprops-method.md)|<span data-ttu-id="700ab-116">Возвращает метаданные, связанные с универсальным параметром, представленным указанным токеном.</span><span class="sxs-lookup"><span data-stu-id="700ab-116">Gets the metadata associated with the generic parameter represented by the specified token.</span></span>|  
|[<span data-ttu-id="700ab-117">Метод GetMethodSpecProps</span><span class="sxs-lookup"><span data-stu-id="700ab-117">GetMethodSpecProps Method</span></span>](imetadataimport2-getmethodspecprops-method.md)|<span data-ttu-id="700ab-118">Возвращает сигнатуру метаданных метода, на который ссылается указанный токен MethodSpec.</span><span class="sxs-lookup"><span data-stu-id="700ab-118">Gets the metadata signature of the method referenced by the specified MethodSpec token.</span></span>|  
|[<span data-ttu-id="700ab-119">Метод GetPEKind</span><span class="sxs-lookup"><span data-stu-id="700ab-119">GetPEKind Method</span></span>](imetadataimport2-getpekind-method.md)|<span data-ttu-id="700ab-120">Возвращает значение, определяющее природу кода в переносимом исполняемом (PE) файле (обычно это DLL или EXE-файл), определенный в текущей области метаданных.</span><span class="sxs-lookup"><span data-stu-id="700ab-120">Gets a value identifying the nature of the code in a portable executable (PE) file, typically a DLL or EXE file, defined in the current metadata scope</span></span>|  
|[<span data-ttu-id="700ab-121">Метод GetVersionString</span><span class="sxs-lookup"><span data-stu-id="700ab-121">GetVersionString Method</span></span>](imetadataimport2-getversionstring-method.md)|<span data-ttu-id="700ab-122">Возвращает номер версии среды выполнения, которая использовалась для построения сборки.</span><span class="sxs-lookup"><span data-stu-id="700ab-122">Gets the version number of the runtime that was used to build the assembly.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="700ab-123">Требования</span><span class="sxs-lookup"><span data-stu-id="700ab-123">Requirements</span></span>  

 <span data-ttu-id="700ab-124">**Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="700ab-124">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="700ab-125">**Заголовок:** COR. h</span><span class="sxs-lookup"><span data-stu-id="700ab-125">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="700ab-126">**Библиотека:** Используется в качестве ресурса в MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="700ab-126">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="700ab-127">**.NET Framework версии:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="700ab-127">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="700ab-128">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="700ab-128">See also</span></span>

- <xref:System.Reflection.PortableExecutableKinds>
- [<span data-ttu-id="700ab-129">Интерфейсы метаданных</span><span class="sxs-lookup"><span data-stu-id="700ab-129">Metadata Interfaces</span></span>](metadata-interfaces.md)
- [<span data-ttu-id="700ab-130">Интерфейс IMetaDataImport</span><span class="sxs-lookup"><span data-stu-id="700ab-130">IMetaDataImport Interface</span></span>](imetadataimport-interface.md)
