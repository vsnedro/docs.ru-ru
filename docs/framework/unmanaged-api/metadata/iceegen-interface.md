---
description: 'Дополнительные сведения о: ICeeGen Interface'
title: Интерфейс ICeeGen
ms.date: 03/30/2017
api_name:
- ICeeGen
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICeeGen
helpviewer_keywords:
- ICeeGen interface [.NET Framework metadata]
ms.assetid: 383d20b0-efe9-4e71-8fb8-1186b2e7d0c0
topic_type:
- apiref
ms.openlocfilehash: 43e9e0696523346ffbcf0b8823a48ed2c9c359e4
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/06/2021
ms.locfileid: "99706816"
---
# <a name="iceegen-interface"></a>Интерфейс ICeeGen

Предоставляет методы для динамической компиляции кода.  
  
 Этот интерфейс устарел и не должен использоваться.  
  
## <a name="methods"></a>Методы  
  
|Метод|Описание|  
|------------|-----------------|  
|[Метод AddSectionReloc](iceegen-addsectionreloc-method.md)|Является устаревшей. Добавляет инструкцию. reloc в базу кода.|  
|[Метод AllocateMethodBuffer](iceegen-allocatemethodbuffer-method.md)|Является устаревшей. Создает буфер указанного размера для метода и получает относительный виртуальный адрес метода.|  
|[Метод ComputePointer](iceegen-computepointer-method.md)|Является устаревшей. Определяет буфер для указанного раздела кода.|  
|[Метод EmitString](iceegen-emitstring-method.md)|Является устаревшей. Порождает указанную строку в базу кода.|  
|[Метод GenerateCeeFile](iceegen-generateceefile-method.md)|Является устаревшей. Создает файл с базовым кодом, который содержит базу кода, загруженную в данный момент `ICeeGen` .|  
|[Метод GenerateCeeMemoryImage](iceegen-generateceememoryimage-method.md)|Является устаревшей. Создает изображение в памяти для базы кода.|  
|[Метод GetIlSection](iceegen-getilsection-method.md)|Является устаревшей. Возвращает раздел базы кода промежуточного языка, на который ссылается указанный обработчик.|  
|[Метод GetIMapTokenIface](iceegen-getimaptokeniface-method.md)|Является устаревшей. Возвращает интерфейс, на который ссылается указанный токен.|  
|[Метод GetMethodBuffer](iceegen-getmethodbuffer-method.md)|Является устаревшей. Возвращает буфер соответствующего размера для метода по указанному относительному виртуальному адресу.|  
|[Метод GetSectionBlock](iceegen-getsectionblock-method.md)|Является устаревшей. Возвращает блок базы кода.|  
|[Метод GetSectionCreate](iceegen-getsectioncreate-method.md)|Является устаревшей. Создает и получает раздел кода, используя указанные значения имени и флага.|  
|[Метод GetSectionDataLen](iceegen-getsectiondatalen-method.md)|Является устаревшей. Возвращает длину указанного раздела.|  
|[Метод GetString](iceegen-getstring-method.md)|Является устаревшей. Возвращает строку, хранящуюся по указанному относительному виртуальному адресу.|  
|[Метод GetStringSection](iceegen-getstringsection-method.md)|Является устаревшей. Возвращает строковое представление раздела кода, на который ссылается указанный маркер.|  
|[Метод TruncateSection](iceegen-truncatesection-method.md)|Является устаревшей. Усекает указанный раздел кода на заданную длину.|  
  
## <a name="requirements"></a>Требования  

 **Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).  
  
 **Заголовок:** COR. h  
  
 **Библиотека:** Используется в качестве ресурса в MsCorEE.dll  
  
 **Платформа .NET Framework версии:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>См. также

- [Интерфейсы метаданных](metadata-interfaces.md)
