---
title: "conditional クラス | Microsoft Docs"
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
  - "std::tr1::conditional"
  - "std.tr1.conditional"
  - "conditional"
  - "std.conditional"
  - "std::conditional"
  - "type_traits/std::conditional"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "conditional クラス [TR1]"
  - "conditional"
ms.assetid: ece9f539-fb28-4e26-a79f-3264bc984493
caps.latest.revision: 22
caps.handback.revision: 12
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# conditional クラス
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

指定された条件に基づいて、2 つの型のいずれかを選択します。  
  
## 構文  
  
```  
template <bool B, class T1, class T2>  
    struct conditional;  
  
template <bool _Test, class _T1, class _T2>  
    using conditional_t = typename conditional<_Test, _T1, _T2>::type;  
```  
  
#### パラメーター  
 `B`  
 選択される型を決定する値。  
  
 `T1`  
 B が true の場合の型の結果。  
  
 `T2`  
 B が false の場合の型の結果。  
  
## 解説  
 テンプレート メンバー typedef `conditional<B, T1, T2>::type` は、`T1` が `B` に評価されるときは `true` として、`T2` が `B` に評価されるときは `false` として評価されます。  
  
## 必要条件  
 **ヘッダー:** \<type\_traits\>  
  
 **名前空間:** std  
  
## 参照  
 [\<type\_traits\>](../standard-library/type-traits.md)