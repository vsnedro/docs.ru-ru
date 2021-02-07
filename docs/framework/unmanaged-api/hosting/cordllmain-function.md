---
description: Дополнительные сведения о функции _CorDllMain
title: Функция _CorDllMain
ms.date: 03/30/2017
api_name:
- _CorDllMain
api_location:
- mscoree.dll
api_type:
- DLLExport
f1_keywords:
- _CorDllMain
helpviewer_keywords:
- _CorDllMain function [.NET Framework hosting]
ms.assetid: bc7b51cf-39d3-48ec-a5cb-2f179fbefff8
topic_type:
- apiref
ms.openlocfilehash: 442afae3a627eb684a86c02fbc6e546aa804b7a5
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/06/2021
ms.locfileid: "99717155"
---
# <a name="_cordllmain-function"></a>\_Функция Кордллмаин

Инициализирует среду CLR, находит управляемую точку входа в заголовке CLR сборки DLL и начинает выполнение.  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
BOOL STDMETHODCALLTYPE _CorDllMain (  
   [in] HINSTANCE hInst,  
   [in] DWORD     dwReason,  
   [in] LPVOID    lpReserved  
);  
```  
  
## <a name="parameters"></a>Параметры  

 `hInst`  
 окне Экземпляр загруженного модуля.  
  
 `dwReason`  
 окне Указывает, почему вызывается функция точки входа DLL. Этот параметр может принимать одно из следующих значений: DLL \_ PROCESS_ATTACH, присоединение потока DLL, присоединение \_ потока DLL \_ \_ \_ или \_ Отключение процесса DLL \_ . Описание этих значений см. в документации по `DllMain` Platform SDK.  
  
 `lpReserved`  
 [in] Не используется.  
  
## <a name="return-value"></a>Возвращаемое значение  

 Этот метод возвращает значение `true` для успешного выполнения и `false` при возникновении ошибки.  
  
## <a name="remarks"></a>Remarks  

 Эта функция вызывается загрузчиком операционной системы для сборок DLL. Для исполняемых сборок загрузчик вызывает функцию [ \_ корексемаин](corexemain-function.md) .  
  
 Загрузчик операционной системы вызывает этот метод независимо от точки входа, указанной в файле DLL.  
  
`_CorDllMain`Функция вызывается непосредственно загрузчиком операционной системы.
  
 Дополнительные сведения см. в подразделе "Примечания" раздела [ \_ корвалидатеимаже](corvalidateimage-function.md) .  
  
## <a name="requirements"></a>Требования  

 **Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).  
  
 **Заголовок:** COR. h  
  
 **Библиотека:** Включается в качестве ресурса в MsCorEE.dll  
  
 **Платформа .NET Framework версии:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>См. также

- [Глобальные статические функции метаданных](../metadata/metadata-global-static-functions.md)
