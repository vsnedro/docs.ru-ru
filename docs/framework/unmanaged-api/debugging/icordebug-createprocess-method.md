---
description: 'Дополнительные сведения: метод ICorDebug:: CreateProcess'
title: Метод ICorDebug::CreateProcess
ms.date: 03/30/2017
api_name:
- ICorDebug.CreateProcess
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebug::CreateProcess
helpviewer_keywords:
- ICorDebug::CreateProcess method [.NET Framework debugging]
- CreateProcess method, ICorDebugProcess interface [.NET Framework debugging]
ms.assetid: b6128694-11ed-46e7-bd4e-49ea1914c46a
topic_type:
- apiref
ms.openlocfilehash: b504b5f7a60fd0fd4a8f8f1c5d8e3c3b8dcfd858
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/06/2021
ms.locfileid: "99712120"
---
# <a name="icordebugcreateprocess-method"></a>Метод ICorDebug::CreateProcess

Запускает процесс и его основной поток под управлением отладчика.  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
HRESULT CreateProcess (  
    [in]  LPCWSTR                     lpApplicationName,  
    [in]  LPWSTR                      lpCommandLine,  
    [in]  LPSECURITY_ATTRIBUTES       lpProcessAttributes,  
    [in]  LPSECURITY_ATTRIBUTES       lpThreadAttributes,  
    [in]  BOOL                        bInheritHandles,  
    [in]  DWORD                       dwCreationFlags,  
    [in]  PVOID                       lpEnvironment,  
    [in]  LPCWSTR                     lpCurrentDirectory,  
    [in]  LPSTARTUPINFOW              lpStartupInfo,  
    [in]  LPPROCESS_INFORMATION       lpProcessInformation,  
    [in]  CorDebugCreateProcessFlags  debuggingFlags,  
    [out] ICorDebugProcess            **ppProcess  
);  
```  
  
## <a name="parameters"></a>Параметры  

 `lpApplicationName`  
 окне Указатель на строку, завершающуюся нулем, которая указывает модуль, выполняемый запущенным процессом. Модуль выполняется в контексте безопасности вызывающего процесса.  
  
 `lpCommandLine`  
 окне Указатель на строку, завершающуюся нулем, которая указывает командную строку, выполняемую запущенным процессом. Имя приложения (например, "SomeApp.exe") должно быть первым аргументом.  
  
 `lpProcessAttributes`  
 окне Указатель на структуру Win32 `SECURITY_ATTRIBUTES` , указывающую дескриптор безопасности для процесса. Если значение `lpProcessAttributes` равно null, процесс получает дескриптор безопасности по умолчанию.  
  
 `lpThreadAttributes`  
 окне Указатель на структуру Win32 `SECURITY_ATTRIBUTES` , указывающую дескриптор безопасности для основного потока процесса. Если значение `lpThreadAttributes` равно null, то поток получает дескриптор безопасности по умолчанию.  
  
 `bInheritHandles`  
 окне Задайте значение, `true` чтобы указать, что каждый наследуемый дескриптор в вызывающем процессе наследуется запущенным процессом, или `false` чтобы указать, что дескрипторы не наследуются. Унаследованные дескрипторы имеют те же значения и права доступа, что и исходные дескрипторы.  
  
 `dwCreationFlags`  
 окне Побитовое сочетание [флагов создания процесса Win32](/windows/win32/procthread/process-creation-flags) , управляющих классом приоритета и поведением запущенного процесса.  
  
 `lpEnvironment`  
 окне Указатель на блок среды для нового процесса.  
  
 `lpCurrentDirectory`  
 окне Указатель на строку, завершающуюся нулем, которая указывает полный путь к текущему каталогу для процесса. Если этот параметр имеет значение null, то новый процесс будет иметь тот же текущий диск и каталог, что и вызывающий процесс.  
  
 `lpStartupInfo`  
 окне Указатель на структуру Win32 `STARTUPINFOW` , указывающую станцию окон, Рабочий стол, стандартные маркеры и внешний вид главного окна для запущенного процесса.  
  
 `lpProcessInformation`  
 окне Указатель на структуру Win32 `PROCESS_INFORMATION` , указывающую идентификационную информацию о процессе, который необходимо запустить.  
  
 `debuggingFlags`  
 окне Значение перечисления Кордебугкреатепроцессфлагс, определяющее параметры отладки.  
  
 `ppProcess`  
 заполняет Указатель на адрес объекта ICorDebugProcess, который представляет процесс.  
  
## <a name="remarks"></a>Remarks  

 Параметры этого метода совпадают с параметрами `CreateProcess` метода Win32.  
  
 Чтобы включить неуправляемую отладку в смешанном режиме, задайте для параметра значение `dwCreationFlags` DEBUG_PROCESS &#124; DEBUG_ONLY_THIS_PROCESS. Если вы хотите использовать только управляемую отладку, не устанавливайте эти флаги.  
  
 Если отладчик и отлаживаемый процесс (присоединенный процесс) совместно используют одну консоль, и если используется отладка взаимодействия, то присоединенный процесс может содержать блокировки консоли и останавливать при отладке события. Отладчик будет блокировать любые попытки использования консоли. Чтобы избежать этой проблемы, установите флаг CREATE_NEW_CONSOLE в `dwCreationFlags` параметре.  
  
 Отладка взаимодействия не поддерживается на платформах Win9x и на платформе, отличной от x86, например на платформах на основе IA-64 и AMD64.  
  
## <a name="requirements"></a>Требования  

 **Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).  
  
 **Заголовок:** CorDebug.idl, CorDebug.h  
  
 **Библиотека:** CorGuids.lib  
  
 **Платформа .NET Framework версии:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>См. также

- [Интерфейс ICorDebug](icordebug-interface.md)
