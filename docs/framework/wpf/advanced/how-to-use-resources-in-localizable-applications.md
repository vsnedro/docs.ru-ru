---
title: Как использовать ресурсы в локализуемых приложениях
ms.date: 03/30/2017
helpviewer_keywords:
- applications [WPF], localizable
- localizable applications [WPF]
ms.assetid: 08539ad6-7fca-4f34-b82b-ff439e11dfa7
ms.openlocfilehash: 8f516a86036656b98add23d38c588b5c19be4d7a
ms.sourcegitcommit: 488aced39b5f374bc0a139a4993616a54d15baf0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/12/2020
ms.locfileid: "83212479"
---
# <a name="how-to-use-resources-in-localizable-apps"></a>Как использовать ресурсы в локализуемых приложениях

Локализация означает адаптацию пользовательского интерфейса для различных языков и региональных параметров. Для этого необходимо перевести текст, например заголовки, заголовки и элементы списка. Чтобы упростить перевод, преобразуемые элементы собираются в файлы ресурсов. Сведения о создании файла ресурсов для локализации см. в статье [Локализация приложения](how-to-localize-an-application.md) . Чтобы сделать приложение WPF локализованным, разработчики должны собрать все локализуемые ресурсы в сборку ресурсов. Сборка ресурсов локализуется на разные языки, и для загрузки кода программной части используется API управления ресурсами.

## <a name="example"></a>Пример

Одним из файлов, необходимых для приложения WPF, является файл проекта (proj). Все ресурсы, используемые в приложении, необходимо включить в файл проекта. Это показано в следующем примере XAML.

```xaml
<Resource Include="data\picture1.jpg"/>  
<EmbeddedResource Include="data\stringtable.en-US.restext"/>
```

Чтобы использовать ресурс в приложении, создайте экземпляр <xref:System.Resources.ResourceManager> и загрузите ресурс, который вы хотите использовать. В следующем коде C# показано, как это сделать.

[!code-csharp[LocalizationResources#2](~/samples/snippets/csharp/VS_Snippets_Wpf/LocalizationResources/CSharp/page1.xaml.cs#2)]

## <a name="see-also"></a>См. также

- [Локализация приложения](how-to-localize-an-application.md)
