---
title: "制御の移動 | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "制御フロー, 分岐"
  - "制御フロー, 転送 (制御を)"
ms.assetid: aa51e7f2-060f-4106-b0fe-331f04357423
caps.latest.revision: 7
caps.handback.revision: 7
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# 制御の移動
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

`goto` ステートメント、または  **ステートメント内の `switch`case** ラベルを使用して、初期化子を越えて分岐するプログラムを指定できます。  初期化子を含む宣言がジャンプ ステートメントの発生元のブロックで囲まれたブロックに存在しない限り、このようなコードは無効です。  
  
 次の例は、オブジェクト `total`、`ch`、`i` を宣言して初期化するループを示します。  初期化子を越えて制御を転送する、不適切な `goto` ステートメントもあります。  
  
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
  
 前の例では、`goto` ステートメントは、`i` の初期化の後、制御権を委譲しようとします。  ただし、`i` が宣言されていても初期化されていない場合、転送は有効になります。  
  
 `total` ステートメントのステートメントとして動作するブロックで宣言されたオブジェクト `ch` と  *は、ブロックが `while` ステートメントを使用して終了すると破棄されます`break`*。  
  
## 参照  
 [\(NOTINBUILD\) Declaration of Automatic Objects](http://msdn.microsoft.com/ja-jp/81f941e9-c1b1-4d1c-a28d-70b6ee9765db)