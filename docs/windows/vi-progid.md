---
title: "vi_progid | Microsoft Docs"
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
  - "vc-attr.vi_progid"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "vi_progid attribute"
ms.assetid: a52449be-b93e-4111-b883-44bb8da53261
caps.latest.revision: 10
caps.handback.revision: 10
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# vi_progid
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

ProgID のバージョンに依存しない形式を指定します。  
  
## 構文  
  
```  
  
      [ vi_progid(  
   name  
) ];  
```  
  
#### パラメーター  
 *name*  
 オブジェクトを表すバージョンに依存しない ProgID。  
  
 ProgID を指定 COM\/ActiveX のオブジェクトを識別するために使用されるクラス ID \(CLSID\) の人が判読できるバージョン。  
  
## 解説  
 **vi\_progid** C\+\+ 属性はCOM オブジェクトのバージョンに依存しない ProgID を指定することができます。  ProgID にフォーム *name1.name2.version が*  あります。  バージョン依存しない  *バージョン*  に ProgID  *は*  ありません。  コクラスに **ProgID** と **vi\_progid** の属性の両方を指定することもできます。  **vi\_progid** を指定しない場合バージョンに依存しない ProgID は [ProgID](../Topic/progid.md) の属性で指定された値になります。  
  
 **vi\_progid** は  **コクラス**  の属性を意味します。つまり**vi\_progid** を指定する場合は **コクラス**  と **vi\_progid** の属性を指定するのと同じ意味です。  
  
 **vi\_progid** の属性によってクラスが自動的に指定された名前で登録します。  生成された .idl ファイルはProgID の値を表示します。  
  
 ATL プロジェクトでは[コクラス](../windows/coclass.md) の属性も指定してある場合はProgID は **GetVersionIndependentProgID** の関数で使用されます \( **コクラス**  の属性によって挿入\)。  
  
## 使用例  
 **vi\_progid** の使用例については [コクラス](../windows/coclass.md) の例を参照してください。  
  
## 必要条件  
  
### 属性コンテキスト  
  
|||  
|-|-|  
|**対象**|**クラス**  `struct`|  
|**複数回の適用**|Ｘ|  
|**必要な属性**|なし|  
|**無効な属性**|なし|  
  
 属性コンテキストの詳細については、「[属性コンテキスト](../windows/attribute-contexts.md)」を参照してください。  
  
## 参照  
 [IDL Attributes](../windows/idl-attributes.md)   
 [Typedef, Enum, Union, and Struct Attributes](../windows/typedef-enum-union-and-struct-attributes.md)   
 [Class Attributes](../windows/class-attributes.md)   
 [ProgID Key](http://msdn.microsoft.com/library/windows/desktop/dd542719)   
 [Attributes Samples](http://msdn.microsoft.com/ja-jp/558ebdb2-082f-44dc-b442-d8d33bf7bdb8)