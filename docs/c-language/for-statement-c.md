---
title: "for ステートメント (C) | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
  - "C"
helpviewer_keywords: 
  - "for キーワード [C]"
ms.assetid: 560a8de4-19db-4868-9f18-dbe51b17900d
caps.latest.revision: 9
caps.handback.revision: 9
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# for ステートメント (C)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

`for` ステートメントを使用すると、指定したステートメントまたは複合ステートメントを、指定した回数だけ繰り返すことができます。  `for` ステートメントの本体は、省略可能な条件が false になるまで、ゼロ回以上実行されます。  `for` ステートメント内で省略可能な式を使用して、値を初期化し、`for` ステートメントの実行中に値を変更することができます。  
  
## 構文  
 *iteration\-statement*:  
 `for` \( `init-expression` opt ; `cond-expression`opt ; `loop-expression` opt \)`statement`  
  
 `for` ステートメントの実行は、次のように進行します。  
  
1.  `init-expression` が指定されている場合は、それが評価されます。  この式は、ループの初期化を指定します。  `init-expression` の型に制限はありません。  
  
2.  `cond-expression` が指定されている場合は、それが評価されます。  この式は、演算型またはポインター型である必要があります。  この式は、各イテレーションの前に評価されます。  次の 3 つの結果が発生する可能性があります。  
  
    -   `cond-expression` が true \(0 以外\) の場合、`statement` が実行されます。その後、`loop-expression` が指定されていれば、それが評価されます。  各イテレーションの完了後に、`loop-expression` が評価されます。  この式の型に制限はありません。  副作用が順に実行されます。  その後、`cond-expression` の評価から再び処理が開始されます。  
  
    -   `cond-expression` を省略すると、`cond-expression` を true と見なして前述の説明どおりに処理が進行します。  `cond-expression` 引数のない `for` ステートメントが終了するのは、ステートメント本体内の `break` ステートメントまたは `return` ステートメントが実行されたときか、\(`for` ステートメント本体外にあるラベル付きステートメントへの\) `goto` が実行された場合だけです。  
  
    -   `cond-expression` が `false` \(0\) の場合、`for` ステートメントの実行が終了し、プログラムの次のステートメントに制御が渡されます。  
  
 また、ステートメント本体内で `break`、`goto`、または `return` ステートメントが実行された場合も、`for` ステートメントは終了します。  `for` ループ内で `continue` ステートメントが実行されると、`loop-expression` が評価されます。  `for` ループ内で `break` ステートメントが実行されると、`loop-expression` は評価されず、実行もされません。  次のステートメント、  
  
```  
for( ;; )  
```  
  
 は、`break`、`goto`、または `return` のいずれかのステートメントによってしか終了できない無限ループを発生させる、よく使用される方法です。  
  
## コード  
 `for` ステートメントの例を次に示します。  
  
```  
// c_for.c  
int main()  
{  
   char* line = "H e  \tl\tlo World\0";  
   int space = 0;  
   int tab = 0;  
   int i;  
   int max = strlen(line);  
   for (i = 0; i < max; i++ )   
   {  
      if ( line[i] == ' ' )  
      {  
          space++;  
      }  
      if ( line[i] == '\t' )  
      {  
          tab++;  
      }  
   }  
  
   printf("Number of spaces: %i\n", space);  
   printf("Number of tabs: %i\n", tab);  
   return 0;  
}  
```  
  
## 出力  
  
```  
Number of spaces: 4  
Number of tabs: 2  
```  
  
## 参照  
 [ステートメント](../c-language/statements-c.md)