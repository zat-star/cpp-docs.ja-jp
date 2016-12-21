---
title: "pair (STL/CLR) | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "cliext::pair"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "pair クラス [STL/CLR]"
ms.assetid: 3326b4d9-a52a-49e5-8103-9aa5e8b352de
caps.latest.revision: 5
caps.handback.revision: 5
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# pair (STL/CLR)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

このテンプレート クラスは、値のペアをラップするオブジェクトを表します。  
  
## 構文  
  
```  
template<typename Value1,  
    typename Value2>  
    ref class pair;  
```  
  
#### パラメーター  
 Value1  
 最初にラップされた値の型。  
  
 Value2  
 2 番目のラップされた値の型。  
  
## メンバー  
  
|型定義|説明|  
|---------|--------|  
|[pair::first\_type](../dotnet/pair-first-type-stl-clr.md)|最初のラップされた値の型。|  
|[pair::second\_type](../dotnet/pair-second-type-stl-clr.md)|2 番目のラップされた値の型。|  
  
|メンバー オブジェクト|説明|  
|-----------------|--------|  
|[pair::first](../dotnet/pair-first-stl-clr.md)|最初に格納されている値。|  
|[pair::second](../dotnet/pair-second-stl-clr.md)|2 番目の格納されている値。|  
  
|メンバー関数|説明|  
|------------|--------|  
|[pair::pair](../dotnet/pair-pair-stl-clr.md)|pair オブジェクトを構築します。|  
|[pair::swap](../Topic/pair::swap%20\(STL-CLR\).md)|2 組のかっこの内容を交換します。|  
  
|演算子|説明|  
|---------|--------|  
|[pair::operator\=](../dotnet/pair-operator-assign-stl-clr.md)|値の格納されたペアを置き換えます。|  
  
## 解説  
 オブジェクトが値のペアを格納します。  単一のオブジェクトに値 2 を結合するには、このテンプレート クラスを使用します。  `cliext::pair` \(ここで説明した\) マネージ型だけを格納することに注意してください; アンマネージ型のペアを格納するには、宣言されている `<utility>`で `std::pair`を使用します。  
  
## 必要条件  
 **ヘッダー:** \<cliext\/ユーティリティ\>  
  
 **名前空間:** の cliext  
  
## 参照  
 [make\_pair](../dotnet/make-pair-stl-clr.md)