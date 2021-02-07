---
description: 'Дополнительные сведения о: <bypassTrustedAppStrongNames> element'
title: Элемент <bypassTrustedAppStrongNames>
ms.date: 03/30/2017
helpviewer_keywords:
- strong-name bypass feature
- bypassTrustedAppStrongNames element
- strong-named assemblies, loading into trusted application domains
- <bypassTrustedAppStrongNames> element
ms.assetid: 71b2ebf6-3843-41e2-ad52-ffa5cd083a40
ms.openlocfilehash: d23b9efa19481027480f2a1c7dab22bc97a05e13
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/06/2021
ms.locfileid: "99719166"
---
# <a name="bypasstrustedappstrongnames-element"></a>Элемент \<bypassTrustedAppStrongNames>

Указывает, следует ли обходить проверку строгих имен в сборках с полным доверием, загружаемых в полное доверие <xref:System.AppDomain> .

[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<runtime>**](runtime-element.md)\
&nbsp;&nbsp;&nbsp;&nbsp;**\<bypassTrustedAppStrongNames>**

## <a name="syntax"></a>Синтаксис

```xml
<bypassTrustedAppStrongNames
   enabled="true|false"/>
```

## <a name="attributes-and-elements"></a>Атрибуты и элементы

В следующих разделах описаны атрибуты, дочерние и родительские элементы.

### <a name="attributes"></a>Атрибуты

|Атрибут|Описание|
|---------------|-----------------|
|`enabled`|Обязательный атрибут.<br /><br /> Указывает, включена ли функция обхода, которая не позволяет проверять строгие имена для сборок с полным доверием. Если эта функция включена, строгие имена не проверяются на правильность при загрузке сборки. Значение по умолчанию — `true`.|

## <a name="enabled-attribute"></a>Атрибут enabled

|Значение|Описание|
|-----------|-----------------|
|`true`|Подписи строгого имени в сборках с полным доверием не проверяются при загрузке сборок в режиме полного доверия <xref:System.AppDomain> . Это значение по умолчанию.|
|`false`|Подписи строгого имени в сборках с полным доверием проверяются при загрузке сборок в режиме полного доверия <xref:System.AppDomain> . Подпись строгого имени проверяется только на правильность сигнатуры; оно не сравнивается с другим строгим именем для соответствия.|

### <a name="child-elements"></a>Дочерние элементы

Отсутствует.

### <a name="parent-elements"></a>Родительские элементы

|Элемент|Описание|
|-------------|-----------------|
|`configuration`|Корневой элемент в любом файле конфигурации, используемом средой CLR и приложениями .NET Framework.|
|`runtime`|Содержит сведения о привязке сборок и сборке мусора.|

## <a name="remarks"></a>Remarks

Функция пропуска строгих имен позволяет избежать дополнительных затрат на проверку подписи строгого имени сборок с полным доверием.

Функция обхода применима к любой сборке, подписанной со строгим именем и имеющей следующие характеристики.

- Полное доверие без <xref:System.Security.Policy.StrongName> свидетельства (например, наличие `MyComputer` свидетельства зоны).

- Загрузка в домен <xref:System.AppDomain> с полным доверием.

- Загрузка из расположения со свойством <xref:System.AppDomainSetup.ApplicationBase%2A> домена <xref:System.AppDomain>.

- Подпись осуществлена без задержки.

> [!NOTE]
> Если функция обхода отключена для всех приложений на компьютере с помощью раздела реестра, этот параметр файла конфигурации не действует. Дополнительные сведения см. в разделе [как отключить функцию обхода Strong-Name](../../../../standard/assembly/disable-strong-name-bypass-feature.md).

## <a name="example"></a>Пример

В следующем примере показано, как задать поведение, которое проверяет подпись строгого имени в сборках с полным доверием.

```xml
<configuration>
   <runtime>
      <bypassTrustedAppStrongNames enabled="false"/>
   </runtime>
</configuration>
```

## <a name="see-also"></a>См. также

- [Схема параметров среды выполнения](index.md)
- [Схема файла конфигурации](../index.md)
- [Практическое руководство. Отключение функции пропуска строгих имен](../../../../standard/assembly/disable-strong-name-bypass-feature.md)
