---
title: "C++ のグローバル定数 | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "定数, global"
  - "グローバル定数"
ms.assetid: df5a9bd4-d0a8-4c1c-956e-b481d0bded7d
caps.latest.revision: 9
caps.handback.revision: 9
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# C++ のグローバル定数
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

C\+\+ のグローバル定数は静的なリンケージを持ちます。  これは C とは異なります。  複数のファイルで C\+\+ のグローバル定数を使用すると、未解決の外部参照エラーになります。  コンパイラはグローバル定数を最適化して取り除き、変数のための領域は予約しません。  
  
 このエラーを解決するには、定数の初期化をヘッダー ファイルに入れて、関数のプロトタイプと同じように、CPP ファイルでこのヘッダーを必要に応じて取り込みます。  別の方法として、変数を非定数とし、アクセスするときには、定数参照します。  
  
 次の例では警告 C2019 が生成されます。  
  
```  
// global_constants.cpp  
// LNK2019 expected  
void test(void);  
const int lnktest1 = 0;  
  
int main() {  
   test();  
}  
```  
  
 次に、以下のコードを実行します。  
  
```  
// global_constants_2.cpp  
// compile with: global_constants.cpp  
extern int lnktest1;  
  
void test() {  
  int i = lnktest1;   // LNK2019  
}  
```  
  
## 参照  
 [リンカ ツール エラー LNK2019](../Topic/Linker%20Tools%20Error%20LNK2019.md)