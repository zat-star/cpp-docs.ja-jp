---
title: "制御の移動 |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-language
ms.tgt_pltfrm: 
ms.topic: language-reference
dev_langs:
- C++
helpviewer_keywords:
- control flow, branching
- control flow, transferring control
ms.assetid: aa51e7f2-060f-4106-b0fe-331f04357423
caps.latest.revision: 7
author: mikeblome
ms.author: mblome
manager: ghogen
ms.translationtype: HT
ms.sourcegitcommit: 6ffef5f51e57cf36d5984bfc43d023abc8bc5c62
ms.openlocfilehash: a604c95bb21ad0098a3d4563738971791fc94a07
ms.contentlocale: ja-jp
ms.lasthandoff: 09/25/2017

---
# <a name="transfers-of-control"></a>制御の移動
使用することができます、`goto`ステートメントまたは**ケース**でラベル付け、`switch`初期化子を越えて分岐するプログラムを指定するステートメント。 初期化子を含む宣言がジャンプ ステートメントの発生元のブロックで囲まれたブロックに存在しない限り、このようなコードは無効です。  
  
 次の例は、オブジェクト `total`、`ch`、`i` を宣言して初期化するループを示します。 初期化子を越えて制御を転送する、不適切な `goto` ステートメントもあります。  
  
```  
// transfers_of_control.cpp  
// compile with: /W1  
// Read input until a nonnumeric character is entered.  
int main()  
{  
   char MyArray[5] = {'2','2','a','c'};  
   int i = 0;  
   while( 1 )  
   {  
      int total = 0;  
  
      char ch = MyArray[i++];  
  
      if ( ch >= '0' && ch <= '9' )  
      {  
         goto Label1;  
  
         int i = ch - '0';  
      Label1:  
         total += i;   // C4700: transfers past initialization of i.  
      } // i would be destroyed here if  goto error were not present  
   else  
      // Break statement transfers control out of loop,  
      //  destroying total and ch.  
      break;  
   }  
}  
```  
  
 前の例では、`goto` ステートメントは、`i` の初期化の後、制御権を委譲しようとします。 ただし、`i` が宣言されていても初期化されていない場合、転送は有効になります。  
  
 オブジェクト`total`と`ch`として機能するブロックで宣言された、*ステートメント*の`while`ステートメントを使用して、そのブロックが終了したときに破棄されますが、`break`ステートメントです。  
  

