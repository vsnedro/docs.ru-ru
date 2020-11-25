---
title: Функция CompareAssemblyIdentity
ms.date: 03/30/2017
api_name:
- CompareAssemblyIdentity
api_location:
- fusion.dll
- clr.dll
api_type:
- COM
f1_keywords:
- CompareAssemblyIdentity
helpviewer_keywords:
- CompareAssemblyIdentity function [.NET Framework fusion]
ms.assetid: 8b364ae1-8efa-4744-a7da-81fd093d84d6
topic_type:
- apiref
ms.openlocfilehash: da32ce6a40378a6f88cf71bd7707be2079d71068
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/24/2020
ms.locfileid: "95717607"
---
# <a name="compareassemblyidentity-function"></a>Функция CompareAssemblyIdentity

Сравнивает два идентификатора сборки, чтобы определить, являются ли они эквивалентными.  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
STDAPI CompareAssemblyIdentity (  
    [in]  LPCWSTR                  pwzAssemblyIdentity1,  
    [in]  BOOL                     fUnified1,  
    [in]  LPCWSTR                  pwzAssemblyIdentity2,  
    [in]  BOOL                     fUnified2,  
    [out] BOOL                     *pfEquivalent,  
    [out] AssemblyComparisonResult *pResult  
 );  
```  
  
## <a name="parameters"></a>Параметры  

 `pwzAssemblyIdentity1`  
 окне Текстовое удостоверение первой сборки в сравнении.  
  
 `fUnified1`  
 окне Логический флаг, который указывает на определенное пользователем унификацию для `pwzAssemblyIdentity1` .  
  
 `pwzAssemblyIdentity2`  
 окне Текстовое удостоверение второй сборки в сравнении.  
  
 `fUnified2`  
 окне Логический флаг, который указывает на определенное пользователем унификацию для `pwzAssemblyIdentity2` .  
  
 `pfEquivalent`  
 заполняет Логический флаг, указывающий, эквивалентны ли две сборки.  
  
 `pResult`  
 заполняет Перечисление [ассембликомпарисонресулт](assemblycomparisonresult-enumeration.md) , содержащее подробные сведения о сравнении.  
  
## <a name="return-value"></a>Возвращаемое значение  

 `pfEquivalent` Возвращает логическое значение, указывающее, эквивалентны ли две сборки. `pResult` Возвращает одно из `AssemblyComparisonResult` значений, чтобы получить более подробную причину для значения `pfEquivalent` .  
  
## <a name="remarks"></a>Комментарии  

 `CompareAssemblyIdentity` проверяет, `pwzAssemblyIdentity1` `pwzAssemblyIdentity2` эквивалентны ли и. `pfEquivalent` задается в `true` одном или нескольких следующих случаях.  
  
- Два удостоверения сборки эквивалентны. Для строго именованных сборок эквивалентность требует идентичности имени сборки, версии, токена открытого ключа и языка и региональных параметров. Для просто именованных сборок эквивалентность требует соответствия имени сборки и языку и региональным параметрам.  
  
- Оба удостоверения сборки ссылаются на сборки, которые выполняются в .NET Framework. Это условие возвращает значение `true` , даже если номера версий сборки не совпадают.  
  
- Эти две сборки не являются управляемыми сборками, но `fUnified1` или имеют `fUnified2` значение `true` .  
  
 `fUnified`Флаг указывает, что все номера версий, вплоть до номера версии строго именованной сборки, считаются эквивалентными сборке со строгим именем. Например, если значение `pwzAssemblyIndentity1` равно "MyAssembly, Version = 3.0.0.0, Culture = Neutral, PublicKeyToken =....", а значение `fUnified1` равно `true` , это означает, что все версии myAssembly от версии 0.0.0.0 до 3.0.0.0 должны рассматриваться как эквивалентные. В этом случае, если `pwzAssemblyIndentity2` ссылается на ту же сборку, что `pwzAssemblyIndentity1` и, за исключением того, что имеет меньший номер версии, устанавливается `pfEquivalent` в значение `true` . Если `pwzAssemblyIdentity2` ссылается на более высокий номер версии, `pfEquivalent` задается `true` только в том случае, если значение `fUnified2` равно `true` .  
  
 `pResult`Параметр содержит конкретные сведения о том, почему две сборки считаются эквивалентными или не эквивалентными. Дополнительные сведения см. в разделе [перечисление ассембликомпарисонресулт](assemblycomparisonresult-enumeration.md).  
  
## <a name="requirements"></a>Требования  

 **Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).  
  
 **Заголовок:** Fusion. h  
  
 **Библиотека:** Включается в качестве ресурса в MsCorEE.dll  
  
 **.NET Framework версии:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>См. также раздел

- [Глобальные статические функции Fusion](fusion-global-static-functions.md)
- [Перечисление AssemblyComparisonResult](assemblycomparisonresult-enumeration.md)
