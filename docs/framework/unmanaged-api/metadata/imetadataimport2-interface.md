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
ms.openlocfilehash: fe9e87618291218a41e52f80198ce9068c9c56e2
ms.sourcegitcommit: da21fc5a8cce1e028575acf31974681a1bc5aeed
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/08/2020
ms.locfileid: "84490402"
---
# <a name="imetadataimport2-interface"></a>Интерфейс IMetaDataImport2
Расширяет интерфейс [IMetaDataImport](imetadataimport-interface.md) для обеспечения возможности работы с универсальными типами.  
  
## <a name="methods"></a>Методы  
  
|Метод|Описание|  
|------------|-----------------|  
|[Метод EnumGenericParamConstraints](imetadataimport2-enumgenericparamconstraints-method.md)|Возвращает перечислитель для массива ограничений универсальных параметров, связанных с универсальным параметром, представленным указанным токеном.|  
|[Метод EnumGenericParams](imetadataimport2-enumgenericparams-method.md)|Возвращает перечислитель для массива маркеров универсальных параметров, связанных с указанным маркером TypeDef или MethodDef.|  
|[Метод EnumMethodSpecs](imetadataimport2-enummethodspecs-method.md)|Возвращает перечислитель для массива токенов MethodSpec, связанных с указанным токеном MethodDef или MemberRef.|  
|[Метод GetGenericParamConstraintProps](imetadataimport2-getgenericparamconstraintprops-method.md)|Возвращает метаданные, связанные с ограничением универсального параметра, представленного указанным маркером ограничения.|  
|[Метод GetGenericParamProps](imetadataimport2-getgenericparamprops-method.md)|Возвращает метаданные, связанные с универсальным параметром, представленным указанным токеном.|  
|[Метод GetMethodSpecProps](imetadataimport2-getmethodspecprops-method.md)|Возвращает сигнатуру метаданных метода, на который ссылается указанный токен MethodSpec.|  
|[Метод GetPEKind](imetadataimport2-getpekind-method.md)|Возвращает значение, определяющее природу кода в переносимом исполняемом (PE) файле (обычно это DLL или EXE-файл), определенный в текущей области метаданных.|  
|[Метод GetVersionString](imetadataimport2-getversionstring-method.md)|Возвращает номер версии среды выполнения, которая использовалась для построения сборки.|  
  
## <a name="requirements"></a>Требования  
 **Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).  
  
 **Заголовок:** COR. h  
  
 **Библиотека:** Используется в качестве ресурса в MsCorEE. dll  
  
 **.NET Framework версии:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>См. также

- <xref:System.Reflection.PortableExecutableKinds>
- [Интерфейсы метаданных](metadata-interfaces.md)
- [Интерфейс IMetaDataImport](imetadataimport-interface.md)
