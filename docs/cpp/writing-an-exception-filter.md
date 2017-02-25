---
title: "例外フィルターの記述 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "例外処理, フィルター"
ms.assetid: 47fc832b-a707-4422-b60a-aaefe14189e5
caps.latest.revision: 9
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 9
---
# 例外フィルターの記述
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

例外は、例外ハンドラーのレベルにジャンプするか、実行を続けるかのいずれかにより、処理できます。  例外ハンドラー コードを使用して例外を処理した後、フォール スルーするのではなく、フィルターを使用して問題をクリーンアップし、–1 を戻すことにより、スタックを消去しないで標準フローを再開することができます。  
  
> [!NOTE]
>  一部の例外は、続行できない場合があります。  このような例外でフィルターが \-1 に評価されると、新しい例外が発生します。  [RaiseException](http://msdn.microsoft.com/library/windows/desktop/ms680552) を呼び出すときに、例外を続行するかどうかを指定します。  
  
 たとえば、次のコードでは、フィルター式で関数呼び出しを使用します。この関数では、問題を処理し、\-1 を返して通常の制御フローを再開します。  
  
```  
// exceptions_Writing_an_Exception_Filter.cpp  
#include <windows.h>  
int main() {  
   int Eval_Exception( int );  
  
   __try {}  
  
   __except ( Eval_Exception( GetExceptionCode( ))) {  
      ;  
   }  
  
}  
void ResetVars( int ) {}  
int Eval_Exception ( int n_except ) {  
   if ( n_except != STATUS_INTEGER_OVERFLOW &&   
      n_except != STATUS_FLOAT_OVERFLOW )   // Pass on most exceptions  
   return EXCEPTION_CONTINUE_SEARCH;  
  
   // Execute some code to clean up problem  
   ResetVars( 0 );   // initializes data to 0  
   return EXCEPTION_CONTINUE_EXECUTION;  
}  
```  
  
 フィルターで複雑な処理を実行する場合は、フィルター式で関数呼び出しを使用することをお勧めします。  式を評価すると、関数 \(この場合、`Eval_Exception`\) が実行されます。  
  
 [GetExceptionCode](http://msdn.microsoft.com/library/windows/desktop/ms679356) を使用して例外を判断する方法に注意してください。  この関数は、フィルター自体の内部で呼び出す必要があります。  `Eval_Exception` で **GetExceptionCode** を呼び出すことはできませんが、この関数に例外コードを渡す必要があります。  
  
 このハンドラーは、例外が整数または浮動小数点数のオーバーフローでなければ、他のハンドラーに制御を渡します。  オーバーフローがあった場合、ハンドラーは関数 \(`ResetVars` は一例で、API 関数ではありません\) を呼び出して、いくつかのグローバル関数をリセットします。  `Eval_Exception` は EXCEPTION\_EXECUTE\_HANDLER \(1\) を返さないため、この例では空になっているステートメント ブロック 2 が実行されることはありません。  
  
 関数呼び出しの使用は、複雑なフィルター式を処理するための優れた汎用的手法です。  その他の便利な 2 つの C 言語機能を次に示します。  
  
-   条件演算子  
  
-   コンマ演算子  
  
 条件演算子を使用すると、特定のリターン コードをチェックしてから 2 つの異なる値のいずれかを返すことができるため、この演算子は多くの場合に役立ちます。  たとえば、次のコードのフィルターは、例外が `STATUS_INTEGER_OVERFLOW` である場合にのみ例外を認識します。  
  
```  
__except( GetExceptionCode() == STATUS_INTEGER_OVERFLOW ? 1 : 0 ) {  
```  
  
 次のコードでは同じ結果が生成されるため、ここでは条件演算子が主として明確さを高めるために使用されています。  
  
```  
__except( GetExceptionCode() == STATUS_INTEGER_OVERFLOW ) {  
```  
  
 条件演算子は、フィルターが "–1, EXCEPTION\_CONTINUE\_EXECUTION" と評価される必要があるような状況で役立ちます。  
  
 コンマ演算子を使用すると、1 つの式内で複数の個別演算を実行できます。  複数のステートメントを実行してから最後の式の値を返す場合とほぼ同じ効果が得られます。  たとえば、次のコードでは、変数に例外コードを保存してから、そのコードをテストしています。  
  
```  
__except( nCode = GetExceptionCode(), nCode == STATUS_INTEGER_OVERFLOW )  
```  
  
## 参照  
 [例外ハンドラーの記述](../cpp/writing-an-exception-handler.md)   
 [構造化例外処理](../cpp/structured-exception-handling-c-cpp.md)