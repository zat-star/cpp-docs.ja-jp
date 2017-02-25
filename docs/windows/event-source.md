---
title: "event_source | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
f1_keywords: 
  - "vc-attr.event_source"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "イベント処理, 属性"
  - "イベント ログ, イベント ソース"
  - "イベント ソース, 作成"
  - "event_source 属性"
  - "イベント ソース"
  - "イベント処理, イベント ソースの作成"
ms.assetid: 0983e36a-6127-4fbb-8a22-8dfec6564c16
caps.latest.revision: 13
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 13
---
# event_source
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

イベント ソースを作成します。  
  
## 構文  
  
```  
  
       [ event_source(  
       type,  
optimize=[speed | size],  
decorate=[true | false]) ]  
```  
  
#### パラメーター  
 `type`  
 次の値のいずれかの列挙です。  
  
-   アンマネージ C\/C\+\+ コード用の `native` \(アンマネージ クラスの既定\)。  
  
-   COM コード用の `com`。`type`\=`com` の場合、`coclass` を使用する必要があります。 この値の場合、ユーザーが次のヘッダー ファイルを含める必要があります。  
  
    ```  
    #define _ATL_ATTRIBUTES  
    #include <atlbase.h>  
    #include <atlcom.h>  
    ```  
  
 **optimize**  
 `type` が **native** の場合、**optimize\=size** と指定すると、クラスのすべてのイベント用に記憶域が \(最低\) 4 バイトあることを指定でき、\(既定の\) **optimize\=speed** を指定すると、記憶域が 4 \* \(イベントの \#\) バイトあることを指定できます。  
  
 **decorate**  
 `type` が **native** の場合、**decorate\=false** と指定すると、結合 \(.mrg\) ファイル内の拡張名に括弧で囲んでいるクラス名を含まないように指定できます。[\/Fx](../build/reference/fx-merge-injected-code.md) では、.mrg ファイルを生成できます。 既定の **decorate\=false** では、結合されたファイルで型名は完全修飾されます。  
  
## 解説  
 **event\_source** C\+\+ 属性では、それが適用されているクラスまたは構造がイベント ソースとなることを指定します。  
  
 **event\_source** は、[event\_receiver](../windows/event-receiver.md) 属性と [\_\_event](../cpp/event.md) キーワードと共に使用します。 イベント レシーバーの作成には、**event\_receiver** を使用します。 イベント ソース内のメソッドで `__event` を使用すると、それらのメソッドをイベントとして指定することができます。  
  
> [!NOTE]
>  テンプレート クラスまたは構造体にイベントを含めることはできません。  
  
## 必要条件  
  
### 属性コンテキスト  
  
|||  
|-|-|  
|**対象**|**class**、`struct`|  
|**反復可能**|いいえ|  
|**必要な属性**|`type`\=**com** のとき、**coclass**|  
|**無効な属性**|なし|  
  
 詳細については、「[属性コンテキスト](../windows/attribute-contexts.md)」を参照してください。  
  
## 参照  
 [Compiler Attributes](../windows/compiler-attributes.md)   
 [event\_receiver](../windows/event-receiver.md)   
 [\_\_event](../cpp/event.md)   
 [\_\_hook](../cpp/hook.md)   
 [\_\_unhook](../cpp/unhook.md)   
 [Class Attributes](../windows/class-attributes.md)   
 [Attributes Samples](http://msdn.microsoft.com/ja-jp/558ebdb2-082f-44dc-b442-d8d33bf7bdb8)