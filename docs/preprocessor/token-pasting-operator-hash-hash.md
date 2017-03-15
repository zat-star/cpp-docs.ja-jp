---
title: "トークン連結演算子 (##) | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "##"
dev_langs: 
  - "C++"
  - "C"
helpviewer_keywords: 
  - "## プリプロセッサ演算子"
  - "プリプロセッサ, 演算子"
ms.assetid: 4f173503-990f-4bff-aef3-ec4d1f1458ef
caps.latest.revision: 10
caps.handback.revision: 8
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# トークン連結演算子 (##)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

二重シャープ記号またはトークン連結演算子 \(**\#\#**\) は、"マージ" 演算子と呼ばれることもあり、オブジェクトのようなマクロと関数のようなマクロの両方で使用されます。  この演算子を使用すると、別々のトークンを 1 つのトークンに結合できます。そのため、これをマクロ定義の最初または最後のトークンにすることはできません。  
  
 マクロ定義の仮パラメーターの前または後ろにトークン連結演算子がある場合、仮パラメーターは展開されていない実引数に即座に置き換えられます。  引数に対するマクロ展開が置換の前に行われることはありません。  
  
 次に、*token\-string* に出現する各トークン連結演算子が削除され、その前後のトークンが連結されます。  結果のトークンは有効なトークンである必要があります。  有効であれば、トークンがスキャンされ、マクロ名を表す場合は置換が可能かどうかが確認されます。  この識別子は、置換前のプログラム内で連結されたトークンを認識するための名前になります。  各トークンは、他のどこか、つまり、プログラム内またはコンパイラのコマンド ラインで定義された特定のトークンを表します。  演算子の前または後の空白は、省略可能です。  
  
 この例は、プログラムの出力を指定するときの、文字列化演算子とトークン連結演算子の両方の使用方法を示しています。  
  
```  
#define paster( n ) printf_s( "token" #n " = %d", token##n )  
int token9 = 9;  
```  
  
 マクロが次のような数値引数で呼び出された場合、  
  
```  
paster( 9 );  
```  
  
 このマクロは次のようになり、  
  
```  
printf_s( "token" "9" " = %d", token9 );  
```  
  
 さらに、次のようになります。  
  
```  
printf_s( "token9 = %d", token9 );  
```  
  
## 使用例  
  
```  
// preprocessor_token_pasting.cpp  
#include <stdio.h>  
#define paster( n ) printf_s( "token" #n " = %d", token##n )  
int token9 = 9;  
  
int main()  
{  
   paster(9);  
}  
```  
  
  **token9 \= 9**   
## 参照  
 [プリプロセッサ演算子](../preprocessor/preprocessor-operators.md)