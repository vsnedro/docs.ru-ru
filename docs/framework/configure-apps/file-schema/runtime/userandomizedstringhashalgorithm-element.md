---
title: Элемент <UseRandomizedStringHashAlgorithm>
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- UseRandomizedStringHashAlgorithm element
- <UseRandomizedStringHashAlgorithm> element
ms.assetid: c08125d6-56cc-4b23-b482-813ff85dc630
ms.openlocfilehash: a9afa0db516a542b74d08a4c3754a3244abbbea7
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/06/2020
ms.locfileid: "79153781"
---
# <a name="userandomizedstringhashalgorithm-element"></a>Элемент \<UseRandomizedStringHashAlgorithm>
Определяет, вычисляет ли среда CLR хэш-коды для строк на уровне домена приложения.  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<runtime>**](runtime-element.md)\
&nbsp;&nbsp;&nbsp;&nbsp;**\<UseRandomizedStringHashAlgorithm>**  
  
## <a name="syntax"></a>Синтаксис  
  
```xml  
<UseRandomizedStringHashAlgorithm
   enabled=0|1 />  
```  
  
## <a name="attributes-and-elements"></a>Атрибуты и элементы  
 В следующих разделах описаны атрибуты, дочерние и родительские элементы.  
  
### <a name="attributes"></a>Атрибуты  
  
|Атрибут|Описание|  
|---------------|-----------------|  
|`enabled`|Обязательный атрибут.<br /><br /> Указывает, рассчитываются ли хэш-коды для строк на уровне домена приложения.|  
  
## <a name="enabled-attribute"></a>Атрибут enabled  
  
|Значение|Описание|  
|-----------|-----------------|  
|`0`|Среда CLR не выполняет вычисление хэш-кодов для строк на уровне отдельных приложений. для вычисления хэш-кодов строк используется один алгоритм. Это значение по умолчанию.|  
|`1`|Среда CLR выдает хэш-коды для строк на уровне домена приложения. Идентичные строки в разных доменах приложений и в разных процессах будут иметь разные хэш-коды.|  
  
### <a name="child-elements"></a>Дочерние элементы  
 Отсутствует.  
  
### <a name="parent-elements"></a>Родительские элементы  
  
|Элемент|Описание|  
|-------------|-----------------|  
|`configuration`|Корневой элемент в любом файле конфигурации, используемом средой CLR и приложениями .NET Framework.|  
|`runtime`|Содержит сведения о параметрах инициализации среды выполнения.|  
  
## <a name="remarks"></a>Примечания  
 По умолчанию <xref:System.StringComparer> класс и <xref:System.String.GetHashCode%2A?displayProperty=nameWithType> метод используют один алгоритм хэширования, который создает согласованный хэш-код между доменами приложений. Это эквивалентно присвоению `enabled` атрибуту элемента значения `<UseRandomizedStringHashAlgorithm>` `0` . Это алгоритм хэширования, используемый в .NET Framework 4.  
  
 <xref:System.StringComparer>Класс и <xref:System.String.GetHashCode%2A?displayProperty=nameWithType> метод могут также использовать другой алгоритм хэширования, который выполняет вычисление хэш-кодов для каждого домена приложения. В результате хэш-коды для эквивалентных строк будут различаться в разных доменах приложений. Эта функция является обязательной. чтобы воспользоваться его преимуществами, необходимо задать `enabled` атрибуту `<UseRandomizedStringHashAlgorithm>` элемента значение `1` .  
  
 Поиск строки в хэш-таблице обычно является операцией O (1). Однако при возникновении большого количества конфликтов Поиск может стать операцией O (n<sup>2</sup>). Элемент Configuration можно использовать `<UseRandomizedStringHashAlgorithm>` для создания случайного алгоритма хэширования на каждый домен приложения, который, в свою очередь, ограничивает количество потенциальных конфликтов, особенно когда ключи, из которых рассчитываются хэш-коды, основываются на вводе данных пользователями.  
  
## <a name="example"></a>Пример  
 В следующем примере определяется `DisplayString` класс, включающий закрытую строковую константу, `s` значение которой равно «это строка». Он также включает метод `ShowStringHashCode`, который отображает значение строки и ее хэш-код вместе с именем домена приложения, в котором метод выполняется.  
  
 [!code-csharp[System.String.GetHashCode#2](../../../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.String.GetHashCode/CS/perdomain.cs#2)]
 [!code-vb[System.String.GetHashCode#2](../../../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.String.GetHashCode/VB/perdomain.vb#2)]  
  
 При выполнении примера без указания файла конфигурации он отображает подобный следующему вывод. Обратите внимание, что хэш-коды для строки идентичны в обоих доменах приложений.  
  
```console
String 'This is a string.' in domain 'PerDomain.exe': 941BCEAC  
String 'This is a string.' in domain 'NewDomain': 941BCEAC  
```  
  
 Однако при добавлении следующего файла конфигурации в каталог примеров и запуске примера, хэш-коды для той же строки будут отличаться по домену приложения.  
  
```xml  
<?xml version ="1.0"?>  
<configuration>  
   <runtime>  
      <UseRandomizedStringHashAlgorithm enabled="1" />  
   </runtime>  
</configuration>  
```  
  
 Если файл конфигурации существует, пример отображает следующие выходные данные:  
  
```console
String 'This is a string.' in domain 'PerDomain.exe': 5435776D  
String 'This is a string.' in domain 'NewDomain': 75CC8236  
```  
  
## <a name="see-also"></a>См. также

- <xref:System.StringComparer.GetHashCode%2A?displayProperty=nameWithType>
- <xref:System.String.GetHashCode%2A?displayProperty=nameWithType>
- <xref:System.Object.GetHashCode%2A?displayProperty=nameWithType>
