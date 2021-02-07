---
description: Дополнительные сведения о функции Креатеаппликатионконтекст
title: Функция CreateApplicationContext
ms.date: 03/30/2017
api_name:
- CreateApplicationContext
api_location:
- fusion.dll
api_type:
- DLLExport
f1_keywords:
- CreateApplicationContext
helpviewer_keywords:
- CreateApplicationContext function [.NET Framework fusion]
ms.assetid: 7bf8a141-b2c0-4058-9885-1cef7dcaa811
topic_type:
- apiref
ms.openlocfilehash: f192e1ccc371cb6d50e4a41a286c412825ee4181
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/06/2021
ms.locfileid: "99761187"
---
# <a name="createapplicationcontext-function"></a>Функция CreateApplicationContext

Эта функция поддерживает платформа .NET Frameworkную инфраструктуру и не предназначена для непосредственного использования в коде.  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
HRESULT CreateApplicationContext (  
    [in]  IAssemblyName  *pName,  
    [out] LPPAPPLICATIONCONTEXT  *ppCtx  
 );  
```  
  
## <a name="parameters"></a>Параметры  

 `pName`  
 окне Указатель на понятное имя.  
  
 `ppCtx`  
 заполняет Указатель на контекст приложения.  
  
## <a name="requirements"></a>Требования  

 **Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).  
  
 **Заголовок:** Fusion. h  
  
 **Библиотека:** Включается в качестве ресурса в Fusion.dll  
  
 **Платформа .NET Framework версии:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>См. также

- [Интерфейс IAssemblyCache](iassemblycache-interface.md)
- [Глобальные статические функции Fusion](fusion-global-static-functions.md)
- [Глобальный кэш сборок](../../app-domains/gac.md)
