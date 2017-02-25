---
title: "SafeGreaterThanEquals | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
f1_keywords: 
  - "SafeGreaterThanEquals"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "SafeGreaterThanEquals 関数"
ms.assetid: 43312fa9-d925-4f9f-a352-a190c02b3005
caps.latest.revision: 6
author: "ghogen"
ms.author: "ghogen"
manager: "ghogen"
caps.handback.revision: 6
---
# SafeGreaterThanEquals
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

2 つの数値を比較します。  
  
## 構文  
  
```  
template <typename T, typename U>  
inline bool SafeGreaterThanEquals (  
   const T t,  
   const U u  
) throw ();  
```  
  
#### パラメーター  
 \[入力\] `t`  
 比較対象の最初の数値。  これは T 型である必要があります。  
  
 \[入力\] `u`  
 比較対象の 2 番目の数値。  これは U 型である必要があります。  
  
## 戻り値  
 `t` が `u` 以上である場合は `true`。それ以外の場合は `false`。  
  
## 解説  
 `SafeGreaterThanEquals` を使用すると、型が異なる 2 つの数値を比較できるため、このメソッドは標準の比較演算子を拡張したものであると言えます。  
  
 このメソッドは [SafeInt ライブラリ](../windows/safeint-library.md)に含まれており、[SafeInt クラス](../windows/safeint-class.md)のインスタンスを作成せずに単一の比較演算を実行するために用意されています。  
  
> [!NOTE]
>  このメソッドは、単一の数値演算を保護する必要がある場合にのみ使用してください。  複数の演算を実行する場合は、スタンドアロンの関数を個別に呼び出すのではなく、`SafeInt` クラスを使用する必要があります。  
  
 テンプレートの種類である T と U の詳細については、「[SafeInt 関数](../windows/safeint-functions.md)」を参照してください。  
  
## 必要条件  
 **ヘッダー:** safeint.h  
  
 **名前空間:** Microsoft::Utilities  
  
## 参照  
 [SafeInt 関数](../windows/safeint-functions.md)   
 [SafeInt ライブラリ](../windows/safeint-library.md)   
 [SafeInt クラス](../windows/safeint-class.md)   
 [SafeGreaterThan](../windows/safegreaterthan.md)   
 [SafeLessThanEquals](../windows/safelessthanequals.md)   
 [SafeLessThan](../windows/safelessthan.md)