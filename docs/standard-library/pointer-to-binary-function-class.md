---
title: "pointer_to_binary_function クラス | Microsoft Docs"
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
  - "std::pointer_to_binary_function"
  - "xfunctional/std::pointer_to_binary_function"
  - "pointer_to_binary_function"
  - "std.pointer_to_binary_function"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "pointer_to_binary_function クラス"
  - "pointer_to_binary_function 関数"
ms.assetid: fb50599f-bcb3-4076-a669-6dcc3eb189a5
caps.latest.revision: 21
caps.handback.revision: 11
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# pointer_to_binary_function クラス
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

二項関数ポインターを適応性のある二項関数に変換します。  
  
## 構文  
  
```  
template<class Arg1, class Arg2, class Result>  
   class pointer_to_binary_function   
   : public binary_function <Arg1, Arg2, Result>   
   {  
   public:  
   explicit pointer_to_binary_function(  
      Result (*_pfunc )( Arg1, Arg2 )   
   );  
   Result operator()(  
      Arg1 _Left,   
      Arg2 _Right  
   ) const;  
   };  
```  
  
#### パラメーター  
 `_pfunc`  
 変換されるバイナリ関数。  
  
 `_Left`  
 *\*\_pfunc が* 要求する左オブジェクト。  
  
 `_Right`  
 *\*\_pfunc が* 要求する右オブジェクト。  
  
## 戻り値  
 このテンプレート クラスは **\_pfunc**のコピーを保存します。  これは \(\*\) **\_pfunc** \(\_Left、\_Right とメンバー関数 `operator()` を返す定義します\)。  
  
## 解説  
 バイナリ オブジェクト関数では、パラメーターとしてバイナリ関数を要求する、調整できません。標準テンプレート ライブラリのアルゴリズムに渡されます。  値を変数にバインドするか、拒否要素で使用するなど、アダプターを操作するための、このような調整を有効にするには、入れ子にされた型 **first\_argument\_type**、**second\_argument\_type**と **result\_type** で指定する必要があります。  `pointer_to_binary_function` による変換は、関数のアダプターがバイナリ関数ポインターを使用できます。  
  
## 使用例  
 `pointer_to_binary_function` のコンストラクターは、あまり直接使用されません。  `pointer_to_binary_function` アダプターの述語を宣言および使用する方法の例については、" [ptr\_fun](../Topic/ptr_fun%20Function.md) ヘルパー関数を参照してください。  
  
## 必要条件  
 **ヘッダー:** \<functional\>  
  
 **名前空間:** std  
  
## 参照  
 [標準テンプレート ライブラリ](../misc/standard-template-library.md)