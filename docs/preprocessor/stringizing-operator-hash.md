---
title: "文字列化演算子 (#) | Microsoft Docs"
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
  - "#"
dev_langs: 
  - "C++"
  - "C"
helpviewer_keywords: 
  - "# プリプロセッサ演算子"
  - "引数 [C++], 変換 (文字列に)"
  - "マクロ [C++], 変換 (パラメーターを文字列に)"
  - "プリプロセッサ"
  - "プリプロセッサ, 演算子"
  - "リテラル文字列, 変換 (マクロのパラメーター):"
  - "文字列化演算子"
ms.assetid: 1175dd19-4538-43b3-ad97-a008ab80e7b1
caps.latest.revision: 16
caps.handback.revision: 14
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# 文字列化演算子 (#)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

シャープ記号つまり "文字列化" 演算子 \(**\#**\) は、パラメーター定義を展開することなく、マクロ パラメーターを文字列リテラルに変換します。  これは、引数を受け取るマクロでのみ使用されます。  マクロ定義の仮パラメーターの前に指定すると、マクロの呼び出し時に渡される実際の引数は一重引用符で囲まれ、文字列リテラルとして扱われます。  文字列リテラルは、マクロ定義内の文字列化演算子と仮パラメーターの組み合わせをすべて置き換えます。  
  
> [!NOTE]
>  Microsoft C \(Version 6.0 以前\) では、ANSI C 規格を拡張して、文字列リテラルと文字定数の内部に現れるマクロ仮引数を展開していましたが、この拡張機能はサポートされなくなりました。  この拡張機能に依存したコードは、文字列化演算子 \(**\#**\) を使用して書き直す必要があります。  
  
 実引数の最初のトークンに先行する空白と、実引数の最後のトークンに後続する空白は無視されます。  実引数のトークンの間にある空白は、結果の文字列リテラルでは 1 個の空白にまとめられます。  したがって、実引数で 2 つのトークンの間にコメントがある場合、コメントは 1 個の空白に置き換えられます。  結果の文字列リテラルは、隣接する任意の文字列リテラルと、空白のみで区切られて自動的に連結されます。  
  
 さらに、引数に含まれる文字が文字列リテラルで使用されるときに通常はエスケープ シーケンスが必要な場合 \(引用符 \(**"**\) やバックスラッシュ \(**\\**\) など\)、必要なエスケープ バックスラッシュが文字の前に自動的に挿入されます。  
  
 Visual C\+\+ の文字列化演算子はすべての状況で期待どおりに動作しない可能性があります。詳細については、「[16.3.2 \# 演算子](../misc/16-3-2-the-hash-operator.md)」を参照してください。  
  
## 使用例  
 次の例は、文字列化演算子を含むマクロ定義と、そのマクロを呼び出すメイン関数を示しています。  
  
 このような呼び出しはプリプロセッサによって展開され、次のコードが生成されます。  
  
```  
int main() {  
   printf_s( "In quotes in the printf function call\n" "\n" );  
   printf_s( "\"In quotes when printed to the screen\"\n" "\n" );  
   printf_s( "\"This: \\\" prints an escaped double quote\"" "\n" );  
}  
```  
  
```  
// stringizer.cpp  
#include <stdio.h>  
#define stringer( x ) printf_s( #x "\n" )  
int main() {  
   stringer( In quotes in the printf function call );   
   stringer( "In quotes when printed to the screen" );     
   stringer( "This: \"  prints an escaped double quote" );  
}  
```  
  
  **In quotes in the printf function call**  
**"In quotes when printed to the screen"**  
**"This: \\" prints an escaped double quote"**   
## 使用例  
 次の例は、マクロ パラメーターを展開する方法を示しています。  
  
```  
// stringizer_2.cpp  
// compile with: /E  
#define F abc  
#define B def  
#define FB(arg) #arg  
#define FB1(arg) FB(arg)  
FB(F B)  
FB1(F B)  
```  
  
## 参照  
 [プリプロセッサ演算子](../preprocessor/preprocessor-operators.md)