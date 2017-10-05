---
title: "_com_ptr_t 抽出 |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-language
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords:
- _com_ptr_t::operatorInterface&
- operatorInterface*
- operatorInterface&
- _com_ptr_t::operatorbool
- _com_ptr_t.operator->
- _com_ptr_t.operator*
- _com_ptr_t::operator->
- _com_ptr_t::operator*
- _com_ptr_t.operatorInterface&
- _com_ptr_t.operatorbool
dev_langs:
- C++
helpviewer_keywords:
- operator Interface&
- '* operator, with specific objects'
- operator&
- operator*
- -> operator, with specific objects
- '& operator, with specific objects'
- operator Interface*
- operator *
- operator->
- operator bool
- extractors, _com_ptr_t class
- extractors
ms.assetid: 194b9e0e-123c-49ff-a187-0a7fcd68145a
caps.latest.revision: 6
author: mikeblome
ms.author: mblome
manager: ghogen
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
ms.translationtype: HT
ms.sourcegitcommit: 6ffef5f51e57cf36d5984bfc43d023abc8bc5c62
ms.openlocfilehash: 136afa55361ff25f9ad606886be938a00551393d
ms.contentlocale: ja-jp
ms.lasthandoff: 09/25/2017

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
