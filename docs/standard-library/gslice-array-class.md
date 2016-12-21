---
title: "gslice_array クラス | Microsoft Docs"
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
  - "std::gslice_array"
  - "gslice_array"
  - "valarray/std::gslice_array"
  - "std.gslice_array"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "gslice_array クラス"
ms.assetid: ad1b4514-b14a-4baf-a293-d5a8e8674c75
caps.latest.revision: 20
caps.handback.revision: 10
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# gslice_array クラス
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

汎用スライスをサポートする内部、補助テンプレート クラスは valarray の汎用スライスで定義されたサブセットの配列間の操作を提供することによって変更します。  
  
## 構文  
  
```  
template<class Type>  
   class gslice_array : public gsplice {  
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
 クラスは [gslice](../Topic/gslice%20Class.md) オブジェクト **valarray\<Type\>** オブジェクトから選択して要素のシーケンスを記述できます **gs** とともにオブジェクトを格納しているクラス [valarray](../standard-library/valarray-class.md)**\<種類\>**オブジェクトへの参照 **va** 記述します。  
  
 フォーム [gs VA &#91;&#93;](../Topic/valarray::operator.md)の式を作成することによってのみ **gslice\_array\<Type\>** オブジェクトを構築します。  gslice\_array **valarray\<Type\>**に定義されているクラスのメンバー関数では、対応する関数のシグネチャのように動作しますが、選択したシーケンスの要素だけが影響を受けます。  
  
 このテンプレート クラスは、特定の valarray 操作を通じて間接的に作成され、プログラム内で直接使用することはできません。  内部補助テンプレート クラスはスライス添字演算子によって使用されています:  
  
 `gslice_array`\<**\[種類\]**\>`valarray`\<**\[種類\]** の\>::`operator[]` \(**const gslice&**\)。  
  
 valarray **va**のスライス **gsl** にフォーム **va\[gsl\]**の式を作成することによってのみ **gslice\_array\<Type\>** オブジェクトを構築します。  gslice\_array **valarray\<Type\>**に定義されているクラスのメンバー関数では、対応する関数のシグネチャのように動作しますが、選択したシーケンスの要素だけが影響を受けます。  gslice\_array によって制御される最初のスライスの最初の要素のスライス コンストラクター、インデックス、各スライスの要素数、および各スライス要素の間の 3 番目のパラメーターによって定義されます。  
  
 次に例を示します。  
  
```  
const size_t lv[] = {2, 3};  
const size_t dv[] = {7, 2};  
const valarray<size_t> len(lv, 2), str(dv, 2);  
// va[gslice(3, len, str)] selects elements with  
//   indices 3, 5, 7, 10, 12, 14  
```  
  
 インデックスが有効であると手順に有効である必要があります。  
  
## 使用例  
 slice\_array 宣言および使用する方法の例に [gslice::gslice](../Topic/gslice::gslice.md) "の例を参照してください。  
  
## 必要条件  
 **ヘッダー:** \<valarray\>  
  
 **名前空間:** std  
  
## 参照  
 [C\+\+ 標準ライブラリ内のスレッド セーフ](../standard-library/thread-safety-in-the-cpp-standard-library.md)