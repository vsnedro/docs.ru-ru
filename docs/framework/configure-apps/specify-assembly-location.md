---
title: Указание расположения сборки
ms.date: 03/30/2017
helpviewer_keywords:
- configuration [.NET Framework], applications
- application configuration [.NET Framework]
- assemblies [.NET Framework], specifying location
ms.assetid: 1cb92bd7-6bab-44cf-8fd3-36303ce84fea
ms.openlocfilehash: ead69d1e850050214c15295134c06ff6f66e9760
ms.sourcegitcommit: 62285ec11fa8e8424bab00511a90760c60e63c95
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/20/2020
ms.locfileid: "81646036"
---
# <a name="specifying-an-assemblys-location"></a>Указание расположения сборки
Существует два способа указать местоположение сборки:  
  
- Использование [ \<элемента codeBase>.](./file-schema/runtime/codebase-element.md)  
  
- Использование [ \<элемента зондирования>.](./file-schema/runtime/probing-element.md)  
  
 Вы также можете использовать [инструмент конфигурации рамочной конфигурации .NET (Mscorcfg.msc)](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/2bc0cxhc(v=vs.100)) для указания местоположений сборки или указания местоположений для общего времени выполнения языка для зондирования сборок.  
  
## <a name="using-the-codebase-element"></a>Использование \<codeBase> Элемент  
 Элемент ** \<codeBase** можно использовать>только в конфигурации машины или файлах политики издателя, которые также перенаправляют сборочную версию. Когда время выполнения определяет, какую сборочную версию использовать, он применяет настройки базы кода из файла, определяющего версию. Если кодовая база не указана, зонды времени выполнения для сборки в обычном режиме. Для получения подробной информации, [см.](../deployment/how-the-runtime-locates-assemblies.md)  
  
 В следующем примере показано, как указать местоположение сборки.  
  
```xml  
<configuration>  
   <runtime>  
      <assemblyBinding xmlns="urn:schemas-microsoft-com:asm.v1">  
       <dependentAssembly>  
         <assemblyIdentity name="myAssembly"  
                           publicKeyToken="32ab4ba45e0a69a1"  
                           culture="en-us" />  
         <codeBase version="2.0.0.0"  
                   href="http://www.litwareinc.com/myAssembly.dll"/>  
       </dependentAssembly>  
      </assemblyBinding>  
   </runtime>  
</configuration>  
```  
  
 Атрибут **версии** необходим для всех сильных собраний, но должен быть опущен для сборок, которые не являются сильными. Элемент ** \<codeBase>** требует атрибута **href.** Вы не можете указать диапазоны версий в ** \<элементе codeBase>.**  
  
> [!NOTE]
> Если вы поставляете подсказку базы кода для сборки, которая не имеет сильного названия, подсказка должна указывать на базу приложений или субдиректорию базового каталога приложения.  
  
## <a name="using-the-probing-element"></a>Использование \<зондирования> элемента  
 Время выполнения находит сборки, которые не имеют кодовой базы путем зондирования. Для получения дополнительной информации о зондирования, см [Как Runtime находит сборки](../deployment/how-the-runtime-locates-assemblies.md).  
  
 Элемент [ \<зондирования>](./file-schema/runtime/probing-element.md) в файле конфигурации приложения можно указать субдиректорам, которые необходимо искать при поиске сборки. В следующем примере показано, как указать каталоги, которые необходимо искать в времени выполнения.  
  
```xml  
<configuration>  
   <runtime>  
      <assemblyBinding xmlns="urn:schemas-microsoft-com:asm.v1">  
         <probing privatePath="bin;bin2\subbin;bin3"/>  
      </assemblyBinding>  
   </runtime>  
</configuration>  
```  
  
 Атрибут **privatePath** содержит каталоги, которые время выполнения должно искать сборки. Если приложение находится на C: «Программные файлы»MyApp, время выполнения будет искать сборки, которые не указывают кодовую базу в C: «Программные файлы»MyApp-Bin, C: «Программные файлы» (MyApp2)Subbin и C:»Программные файлы »MyApp»Bin3. Каталоги, указанные в **privatePath,** должны быть субдиректорами базового каталога приложений.  
  
## <a name="see-also"></a>См. также раздел

- [Сборки в .NET](../../standard/assembly/index.md)
- [Программирование с использованием сборок](../../standard/assembly/index.md)
- [Как Время выполнения находит сборки](../deployment/how-the-runtime-locates-assemblies.md)
- [Настройка приложений с использованием файлов конфигурации](index.md)
