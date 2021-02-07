---
description: 'Дополнительные сведения о методе: ICorPublishAppDomain:: Name'
title: Метод ICorPublishAppDomain::GetName
ms.date: 03/30/2017
api_name:
- ICorPublishAppDomain.GetName
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorPublishAppDomain::GetName
helpviewer_keywords:
- GetName method, ICorPublishAppDomain interface [.NET Framework debugging]
- ICorPublishAppDomain::GetName method [.NET Framework debugging]
ms.assetid: 6ef8ac9b-9803-4b65-8b13-25f3e0b1bc6b
topic_type:
- apiref
ms.openlocfilehash: 05b1b14f7e0db371b29059ec3d44333ac40428e9
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/06/2021
ms.locfileid: "99721805"
---
# <a name="icorpublishappdomaingetname-method"></a>Метод ICorPublishAppDomain::GetName

Возвращает имя домена приложения, представленного этим [ICorPublishAppDomain](icorpublishappdomain-interface.md).  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
HRESULT GetName (  
    [in]  ULONG32   cchName,
    [out] ULONG32   *pcchName,  
    [out, size_is(cchName), length_is(*pcchName)]
        WCHAR       *szName  
);  
```  
  
## <a name="parameters"></a>Параметры  

 `cchName`  
 [in] Размер массива `szName`.  
  
 `pcchName`  
 заполняет Указатель на число расширенных символов, включая символ null, возвращаемый в `szName` массиве.  
  
 `szName`  
 заполняет Массив, в котором сохраняется имя.  
  
## <a name="remarks"></a>Remarks  

 Если `szName` параметр имеет значение, отличное от NULL, `GetName` метод копирует до `cchName` символов (включая знак завершения null) в `szName` . Если в возвращается значение, отличное от NULL `pcchName` , то фактическое число символов в имени (включая знак завершения null) сохраняется в `szName` массиве.  
  
 `GetName`Метод возвращает S_OK HRESULT, независимо от количества скопированных символов.  
  
## <a name="requirements"></a>Требования  

 **Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).  
  
 **Заголовок:** Корпуб. idl, Корпуб. h  
  
 **Библиотека:** CorGuids.lib  
  
 **Платформа .NET Framework версии:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>См. также

- [Интерфейс ICorPublishAppDomain](icorpublishappdomain-interface.md)
