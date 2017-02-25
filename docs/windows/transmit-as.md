---
title: "transmit_as | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
f1_keywords: 
  - "vc-attr.transmit_as"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "transmit_as attribute"
ms.assetid: 53d0b8ab-5b06-423e-83eb-3d01a10424b2
caps.latest.revision: 10
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 10
---
# transmit_as
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

コンパイラにクライアント アプリケーションとサーバー アプリケーションが処理する転送された型と指定の型に関連付けるように指示します。  
  
## 構文  
  
```  
  
      [ transmit_as(  
   type  
) ]  
```  
  
#### パラメーター  
 `type`  
 クライアントとサーバーの間で送信されるデータ型を指定します。  
  
## 解説  
 **transmit\_as** C\+\+ 属性に [transmit\_as](http://msdn.microsoft.com/library/windows/desktop/aa367286) の MIDL の属性と同じ機能があります。  
  
## 使用例  
 次のコードは **transmit\_as** 属性の使用方法を示します :  
  
```  
// cpp_attr_ref_transmit_as.cpp  
// compile with: /LD  
#include "windows.h"  
[module(name="MyLibrary")];  
  
[export] typedef struct _TREE_NODE_TYPE {  
unsigned short data;   
struct _TREE_NODE_TYPE * left;  
struct _TREE_NODE_TYPE * right;   
} TREE_NODE_TYPE;  
  
[export] struct PACKED_NODE {  
   unsigned short data;   // same as normal node  
   int index;   // array index of parent  
};  
  
// A left node recursive built array of  
// the nodes in the tree.  Can be unpacked with  
// that knowledge  
[export] typedef struct _TREE_XMIT_TYPE {  
   int count;  
   [size_is(count)] PACKED_NODE node[];  
} TREE_XMIT_TYPE;  
  
[transmit_as(TREE_XMIT_TYPE)] typedef TREE_NODE_TYPE * TREE_TYPE;  
```  
  
## 必要条件  
  
### 属性コンテキスト  
  
|||  
|-|-|  
|**対象**|`typedef`|  
|**複数回の適用**|Ｘ|  
|**必要な属性**|なし|  
|**無効な属性**|なし|  
  
 属性コンテキストの詳細については、「[属性コンテキスト](../windows/attribute-contexts.md)」を参照してください。  
  
## 参照  
 [IDL Attributes](../windows/idl-attributes.md)   
 [Typedef, Enum, Union, and Struct Attributes](../windows/typedef-enum-union-and-struct-attributes.md)   
 [export](../windows/export.md)   
 [Attributes Samples](http://msdn.microsoft.com/ja-jp/558ebdb2-082f-44dc-b442-d8d33bf7bdb8)