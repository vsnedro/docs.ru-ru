---
description: 'Дополнительные сведения: <chunkedCookieHandler>'
title: <chunkedCookieHandler>
ms.date: 03/30/2017
ms.assetid: 7220de45-1d14-4aec-a29e-4a2ea8ac861f
author: BrucePerlerMS
ms.openlocfilehash: b0090706d3d7a9f62e17ae63ec16e4b3a869a812
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/06/2021
ms.locfileid: "99664292"
---
# \<chunkedCookieHandler>

Настраивает <xref:System.IdentityModel.Services.ChunkedCookieHandler> . Этот элемент может присутствовать только в том случае, если `mode` атрибут `<cookieHandler>` элемента имеет значение "default" или "фрагментированный".  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.identityModel.services>**](system-identitymodel-services.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<federationConfiguration>**](federationconfiguration.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<cookieHandler>**](cookiehandler.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<chunkedCookieHandler>**  
  
## <a name="syntax"></a>Синтаксис  
  
```xml  
<system.identityModel.services>  
  <federationConfiguration>  
    <cookieHandler mode="Chunked||Default" >  
      <chunkedCookieHandler size=xs:int >  
      </chunkedCookieHandler>  
    </cookieHandler>  
  </federationConfiguration>  
</system.identityModel.services>  
```  
  
## <a name="attributes-and-elements"></a>Атрибуты и элементы  

 В следующих разделах описаны атрибуты, дочерние и родительские элементы.  
  
### <a name="attributes"></a>Атрибуты  
  
|Атрибут|Описание|  
|---------------|-----------------|  
|chunkSize|Максимальный размер (в символах) данных cookie HTTP для одного файла cookie HTTP. При изменении размера фрагмента данных необходимо соблюдать осторожность. Веб-браузеры имеют разные ограничения на размер файлов cookie и число допустимых для каждого домена. Например, исходная спецификация Netscape поменяет такие ограничения: 300 cookies Total, 4096 байт на заголовок файла cookie (включая метаданные, а не только значение файла cookie) и 20 файлов cookie на домен. Значение по умолчанию — 2000. Обязательный элемент.|  
  
### <a name="child-elements"></a>Дочерние элементы  

 None  
  
### <a name="parent-elements"></a>Родительские элементы  
  
|Элемент|Описание|  
|-------------|-----------------|  
|[\<cookieHandler>](cookiehandler.md)|Настраивает <xref:System.IdentityModel.Services.CookieHandler> , что <xref:System.IdentityModel.Services.SessionAuthenticationModule> (SAM) использует для чтения и записи файлов cookie.|  
  
## <a name="remarks"></a>Remarks  

 При указании, <xref:System.IdentityModel.Services.ChunkedCookieHandler> задав `mode` `<cookieHandler>` для атрибута элемента значение "по умолчанию" или "фрагментированный", можно указать размер фрагмента, который обработчик файлов cookie использует для чтения и записи файлов cookie, включая `<chunkedCookieHandler>` дочерний элемент и устанавливая его `chunkSize` атрибут. Если `<chunkedCookieHandler>` элемент отсутствует, используется размер фрагмента по умолчанию (2000 байт). Этот элемент не может быть указан, если `mode` для атрибута задано значение Custom.  
  
 `<chunkedCookieHandler>`Элемент представлен <xref:System.IdentityModel.Services.ChunkedCookieHandlerElement> классом.  
  
## <a name="example"></a>Пример  

 В следующем примере настраивается обработчик фрагментированных файлов cookie, который записывает файлы cookie в фрагменты 3000 байт.  
  
```xml  
<cookieHandler mode="Chunked">  
    <chunkedCookieHandler chunkSize=3000/>  
</cookieHandler>  
```  
  
## <a name="see-also"></a>См. также

- <xref:System.IdentityModel.Services.ChunkedCookieHandler>
