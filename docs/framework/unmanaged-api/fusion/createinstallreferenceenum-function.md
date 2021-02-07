---
description: Дополнительные сведения о функции CreateInstallReferenceEnum
title: Функция CreateInstallReferenceEnum
ms.date: 03/30/2017
api_name:
- CreateInstallReferenceEnum
api_location:
- fusion.dll
- clr.dll
- mscorwks.dll
api_type:
- DLLExport
f1_keywords:
- CreateInstallReference
helpviewer_keywords:
- CreateInstallReference function [.NET Framework fusion]
ms.assetid: 80dbbbf8-54fc-4894-b74a-0179d3201083
topic_type:
- apiref
ms.openlocfilehash: cc7551707cb46bcf0c475a0095684dbc790836e3
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/06/2021
ms.locfileid: "99761155"
---
# <a name="createinstallreferenceenum-function"></a>Функция CreateInstallReferenceEnum

Возвращает указатель на экземпляр [IInstallReferenceEnum](iinstallreferenceenum-interface.md) , представляющий список ссылок приложения на указанную сборку.  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
HRESULT CreateInstallReferenceEnum (  
    [out] IInstallReferenceEnum **ppRefEnum,  
    [in]  IAssemblyName         *pName,  
    [in]  DWORD                 dwFlags,  
    [in]  LPVOID                pvReserved  
 );  
```  
  
## <a name="parameters"></a>Параметры  

 `ppRefEnum`  
 заполняет Возвращаемый `IInstallReferenceEnum` указатель.  
  
 `pName`  
 окне Объект [IAssemblyName](iassemblyname-interface.md) , определяющий сборку, для которой перечисляются ссылки.  
  
 `dwFlags`  
 окне Флаги, влияющие на поведение перечислителя.  
  
 `pvReserved`  
 окне Зарезервировано для будущего расширения. `pvReserved` должен быть пустой ссылкой.  
  
## <a name="requirements"></a>Требования  

 **Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).  
  
 **Заголовок:** Fusion. h  
  
 **Библиотека:** Fusion.dll и Mscorwks.dll. Используйте Fusion.dll вместо Mscorwks.dll, чтобы убедиться в правильности целевой версии платформа .NET Framework.  
  
 **Платформа .NET Framework версии:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>См. также

- [Интерфейс IInstallReferenceEnum](iinstallreferenceenum-interface.md)
- [Интерфейс IAssemblyName](iassemblyname-interface.md)
- [Глобальные статические функции Fusion](fusion-global-static-functions.md)
