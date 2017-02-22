---
title: "SafeCast | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
f1_keywords: 
  - "SafeCast"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "SafeCast 関数"
ms.assetid: 55316729-8456-403a-9f96-59d4038f67af
caps.latest.revision: 7
author: "ghogen"
ms.author: "ghogen"
manager: "ghogen"
caps.handback.revision: 7
---
# SafeCast
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

数値の型を別の型にキャストします。  
  
## 構文  
  
```  
template<typename T, typename U>  
inline bool SafeCast (  
   const T From,  
   U& To  
);  
```  
  
#### パラメーター  
 \[入力\] `From`  
 変換する元の数値。  これは T 型である必要があります。  
  
 \[出力\] `To`  
 新しい数値の型の参照。  これは U 型である必要があります。  
  
## 戻り値  
 エラーが発生しなかった場合は `true`。エラーが発生した場合は `false`。  
  
## 解説  
 このメソッドは [SafeInt ライブラリ](../windows/safeint-library.md)に含まれており、[SafeInt クラス](../windows/safeint-class.md)のインスタンスを作成せずに単一のキャスト演算を実行するために用意されています。  
  
> [!NOTE]
>  このメソッドは、単一の演算を保護する必要がある場合にのみ使用してください。  複数の演算を実行する場合は、スタンドアロンの関数を個別に呼び出すのではなく、`SafeInt` クラスを使用する必要があります。  
  
 テンプレートの種類である T と U の詳細については、「[SafeInt 関数](../windows/safeint-functions.md)」を参照してください。  
  
## 必要条件  
 **ヘッダー:** safeint.h  
  
 **名前空間:** Microsoft::Utilities  
  
## 参照  
 [SafeInt 関数](../windows/safeint-functions.md)   
 [SafeInt ライブラリ](../windows/safeint-library.md)   
 [SafeInt クラス](../windows/safeint-class.md)