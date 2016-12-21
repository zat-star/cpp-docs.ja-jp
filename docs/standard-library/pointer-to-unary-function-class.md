---
title: "pointer_to_unary_function クラス | Microsoft Docs"
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
  - "xfunctional/std::pointer_to_unary_function"
  - "pointer_to_unary_function"
  - "std.pointer_to_unary_function"
  - "std::pointer_to_unary_function"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "pointer_to_unary_function クラス"
  - "pointer_to_unary_function 関数"
ms.assetid: 05600207-b916-4759-beca-6b6facd2d6f6
caps.latest.revision: 21
caps.handback.revision: 11
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# pointer_to_unary_function クラス
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

単項関数ポインターを適応性のある単項関数に変換します。  
  
## 構文  
  
```  
template<class Arg, class Result>  
class pointer_to_unary_function  
    : public unary_function<Arg, Result>   
    {  
    public:  
        explicit pointer_to_unary_function(  
            Result (*_pfunc)(Arg)  
        );  
        Result operator()(  
            Arg _Left  
        ) const;  
    };  
```  
  
#### パラメーター  
 `_pfunc`  
 変換されるバイナリ関数。  
  
 `_Left`  
 *\*\_pfunc が* 要求するオブジェクト。  
  
## 戻り値  
 このテンプレート クラスは **\_pfunc**のコピーを保存します。  これは、返されるとメンバー関数 `operator()` を定義します**\_pfunc** \(\*\) \(\_Left\)。  
  
## 解説  
 単項関数オブジェクトでは、パラメーターとして単項関数を要求する、調整できません。標準テンプレート ライブラリのアルゴリズムに渡されます。  値を変数にバインドするか、拒否要素で使用するなど、アダプターを操作するための、このような調整を有効にするには、入れ子にされた型 **argument\_type** と **result\_type** で指定する必要があります。  `pointer_to_unary_function` による変換は、関数のアダプターがバイナリ関数ポインターを使用できます。  
  
## 使用例  
 `pointer_to_unary_function` のコンストラクターは、あまり直接使用されません。  `pointer_to_unary_function` アダプターの述語を宣言および使用する方法の例については、" [ptr\_fun](../Topic/ptr_fun%20Function.md) ヘルパー関数を参照してください。  
  
## 必要条件  
 **ヘッダー:** \<functional\>  
  
 **名前空間:** std  
  
## 参照  
 [標準テンプレート ライブラリ](../misc/standard-template-library.md)