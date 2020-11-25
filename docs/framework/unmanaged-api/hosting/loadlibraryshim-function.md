---
title: Функция LoadLibraryShim
ms.date: 03/30/2017
api_name:
- LoadLibraryShim
api_location:
- mscoree.dll
- mscoreei.dll
api_type:
- DLLExport
f1_keywords:
- LoadLibraryShim
helpviewer_keywords:
- LoadLibraryShim function [.NET Framework hosting]
ms.assetid: 30931874-4d0e-4df1-b3d1-e425b50655d1
topic_type:
- apiref
ms.openlocfilehash: d5e9ba0023b6516eb6190f32bc65b2b8b6af79f9
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/24/2020
ms.locfileid: "95727566"
---
# <a name="loadlibraryshim-function"></a>Функция LoadLibraryShim

Загружает указанную версию библиотеки DLL, которая входит в состав распространяемого пакета .NET Framework.  
  
 Эта функция является устаревшей в .NET Framework 4. Используйте вместо этого метод [ICLRRuntimeInfo:: LoadLibrary](iclrruntimeinfo-loadlibrary-method.md) .  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
HRESULT LoadLibraryShim (  
    [in]  LPCWSTR  szDllName,  
    [in]  LPCWSTR  szVersion,  
          LPVOID   pvReserved,  
    [out] HMODULE *phModDll  
);  
```  
  
## <a name="parameters"></a>Параметры  

 `szDllName`  
 окне Строка, завершающаяся нулем, которая представляет имя библиотеки DLL, загружаемой из библиотеки .NET Framework.  
  
 `szVersion`  
 окне Строка, заканчивающаяся нулем и представляющая версию загружаемой библиотеки DLL. Если `szVersion` параметр имеет значение null, версия, выбранная для загрузки, является последней версией указанной библиотеки DLL, которая меньше версии 4. То есть все версии, равные или больше версии 4, игнорируются `szVersion` , если имеет значение null, и если не установлена версия, отличная от версии 4, то не удается загрузить библиотеку DLL. Это необходимо для того, чтобы установка .NET Framework 4 не влияла на существующие приложения или компоненты. См. запись [In-Proc SxS и Migration быстрое начало](https://devblogs.microsoft.com/dotnet/in-proc-sxs-and-migration-quick-start/) в блоге команды разработчиков CLR.  
  
 `pvReserved`  
 Зарезервировано для будущего использования.  
  
 `phModDll`  
 заполняет Указатель на маркер модуля.  
  
## <a name="return-value"></a>Возвращаемое значение  

 Этот метод возвращает коды стандартных ошибок модели COM, как определено в файле WinError. h, в дополнение к следующим значениям.  
  
|Код возврата|Описание|  
|-----------------|-----------------|  
|S_OK|Метод завершился успешно.|  
|CLR_E_SHIM_RUNTIMELOAD|`szDllName`Для загрузки требуется загрузка среды CLR, и необходимая версия CLR не может быть загружена.|  
  
## <a name="remarks"></a>Комментарии  

 Эта функция используется для загрузки библиотек DLL, включенных в распространяемый пакет .NET Framework. Он не загружает создаваемые пользователем библиотеки DLL.  
  
> [!NOTE]
> Начиная с версии .NET Framework 2,0, Загрузка Fusion.dll приводит к загрузке среды CLR. Это обусловлено тем, что функции в Fusion.dll теперь являются оболочками, реализации которых предоставляются средой выполнения.  
  
## <a name="requirements"></a>Требования  

 **Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).  
  
 **Заголовок:** MSCorEE. h  
  
 **.NET Framework версии:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>См. также раздел

- [Устаревшие функции размещения CLR](deprecated-clr-hosting-functions.md)
