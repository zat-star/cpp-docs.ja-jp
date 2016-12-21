---
title: "basic_iostream クラス | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "istream/std::basic_iostream"
  - "std.basic_iostream"
  - "basic_iostream"
  - "std::basic_iostream"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "basic_iostream クラス"
ms.assetid: 294b680b-eb49-4066-8db2-6d52dac9d6e3
caps.latest.revision: 22
caps.handback.revision: 11
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# basic_iostream クラス
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

入力と出力の両方を行うことができるストリーム クラス。  
  
## 構文  
  
```  
template <class Elem, class Tr = char_traits<Elem> >  
    class basic_iostream : public basic_istream<Elem, Tr>,  
        public basic_ostream<Elem, Tr>  
{  
public:  
    explicit basic_iostream(basic_streambuf<Elem, Tr> *_Strbuf);  
    virtual ~basic_iostream();  
};  
```  
  
## 解説  
 このテンプレート クラスは、基底クラス [basic\_ostream](../Topic/basic_ostream%20Class.md)\<`Elem`, `Tr`\> を使用した挿入の制御、および基底クラス [basic\_istream](../Topic/basic_istream%20Class.md)\<`Elem`, `Tr`\> を使用した抽出の制御を行うオブジェクトを記述します。  2 つのオブジェクトは、仮想基底クラス [basic\_ios](../Topic/basic_ios%20Class.md)\<`Elem`、`Tr`\> を共有しています。  また、これらは共通のストリーム バッファーを管理します。このストリーム バッファーには、`Elem` 型の要素が含まれ、その文字特性は `Tr` クラスによって決定されます。  コンストラクターは `basic_istream`\(**strbuf**\) および `basic_ostream`\(**strbuf**\) を使用して基底クラスを初期化します。  
  
### コンストラクター  
  
|||  
|-|-|  
|[basic\_iostream](../Topic/basic_iostream::basic_iostream.md)|`basic_iostream` オブジェクトを作成します。|  
  
### メンバー関数  
  
|||  
|-|-|  
|[swap](../Topic/basic_iostream::swap.md)|提供された `basic_iostream` オブジェクトのコンテンツを、このオブジェクトのコンテンツと交換します。|  
  
### 演算子  
  
|||  
|-|-|  
|[operator \=](../Topic/basic_iostream::operator=.md)|このオブジェクトに、指定された `basic_iostream` オブジェクトの値を代入します。  これは、`rvalue` が関係する移動代入で、コピーは残りません。|  
  
## 必要条件  
 **ヘッダー:** \<istream\>  
  
 **名前空間:** std  
  
## 参照  
 [C\+\+ 標準ライブラリ内のスレッド セーフ](../standard-library/thread-safety-in-the-cpp-standard-library.md)   
 [iostream プログラミング](../Topic/iostream%20Programming.md)   
 [iostreams の規則](../standard-library/iostreams-conventions.md)