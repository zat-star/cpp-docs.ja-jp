---
title: "export | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
f1_keywords: 
  - "vc-attr.export"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "export attribute"
ms.assetid: 70b3e848-fad6-4e09-8c72-be60ca72a4df
caps.latest.revision: 11
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 11
---
# export
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

データ構造を .idl ファイル内に配置します。  
  
## 構文  
  
```  
  
[export]  
  
```  
  
## 解説  
 **エクスポート**  C\+\+ 属性はデータ構造を .idl ファイルに置かれとそのすべての言語で使用できるようにするバイナリ互換性のない形式でタイプ ライブラリで使用できます。  
  
 クラスにパブリック メンバー \(`struct` の値\) がある場合でもクラスに  **エクスポート**  の属性を適用できません。  
  
 名前のない `enum`または `struct`をエクスポートし*x* はシーケンシャル番号です。*x* は**\_\_unnamed** から始まる指定された名前です。  
  
 エクスポートに対して有効な型定義は基本型構造体共用体列挙型または型の識別子です。  詳細については[型定義](http://msdn.microsoft.com/library/windows/desktop/aa367287) を参照してください。  
  
## 使用例  
 次のコードは  **エクスポート**  属性の使用方法を示します :  
  
```  
// cpp_attr_ref_export.cpp  
// compile with: /LD  
[module(name="MyLibrary")];  
  
[export]  
struct MyStruct {  
   int i;  
};  
```  
  
## 必要条件  
  
### 属性コンテキスト  
  
|||  
|-|-|  
|**対象**|**共用体**  `typedef` `enum` `struct`または `interface`|  
|**複数回の適用**|Ｘ|  
|**必要な属性**|なし|  
|**無効な属性**|なし|  
  
 詳細については[属性コンテキスト](../windows/attribute-contexts.md) を参照してください。  
  
## 参照  
 [Compiler Attributes](../windows/compiler-attributes.md)   
 [Typedef, Enum, Union, and Struct Attributes](../windows/typedef-enum-union-and-struct-attributes.md)   
 [Attributes Samples](http://msdn.microsoft.com/ja-jp/558ebdb2-082f-44dc-b442-d8d33bf7bdb8)