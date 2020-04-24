---
title: Практическое руководство. Создание политики издателя
ms.date: 03/30/2017
helpviewer_keywords:
- publisher policy assembly
- publisher policy files
- GAC (global assembly cache), publisher policy assembly
- global assembly cache, publisher policy assembly
ms.assetid: 8046bc5d-2fa9-4277-8a5e-6dcc96c281d9
ms.openlocfilehash: 7c36f6126f0d779a43a22fc11e647ba2d3b03a30
ms.sourcegitcommit: 62285ec11fa8e8424bab00511a90760c60e63c95
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/20/2020
ms.locfileid: "81646058"
---
# <a name="how-to-create-a-publisher-policy"></a>Практическое руководство. Создание политики издателя

Поставщики сборок могут указать, что приложения должны использовать более новую версию сборки, включив файл политики издателя в обновленную сборку. Файл политики издателя определяет настройки перенаправления сборки и базы кода и использует тот же формат, что и файл конфигурации приложения. Файл политики издателя компилируется в сборку и помещается в кэш глобальной сборки.

Существует три этапа создания политики издателя:

1. Создайте файл политики издателя.

2. Создание сборки политики издателя.

3. Добавьте сборку политики издателя в кэш глобальной сборки.

Схема политики издателя описана в [перенаправлении версий сборки.](redirect-assembly-versions.md) В следующем примере показан файл политики издателя, который перенаправляет одну версию `myAssembly` в другую.

```xml
<configuration>
   <runtime>
      <assemblyBinding xmlns="urn:schemas-microsoft-com:asm.v1">
       <dependentAssembly>
         <assemblyIdentity name="myAssembly"
                           publicKeyToken="32ab4ba45e0a69a1"
                           culture="en-us" />
         <!-- Redirecting to version 2.0.0.0 of the assembly. -->
         <bindingRedirect oldVersion="1.0.0.0"
                          newVersion="2.0.0.0"/>
       </dependentAssembly>
      </assemblyBinding>
   </runtime>
</configuration>
```

Чтобы узнать, как указать базу кода, [см.](specify-assembly-location.md)

## <a name="creating-the-publisher-policy-assembly"></a>Создание Собрания политики издателей

Используйте [сборку Linker (Al.exe)](../tools/al-exe-assembly-linker.md) для создания сборки политики издателя.

#### <a name="to-create-a-publisher-policy-assembly"></a>Создание сборки политики издателя

В командной строке введите следующую команду:

```console
al /link:publisherPolicyFile /out:publisherPolicyAssemblyFile /keyfile:keyPairFile /platform:processorArchitecture
```

В этой команде:

- Аргументом `publisherPolicyFile` является название файла политики издателя.

- Аргументом `publisherPolicyAssemblyFile` является название собрания политики издателя, которое является результатом этой команды. Имя файла сборки должно следовать формату:

  'policy.majorNumber.minorNumber.mainAssemblyName.dll'

- Аргументом `keyPairFile` является название файла, содержащего пару ключей. Необходимо подписать собрание политики сборки сборки и издателя одной и той же ключевой парой.

- Аргумент `processorArchitecture` определяет платформу, ориентированную на сборку, предназначенную для процессора.

  > [!NOTE]
  > Возможность таргетинга на конкретную архитектуру процессора доступна начиная с .NET Framework 2.0.

Возможность таргетинга на конкретную архитектуру процессора доступна начиная с .NET Framework 2.0. Следующая команда создает сборку `policy.1.0.myAssembly` политики издателя, вызванную из файла политики издателя, называемого, `pub.config`присваивая сильное имя сборке с помощью пары ключей в `sgKey.snk` файле, и указывает, что сборка нацелена на архитектуру процессора x86.

```console
al /link:pub.config /out:policy.1.0.myAssembly.dll /keyfile:sgKey.snk /platform:x86
```

Сборка политики издателя должна соответствовать архитектуре процессора сборки, к которым она применяется. Таким образом, если <xref:System.Reflection.AssemblyName.ProcessorArchitecture%2A> ваша <xref:System.Reflection.ProcessorArchitecture.MSIL>сборка имеет ценность, сборка политики издателя для этой сборки должна быть создана с `/platform:anycpu`помощью. Необходимо предоставить отдельную сборку политики издателя для каждой сборки, конкретной для процессора.

Следствием этого правила является то, что для изменения архитектуры процессора для сборки необходимо изменить основной или незначительный компонент номера версии, чтобы можно было поставить новую сборку политики издателя с правильной архитектурой процессора. Старая сборка политики издателя не может обслуживать сборку, как только сборка имеет другую архитектуру процессора.

Другим последствием является то, что ссылка версии 2.0 не может быть использована для создания сборки политики издателя для сборки, компиляции, составленной с использованием более ранних версий рамочного значения .NET, поскольку она всегда определяет архитектуру процессора.

## <a name="adding-the-publisher-policy-assembly-to-the-global-assembly-cache"></a>Добавление Собрания по политике издателей в кэш Глобальной ассамблеи

Используйте [инструмент Глобального кэша собраний (Gacutil.exe)](../tools/gacutil-exe-gac-tool.md) для добавления сборки политики издателя в кэш глобальной сборки.

### <a name="to-add-the-publisher-policy-assembly-to-the-global-assembly-cache"></a>Добавление сборки политики издателя в глобальный кэш сборки

В командной строке введите следующую команду:

```console
gacutil /i publisherPolicyAssemblyFile
```

Следующая команда `policy.1.0.myAssembly.dll` добавляет к глобальному кэшу сборки.

```console
gacutil /i policy.1.0.myAssembly.dll
```

> [!IMPORTANT]
> Сборка политики издателя не может быть добавлена в кэш `/link` глобальной сборки, если исходный файл политики издателя, указанный в аргументе, не находится в том же каталоге, что и сборка.

## <a name="see-also"></a>См. также раздел

- [Программирование с использованием сборок](../../standard/assembly/index.md)
- [Как Время выполнения находит сборки](../deployment/how-the-runtime-locates-assemblies.md)
- [Настройка приложений с использованием файлов конфигурации](index.md)
- [Схема настройки выполнения](./file-schema/runtime/index.md)
- [Схема конфигурации файлов](./file-schema/index.md)
- [Перенаправление версий сборки](redirect-assembly-versions.md)
