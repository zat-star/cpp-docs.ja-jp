---
title: "import | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
f1_keywords: 
  - "vc-attr.import"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "import attribute"
ms.assetid: ebf07cae-39fb-4047-8b57-54af0a9a83de
caps.latest.revision: 9
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 9
---
# import
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

ユーザーがメイン IDL から参照する定義を含む別の .idl .odlまたはヘッダー ファイルを指定します。  
  
## 構文  
  
```  
  
      [ import(  
   idl_file  
) ];  
```  
  
#### パラメーター  
 `idl_file`  
 で目的の .idl ファイルの名前は現在のプロジェクト タイプ ライブラリにインポートします。  
  
## 解説  
 **インポート**  C\+\+ 属性は生成された .idl ファイルで `#import` のステートメントを `import "docobj.idl"` のステートメントの下に配置します。   **インポート**  の属性に [インポート](http://msdn.microsoft.com/library/windows/desktop/aa367047) の MIDL の属性と同じ機能があります。  
  
 **インポート**  の属性はプロジェクトで生成された .idl ファイルに指定したファイルのみを配置します ;  **インポート**  の属性はプロジェクトのソース・コードの指定したファイルの構造を呼び出すことはできません。  .h ファイルがある場合はプロジェクトのソース・コードの指定したファイルの構造を呼び出すにはを [\#import](../Topic/%23import%20Directive%20\(C++\).md) と `embedded_idl` は属性と属性がまたは `idl_file` の .h ファイルを含めることができます。  
  
## 使用例  
 次のコード :  
  
```  
// cpp_attr_ref_import.cpp  
// compile with: /LD  
[module(name="MyLib")];  
[import(import.idl)];  
```  
  
 生成された .idl ファイルに次のコードを生成します :  
  
```  
import "docobj.idl";  
import "import.idl";  
  
[ uuid(EED3644C-8488-3ECD-BA97-147DB3CDB499), version(1.0) ]  
library MyLib {  
   importlib("stdole2.tlb");  
   importlib("olepro32.dll");  
...  
```  
  
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
 [IDL Attributes](../windows/idl-attributes.md)   
 [Stand\-Alone Attributes](../Topic/Stand-Alone%20Attributes.md)   
 [importidl](../windows/importidl.md)   
 [importlib](../windows/importlib.md)   
 [include](../windows/include-cpp.md)   
 [includelib](../windows/includelib-cpp.md)   
 [Attributes Samples](http://msdn.microsoft.com/ja-jp/558ebdb2-082f-44dc-b442-d8d33bf7bdb8)