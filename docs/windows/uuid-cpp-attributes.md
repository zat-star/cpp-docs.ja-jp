---
title: "uuid (C++ Attributes) | Microsoft Docs"
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
  - "vc-attr.uuid"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "uuid attribute"
ms.assetid: 90562a94-5e28-451b-a4b0-cadda7f66efe
caps.latest.revision: 11
caps.handback.revision: 11
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# uuid (C++ Attributes)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

クラスまたはインターフェイスの一意の ID を指定します。  
  
## 構文  
  
```  
  
      [ uuid(  
   "uuid"  
) ]  
```  
  
#### パラメーター  
 *uuid*  
 128 ビットの一意の識別子。  
  
## 解説  
 インターフェイスまたはクラスの定義で C\+\+ 属性 `uuid` を指定しない場合は、Visual C\+\+ コンパイラが指定します。  `uuid` を指定する場合は、引用符を含める必要があります。  
  
 `uuid` を指定しない場合は、コンピューター上にある異なる属性のプロジェクトの同名のインターフェイスやクラスに対して、1 つの GUID がコンパイラによって生成されます。  
  
 Uuidgen.exe または Guidgen.exe を使用すると、独自の ID を生成できます。  これらのツールのいずれかを実行するには、**\[スタート\]** をクリックし、メニューの \[ファイル名を指定して実行\] をクリックします。  次に、必要なツールの名前を入力します。  
  
 ATL も使用しないプロジェクトでは、`uuid` 属性の指定は [uuid](../cpp/uuid-cpp.md) の \_\_declspec 修飾子の指定と同じです。  クラスの `uuid` の取得には [\_\_uuidof](../cpp/uuidof-operator.md) を使用できます。  
  
## 使用例  
 `uuid` の使用例については、「[bindable](../windows/bindable.md)」を参照してください。  
  
## 必要条件  
  
### 属性コンテキスト  
  
|||  
|-|-|  
|**対象**|**class**、`struct`、`interface`、**union**、`enum`|  
|**複数回の適用**|Ｘ|  
|**必要な属性**|なし|  
|**無効な属性**|なし|  
  
 属性コンテキストの詳細については、「[属性コンテキスト](../windows/attribute-contexts.md)」を参照してください。  
  
## 参照  
 [IDL Attributes](../windows/idl-attributes.md)   
 [Interface Attributes](../windows/interface-attributes.md)   
 [Class Attributes](../windows/class-attributes.md)   
 [Typedef, Enum, Union, and Struct Attributes](../windows/typedef-enum-union-and-struct-attributes.md)   
 [uuid](http://msdn.microsoft.com/library/windows/desktop/aa367302)   
 [Attributes Samples](http://msdn.microsoft.com/ja-jp/558ebdb2-082f-44dc-b442-d8d33bf7bdb8)