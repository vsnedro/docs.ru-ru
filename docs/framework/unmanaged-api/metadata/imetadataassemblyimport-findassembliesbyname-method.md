---
description: 'Дополнительные сведения о методе: IMetaDataAssemblyImport:: Финдассемблиесбинаме'
title: Метод IMetaDataAssemblyImport::FindAssembliesByName
ms.date: 03/30/2017
api_name:
- IMetaDataAssemblyImport.FindAssembliesByName
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataAssemblyImport::FindAssembliesByName
helpviewer_keywords:
- FindAssembliesByName method [.NET Framework metadata]
- IMetaDataAssemblyImport::FindAssembliesByName method [.NET Framework metadata]
ms.assetid: 4db97cf9-e4c1-4233-8efa-cbdc0e14a8e4
topic_type:
- apiref
ms.openlocfilehash: f9c25392cc2c70a0ebc17181b876cf9c6ba03c78
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/06/2021
ms.locfileid: "99789298"
---
# <a name="imetadataassemblyimportfindassembliesbyname-method"></a>Метод IMetaDataAssemblyImport::FindAssembliesByName

Возвращает массив сборок с указанным `szAssemblyName` параметром, используя стандартные правила, используемые средой CLR для разрешения ссылок.  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
HRESULT FindAssembliesByName (  
    [in]  LPCWSTR     szAppBase,
    [in]  LPCWSTR     szPrivateBin,
    [in]  LPCWSTR     szAssemblyName,
    [out] IUnknown    *ppIUnk[],
    [in]  ULONG       cMax,
    [out] ULONG       *pcAssemblies  
);  
```  
  
## <a name="parameters"></a>Параметры  

 `szAppBase`  
 окне Корневой каталог, в котором выполняется поиск данной сборки. Если это значение равно `null` , `FindAssembliesByName` будет искать сборку только в глобальном кэше сборок.  
  
 `szPrivateBin`  
 окне Список подкаталогов, разделенных точкой с запятой (например, "bin; BIN2"), в корневом каталоге, в котором выполняется поиск сборки. Эти каталоги проверяются в дополнение к тем, которые указаны в правилах проверки по умолчанию.  
  
 `szAssemblyName`  
 окне Имя искомой сборки. Формат этой строки определяется на странице ссылки на класс для <xref:System.Reflection.AssemblyName> .  
  
 `ppIUnk`  
 окне Массив типа [IUnknown](/cpp/atl/iunknown) , в который помещаются `IMetadataAssemblyImport` указатели интерфейса.  
  
 `cMax`  
 заполняет Максимальное число указателей интерфейса, которые могут быть помещены в `ppIUnk` .  
  
 `pcAssemblies`  
 заполняет Число возвращаемых указателей на интерфейс. То есть число указателей интерфейса, фактически помещаемых в `ppIUnk` .  
  
## <a name="return-value"></a>Возвращаемое значение  
  
|HRESULT|Описание|  
|-------------|-----------------|  
|`S_OK`|`FindAssembliesByName` успешно возвращено.|  
|`S_FALSE`|Нет сборок.|  
  
## <a name="remarks"></a>Remarks  

 При наличии имени сборки `FindAssembliesByName` метод находит сборку, следуя стандартным правилам разрешения ссылок на сборки. (Дополнительные сведения см. [в разделе Обнаружение сборок в среде выполнения](../../deployment/how-the-runtime-locates-assemblies.md).) `FindAssembliesByName` позволяет вызывающему объекту настраивать различные аспекты контекста сопоставителя сборок, такие как базовый и частный путь поиска приложения.  
  
 `FindAssembliesByName`Метод требует инициализации среды CLR в процессе для вызова логики разрешения сборки. Поэтому необходимо вызвать [CoInitialize](../hosting/coinitializeee-function.md) (передав COINITEE_DEFAULT) перед вызовом `FindAssembliesByName` , а затем выполнить вызов [каунинитиализекор](../hosting/couninitializecor-function.md).  
  
 `FindAssembliesByName` Возвращает указатель [IMetaDataImport](imetadataimport-interface.md) на файл, содержащий манифест сборки для переданного имени сборки. Если заданное имя сборки не указано полностью (например, если оно не включает версию), может возвращаться несколько сборок.  
  
 `FindAssembliesByName` обычно используется компилятором, который пытается найти ссылочную сборку во время компиляции.  
  
## <a name="requirements"></a>Требования  

 **Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).  
  
 **Заголовок:** COR. h  
  
 **Библиотека:** Используется в качестве ресурса в MsCorEE.dll  
  
 **Платформа .NET Framework версии:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>См. также

- [Обнаружение сборок в среде выполнения](../../deployment/how-the-runtime-locates-assemblies.md)
- [Интерфейс IMetaDataAssemblyImport](imetadataassemblyimport-interface.md)
