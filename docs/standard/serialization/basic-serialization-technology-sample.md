---
title: Образец технологии базовой сериализации
description: В этом примере показано, как среда CLR может выполнять сериализацию графа объекта в поток. В этом примере можно использовать SoapFormatter или BinaryFormatter.
ms.date: 03/30/2017
ms.assetid: 9d824e16-08d1-4a36-bc7f-2388c1f75f34
ms.openlocfilehash: 3f2273e6afb3a72f9734444ffe92d30871fb762b
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/06/2020
ms.locfileid: "84276573"
---
# <a name="basic-serialization-technology-sample"></a>Образец технологии базовой сериализации

[Скачать образец](https://download.microsoft.com/download/4/7/B/47B2164C-E780-4B10-8DE4-2CB5B886E0A6/Technologies/Serialization/Runtime%20Serialization/Basic.zip.exe)

В этом образце демонстрируется возможность среды CLR выполнять сериализацию графа объекта в поток. Для сериализации в примере могут использоваться классы <xref:System.Runtime.Serialization.Formatters.Soap.SoapFormatter> или <xref:System.Runtime.Serialization.Formatters.Binary.BinaryFormatter>. Связанный список, заполненный данными, сериализируется в поток файла или десериализируется из потока файла. В любом случае этот список отображается для того, чтобы можно было видеть результаты. Связанный список является списком типа `LinkedList`, который определен в этом примере.

Дополнительные сведения о сериализации см. в комментариях к исходному коду и в файлах build.proj.

### <a name="to-build-the-sample-using-the-command-prompt"></a>Сборка образца с использованием командной строки

1. С помощью командной строки перейдите к одной из вложенных папок в каталоге Technologies\Serialization\Runtime Serialization\Basic, соответствующей выбранному языку.

2. В командной строке введите **msbuild SerializationCS.sln**, **msbuild SerializationJSL.sln** или **msbuild SerializationVB.sln**, в зависимости от выбранного языка программирования.

### <a name="to-build-the-sample-using-visual-studio"></a>Сборка образца с использованием Visual Studio

1. Откройте File Explorer и перейдите к вложенной папке для данного образца, соответствующей выбранному языку.

2. Дважды щелкните значок файла SerializationCS.sln, SerializationJSL.sln или SerializationVB.sln file, в зависимости от выбранного языка программирования, чтобы открыть файл в Visual Studio.

3. В меню **Построение** выберите команду **Построить решение**.

 По умолчанию сборка образца приложения помещается в подкаталог \bin или \bin\Debug.

### <a name="to-run-the-sample"></a>Выполнение образца

1. Перейдите в каталог, содержащий построенный исполняемый файл.

2. В командной строке введите **Serialization.exe** вместе с необходимыми значениями параметров.

  > [!NOTE]
  > В данном образце выполняется построение консольного приложения. Чтобы просмотреть выводимые им данные, необходимо запустить его в командной строке.

## <a name="remarks"></a>Примечания

Образец приложения принимает параметры командной строки, указывающие, какой тест следует выполнить. Чтобы выполнить сериализацию списка из 10 узлов в файл с именем **Test.xml** с помощью модуля форматирования SOAP, используйте параметры **sx Test.xml 10**.

Пример.

```console
Serialize.exe -sx Test.xml 10
```

Чтобы десериализировать файл **Test.xml** из предыдущего примера, используйте параметры **dx Test.xml**.

Пример.

```console
Serialize.exe -dx Test.xml
```

В двух приведенных выше примерах параметр командной строки "x" означает использование сериализации XML SOAP. Вместо этого можно использовать "b" для двоичной сериализации. Если необходимо испытать сериализацию с очень большим числом узлов, может потребоваться перенаправить выходные данные с консоли в файл.

Пример.

```console
Serialize.exe -sb Test.bin 10000 >somefile.txt
```

В следующем маркированном списке кратко описываются технологии и классы, используемые в этом образце.

- Сериализация во время выполнения

  - <xref:System.Runtime.Serialization.IFormatter> Используется для ссылки на объект <xref:System.Runtime.Serialization.Formatters.Binary.BinaryFormatter> или <xref:System.Runtime.Serialization.Formatters.Soap.SoapFormatter>.

  - <xref:System.Runtime.Serialization.Formatters.Binary.BinaryFormatter> Используется для сериализации связанного списка в поток в двоичном формате. Двоичный модуль форматирования использует формат, который понятен только типу <xref:System.Runtime.Serialization.Formatters.Binary.BinaryFormatter>. Однако данные являются краткими.

  - <xref:System.Runtime.Serialization.Formatters.Soap.SoapFormatter> Используется для сериализации связанного списка в поток в формате SOAP. SOAP является стандартным форматом.

- Потоковый ввод-вывод

  - <xref:System.IO.Stream> Используется для сериализации и десериализации. Особый тип потока, который используется в этом примере, является типом <xref:System.IO.FileStream>. Однако сериализация может быть использована с любым типом, производным от <xref:System.IO.Stream>.

  - <xref:System.IO.File> Используется для создания объектов <xref:System.IO.FileStream> для чтения и создания файлов на диске.

  - <xref:System.IO.FileStream> Используется для сериализации и десериализации связанных списков.

## <a name="see-also"></a>См. также

- <xref:System.IO>
- <xref:System.IO.File>
- <xref:System.IO.FileStream>
- <xref:System.IO.Stream>
- <xref:System.Random>
- <xref:System.Runtime.Serialization>
- <xref:System.Runtime.Serialization.Formatters.Binary.BinaryFormatter>
- <xref:System.Runtime.Serialization.Formatters.Soap.SoapFormatter>
- <xref:System.Runtime.Serialization.IFormatter>
- <xref:System.SerializableAttribute>
- <xref:System.Xml.Serialization>
- [Базовая сериализация](basic-serialization.md)
- [Двоичная сериализация](binary-serialization.md)
- [Управление сериализацией XML с использованием атрибутов](controlling-xml-serialization-using-attributes.md)
- [Введение в сериализацию XML](introducing-xml-serialization.md)
- [Сериализация](index.md)
- [Сериализация XML и SOAP](xml-and-soap-serialization.md)
