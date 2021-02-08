---
description: 'Дополнительные сведения о: <PreferComInsteadOfManagedRemoting> element'
title: Элемент <PreferComInsteadOfManagedRemoting>
ms.date: 03/30/2017
helpviewer_keywords:
- <PreferComInsteadOfManagedRemoting> element
- PreferComInsteadOfManagedRemoting element
ms.assetid: a279a42a-c415-4e79-88cf-64244ebda613
ms.openlocfilehash: b621af9b584d1ea2623ffe5a44f74b5b7bd520e7
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/06/2021
ms.locfileid: "99782277"
---
# <a name="prefercominsteadofmanagedremoting-element"></a>Элемент \<PreferComInsteadOfManagedRemoting>

Указывает, будет ли среда выполнения использовать COM-взаимодействие вместо удаленного взаимодействия для всех вызовов через границы домена приложения.  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<runtime>**](runtime-element.md)\
&nbsp;&nbsp;&nbsp;&nbsp;**\<PreferComInsteadOfManagedRemoting>**  
  
## <a name="syntax"></a>Синтаксис  
  
```xml  
<PreferComInsteadOfManagedRemoting enabled="true|false"/>  
```  
  
## <a name="attributes-and-elements"></a>Атрибуты и элементы  

 В следующих разделах описаны атрибуты, дочерние и родительские элементы.  
  
### <a name="attributes"></a>Атрибуты  
  
|Атрибут|Описание|  
|---------------|-----------------|  
|`enabled`|Обязательный атрибут.<br /><br /> Указывает, будет ли среда выполнения использовать COM-взаимодействие вместо удаленного взаимодействия через границы домена приложения.|  
  
## <a name="enabled-attribute"></a>Атрибут enabled  
  
|Значение|Описание|  
|-----------|-----------------|  
|`false`|Среда выполнения будет использовать удаленное взаимодействие через границы домена приложения. Это значение по умолчанию.|  
|`true`|Среда выполнения будет использовать COM-взаимодействие через границы домена приложения.|  
  
### <a name="child-elements"></a>Дочерние элементы  

 Отсутствует.  
  
### <a name="parent-elements"></a>Родительские элементы  
  
|Элемент|Описание|  
|-------------|-----------------|  
|`configuration`|Корневой элемент в любом файле конфигурации, используемом средой CLR и приложениями .NET Framework.|  
|`runtime`|Содержит сведения о привязке сборок и сборке мусора.|  
  
## <a name="remarks"></a>Remarks  

 Если `enabled` для атрибута задано значение `true` , среда выполнения ведет себя следующим образом:  
  
- Среда выполнения не вызывает [IUnknown:: QueryInterface](/windows/win32/api/unknwn/nf-unknwn-iunknown-queryinterface(q)) для интерфейса [IManagedObject](../../../unmanaged-api/hosting/imanagedobject-interface.md) , когда интерфейс [IUnknown](/windows/win32/api/unknwn/nn-unknwn-iunknown) входит в домен через интерфейс COM. Вместо этого он формирует [вызываемую оболочку времени выполнения](../../../../standard/native-interop/runtime-callable-wrapper.md) (RCW) вокруг объекта.  
  
- Среда выполнения возвращает E_NOINTERFACE при получении `QueryInterface` вызова для интерфейса [IManagedObject](../../../unmanaged-api/hosting/imanagedobject-interface.md) для любой [вызываемой оболочки com](../../../../standard/native-interop/com-callable-wrapper.md) (CCW), созданной в этом домене.  
  
 Эти два поведения гарантируют, что все вызовы через COM-интерфейсы между управляемыми объектами в границах доменов приложений используют COM и COM-взаимодействие вместо удаленного взаимодействия.  
  
## <a name="example"></a>Пример  

 В следующем примере показано, как указать, что среда выполнения должна использовать COM-взаимодействие через границы изоляции:  
  
```xml  
<configuration>  
  <runtime>  
    <PreferComInsteadOfManagedRemoting enabled="true"/>  
  </runtime>  
</configuration>  
```  
  
## <a name="see-also"></a>См. также

- [Схема параметров среды выполнения](index.md)
- [Схема файла конфигурации](../index.md)
