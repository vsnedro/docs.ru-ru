---
title: -linkresource
ms.date: 03/10/2018
helpviewer_keywords:
- /linkresource compiler option [Visual Basic]
- -linkresource compiler option [Visual Basic]
- linkresource compiler option [Visual Basic]
- /linkres compiler option [Visual Basic]
- linkres compiler option [Visual Basic]
- -linkres compiler option [Visual Basic]
ms.assetid: cf4dcad8-17b7-404c-9184-29358aa05b15
ms.openlocfilehash: 8c4f753f94aedaf0a4f997a3f9b99fb3f417abf8
ms.sourcegitcommit: bf5c5850654187705bc94cc40ebfb62fe346ab02
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/23/2020
ms.locfileid: "91065688"
---
# <a name="-linkresource-visual-basic"></a>-linkresource (Visual Basic)

Создает ссылку на управляемый ресурс.  
  
## <a name="syntax"></a>Синтаксис  
  
```console  
-linkresource:filename[,identifier[,public|private]]  
```

or  

```console
-linkres:filename[,identifier[,public|private]]  
```  
  
## <a name="arguments"></a>Аргументы  

 `filename`  
 Обязательный. Файл ресурсов, связываемый со сборкой. Если имя файла содержит пробел, заключите его в кавычки (" ").  
  
 `identifier`  
 Необязательный элемент. Логическое имя ресурса. Имя, которое используется для загрузки ресурса. По умолчанию используется имя файла. При необходимости в манифесте сборки можно указать, является ли файл общедоступным или частным, например: `-linkres:filename.res,myname.res,public`. По умолчанию `filename` в сборке является общедоступным.  
  
## <a name="remarks"></a>Примечания  

 Параметр `-linkresource` не подразумевает внедрение файла ресурсов в выходной файл; для этого используйте параметр `-resource`.  
  
 Для параметра `-linkresource` требуется один из параметров `-target`, кроме `-target:module`.  
  
 Если `filename` является файлом ресурсов .NET Framework, созданным, например, генератором файлов ресурсов ([Resgen.exe](../../../framework/tools/resgen-exe-resource-file-generator.md)) или в среде разработки, то к нему можно обращаться с помощью элементов пространства имен <xref:System.Resources>. (Дополнительные сведения см. в разделе <xref:System.Resources.ResourceManager>.) Для доступа ко всем остальным ресурсам во время выполнения используйте методы, начинающиеся с `GetManifestResource`, из класса <xref:System.Reflection.Assembly>.  
  
 Имя файла может быть в любом формате файла. Например, может потребоваться сделать имеющуюся на компьютере библиотеку DLL частью сборки, поэтому ее можно разместить в глобальном кэше сборок и обеспечить к ней доступ из управляемого кода сборки.  
  
 Краткой формой `-linkresource` является `-linkres`.  
  
> [!NOTE]
> Параметр `-linkresource` недоступен в среде разработки Visual Studio. Его можно использовать только при компиляции из командной строки.  
  
## <a name="example"></a>Пример  

 Следующий код компилирует `in.vb` и обращается к файлу ресурсов `rf.resource`.  
  
```console  
vbc -linkresource:rf.resource in.vb  
```  
  
## <a name="see-also"></a>См. также

- [Компилятор Visual Basic с интерфейсом командной строки](index.md)
- [-target (Visual Basic)](target.md)
- [-resource (Visual Basic)](resource.md)
- [Примеры командных строк компиляции](sample-compilation-command-lines.md)
