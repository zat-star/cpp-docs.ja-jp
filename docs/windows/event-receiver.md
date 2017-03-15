---
title: "event_receiver | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
f1_keywords: 
  - "vc-attr.event_receiver"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "event_receiver attribute"
  - "event receivers"
  - "events [C++], event receivers (sinks)"
  - "event handling [C++], attributes"
  - "event handling [C++], creating receiver"
  - "event sinks, creating"
  - "event sinks"
ms.assetid: bf8fe770-3ea2-4128-b46b-166222ee4097
caps.latest.revision: 13
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 13
---
# event_receiver
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

イベント レシーバー \(シンク\) を作成します。  
  
## 構文  
  
```  
  
      [ event_receiver(  
   type   
   [, layout_dependent=false]   
) ]  
```  
  
#### パラメーター  
 `type`  
 次の値の 1 種類の列挙型 :  
  
-   アンマネージ ネイティブ \(C\/C\+\+ コードのクラスの既定\) の `native`。  
  
-   COM コードの `com`。  この値は次のヘッダー ファイルが含まれていることが必要です :  
  
    ```  
    #define _ATL_ATTRIBUTES  
    #include <atlbase.h>  
    #include <atlcom.h>  
    ```  
  
 **layout\_dependent**  
 *layout\_dependent* だけ `type`\=**com** 指定します。  *layout\_dependent* ブール値です :  
  
-   **true** イベント ハンドラーのデリゲートのシグネチャがイベント ソースにフックするシグネチャと一致しなければならないことを意味します。  イベント レシーバーのハンドラー名は関連するイベント ソース インターフェイスで指定された名前と一致する必要があります。  *layout\_dependent* です **true コクラス**  を使用する必要があります。  これは **True** を指定するとわずかに効率的です。  
  
-   呼び出し規約およびストレージ クラスが仮想 \(など\)静的メソッドおよびイベント ハンドラーと一致する必要がないことを **False** \(既定値\) になります。; ハンドラー名はイベント ソース インターフェイスのメソッド名と一致する必要があります。  
  
## 解説  
 **event\_receiver** C\+\+ 属性が適用されたクラスまたは構造体がイベント レシーバーであることを指定します。Visual C\+\+ で統一されたイベント モデルを使用します。  
  
 **event\_receiver** は [ソース](../windows/event-source.md) の属性と [\_\_hook](../cpp/hook.md) と [\_\_unhook](../cpp/unhook.md) のキーワードとともに使用されます。  イベント ソースを作成するには  **ソース**  を使用します。  イベント ソースでイベントにフック \(「」\) イベント レシーバーのメソッドを関連付けるにはイベント レシーバーのメソッド内の `__hook` を使用します。  これらを分離するために `__unhook` を使用します。  
  
 *layout\_dependent* COM イベント レシーバー `type`\(\=\)**com** に対してのみ指定されます。  *layout\_dependent* の既定値は **False** です。  
  
> [!NOTE]
>  テンプレート クラスまたは構造体にイベントを含めることはできません。  
  
## 必要条件  
  
### 属性コンテキスト  
  
|||  
|-|-|  
|**対象**|**クラス**  `struct`|  
|**複数回の適用**|Ｘ|  
|**必要な属性**|**コクラス**  ときに layout\_dependent\=**true**|  
|**無効な属性**|なし|  
  
 詳細については[属性コンテキスト](../windows/attribute-contexts.md) を参照してください。  
  
## 参照  
 [Compiler Attributes](../windows/compiler-attributes.md)   
 [event\_source](../windows/event-source.md)   
 [\_\_event](../cpp/event.md)   
 [\_\_hook](../cpp/hook.md)   
 [\_\_unhook](../cpp/unhook.md)   
 [Class Attributes](../windows/class-attributes.md)   
 [Attributes Samples](http://msdn.microsoft.com/ja-jp/558ebdb2-082f-44dc-b442-d8d33bf7bdb8)