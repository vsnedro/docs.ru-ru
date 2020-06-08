---
title: Метод IMetaDataImport::GetEventProps
ms.date: 03/30/2017
api_name:
- IMetaDataImport.GetEventProps
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataImport::GetEventProps
helpviewer_keywords:
- IMetaDataImport::GetEventProps method [.NET Framework metadata]
- GetEventProps method [.NET Framework metadata]
ms.assetid: 5eaf3b4a-92b7-4d5b-97e0-1e83721e0052
topic_type:
- apiref
ms.openlocfilehash: 3b47d1559300a462ccda42bc88da43f66c1043ec
ms.sourcegitcommit: da21fc5a8cce1e028575acf31974681a1bc5aeed
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/08/2020
ms.locfileid: "84491307"
---
# <a name="imetadataimportgeteventprops-method"></a>Метод IMetaDataImport::GetEventProps
Возвращает сведения о метаданных для события, представленного указанным маркером события, включая объявляющий тип, методы добавления и удаления для делегатов, а также любые флаги и другие связанные данные.  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
HRESULT GetEventProps (  
   [in]  mdEvent       ev,  
   [out] mdTypeDef     *pClass,
   [out] LPCWSTR       szEvent,
   [in]  ULONG         cchEvent,
   [out] ULONG         *pchEvent,
   [out] DWORD         *pdwEventFlags,  
   [out] mdToken       *ptkEventType,  
   [out] mdMethodDef   *pmdAddOn,
   [out] mdMethodDef   *pmdRemoveOn,
   [out] mdMethodDef   *pmdFire,
   [out] mdMethodDef   rmdOtherMethod[],
   [in]  ULONG         cMax,  
   [out] ULONG         *pcOtherMethod  
);  
```  
  
## <a name="parameters"></a>Параметры  
 `ev`  
 окне Токен метаданных события, представляющий событие, для которого необходимо получить метаданные.  
  
 `pClass`  
 заполняет Указатель на маркер TypeDef, представляющий класс, объявляющий событие.  
  
 `szEvent`  
 заполняет Имя события, на которое ссылается `ev` .  
  
 `pchEvent`  
 окне Запрошенная длина в расширенных символах `szEvent` .  
  
 `pdwEventFlags`  
 заполняет Возвращаемая длина в расширенных символах `szEvent` .  
  
 `ptkEventType`  
 заполняет Указатель на маркер метаданных TypeRef или TypeDef, представляющий <xref:System.Delegate> Тип события.  
  
 `pmdAddOn`  
 заполняет Указатель на маркер метаданных, представляющий метод, который добавляет обработчики для события.  
  
 `pmdRemoveOn`  
 заполняет Указатель на маркер метаданных, представляющий метод, который удаляет обработчики для события.  
  
 `pmdFire`  
 заполняет Указатель на маркер метаданных, представляющий метод, который вызывает событие.  
  
 `rmdOtherMethod`  
 заполняет Массив указателей токенов на другие методы, связанные с событием.  
  
 `cMax`  
 [in] Максимальный размер массива `rmdOtherMethod`.  
  
 `pcOtherMethod`  
 заполняет Число токенов, возвращаемых в `rmdOtherMethod` .  
  
## <a name="requirements"></a>Требования  
 **Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).  
  
 **Заголовок:** COR. h  
  
 **Библиотека:** Включается в качестве ресурса в библиотеку MsCorEE. dll  
  
 **.NET Framework версии:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>См. также

- [Интерфейс IMetaDataImport](imetadataimport-interface.md)
- [Интерфейс IMetaDataImport2](imetadataimport2-interface.md)
