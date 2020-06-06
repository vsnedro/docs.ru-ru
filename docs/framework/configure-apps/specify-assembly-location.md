---
title: Указание расположения сборки
ms.date: 03/30/2017
helpviewer_keywords:
- configuration [.NET Framework], applications
- application configuration [.NET Framework]
- assemblies [.NET Framework], specifying location
ms.assetid: 1cb92bd7-6bab-44cf-8fd3-36303ce84fea
ms.openlocfilehash: ead69d1e850050214c15295134c06ff6f66e9760
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/06/2020
ms.locfileid: "81646036"
---
# <a name="specifying-an-assemblys-location"></a>Указание расположения сборки
Существует два способа указания расположения сборки:  
  
- С помощью [\<codeBase>](./file-schema/runtime/codebase-element.md) элемента.  
  
- С помощью [\<probing>](./file-schema/runtime/probing-element.md) элемента.  
  
 Можно также использовать [средство настройки .NET Framework (Mscorcfg. msc)](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/2bc0cxhc(v=vs.100)) , чтобы указать расположения сборок или указать расположения среды CLR для проверки сборок.  
  
## <a name="using-the-codebase-element"></a>Использование \<codeBase> элемента  
 Элемент можно использовать **\<codeBase>** только в конфигурации компьютера или в файлах политики издателя, которые также перенаправляют версию сборки. Когда среда выполнения определяет используемую версию сборки, она применяет параметр базы кода из файла, который определяет версию. Если не указано ни одной базы кода, среда выполнения проверяет наличие сборки обычным способом. Дополнительные сведения см. [в разделе Обнаружение сборок в среде выполнения](../deployment/how-the-runtime-locates-assemblies.md).  
  
 В следующем примере показано, как указать расположение сборки.  
  
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
  
 Атрибут **Version** необходим для всех сборок со строгими именами, но должен быть опущен для сборок, не имеющих строгих имен. **\<codeBase>** Элементу требуется атрибут **href** . В элементе нельзя указывать диапазоны версий **\<codeBase>** .  
  
> [!NOTE]
> Если вы предоставляете указание базы кода для сборки, не имеющей строгого имени, подсказка должна указывать на базу приложения или подкаталог базового каталога приложения.  
  
## <a name="using-the-probing-element"></a>Использование \<probing> элемента  
 Среда выполнения находит сборки, не имеющие базы кода, путем проверки. Дополнительные сведения о проверке см. в разделе [как среда выполнения находит сборки](../deployment/how-the-runtime-locates-assemblies.md).  
  
 [\<probing>](./file-schema/runtime/probing-element.md)Элемент в файле конфигурации приложения можно использовать для указания подкаталогов, которые среда выполнения должна искать при поиске сборки. В следующем примере показано, как указать каталоги, которые должна искать среда выполнения.  
  
```xml  
<configuration>  
   <runtime>  
      <assemblyBinding xmlns="urn:schemas-microsoft-com:asm.v1">  
         <probing privatePath="bin;bin2\subbin;bin3"/>  
      </assemblyBinding>  
   </runtime>  
</configuration>  
```  
  
 Атрибут **privatePath** содержит каталоги, в которых среда выполнения должна искать сборки. Если приложение расположено в папке C:\Program Files\MyApp, среда выполнения будет искать сборки, не указывающие базу кода в C:\Program Филес\мяпп\бин, C:\Program Files\MyApp\Bin2\Subbin и C:\Program Files\MyApp\Bin3. Каталоги, указанные в параметре **privatePath** , должны быть подкаталогами базового каталога приложения.  
  
## <a name="see-also"></a>См. также

- [Сборки в .NET](../../standard/assembly/index.md)
- [Программирование с использованием сборок](../../standard/assembly/index.md)
- [Обнаружение сборок в среде выполнения](../deployment/how-the-runtime-locates-assemblies.md)
- [Настройка приложений с использованием файлов конфигурации](index.md)
