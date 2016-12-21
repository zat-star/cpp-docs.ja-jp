---
title: "const_mem_fun1_t クラス | Microsoft Docs"
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
  - "std.const_mem_fun1_t"
  - "xfunctional/std::const_mem_fun1_t"
  - "std::const_mem_fun1_t"
  - "const_mem_fun1_t"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "const_mem_fun1_t クラス"
ms.assetid: 250fac30-9663-4133-9051-6303f76ea259
caps.latest.revision: 20
caps.handback.revision: 10
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# const_mem_fun1_t クラス
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

ポインター引数と初期化された場合二項関数オブジェクトとして呼び出される一つの引数を受け取り **const** メンバー関数を可能にするアダプター クラスです。  
  
## 構文  
  
```  
template<class Result, class Type, class Arg>  
   class const_mem_fun1_t  
      : public binary_function<const Type *, Arg, Result>   
   {  
   explicit const_mem_fun1_t( Result ( Type::* _Pm )( Arg ) const );  
   Result operator()(  
      const Type* _Pleft,   
      Arg _Right  
   ) const;  
   };  
```  
  
#### パラメーター  
 `_Pm`  
 関数オブジェクトに変換する **\[種類\]** クラスのメンバー関数へのポインター。  
  
 `_Pleft`  
 `_Pm` のメンバー関数を呼び出すこと **const** オブジェクト。  
  
 `_Right`  
 `_Pm`に指定する引数。  
  
## 戻り値  
 最適なバイナリ関数。  
  
## 解説  
 このテンプレート クラスは、プライベート メンバー オブジェクトのクラス **\[種類\]** のメンバー関数へのポインターである `_Pm`のコピーを保存します。  これは、返されるとメンバー関数 `operator()` \(**\_Pleft**\-\>\* *Pm\)* **右** \(定義\) **const**。  
  
## 使用例  
 `const_mem_fun1_t` のコンストラクターは、通常、直接使用できません; ヘルパー関数 `mem_fun` がメンバー関数を適応させるために使用されます。  メンバー関数アダプターを使用する方法の例については、" [mem\_fun](../Topic/mem_fun%20Function.md) を参照してください。  
  
## 必要条件  
 **ヘッダー:** \<functional\>  
  
 **名前空間:** std  
  
## 参照  
 [C\+\+ 標準ライブラリ内のスレッド セーフ](../standard-library/thread-safety-in-the-cpp-standard-library.md)   
 [標準テンプレート ライブラリ](../misc/standard-template-library.md)