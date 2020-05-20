---
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
ms.openlocfilehash: 3b2322f708afed08172f87e843c225aa9c60d9d3
ms.sourcegitcommit: 27db07ffb26f76912feefba7b884313547410db5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/19/2020
ms.locfileid: "83616610"
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
  
## <a name="remarks"></a>Комментарии  
 Эта функция вызывается загрузчиком операционной системы для сборок DLL. Для исполняемых сборок загрузчик вызывает функцию [ \_ корексемаин](corexemain-function.md) .  
  
 Загрузчик операционной системы вызывает этот метод независимо от точки входа, указанной в файле DLL.  
  
`_CorDllMain`Функция вызывается непосредственно загрузчиком операционной системы.
  
 Дополнительные сведения см. в подразделе "Примечания" раздела [ \_ корвалидатеимаже](corvalidateimage-function.md) .  
  
## <a name="requirements"></a>Требования  

 **Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).  
  
 **Заголовок:** COR. h  
  
 **Библиотека:** Включается в качестве ресурса в библиотеку MsCorEE. dll  
  
 **.NET Framework версии:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>См. также статью

- [Глобальные статические функции метаданных](../metadata/metadata-global-static-functions.md)
