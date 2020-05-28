---
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
ms.openlocfilehash: e6cf0aa6f731d0a417e1a2be0ca1d0f8c9299379
ms.sourcegitcommit: 03fec33630b46e78d5e81e91b40518f32c4bd7b5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/27/2020
ms.locfileid: "84008278"
---
# <a name="iceegen-interface"></a>Интерфейс ICeeGen
Предоставляет методы для динамической компиляции кода.  
  
 Этот интерфейс устарел и не должен использоваться.  
  
## <a name="methods"></a>Методы  
  
|Метод|Описание|  
|------------|-----------------|  
|[Метод AddSectionReloc](iceegen-addsectionreloc-method.md)|Устаревшее. Добавляет инструкцию. reloc в базу кода.|  
|[Метод AllocateMethodBuffer](iceegen-allocatemethodbuffer-method.md)|Устаревшее. Создает буфер указанного размера для метода и получает относительный виртуальный адрес метода.|  
|[Метод ComputePointer](iceegen-computepointer-method.md)|Устаревшее. Определяет буфер для указанного раздела кода.|  
|[Метод EmitString](iceegen-emitstring-method.md)|Устаревшее. Порождает указанную строку в базу кода.|  
|[Метод GenerateCeeFile](iceegen-generateceefile-method.md)|Устаревшее. Создает файл с базовым кодом, который содержит базу кода, загруженную в данный момент `ICeeGen` .|  
|[Метод GenerateCeeMemoryImage](iceegen-generateceememoryimage-method.md)|Устаревшее. Создает изображение в памяти для базы кода.|  
|[Метод GetIlSection](iceegen-getilsection-method.md)|Устаревшее. Возвращает раздел базы кода промежуточного языка, на который ссылается указанный обработчик.|  
|[Метод GetIMapTokenIface](iceegen-getimaptokeniface-method.md)|Устаревшее. Возвращает интерфейс, на который ссылается указанный токен.|  
|[Метод GetMethodBuffer](iceegen-getmethodbuffer-method.md)|Устаревшее. Возвращает буфер соответствующего размера для метода по указанному относительному виртуальному адресу.|  
|[Метод GetSectionBlock](iceegen-getsectionblock-method.md)|Устаревшее. Возвращает блок базы кода.|  
|[Метод GetSectionCreate](iceegen-getsectioncreate-method.md)|Устаревшее. Создает и получает раздел кода, используя указанные значения имени и флага.|  
|[Метод GetSectionDataLen](iceegen-getsectiondatalen-method.md)|Устаревшее. Возвращает длину указанного раздела.|  
|[Метод GetString](iceegen-getstring-method.md)|Устаревшее. Возвращает строку, хранящуюся по указанному относительному виртуальному адресу.|  
|[Метод GetStringSection](iceegen-getstringsection-method.md)|Устаревшее. Возвращает строковое представление раздела кода, на который ссылается указанный маркер.|  
|[Метод TruncateSection](iceegen-truncatesection-method.md)|Устаревшее. Усекает указанный раздел кода на заданную длину.|  
  
## <a name="requirements"></a>Требования  
 **Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).  
  
 **Заголовок:** COR. h  
  
 **Библиотека:** Используется в качестве ресурса в MsCorEE. dll  
  
 **.NET Framework версии:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>См. также статью

- [Интерфейсы метаданных](metadata-interfaces.md)
