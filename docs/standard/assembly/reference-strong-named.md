---
title: Практическое руководство. Ссылка на сборку со строгим именем
description: В этой статье показано, как создавать ссылки на типы или ресурсы в сборке .NET со строгим именем во время компиляции или выполнения.
ms.date: 08/20/2019
helpviewer_keywords:
- strong-named assemblies, compile-time references
- compile-time assembly referencing
- assemblies [.NET], strong-named
- assembly binding, strong-named
ms.assetid: 4c6a406a-b5eb-44fa-b4ed-4e95bb95a813
dev_langs:
- csharp
- vb
- cpp
ms.openlocfilehash: 478f786995cfc4b57f0b18b2159775db104e9cfb
ms.sourcegitcommit: 279fb6e8d515df51676528a7424a1df2f0917116
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/27/2020
ms.locfileid: "92687691"
---
# <a name="how-to-reference-a-strong-named-assembly"></a>Практическое руководство. Ссылка на сборку со строгим именем
Процесс использования ссылок на типы или ресурсы, находящиеся в сборке со строгим именем, обычно понятен. Создать ссылку можно в момент компиляции (ранняя привязка) или же во время выполнения.  
  
Во время компиляции создание ссылки происходит, когда компилятору указывается, что компилируемая сборка явно ссылается на другую сборку. При создании ссылок в момент компиляции компилятор автоматически получает открытый ключ нужной сборки со строгим именем и помещает его в ссылку компилируемой сборки.
  
> [!NOTE]
> Сборка со строгими именами может использовать только типы из других сборок со строгими именами. В противном случае нарушается безопасность сборки со строгими именами.  
  
## <a name="make-a-compile-time-reference-to-a-strong-named-assembly"></a>Создание ссылки на сборку со строгим именем во время компиляции  

В командной строке введите следующую команду:  

\<*compiler command*> **/reference:** \<*assembly name*>  

В этой команде *команда компилятора*  — команда компилятора для используемого языка, а *имя сборки*  — строгое имя сборки, на которую создается ссылка. Кроме того, для создания сборки библиотеки можно использовать другие параметры компилятора, такие как **/t:library**.  

В следующем примере показано создание сборки с именем *myAssembly.dll* , которая ссылается на сборку со строгим именем *myLibAssembly.dll* из модуля кода *myAssembly.cs*.  

```cmd
csc /t:library myAssembly.cs /reference:myLibAssembly.dll  
```  

## <a name="make-a-run-time-reference-to-a-strong-named-assembly"></a>Создание ссылки на сборку со строгим именем во время выполнения  
  
Если вы создаете ссылку на сборку со строгим именем во время выполнения (например, с помощью метода <xref:System.Reflection.Assembly.Load%2A?displayProperty=nameWithType> или <xref:System.Reflection.Assembly.GetType%2A?displayProperty=nameWithType>), нужно использовать отображаемое имя сборки со строгим именем, на которую указывает ссылка. Отображаемое имя имеет следующий синтаксис:  

\<*assembly name*>**,** \<*version number*>**,** \<*culture*>**,** \<*public key token*>  

Пример:  

```console
myDll, Version=1.1.0.0, Culture=en, PublicKeyToken=03689116d3a4ae33
```  

В этом примере `PublicKeyToken` представляет собой шестнадцатеричную форму маркера открытого ключа. Если значение языка и региональных параметров отсутствует, используйте `Culture=neutral`.  

В следующем примере кода показано использование этих данных с помощью метода <xref:System.Reflection.Assembly.Load%2A?displayProperty=nameWithType>.  

```cpp
Assembly^ myDll =
    Assembly::Load("myDll, Version=1.0.0.1, Culture=neutral, PublicKeyToken=9b35aa32c18d4fb1");
```

```csharp
Assembly myDll =
    Assembly.Load("myDll, Version=1.0.0.1, Culture=neutral, PublicKeyToken=9b35aa32c18d4fb1");
```

```vb
Dim myDll As Assembly = _
    Assembly.Load("myDll, Version=1.0.0.1, Culture=neutral, PublicKeyToken=9b35aa32c18d4fb1")
```

Распечатать в шестнадцатеричном формате открытый ключ и токен открытого ключа для определенной сборки можно с помощью следующей команды [строгого имени (Sn.exe)](../../framework/tools/sn-exe-strong-name-tool.md):  

**sn -Tp \<** *assembly* **>**  

Если же имеется файл открытого ключа, то вместо этого можно использовать следующую команду (обратите внимание на разный регистр символов в параметре командной строки):  

**sn -tp \<** *public key file* **>**  

## <a name="see-also"></a>См. также

- [Создание и использование сборок со строгими именами](create-use-strong-named.md)
