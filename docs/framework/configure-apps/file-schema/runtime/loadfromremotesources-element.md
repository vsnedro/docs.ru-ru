---
title: Элемент <loadFromRemoteSources>
ms.date: 05/24/2018
helpviewer_keywords:
- loadFromRemoteSources element
- <loadFromRemoteSources> element
ms.assetid: 006d1280-2ac3-4db6-a984-a3d4e275046a
ms.openlocfilehash: a0dcffe378cdd09de0fbd8f0a6ef0635c033fd9c
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/06/2020
ms.locfileid: "79154066"
---
# <a name="loadfromremotesources-element"></a>Элемент \<loadFromRemoteSources>
Указывает, должны ли сборки, загруженные из удаленных источников, предоставлять полное доверие в .NET Framework 4 и более поздних версий.
  
> [!NOTE]
> Если вы перенаправлялись на эту статью из-за сообщения об ошибке в списке ошибок проекта Visual Studio или ошибки сборки, см. раздел [как использовать сборку из Интернета в Visual Studio](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2010/ee890038(v=vs.100)).  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<runtime>**](runtime-element.md)\
&nbsp;&nbsp;&nbsp;&nbsp;**\<loadFromRemoteSources>**  
  
## <a name="syntax"></a>Синтаксис  
  
```xml  
<loadFromRemoteSources
   enabled="true|false"/>  
```  
  
## <a name="attributes-and-elements"></a>Элементы и атрибуты
 В следующих разделах описаны атрибуты, дочерние и родительские элементы.  
  
### <a name="attributes"></a>Атрибуты  
  
|Атрибут|Описание|  
|---------------|-----------------|  
|`enabled`|Обязательный атрибут.<br /><br /> Указывает, должно ли быть предоставлено полное доверие для сборки, загружаемой из удаленного источника.|  
  
## <a name="enabled-attribute"></a>Включенный атрибут  
  
|Значение|Описание|  
|-----------|-----------------|  
|`false`|Не предоставляйте полное доверие приложениям из удаленных источников. Это значение по умолчанию.|  
|`true`|Предоставление полного доверия приложениям из удаленных источников.|  
  
### <a name="child-elements"></a>Дочерние элементы  
 Отсутствует.  
  
### <a name="parent-elements"></a>Родительские элементы  
  
|Элемент|Описание|  
|-------------|-----------------|  
|`configuration`|Корневой элемент в любом файле конфигурации, используемом средой CLR и приложениями .NET Framework.|  
|`runtime`|Содержит сведения о параметрах инициализации среды выполнения.|  
  
## <a name="remarks"></a>Примечания

В .NET Framework 3,5 и более ранних версиях при загрузке сборки из удаленного расположения код в сборке выполняется в режиме частичного доверия с набором разрешений, зависящим от зоны, из которой она загружена. Например, если загрузить сборку с веб-сайта, она загружается в зону Интернета и предоставляет набор разрешений Интернета. Иными словами, он выполняется в песочнице Интернета.

Начиная с .NET Framework 4, политика разграничения доступа кода (CAS) отключена, и сборки загружаются с полным доверием. Обычно это обеспечивает полное доверие сборкам, загруженным с помощью <xref:System.Reflection.Assembly.LoadFrom%2A?displayProperty=nameWithType> ранее изолированного метода. Чтобы предотвратить это, возможность запуска кода в сборках, загружаемых из удаленного источника, по умолчанию отключена. По умолчанию при попытке загрузить удаленную сборку <xref:System.IO.FileLoadException> выдается сообщение об исключении, подобное следующему:

```text
System.IO.FileNotFoundException: Could not load file or assembly 'file:assem.dll' or one of its dependencies. Operation is not supported.
(Exception from HRESULT: 0x80131515)
File name: 'file:assem.dll' --->
System.NotSupportedException: An attempt was made to load an assembly from a network location which would have caused the assembly
to be sandboxed in previous versions of the .NET Framework. This release of the .NET Framework does not enable CAS policy by default,
so this load may be dangerous. If this load is not intended to sandbox the assembly, please enable the loadFromRemoteSources switch.
```

Для загрузки сборки и выполнения ее кода необходимо выполнить одно из следующих действий.

