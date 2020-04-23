---
title: Элемент <GCCpuGroup>
ms.date: 03/30/2017
helpviewer_keywords:
- GCCpuGroup element
- <GCCpuGroup> element
ms.assetid: c1fc7d6c-7220-475c-a312-5b8b201f66e0
ms.openlocfilehash: f1cbe5a7109d6e4aae2e92710920a1c6b3a40d00
ms.sourcegitcommit: 73aa9653547a1cd70ee6586221f79cc29b588ebd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2020
ms.locfileid: "82102896"
---
# <a name="gccpugroup-element"></a>\<GCCpuGroup> Элемент

Определяет, поддерживает ли сборка мусора несколько групп ЦП.

[**\<конфигурация>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<>выполнения**](runtime-element.md)\
&nbsp;&nbsp;&nbsp;&nbsp;**\<GCCpuGroup>**

## <a name="syntax"></a>Синтаксис

```xml
<GCCpuGroup
   enabled="true|false"/>
```

## <a name="attributes-and-elements"></a>Атрибуты и элементы

В следующих разделах описаны атрибуты, дочерние и родительские элементы.

### <a name="attributes"></a>Атрибуты

|Атрибут|Описание|
|---------------|-----------------|
|`enabled`|Обязательный атрибут.<br /><br /> Определяет, поддерживает ли сборка мусора несколько групп ЦП.|

## <a name="enabled-attribute"></a>Атрибут enabled

|Значение|Описание|
|-----------|-----------------|
|`false`|Сбор мусора не поддерживает несколько групп процессоров. Это значение по умолчанию.|
|`true`|Сбор мусора поддерживает несколько групп процессоров, если включен сбор мусора сервера.|

### <a name="child-elements"></a>Дочерние элементы

Отсутствует.

### <a name="parent-elements"></a>Родительские элементы

|Элемент|Описание|
|-------------|-----------------|
|`configuration`|Корневой элемент в любом файле конфигурации, используемом средой CLR и приложениями .NET Framework.|
|`runtime`|Содержит сведения о привязке сборок и сборке мусора.|

## <a name="remarks"></a>Remarks

Когда компьютер имеет несколько групп процессоров и сбор мусора сервера включен (см. [ \<элемент gcServer>),](gcserver-element.md) что позволяет этот элемент расширяет сбор мусора во всех группах процессоров и принимает все ядра во внимание при создании и балансировке кучи.

> [!NOTE]
> Этот элемент применяется только к потокам сбора мусора. Чтобы включить время выполнения для распределения потоков пользователей по всем группам процессора, необходимо также включить [ \<элемент Thread_UseAllCpuGroups>.](thread-useallcpugroups-element.md)

## <a name="example"></a>Пример

В следующем примере показано, как включить сбор мусора для нескольких групп процессоров.

```xml
<configuration>
   <runtime>
      <GCCpuGroup enabled="true"/>
      <gcServer enabled="true"/>
   </runtime>
</configuration>
```

## <a name="see-also"></a>См. также раздел

- [Схема настройки выполнения](index.md)
- [Схема конфигурации файлов](../index.md)
- [Отключить параллельный сбор мусора](gcconcurrent-element.md#to-disable-background-garbage-collection)
- [Сборка мусора рабочей станции и сборка мусора сервера](../../../../standard/garbage-collection/workstation-server-gc.md)
