---
description: 'Дополнительные сведения: <Thread_UseAllCpuGroups элемент>'
title: Элемент <Thread_UseAllCpuGroups>
ms.date: 03/30/2017
ms.assetid: d30fe7c5-8469-46e2-b804-e3eec7b24256
ms.openlocfilehash: 3f11ba6855caab25bd261de71c80c78232f2690f
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/06/2021
ms.locfileid: "99802415"
---
# <a name="thread_useallcpugroups-element"></a>Элемент \<Thread_UseAllCpuGroups>

Указывает, распределяет ли среда выполнения управляемые потоки во всех группах ЦП.

[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<runtime>**](runtime-element.md)\
&nbsp;&nbsp;&nbsp;&nbsp;**\<Thread_UseAllCpuGroups>**  

## <a name="syntax"></a>Синтаксис

```xml
<Thread_UseAllCpuGroups
   enabled="true|false"/>
```

## <a name="attributes-and-elements"></a>Атрибуты и элементы

В следующих разделах описаны атрибуты, дочерние и родительские элементы.

### <a name="attributes"></a>Атрибуты

|Атрибут|Описание|
|---------------|-----------------|
|`enabled`|Обязательный атрибут.<br /><br /> Указывает, распределяет ли среда выполнения управляемые потоки во всех группах ЦП.|

## <a name="enabled-attribute"></a>Атрибут enabled

|Значение|Описание|
|-----------|-----------------|
|`false`|Среда выполнения не распределяет управляемые потоки между несколькими группами ЦП. Это значение по умолчанию.|
|`true`|Среда выполнения распределяет управляемые потоки между несколькими группами ЦП, если компьютер имеет несколько групп ЦП и [\<GCCpuGroup>](gccpugroup-element.md) элемент включен.|

### <a name="child-elements"></a>Дочерние элементы

Отсутствует.

### <a name="parent-elements"></a>Родительские элементы

|Элемент|Описание|
|-------------|-----------------|
|`configuration`|Корневой элемент в любом файле конфигурации, используемом средой CLR и приложениями .NET Framework.|
|`runtime`|Содержит сведения о привязке сборок и сборке мусора.|

## <a name="remarks"></a>Remarks

Если компьютер имеет несколько групп ЦП, включение этого элемента приводит к тому, что среда выполнения распределяет управляемые потоки по всем группам ЦП. Чтобы использовать эту функцию, необходимо также включить [\<GCCpuGroup>](gccpugroup-element.md) элемент, который расширяет сборку мусора на все группы ЦП и учитывает все ядра при создании и балансировке куч. Включение [\<GCCpuGroup>](gccpugroup-element.md) элемента требует включения [\<gcServer>](gcserver-element.md) элемента. Если эти элементы не включены, включение `<Thread_UseAllCpuGroups>` элемента не оказывает никакого влияния.

## <a name="example"></a>Пример

В следующем примере показано, как включить поддержку нескольких групп ЦП.

```xml
<configuration>
   <runtime>
      <Thread_UseAllCpuGroups enabled="true"/>
      <GCCpuGroup enabled="true"/>
      <gcServer enabled="true"/>
   </runtime>
</configuration>
```

## <a name="see-also"></a>См. также

- [Схема параметров среды выполнения](index.md)
- [Схема файла конфигурации](../index.md)
- [\<GCCpuGroup> Элемент](gccpugroup-element.md)
