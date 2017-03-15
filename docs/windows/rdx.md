---
title: "rdx | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
f1_keywords: 
  - "vc-attr.rdx"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "rdx attribute"
ms.assetid: ff8e4312-c1ad-4934-bdaa-86f54409651e
caps.latest.revision: 14
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 14
---
# rdx
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

レジストリ キーを作成するか既存のレジストリ キーを変更します。  
  
## 構文  
  
```  
  
      [ rdx(   
   key,   
   valuename=NULL,   
   regtype   
) ]  
```  
  
#### パラメーター  
 `key`  
 作成または開くキーの名前。  
  
 `valuename`\(省略可能\)  
 フィールド値を設定するように指定します。  この名前を持つフィールド値が存在しない場合はキーに追加されます。  
  
 *regtype*  
 追加されたレジストリ キーの型。  次のいずれかがあります :  **テキスト  ダブルワード  バイナリ** または `CString`。  
  
## 解説  
 **rdx** C\+\+ 属性はCOM コンポーネントの既存レジストリ キーを作成または変更します。  属性はオブジェクトに BEGIN\_RDX\_MAP マクロを実装する対象メンバー追加します。  `RegistryDataExchange` の BEGIN\_RDX\_MAP マクロの結果として挿入された関数がレジストリにデータ メンバー間でデータの転送に使用できます。  
  
 これらの 1 種類の場合この属性は [コクラス](../windows/coclass.md) とともに[ProgID](../Topic/progid.md)または [vi\_progid](../windows/vi-progid.md) の属性またはそのほかの属性を使用できます。  
  
## 必要条件  
  
### 属性コンテキスト  
  
|||  
|-|-|  
|**対象**|**クラス**  または `struct` のメンバー|  
|**複数回の適用**|Ｘ|  
|**必要な属性**|なし|  
|**無効な属性**|なし|  
  
 属性コンテキストの詳細については、「[属性コンテキスト](../windows/attribute-contexts.md)」を参照してください。  
  
## 使用例  
 次のコードはCMyClass COM コンポーネントを記述するシステムに MyValue というレジストリ キーを追加します。  
  
```  
// cpp_attr_ref_rdx.cpp  
// compile with: /LD /link /OPT:NOREF  
#define _ATL_ATTRIBUTES  
#include "atlbase.h"  
  
[module (name="MyLib")];  
  
class CMyClass {  
public:  
   CMyClass() {  
      strcpy_s(m_sz, "SomeValue");  
   }  
  
   [ rdx(key = "HKCR\\MyApp.MyApp.1", valuename = "MyValue", regtype = "text")]   
   char m_sz[256];  
};  
```  
  
## 参照  
 [COM Attributes](../Topic/COM%20Attributes.md)   
 [registration\_script](../windows/registration-script.md)   
 [Attributes Samples](http://msdn.microsoft.com/ja-jp/558ebdb2-082f-44dc-b442-d8d33bf7bdb8)