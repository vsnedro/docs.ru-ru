---
title: Метод IMetaDataImport::ResolveTypeRef
ms.date: 03/30/2017
api_name:
- IMetaDataImport.ResolveTypeRef
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataImport::ResolveTypeRef
helpviewer_keywords:
- ResolveTypeRef method [.NET Framework metadata]
- IMetaDataImport::ResolveTypeRef method [.NET Framework metadata]
ms.assetid: 556bccfb-61bc-4761-b1d5-de4b1c18a38f
topic_type:
- apiref
ms.openlocfilehash: f55af87e21b48430807166cb03e1d41271e830a1
ms.sourcegitcommit: da21fc5a8cce1e028575acf31974681a1bc5aeed
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/08/2020
ms.locfileid: "84503449"
---
# <a name="imetadataimportresolvetyperef-method"></a>Метод IMetaDataImport::ResolveTypeRef
Разрешает <xref:System.Type> ссылку, представленную указанным токеном TypeRef.  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
HRESULT ResolveTypeRef (  
   [in]  mdTypeRef       tr,  
   [in]  REFIID          riid,  
   [out] IUnknown        **ppIScope,  
   [out] mdTypeDef       *ptd  
);  
```  
  
## <a name="parameters"></a>Параметры  
 `tr`  
 окне Токен метаданных TypeRef для возврата сведений о типе, на который указывает ссылка.  
  
 `riid`  
 окне IID интерфейса, в котором возвращается `ppIScope` . Как правило, это IID_IMetaDataImport.  
  
 `ppIScope`  
 заполняет Интерфейс к области модуля, в которой определен ссылочный тип.  
  
 `ptd`  
 заполняет Указатель на маркер TypeDef, представляющий ссылочный тип.  
  
## <a name="remarks"></a>Примечания  
  
> [!IMPORTANT]
> Не используйте этот метод, если загружено несколько доменов приложений. Метод не учитывает границы домена приложения. Если загружено несколько версий сборки и они содержат один и тот же тип с одним и тем же пространством имен, метод возвращает область действия модуля первого найденного типа.  
  
 `ResolveTypeRef`Метод выполняет поиск определения типа в других модулях. Если обнаружено определение типа, `ResolveTypeRef` возвращает интерфейс для этой области модуля, а также маркер TypeDef для типа.  
  
 Если разрешенная ссылка на тип имеет область определения AssemblyRef, `ResolveTypeRef` метод выполняет поиск совпадения только в областях метаданных, которые уже открыты с вызовами метода [IMetaDataDispenser:: OpenScope](imetadatadispenser-openscope-method.md) или [IMetaDataDispenser:: OpenScopeOnMemory](imetadatadispenser-openscopeonmemory-method.md) . Это связано с тем, что `ResolveTypeRef` не может определить только из области AssemblyRef, в которой хранится сборка на диске или в глобальном кэше сборок.  
  
## <a name="requirements"></a>Требования  
 **Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).  
  
 **Заголовок:** COR. h  
  
 **Библиотека:** Включается в качестве ресурса в библиотеку MsCorEE. dll  
  
 **.NET Framework версии:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>См. также

- [Интерфейс IMetaDataImport](imetadataimport-interface.md)
- [Интерфейс IMetaDataImport2](imetadataimport2-interface.md)
