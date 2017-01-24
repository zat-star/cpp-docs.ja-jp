---
title: "custom (C++) | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
f1_keywords: 
  - "vc-attr.custom"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "custom attributes, defining"
ms.assetid: 3abac928-4d55-4ea6-8cf6-8427a4ad79f1
caps.latest.revision: 12
caps.handback.revision: 12
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# custom (C++)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

タイプ ライブラリ内のオブジェクトのメタデータを定義します。  
  
## 構文  
  
```  
  
      [ custom(  
   uuid,   
   value  
) ];  
```  
  
#### パラメーター  
 *uuid*  
 一意の ID。  
  
 *value*  
 バリアントに送信する値。  
  
## 解説  
 **カスタム**  C\+\+ 属性は情報をタイプ ライブラリに配置します。  タイプ ライブラリから値を読み取るカスタム ツールが必要です。  
  
 **カスタム**  の属性に [カスタム](http://msdn.microsoft.com/library/windows/desktop/aa366766) の MIDL の属性と同じ機能があります。  
  
## 必要条件  
  
### 属性コンテキスト  
  
|||  
|-|-|  
|**対象**|非 COM `interface` **クラス** `enum`の `idl_module` のメソッドはインターフェイスとインターフェイスのメンバーパラメーター`typedef` **共用体** `struct`|  
|**複数回の適用**|○|  
|**必要な属性**|\(クラスで使用される場合\) **コクラス**|  
|**無効な属性**|なし|  
  
 属性コンテキストの詳細については、「[属性コンテキスト](../windows/attribute-contexts.md)」を参照してください。  
  
## 参照  
 [IDL Attributes](../windows/idl-attributes.md)   
 [Stand\-Alone Attributes](../Topic/Stand-Alone%20Attributes.md)   
 [Typedef, Enum, Union, and Struct Attributes](../windows/typedef-enum-union-and-struct-attributes.md)   
 [Parameter Attributes](../windows/parameter-attributes.md)   
 [Method Attributes](../windows/method-attributes.md)   
 [Class Attributes](../windows/class-attributes.md)   
 [Interface Attributes](../windows/interface-attributes.md)   
 [Attributes Samples](http://msdn.microsoft.com/ja-jp/558ebdb2-082f-44dc-b442-d8d33bf7bdb8)