---
title: "SafeSubtract | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
f1_keywords: 
  - "SafeSubtract"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "SafeSubtract 関数"
ms.assetid: c2712ddc-173f-46a1-b09c-e7ebbd9e68b2
caps.latest.revision: 5
author: "ghogen"
ms.author: "ghogen"
manager: "ghogen"
caps.handback.revision: 5
---
# SafeSubtract
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

オーバーフローが生じないように 2 つの数値を減算します。  
  
## 構文  
  
```  
template<typename T, typename U>  
inline bool SafeSubtract (  
   T t,  
   U u,  
   T& result  
) throw ();  
```  
  
#### パラメーター  
 \[入力\] `t`  
 減算の最初の数値。  これは T 型である必要があります。  
  
 \[入力\] `u`  
 `t` から減算する数値。  これは U 型である必要があります。  
  
 \[出力\] `result`  
 `SafeSubtract` が結果を格納するパラメーター。  
  
## 戻り値  
 エラーが発生しなかった場合は `true`。エラーが発生した場合は `false`。  
  
## 解説  
 このメソッドは [SafeInt ライブラリ](../windows/safeint-library.md)に含まれており、[SafeInt クラス](../windows/safeint-class.md)のインスタンスを作成せずに単一の減算演算を実行するために用意されています。  
  
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
 [SafeAdd](../windows/safeadd.md)