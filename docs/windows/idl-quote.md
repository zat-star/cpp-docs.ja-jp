---
title: "idl_quote | Microsoft Docs"
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
  - "vc-attr.idl_quote"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "idl_quote attribute"
ms.assetid: a370e1b7-948b-4e67-9a25-58facf24e4c9
caps.latest.revision: 10
caps.handback.revision: 10
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# idl_quote
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

はVisual C\+\+ の現在のバージョンでサポートされていない使用して生成された .idl ファイルにIDL いる構造体。  
  
## 構文  
  
```  
  
      [ idl_quote(  
   text  
) ]  
```  
  
#### パラメーター  
 *text*  
 コンパイラ エラーを返さないで生成された .idl ファイルに渡されるようにVisual C\+\+ コンパイラを使用する属性名。  
  
## 解説  
 **idl\_quote** C\+\+ 属性は属性として最後にセミコロン \(後の角かっこ\) を使用するとあるようにテキスト  *は* マージされた .idl ファイル内に配置されます。  **idl\_quote** がシンボルで使用する場合 *テキストは*  そのシンボルの属性ブロック内に配置されます。  
  
## 使用例  
 次のコードはのサポートされる .idl\) と未定義の構造を定義および使用する方法を示しています  **入力**  を使用してサポートされていない属性を指定する方法を示しています :  
  
```  
// cpp_attr_ref_idl_quote.cpp  
// compile with: /LD  
#include <unknwn.h>  
[module(name="MyLibrary")];  
  
[export]  
struct MYFLOT {  
   int i;  
};  
  
[export]  
struct MYDUB {  
   int i;  
};  
  
[idl_quote("typedef union _S1_TYPE switch (long l1) U1_TYPE { case 1024: \  
struct MYFLOT f1; case 2048: struct MYDUB d2; } S1_TYPE;") ];  
  
typedef struct _S1_TYPE {   
   long l1;   
  
union {   
   MYFLOT f1; MYDUB d2; } U1_TYPE;   
} S1_TYPE;  
  
[uuid("2F5F63F1-16DA-11d2-9E7B-00C04FB926DA"), object]  
__interface IStatic{  
   HRESULT Func1([idl_quote("in")] int i);  
   HRESULT func( S1_TYPE* myStruct );  
};  
```  
  
 このコードは MYFLOT と MYDUB と生成された .idl ファイルに含める  *テキスト入力*  します。  *name パラメーターの*  型は前に生成された .idl ファイルの参照の  *名前*  は何も配置に  *短いメッセージを*  送信します。   *依存関係の*  パラメーターは依存関係のリスト定義を生成される .idl ファイルにあらかじめ  *テキスト*  配置されるようにします。  
  
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
 [Attributes Samples](http://msdn.microsoft.com/ja-jp/558ebdb2-082f-44dc-b442-d8d33bf7bdb8)