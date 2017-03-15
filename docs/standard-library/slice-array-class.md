---
title: "slice_array クラス | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "slice_array"
  - "valarray/std::slice_array"
  - "std.slice_array"
  - "std::slice_array"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "slice_array クラス"
ms.assetid: a182d5f7-f35c-4e76-86f2-b5ac64ddc846
caps.latest.revision: 20
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 20
---
# slice_array クラス
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

一部の配列間の操作によって、スライス オブジェクトをサポートする内部、補助テンプレート クラスは valarray のスライスで定義されています。  
  
## 構文  
  
```  
template<class Type>  
   class slice_array : public slice {  
public:  
   typedef Type value_type;  
   void operator=(  
      const valarray<Type>& x  
   ) const;  
   void operator=(  
      const Type& x  
   ) const;  
   void operator*=(  
      const valarray<Type>& x  
   ) const;  
   void operator/=(  
      const valarray<Type>& x  
   ) const;  
   void operator%=(  
      const valarray<Type>& x  
   ) const;  
   void operator+=(  
      const valarray<Type>& x  
   ) const;  
   void operator-=(  
      const valarray<Type>& x  
   ) const;  
   void operator^=(  
      const valarray<Type>& x  
   ) const;  
   void operator&=(  
      const valarray<Type>& x  
   ) const;  
   void operator|=(  
      const valarray<Type>& x  
   ) const;  
   void operator<<=(  
      const valarray<Type>& x  
   ) const;  
   void operator>>=(  
      const valarray<Type>& x  
   ) const;  
// The rest is private or implementation defined  
}  
```  
  
## 解説  
 クラスは **valarray\<Type\>** オブジェクトから選択して要素のシーケンスを表すクラス [スライス](../Topic/slice%20Class.md)オブジェクトとともにオブジェクトを格納しているクラス [valarray](../standard-library/valarray-class.md)**\<種類\>**オブジェクトへの参照を記述します。  
  
 このテンプレート クラスは、特定の valarray 操作を通じて間接的に作成され、プログラム内で直接使用することはできません。  スライス添字演算子によって使用される内部、補助テンプレート クラス:  
  
 `slice_array`\<**\[種類\]**\>`valarray`\<**\[種類\]** の::`operator[]` \(`slice`\)。  
  
 valarray **va**のスライス **sl** にフォーム [sl VA &#91;&#93;](../Topic/valarray::operator.md)の式を作成することによってのみ **slice\_array\<Type\>** オブジェクトを構築します。  slice\_array **valarray\<Type\>**に定義されているクラスのメンバー関数では、対応する関数のシグネチャのように動作しますが、選択したシーケンスの要素だけが影響を受けます。  slice\_array によって制御スライスの最初の要素のスライス コンストラクター、インデックス、要素数、および要素の間の 3 番目のパラメーターによって定義されます。  **va**で宣言された valarray **va** から slice\_array 切り取り\[`slice` \(2、5、3\) は **va**からのインデックス 2、5、8、11、および 14 を持つ要素を選択します。  インデックスが有効であると手順に有効である必要があります。  
  
## 使用例  
 slice\_array 宣言および使用する方法の例に [slice::slice](../Topic/slice::slice.md) "の例を参照してください。  
  
## 必要条件  
 **ヘッダー:** \<valarray\>  
  
 **名前空間:** std  
  
## 参照  
 [C\+\+ 標準ライブラリ内のスレッド セーフ](../standard-library/thread-safety-in-the-cpp-standard-library.md)