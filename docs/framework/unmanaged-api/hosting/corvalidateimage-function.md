---
title: Функция _CorValidateImage
ms.date: 03/30/2017
api_name:
- _CorValidateImage
api_location:
- mscoree.dll
api_type:
- DLLExport
f1_keywords:
- _CorValidateImage
helpviewer_keywords:
- _CorValidateImage function [.NET Framework hosting]
ms.assetid: 0117e080-05f9-4772-885d-e1847230947c
topic_type:
- apiref
ms.openlocfilehash: 426b39aa3d1ada5ae44565a742b70681a7bcf6d3
ms.sourcegitcommit: da21fc5a8cce1e028575acf31974681a1bc5aeed
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/08/2020
ms.locfileid: "84493478"
---
# <a name="_corvalidateimage-function"></a>Функция _CorValidateImage
Проверяет образы управляемого модуля и уведомляет загрузчик операционной системы после их загрузки.  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
STDAPI _CorValidateImage (
   [in] PVOID* ImageBase,  
   [in] LPCWSTR FileName  
);  
```  
  
## <a name="parameters"></a>Параметры  
 `ImageBase`  
 окне Указатель на начальное расположение изображения для проверки в качестве управляемого кода. Образ уже должен быть загружен в память.  
  
 `FileName`  
 окне Имя файла образа.  
  
## <a name="return-value"></a>Возвращаемое значение  
 Эта функция возвращает стандартные значения `E_INVALIDARG` ,, `E_OUTOFMEMORY` `E_UNEXPECTED` и, а `E_FAIL` также следующие значения.  
  
|Возвращаемое значение|Описание|  
|------------------|-----------------|  
|`STATUS_INVALID_IMAGE_FORMAT`|Недопустимый образ. Это значение имеет 0xC000007BL HRESULT.|  
|`STATUS_SUCCESS`|Изображение является допустимым. Это значение равно HRESULT 0x00000000.|  
  
## <a name="remarks"></a>Примечания  
 В Windows XP и более поздних версиях загрузчик операционной системы проверяет наличие управляемых модулей, проверяя бит каталога дескрипторов COM в заголовке COFF. Заданный бит указывает на управляемый модуль. Если загрузчик обнаруживает управляемый модуль, он загружает библиотеку MsCorEE. dll и вызывает метод `_CorValidateImage` , который выполняет следующие действия:  
  
- Подтверждает, что образ является допустимым управляемым модулем.  
  
- Изменяет точку входа в образе на точку входа в среде CLR.  
  
- Для 64-разрядных версий Windows изменяет образ, наявляющийся в памяти, преобразуя его из формат PE32 в формат формат PE32 +.  
  
- Возвращается загрузчику при загрузке образов управляемого модуля.  
  
 Для исполняемых образов загрузчик операционной системы затем вызывает функцию [_CorExeMain](corexemain-function.md) , независимо от точки входа, указанной в исполняемом файле. Для образов сборки DLL загрузчик вызывает функцию [_CorDllMain](cordllmain-function.md) .  
  
 `_CorExeMain`или `_CorDllMain` выполняет следующие действия.  
  
- Инициализирует среду CLR.  
  
- Находит управляемую точку входа из заголовка CLR сборки.  
  
- Начинает выполнение.  
  
 Загрузчик вызывает функцию [_CorImageUnloading](corimageunloading-function.md) при выгрузке образов управляемых модулей. Однако эта функция не выполняет никаких действий. Он просто возвращает значение.  
  
## <a name="requirements"></a>Требования  
 **Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).  
  
 **Заголовок:** COR. h  
  
 **Библиотека:** Включается в качестве ресурса в библиотеку MsCorEE. dll  
  
 **.NET Framework версии:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>См. также

- [Глобальные статические функции метаданных](../metadata/metadata-global-static-functions.md)
