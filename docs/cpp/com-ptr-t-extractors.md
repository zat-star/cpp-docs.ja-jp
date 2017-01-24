---
title: "_com_ptr_t 抽出 | Microsoft Docs"
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
  - "_com_ptr_t::operatorInterface&"
  - "operatorInterface*"
  - "operatorInterface&"
  - "_com_ptr_t::operatorbool"
  - "_com_ptr_t.operator->"
  - "_com_ptr_t.operator*"
  - "_com_ptr_t::operator->"
  - "_com_ptr_t::operator*"
  - "_com_ptr_t.operatorInterface&"
  - "_com_ptr_t.operatorbool"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "& 演算子, 固有のオブジェクトを使用する"
  - "* 演算子, 固有のオブジェクトを使用する"
  - "-> 演算子, 固有のオブジェクトを使用する"
  - "抽出"
  - "抽出, _com_ptr_t クラス"
  - "* 演算子"
  - "演算子 bool"
  - "演算子インターフェイス &"
  - "演算子インターフェイス *"
  - "演算子 &"
  - "演算子 *"
  - "演算子 ->"
ms.assetid: 194b9e0e-123c-49ff-a187-0a7fcd68145a
caps.latest.revision: 6
caps.handback.revision: 6
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# _com_ptr_t 抽出
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

**Microsoft 固有の仕様 →**  
  
 カプセル化された COM インターフェイス ポインターを抽出します。  
  
## 構文  
  
```  
  
      operator Interface*( ) const throw( );   
operator Interface&( ) const;   
Interface& operator*( ) const;   
Interface* operator->( ) const;   
Interface** operator&( ) throw( );   
operator bool( ) const throw( );  
```  
  
## 解説  
  
-   **operator Interface\* NULL** である可能性があるカプセル化されたインターフェイス ポインターを返します。  
  
-   **operator Interface&** カプセル化されたインターフェイス ポインターへの参照を返し、ポインターが **NULL** の場合はエラーを返します。  
  
-   **operator\*** 逆参照されたときに、実際にカプセル化されたインターフェイスのようにスマート ポインター オブジェクトが機能できるようにします。  
  
-   **operator\-\>** 逆参照されたときに、実際にカプセル化されたインターフェイスのようにスマート ポインター オブジェクトが機能できるようにします。  
  
-   **operator&** カプセル化されたインターフェイス ポインターを解放して **NULL** で置き換え、カプセル化されたポインターのアドレスを返します。  これにより、インターフェイス ポインターを返す **out** パラメーターを持つ関数に、アドレスを使用してスマート ポインターを渡すことができます。  
  
-   **operator bool** スマート ポインター オブジェクトを条件式で使用できるようにします。  この演算子は、ポインターが **NULL** でない場合、**true** を返します。  
  
 **END Microsoft 固有の仕様**  
  
## 参照  
 [\_com\_ptr\_t クラス](../cpp/com-ptr-t-class.md)