---
title: "_com_ptr_t 抽出 |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-language
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords:
- _com_ptr_t::operatorInterface&
- _com_ptr_t::operatorbool
- _com_ptr_t::operator->
- _com_ptr_t::operator*
dev_langs: C++
helpviewer_keywords:
- operator Interface& [C++]
- '* operator [C++], with specific objects'
- operator& [C++]
- operator* [C++]
- -> operator [C++], with specific objects
- '& operator [C++], with specific objects'
- operator Interface* [C++]
- operator * [C++]
- operator->
- operator bool
- extractors, _com_ptr_t class
- extractors [C++]
ms.assetid: 194b9e0e-123c-49ff-a187-0a7fcd68145a
caps.latest.revision: "6"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: 73e2dca693939765e700d51b6caab0815c6d5e7e
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/24/2017
---
# <a name="comptrt-extractors"></a>_com_ptr_t 抽出
**Microsoft 固有の仕様**  
  
 カプセル化された COM インターフェイス ポインターを抽出します。  
  
## <a name="syntax"></a>構文  
  
```  
  
      operator Interface*( ) const throw( );   
operator Interface&( ) const;   
Interface& operator*( ) const;   
Interface* operator->( ) const;   
Interface** operator&( ) throw( );   
operator bool( ) const throw( );  
```  
  
## <a name="remarks"></a>コメント  
  
-   **演算子インターフェイス\***可能性のあるカプセル化されたインターフェイス ポインターを返します。 **NULL**です。  
  
-   **演算子インターフェイス &**カプセル化されたインターフェイス ポインターへの参照を返し、ポインターがある場合はエラー **NULL**です。  
  
-   **演算子\***逆参照時に、実際のカプセル化されたインターフェイスのように動作するスマート ポインター オブジェクトを使用します。  
  
-   **-> 演算子**逆参照時に、実際のカプセル化されたインターフェイスのように動作するスマート ポインター オブジェクトを使用します。  
  
-   **演算子 &**置き換えることで、任意のカプセル化されたインターフェイス ポインターを解放**NULL**、カプセル化されたポインターのアドレスを返します。 これにより、アドレスを持つ関数に渡されるスマート ポインター、**アウト**パラメーターを使用するインターフェイス ポインターを返します。  
  
-   **operator bool**条件式で使用するスマート ポインター オブジェクトを使用します。 この演算子を返します**true**ポインターがない場合**NULL**です。  
  
 **Microsoft 固有の仕様はここまで**  
  
## <a name="see-also"></a>関連項目  
 [_com_ptr_t クラス](../cpp/com-ptr-t-class.md)