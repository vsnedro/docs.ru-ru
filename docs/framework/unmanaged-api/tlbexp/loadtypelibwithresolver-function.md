---
description: Дополнительные сведения о функции LoadTypeLibWithResolver
title: Функция LoadTypeLibWithResolver
ms.date: 03/30/2017
api_name:
- LoadTypeLibWithResolver
api_location:
- TlbRef.dll
api_type:
- DLLExport
f1_keywords:
- LoadTypeLibWithResolver
helpviewer_keywords:
- LoadTypeLibWithResolver function [.NET Framework]
ms.assetid: 7123a89b-eb9b-463a-a552-a081e33b0a3a
topic_type:
- apiref
ms.openlocfilehash: 6747199364a549d922ad73bfac3e93b329d1172a
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/06/2021
ms.locfileid: "99646222"
---
# <a name="loadtypelibwithresolver-function"></a>Функция LoadTypeLibWithResolver

Загружает библиотеку типов и использует предоставляемый [интерфейс итипелибресолвер](itypelibresolver-interface.md) для разрешения любых библиотек типов, на которые имеются ссылки.  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
HRESULT LoadTypeLibWithResolver(  
    [in]  LPCOLESTR           szFile,  
    [in]  REGKIND             regkind,  
    [in]  ITypeLibResolver   *pTlbResolver,  
    [out] ITypeLib          **pptlib);  
```  
  
## <a name="parameters"></a>Параметры  

 `szFile`  
 окне Путь к файлу библиотеки типов.  
  
 `regkind`  
 окне Флаг [перечисления регкинд](/windows/win32/api/oleauto/ne-oleauto-regkind) , управляющий регистрацией библиотеки типов. Возможные значения:  
  
- `REGKIND_DEFAULT`: Использовать поведение регистрации по умолчанию.  
  
- `REGKIND_REGISTER`: Зарегистрируйте эту библиотеку типов.  
  
- `REGKIND_NONE`: Не регистрировать эту библиотеку типов.  
  
 `pTlbResolver`  
 окне Указатель на реализацию [интерфейса итипелибресолвер](itypelibresolver-interface.md).  
  
 `pptlib`  
 заполняет Ссылка на загружаемую библиотеку типов.  
  
## <a name="return-value"></a>Возвращаемое значение  

 Одно из значений HRESULT, перечисленных в следующей таблице.  
  
|Возвращаемое значение|Значение|  
|------------------|-------------|  
|`S_OK`|Успешно.|  
|`E_OUTOFMEMORY`|Недостаточно памяти.|  
|`E_POINTER`|Один или несколько указателей являются недопустимыми.|  
|`E_INVALIDARG`|Один или несколько аргументов являются недопустимыми.|  
|`TYPE_E_IOERROR`|Функции не удалось выполнить запись в файл.|  
|`TYPE_E_REGISTRYACCESS`|Не удалось открыть базу данных регистрации системы.|  
|`TYPE_E_INVALIDSTATE`|Не удалось открыть библиотеку типов.|  
|`TYPE_E_CANTLOADLIBRARY`|Не удалось загрузить библиотеку типов или библиотеку DLL.|  
  
## <a name="remarks"></a>Remarks  

 [Tlbexp.exe (программа экспорта библиотек типов)](../../tools/tlbexp-exe-type-library-exporter.md) вызывает `LoadTypeLibWithResolver` функцию во время преобразования сборки в библиотеку типов.  
  
 Эта функция загружает указанную библиотеку типов с минимальным доступом к реестру. Затем функция проверяет библиотеку типов для внутренних ссылочных библиотек типов, каждая из которых должна быть загружена и добавлена в родительскую библиотеку типов.  
  
 Прежде чем можно будет загрузить библиотеку типов, на которую указывает ссылка, путь к файлу ссылки должен быть разрешаться в полный путь к файлу. Это осуществляется с помощью [метода ресолветипелиб](resolvetypelib-method.md) , предоставляемого [интерфейсом итипелибресолвер](itypelibresolver-interface.md), который передается в `pTlbResolver` параметре.  
  
 Если известен полный путь к файлу библиотеки типов, на которую указывает ссылка, `LoadTypeLibWithResolver` функция загружает и добавляет библиотеку типов, на которую указывает ссылка, в родительскую библиотеку типов, создавая объединенную библиотеку типов Master.  
  
 После того как функция разрешает и загружает все библиотеки типов, на которые имеются ссылки, она возвращает ссылку на библиотеку разрешенных шаблонов в `pptlib` параметре.  
  
 `LoadTypeLibWithResolver`Функция обычно вызывается [Tlbexp.exe (программа экспорта библиотек типов)](../../tools/tlbexp-exe-type-library-exporter.md), которая предоставляет собственную реализацию внутреннего [интерфейса итипелибресолвер](itypelibresolver-interface.md) в `pTlbResolver` параметре.  
  
 При вызове `LoadTypeLibWithResolver` напрямую необходимо предоставить собственную реализацию [интерфейса итипелибресолвер](itypelibresolver-interface.md) .  
  
## <a name="requirements"></a>Требования  

 **Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).  
  
 **Заголовок:** Тлбреф. h  
  
 **Библиотека:** Тлбреф. lib  
  
 **Версия платформа .NET Framework:** 3,5, 3,0, 2,0  
  
## <a name="see-also"></a>См. также

- [Вспомогательные функции Tlbexp](index.md)
- [Функция Лоадтипелибекс](/previous-versions/windows/desktop/api/oleauto/nf-oleauto-loadtypelibex)
