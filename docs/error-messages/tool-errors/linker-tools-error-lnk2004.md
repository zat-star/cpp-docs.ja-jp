---
title: "リンカ ツール エラー LNK2004 |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- LNK2004
dev_langs:
- C++
helpviewer_keywords:
- LNK2004
ms.assetid: 07645371-e67b-4a2c-b0e0-dde24c94ef7e
caps.latest.revision: 7
author: corob-msft
ms.author: corob
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
translationtype: Machine Translation
ms.sourcegitcommit: 3168772cbb7e8127523bc2fc2da5cc9b4f59beb8
ms.openlocfilehash: f66c3eda90f3d0f9149d70418cb40f08b3b94df7
ms.lasthandoff: 02/24/2017

---
# <a name="linker-tools-error-lnk2004"></a>リンカ ツール エラー LNK2004
gp 相対フィックスを '対象';短いセクション 'section' が長すぎるか範囲外です。  
  
 セクションが大きすぎます。  
  
 このエラーを解決するには、#pragma セクション (".sectionname"を読み取り、書き込み、時間の長い) 経由で長いセクションでデータを明示的に設定しを使用していずれかの短いセクションのサイズを小さく`__declspec(allocate(".sectionname"))`にデータ定義と宣言します。  次に例を示します。  
  
```  
#pragma section(".data$mylong", read, write, long)  
__declspec(allocate(".data$mylong"))  
char    rg0[1] = { 1 };  
char    rg1[2] = { 1 };  
char    rg2[4] = { 1 };  
char    rg3[8] = { 1 };  
char    rg4[16] = { 1 };  
char    rg5[32] = { 1 };  
```  
  
 8 バイトは、コンパイラは長い形式のデータ セクションに割り当てるよりも大きいデータのコレクションであるが、独自の構造体に論理的にグループ化されたデータを移動することもできます。  次に例を示します。  
  
```  
// from this...  
int     w1  = 23;  
int     w2 = 46;  
int     w3 = 23*3;  
int     w4 = 23*4;  
  
// to this...  
struct X {  
    int     w1;  
    int     w2;  
    int     w3;  
    int     w4;  
} x  = { 23, 23*2, 23*3, 23*4 };  
  
```  
  
 このエラーは致命的なエラーの後に`LNK1165`します。
