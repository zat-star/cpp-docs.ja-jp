---
title: "emitidl | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
f1_keywords: 
  - "vc-attr.emitidl"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "emitidl attribute"
ms.assetid: 85b80c56-578e-4392-ac03-8443c74ebb7d
caps.latest.revision: 10
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 10
---
# emitidl
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

その後の IDL 属性が生成される .idl ファイルを処理して配置されているかどうかを判定します。  
  
## 構文  
  
```  
  
      [ emitidl([boolean],  
   defaultimports=[boolean]  
) ] ;  
```  
  
#### パラメーター  
 `boolean`  
 有効値 : **trueFalse 強制 restricted プッシュ** または **pop**。  
  
-   **true** が生成された .idl ファイルはソース・コード ファイルで見つかったすべての IDL 宣言のカテゴリ属性。  これは **out** の既定の設定です。  
  
-   **False** が生成された .idl ファイルはソース・コード ファイルで見つかったすべてのカテゴリの配置する IDL 属性。  
  
-   **restricted**の [モジュール](../windows/module-cpp.md) の属性を持たないファイルの割り当ての IDL 属性。  コンパイラは.idl ファイルは生成されません。  
  
-   **強制**  のファイルの上書きに IDL 属性がある場合ファイルは  **モジュール**  の属性を持つことを要求する **restricted**  の後続の属性。  
  
-   **プッシュ**  は **out**  の内部スタックに **out**  の現在の設定を保存できるようにし値が **out**  の内部スタックの上部にある **pop**  は **out**  をに設定することもできます。  
  
 \[**defaultimports***\=*\(省略可能\) `boolean` 入力\]  
 -   `boolean` が **True** 場合docobj.idl は生成された .idl ファイルにインポートします。  また.h ファイルと同じディレクトリにソース・コードに含まれる同じ `#include` の .idl ファイルとして .h ファイルとし生成された .idl ファイルは次のインポート ステートメントを .idl ファイルが含まれます。  
  
-   `boolean` が **False** 場合docobj.idl は生成された .idl ファイルにインポートします。  明示的に [インポート](../windows/import.md) の .idl ファイルをインポートする必要があります。  
  
## 解説  
 **out** C\+\+ 属性がソース・コード ファイルで見つかった後IDL カテゴリ属性は生成された .idl ファイルに格納されます。  **out** の属性がない場合ソース・コード ファイルの IDL 属性は生成された .idl ファイルに出力されます。  
  
 ソース・コード ファイルの **out** の複数の属性を持つことができます。  `[emitidl(false)];` が後続の `[emitidl(true)];` なしでファイルに検出された場合属性は生成された .idl ファイルに処理されません。  
  
 コンパイラが新しいファイルが発生するたびに**out** は **true** に暗黙的に設定されます。  
  
## 必要条件  
  
### 属性コンテキスト  
  
|||  
|-|-|  
|**対象**|任意|  
|**複数回の適用**|Ｘ|  
|**必要な属性**|なし|  
|**無効な属性**|なし|  
  
 詳細については[属性コンテキスト](../windows/attribute-contexts.md) を参照してください。  
  
## 参照  
 [Compiler Attributes](../windows/compiler-attributes.md)   
 [Stand\-Alone Attributes](../Topic/Stand-Alone%20Attributes.md)   
 [Attributes Samples](http://msdn.microsoft.com/ja-jp/558ebdb2-082f-44dc-b442-d8d33bf7bdb8)