- Явно Создайте песочницу для сборки (см. раздел [как запустить частично доверенный код в песочнице](../../../misc/how-to-run-partially-trusted-code-in-a-sandbox.md)).

- Запустите код сборки в режиме полного доверия. Для этого нужно настроить `<loadFromRemoteSources>` элемент. Он позволяет указать, что сборки, выполняемые в режиме частичного доверия в более ранних версиях .NET Framework теперь выполняются с полным доверием в .NET Framework 4 и более поздних версиях.

> [!IMPORTANT]
> Если сборка не должна выполняться с полным доверием, не устанавливайте этот элемент конфигурации. Вместо этого создайте изолированную среду, <xref:System.AppDomain> в которой будет загружена сборка.

`enabled`Атрибут для `<loadFromRemoteSources>` элемента эффективен, только если отключена разграничение доступа кода (CAS). По умолчанию политика CAS отключена в .NET Framework 4 и более поздних версиях. Если задано `enabled` значение `true` , удаленным сборкам предоставляется полное доверие.

Если `enabled` параметр не имеет значение `true` , то <xref:System.IO.FileLoadException> исключение создается при любом из следующих условий:

- Поведение "песочницы" текущего домена отличается от поведения в .NET Framework 3,5. Для этого требуется отключить политику разграничения доступа, а текущий домен не должен быть изолирован.

- Загружаемая сборка не принадлежит `MyComputer` зоне.

Установка `<loadFromRemoteSources>` элемента, чтобы `true` запретить возникновение этого исключения. Он позволяет указать, что вы не полагаетесь на среду CLR для использования песочницы загруженными сборками для обеспечения безопасности и можете ли они быть разрешены для выполнения с полным доверием.

## <a name="notes"></a>Примечания

- В .NET Framework 4,5 и более поздних версиях сборки на локальных сетевых ресурсах по умолчанию работают в режиме полного доверия. не нужно включать `<loadFromRemoteSources>` элемент.

- Если приложение скопировано из Интернета, оно помечается ОС Windows как веб-приложение, даже если находится на локальном компьютере. Это обозначение можно изменить, изменив его свойства файла, или с помощью `<loadFromRemoteSources>` элемента можно предоставить сборке полное доверие. Также можно использовать метод <xref:System.Reflection.Assembly.UnsafeLoadFrom%2A>, чтобы загрузить локальную сборку, которую операционная система пометила как загруженную из Интернета.

- Вы можете получить <xref:System.IO.FileLoadException> в приложении, работающем в приложении Windows Virtual PC. Это может произойти при попытке загрузить файл из связанных папок на компьютере размещения. Это также может произойти при попытке загрузить файл из папки, связанной [службы удаленных рабочих столов](/windows/win32/termserv/terminal-services-portal) (службы терминалов). Чтобы избежать исключения, задайте для параметра значение `enabled` `true` .

## <a name="configuration-file"></a>Файл конфигурации

Этот элемент обычно используется в файле конфигурации приложения, но может использоваться в других файлах конфигурации в зависимости от контекста. Дополнительные сведения см. в статье [более Неявное использование политики CAS: лоадфромремотесаурцес](https://docs.microsoft.com/archive/blogs/shawnfa/more-implicit-uses-of-cas-policy-loadfromremotesources) в блоге по безопасности .NET.  

## <a name="example"></a>Пример

В следующем примере показано, как предоставить полное доверие сборкам, загруженным из удаленных источников.

```xml
<configuration>  
   <runtime>  
      <loadFromRemoteSources enabled="true"/>  
   </runtime>  
</configuration>  
```

## <a name="see-also"></a>См. также

- [Более Неявное использование политики CAS: Лоадфромремотесаурцес](https://docs.microsoft.com/archive/blogs/shawnfa/more-implicit-uses-of-cas-policy-loadfromremotesources)
- [Практическое руководство. Выполнение не вполне безопасного кода в изолированной среде](../../../misc/how-to-run-partially-trusted-code-in-a-sandbox.md)
- [Схема параметров среды выполнения](index.md)
- [Схема файла конфигурации](../index.md)
- <xref:System.Reflection.Assembly.LoadFrom%2A?displayProperty=nameWithType>
