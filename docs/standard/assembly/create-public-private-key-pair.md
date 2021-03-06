---
title: Практическое руководство. Создание пары открытого и закрытого ключей
description: Узнайте, как создать пару общедоступных или закрытых криптографических ключей, которые используются во время компиляции для создания сборки со строгим именем.
ms.date: 08/20/2019
helpviewer_keywords:
- key pairs for strong-named assemblies
- signing assemblies
- assemblies [.NET], signing
- cryptographic key pairs
- snk files (key pair files)
- public-private key pairs
- .snk files
- strong-named assemblies, key pairs
ms.assetid: 05026813-f3bd-4d7c-9e0b-fc588eb3d114
dev_langs:
- csharp
- vb
- cpp
ms.openlocfilehash: c42e98a7e27ded9a21445fae35ade843e834076a
ms.sourcegitcommit: ff5a4eb5cffbcac9521bc44a907a118cd7e8638d
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/17/2020
ms.locfileid: "92163497"
---
# <a name="how-to-create-a-public-private-key-pair"></a>Практическое руководство. Создание пары открытого и закрытого ключей

Для подписи сборки строгим именем необходимо иметь пару, состоящую из открытого и закрытого ключа. Эта пара криптографических ключей используется во время компиляции для создания сборки со строгим именем. Пару ключей можно создать с помощью [средства для работы со строгими именами (Sn.exe)](../../framework/tools/sn-exe-strong-name-tool.md). Файлы пары ключей обычно имеют расширение *SNK*.

> [!NOTE]
> В Visual Studio страницы свойств проекта C# и Visual Basic включают вкладку **Подписывание**, которая позволяет выбрать существующие файлы ключей или создать новые файлы ключей без использования *Sn.exe*. В Visual C++ можно указать расположение уже существующего файла ключа на странице свойств **Дополнительно** в разделе **Компоновщик** раздела **Свойства конфигурации** окна **Страницы свойств**. Использование атрибута <xref:System.Reflection.AssemblyKeyFileAttribute> для идентификации пар файлов ключей признано устаревшим начиная с Visual Studio 2005.

## <a name="create-a-key-pair"></a>Создание пары ключей

Чтобы создать пару ключей, в командной строке введите следующую команду:

**sn –k** \<*file name*>

В этой команде *имя файла* — это имя выходного файла, содержащего пару ключей.

В следующем примере создается пара ключей с именем *sgKey.snk*.

```cmd
sn -k sgKey.snk
```

Если требуется отложить подписание сборки, а также управлять парой ключей целиком (что может потребоваться разве что для тестирования), можно использовать следующие команды для создания пары ключей и извлечения открытого ключа из нее в отдельный файл. Во-первых, создайте пару ключей:

```cmd
sn -k keypair.snk
```

Затем извлеките открытый ключ из пары ключей и скопируйте его в отдельный файл:

```cmd
sn -p keypair.snk public.snk
```

После создания пары ключей необходимо поместить файл в расположение, в котором его смогут найти инструменты создания подписи строгого имени.

При подписании сборки строгим именем [компоновщик сборок (Al.exe)](../../framework/tools/al-exe-assembly-linker.md) выполняет поиск файла ключа относительно текущей и выходной папки. При использовании компиляторов, работающих в режиме командной строки, достаточно просто скопировать ключ в текущий каталог, содержащий модули кода.

При использовании более ранней версии Visual Studio, в которой нет вкладки **Подписание** в свойствах проекта, рекомендуемым расположением файла ключа является каталог проекта с атрибутом файла, заданным следующим образом:

```cpp
[assembly:AssemblyKeyFileAttribute("keyfile.snk")];
```

```csharp
[assembly:AssemblyKeyFileAttribute("keyfile.snk")]
```

```vb
<Assembly:AssemblyKeyFileAttribute("keyfile.snk")>
```

## <a name="see-also"></a>См. также

- [Создание и использование сборок со строгими именами](create-use-strong-named.md)
