---
title: "_bstr_t 関係演算子 | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
f1_keywords: 
  - "_bstr_t::operator>"
  - "_bstr_t::operator=="
  - "_bstr_t::operator>="
  - "_bstr_t::operator!="
  - "_bstr_t::operator<"
  - "_bstr_t::operator<="
  - "_bstr_t::operator!"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "!= 演算子"
  - "< 演算子, 比較 (固有のオブジェクトを)"
  - "<= 演算子, 固有のオブジェクトを使用する"
  - "== 演算子, Visual C++ 固有のオブジェクトを使用する"
  - "> 演算子, 比較 (固有のオブジェクトを)"
  - ">= 演算子, 比較 (固有のオブジェクトを)"
  - "!= 演算子, 関係演算子"
  - "< 演算子, bstr"
  - "<= 演算子, bstr"
  - "== 演算子, bstr"
  - "> 演算子, bstr"
  - ">= 演算子, bstr"
  - "operator!=, 関係演算子"
  - "operator<, bstr"
  - "operator<=, bstr"
  - "operator==, bstr"
  - "operator>=, bstr"
  - "関係演算子, _bstr_t クラス"
ms.assetid: e153da72-37c3-4d8a-b8eb-730d65da64dd
caps.latest.revision: 6
caps.handback.revision: 6
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# _bstr_t 関係演算子
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

**Microsoft 固有の仕様 →**  
  
 2 つの `_bstr_t` オブジェクトを比較します。  
  
## 構文  
  
```  
  
      bool operator!( ) const throw( );   
bool operator==(  
   const _bstr_t& str   
) const throw( );  
bool operator!=(  
   const _bstr_t& str   
) const throw( );  
bool operator<(  
   const _bstr_t& str   
) const throw( );  
bool operator>(  
   const _bstr_t& str   
) const throw( );  
bool operator<=(  
   const _bstr_t& str   
) const throw( );  
bool operator>=(  
   const _bstr_t& str   
) const throw( );  
```  
  
## 解説  
 これらの演算子は 2 つの `_bstr_t` オブジェクトを辞書式に比較します。  演算子は、比較が保持される場合は **true** を返し、それ以外の場合は **false** を返します。  
  
 **END Microsoft 固有の仕様**  
  
## 参照  
 [\_bstr\_t クラス](../cpp/bstr-t-class.md)