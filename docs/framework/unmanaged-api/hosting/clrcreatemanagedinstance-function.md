---
description: Дополнительные сведения о функции Клркреатеманажединстанце
title: Функция ClrCreateManagedInstance
ms.date: 03/30/2017
api_name:
- ClrCreateManagedInstance
api_location:
- mscoree.dll
- clr.dll
- mscorwks.dll
- mscoreei.dll
- mscorsvr.dll
api_type:
- DLLExport
f1_keywords:
- ClrCreateManagedInstance
helpviewer_keywords:
- ClrCreateManagedInstance function [.NET Framework hosting]
ms.assetid: 58ba42c0-4857-43bf-a039-73a4dc6544c2
topic_type:
- apiref
ms.openlocfilehash: b6d3b014f54dd563e53cd8a4c48907d01945015f
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/06/2021
ms.locfileid: "99799932"
---
# <a name="clrcreatemanagedinstance-function"></a>Функция ClrCreateManagedInstance

Создает экземпляр указанного управляемого типа.  
  
 Эта функция является устаревшей в платформа .NET Framework 4. Используйте активацию COM для создания экземпляра управляемого типа или используйте размещение (см. Дополнительные сведения о [интерфейсах размещения CLR, добавленных в платформа .NET Framework 4 и 4,5](clr-hosting-interfaces-added-in-the-net-framework-4-and-4-5.md)).  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
STDAPI ClrCreateManagedInstance (  
    [in]  LPCWSTR  pTypeName,
    [in]  REFIID   riid,
    [out] void     **ppObject  
);  
```  
  
## <a name="parameters"></a>Параметры  

 `pTypeName`  
 окне Указатель на имя запрашиваемого типа экземпляра.  
  
 `riid`  
 окне `IID` Тип запрашиваемого типа экземпляра.  
  
 `ppObject`  
 заполняет Указатель на указатель на экземпляр управляемого типа, запрошенный вызывающим объектом.  
  
## <a name="remarks"></a>Remarks  

 Среда CLR уже должна быть загружена в процесс. Например, его можно загрузить с помощью вызова функции [CorBindToRuntimeEx](corbindtoruntimeex-function.md) перед `ClrCreateManagedInstance` вызовом функции. Если среда выполнения не загружена, `ClrCreateManagedInstance` сначала пытается загрузить v 1.0.3705 среды выполнения. В случае сбоя он пытается загрузить последнюю версию среды выполнения.  
  
## <a name="requirements"></a>Требования  

 **Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).  
  
 **Заголовок:** MSCorEE. h  
  
 **Библиотека:** MSCorEE.dll  
  
 **Платформа .NET Framework версии:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>См. также

- [Устаревшие функции размещения CLR](deprecated-clr-hosting-functions.md)
- [Размещение](index.md)
