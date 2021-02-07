---
description: Дополнительные сведения о функции Корлаунчаппликатион
title: Функция CorLaunchApplication
ms.date: 03/30/2017
api_name:
- CorLaunchApplication
api_location:
- mscoree.dll
- clr.dll
api_type:
- COM
f1_keywords:
- CorLaunchApplication
helpviewer_keywords:
- CorLaunchApplication function [.NET Framework hosting]
ms.assetid: 71f362a9-8fe2-47ce-9302-05a645cf3d7d
topic_type:
- apiref
ms.openlocfilehash: 89f1f37ddde69fb5ecc24fd9dfd0d0c27d5fac40
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/06/2021
ms.locfileid: "99716956"
---
# <a name="corlaunchapplication-function"></a>Функция CorLaunchApplication

Запускает приложение по указанному сетевому пути, используя указанные манифесты и другие данные приложения.  
  
 Эта функция является устаревшей в платформа .NET Framework 4.  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
HRESULT CorLaunchApplication (  
    [in]  HOST_TYPE                dwClickOnceHost,  
    [in]  LPCWSTR                  pwzAppFullName,  
    [in]  DWORD                    dwManifestPaths,  
    [in]  LPCWSTR                 *ppwzManifestPaths,  
    [in]  DWORD                    dwActivationData,  
    [in]  LPCWSTR                 *ppwzActivationData,  
    [out] LPPROCESS_INFORMATION    lpProcessInformation  
);  
```  
  
## <a name="parameters"></a>Параметры  

 `dwClickOnceHost`  
 окне Значение перечисления [HOST_TYPE](host-type-enumeration.md) , указывающее тип узла, запускающего приложение.  
  
 `pwzAppFullName`  
 окне Полное имя запускаемого приложения.  
  
 `dwManifestPaths`  
 окне Число путей манифеста для приложения.  
  
 `ppwzManifestPaths`  
 окне Массив строк, каждый из которых указывает путь к манифесту запускаемого приложения.  
  
 `dwActivationData`  
 окне Количество элементов данных активации для запускаемого приложения.  
  
 `ppwzActivationData`  
 окне Массив строк, каждый из которых является элементом данных активации для запускаемого приложения.  
  
 `lpProcessInformation`  
 заполняет Указатель на сведения о процессе, в котором было загружено приложение.  
  
## <a name="requirements"></a>Требования  

 **Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).  
  
 **Заголовок:** MSCorEE. h  
  
 **Библиотека:** MSCorEE.dll  
  
 **Платформа .NET Framework версии:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>См. также

- [Устаревшие функции размещения CLR](deprecated-clr-hosting-functions.md)
