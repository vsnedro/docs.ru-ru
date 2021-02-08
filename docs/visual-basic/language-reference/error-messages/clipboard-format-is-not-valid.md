---
description: 'Дополнительные сведения о: недопустимый формат буфера обмена'
title: Недопустимый формат буфера обмена
ms.date: 07/20/2015
f1_keywords:
- vbrID460
ms.assetid: 71a4a045-65bb-417d-b3bd-99a9fa3c53f6
ms.openlocfilehash: 58ba6197a14b005cf61d0783e19cb3f957dd2fca
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/06/2021
ms.locfileid: "99796760"
---
# <a name="clipboard-format-is-not-valid"></a>Недопустимый формат буфера обмена

Указанный формат буфера обмена несовместим с выполняемым методом. Среди возможных причин этой ошибки:  
  
- Использование `GetText` метода или буфера обмена `SetText` с форматом буфера обмена, отличным `vbCFText` от или `vbCFLink` .  
  
- Использование `GetData` метода или буфера обмена `SetData` с форматом буфера обмена, отличным от `vbCFBitmap` , `vbCFDIB` или `vbCFMetafile` .  
  
- Использование `GetData` методов или `SetData` объекта `DataObject` с форматом буфера обмена в диапазоне, зарезервированном Microsoft Windows для зарегистрированных форматов (&HC000-&хфффф), если этот формат буфера обмена не зарегистрирован в Microsoft Windows.  
  
## <a name="to-correct-this-error"></a>Исправление ошибки  
  
- Удалите недопустимый формат и укажите допустимый.  
  
## <a name="see-also"></a>См. также

- [Буфер обмена: Добавление других форматов](/cpp/mfc/clipboard-adding-other-formats)
