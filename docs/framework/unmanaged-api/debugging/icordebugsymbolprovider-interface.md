---
title: Интерфейс ICorDebugSymbolProvider
ms.date: 03/30/2017
ms.assetid: 85b24196-b6c6-4bda-9de3-47180bd6ff96
ms.openlocfilehash: ff1f39be3d3db43f70cfa4a0711a3f42c180bc1a
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/24/2020
ms.locfileid: "95672088"
---
# <a name="icordebugsymbolprovider-interface"></a>Интерфейс ICorDebugSymbolProvider

Предоставляет методы, которые могут использоваться для получения сведений об отладочных символах.  
  
## <a name="methods"></a>Методы  
  
|Метод|Описание|  
|------------|-----------------|  
|[Метод GetAssemblyImageBytes](icordebugsymbolprovider-getassemblyimagebytes-method.md)|Считывает данные из объединенной сборки для указанного относительного виртуального адреса (RVA) в объединенной сборке.|  
|[Метод GetAssemblyImageMetadata](icordebugsymbolprovider-getassemblyimagemetadata-method.md)|Возвращает метаданные из объединенной сборки.|  
|[Метод GetCodeRange](icordebugsymbolprovider-getcoderange-method.md)|Получает начальный адрес метода и размер для указанного относительного виртуального адреса (RVA) в методе.|  
|[Метод GetInstanceFieldSymbols](icordebugsymbolprovider-getinstancefieldsymbols-method.md)|Получает символы поля экземпляра, которые соответствуют сигнатуре TypeSpec.|  
|[Метод GetMergedAssemblyRecords](icordebugsymbolprovider-getmergedassemblyrecords-method.md)|Возвращает символьные записи для всех объединенных сборок.|  
|[Метод GetMethodLocalSymbols](icordebugsymbolprovider-getmethodlocalsymbols-method.md)|Получает локальные символы метода с учетом относительного виртуального адреса (RVA) этого метода.|  
|[Метод GetMethodParameterSymbols](icordebugsymbolprovider-getmethodparametersymbols-method.md)|Получает символы параметров метода для указанного относительного виртуального адреса (RVA) этого метода.|  
|[Метод GetMethodProps](icordebugsymbolprovider-getmethodprops-method.md)|Возвращает сведения о свойствах метода, такие как токен метаданных метода и сведения о его универсальных параметрах, для указанного относительного виртуального адреса (RVA) в этом методе.|  
|[Метод GetObjectSize](icordebugsymbolprovider-getobjectsize-method.md)|Возвращает размер объекта для объекта на основе его сигнатуры TypeSpec.|  
|[Метод GetStaticFieldSymbols](icordebugsymbolprovider-getstaticfieldsymbols-method.md)|Получает символы статического поля, которые соответствуют сигнатуре TypeSpec.|  
|[Метод GetTypeProps](icordebugsymbolprovider-gettypeprops-method.md)|Возвращает сведения о свойствах типа, такие как число сигнатур его универсальных параметров, для указанного относительного виртуального адреса (RVA) в таблице VTable.|  
  
## <a name="remarks"></a>Комментарии  
  
> [!NOTE]
> Этот интерфейс доступен только в .NET Native. При реализации этого интерфейса для сценариев ICorDebug вне .NET Native среда CLR будет игнорировать этот интерфейс.  
  
## <a name="requirements"></a>Требования  

 **Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).  
  
 **Заголовок:** CorDebug.idl, CorDebug.h  
  
 **Библиотека:** CorGuids.lib  
  
 **.NET Framework версии:**[!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]  
  
## <a name="see-also"></a>См. также раздел

- [Интерфейсы отладки](debugging-interfaces.md)
- [Отладка](index.md)
