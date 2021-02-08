---
description: Дополнительные сведения о перечислении Вритеаблеметадатаупдатемоде
title: Перечисление WriteableMetadataUpdateMode
ms.date: 03/30/2017
dev_langs:
- cpp
api_name:
- WriteableMetadataUpdateMode
api_location:
- mscordbi.dll
api_type:
- COM
ms.assetid: 6758f4d3-6bc7-4c99-8582-e9be00566784
topic_type:
- apiref
ms.openlocfilehash: b8136963e315c429643bd0ebf4bdb509d5173bec
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/06/2021
ms.locfileid: "99800517"
---
# <a name="writeablemetadataupdatemode-enumeration"></a>Перечисление WriteableMetadataUpdateMode

[Поддерживается в .NET Framework 4.5.2 и более поздних версиях.]  
  
 Предоставляет значения, указывающие, будут ли видны в отладчике обновления копии метаданных в памяти.  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp
typedef enum WriteableMetadataUpdateMode {  
   LegacyCompatPolicy,  
   AlwaysShowUpdates  
} WriteableMetadataUpdateMode;  
```  
  
## <a name="members"></a>Члены  
  
|Имя участника|Описание|  
|-----------------|-----------------|  
|`LegacyCompatPolicy`|Поддерживает совместимость с предыдущими версиями платформы .NET Framework, делая видимыми обновления находящихся в памяти метаданных. Дополнительные сведения см. в разделе "Примечания".|  
|`AlwaysShowUpdates`|Делает обновления находящихся в памяти метаданных видимыми в отладчике.|  
  
## <a name="remarks"></a>Remarks  

 Член `WriteableMetadataUpdateMode` перечисления может быть передан методу [SetWriteableMetadataUpdateMode](icordebugprocess7-setwriteablemetadataupdatemode-method.md) для управления тем, являются ли обновления в памяти в целевом процессе доступными для отладчика.  
  
 Параметр `LegacyCompatPolicy` обеспечивает такое же поведение, как и до версии 4.5.2 платформы .NET Framework. Чаще всего это означает, что метаданные из обновлений не видны. В то же время вызовы ряда методов отладчика неявно вынуждают его делать обновления видимыми. Например, если отладчик передает [ICorDebugILFrame:: жетлокалвариабле](icordebugilframe-getlocalvariable-method.md) индекс переменной, не найденной в исходных метаданных метода, все метаданные модуля обновляются до моментального снимка, соответствующего текущему состоянию процесса. Другими словами, при наличии параметра `LegacyCompatPolicy` отладчик может не видеть вообще, видеть частично или видеть все доступные обновления метаданных в зависимости от того, как он использует другие части неуправляемого API отладки.  
  
## <a name="requirements"></a>Требования  

 **Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).  
  
 **Заголовок:** CorDebug.idl, CorDebug.h  
  
 **Библиотека:** CorGuids.lib  
  
 **Платформа .NET Framework версии:**[!INCLUDE[net_current_v452plus](../../../../includes/net-current-v452plus-md.md)]  
  
## <a name="see-also"></a>См. также

- [Перечисления отладки](debugging-enumerations.md)
- [Метод SetWriteableMetadataUpdateMode](icordebugprocess7-setwriteablemetadataupdatemode-method.md)
