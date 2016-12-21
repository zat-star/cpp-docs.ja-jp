---
title: "try-finally ステートメント | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
f1_keywords: 
  - "__try"
  - "__leave_cpp"
  - "__leave"
  - "__finally_cpp"
  - "__try_cpp"
  - "__finally"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "__finally キーワード [C++]"
  - "__finally キーワード [C++], try-finally ステートメント構文"
  - "__leave キーワード [C++]"
  - "__leave キーワード [C++], try-finally ステートメント"
  - "__try キーワード [C++]"
  - "構造化例外処理, try-finally"
  - "try-catch キーワード [C++], try-finally キーワード"
  - "try-finally キーワード [C++]"
ms.assetid: 826e0347-ddfe-4f6e-a7bc-0398e0edc7c2
caps.latest.revision: 14
caps.handback.revision: 14
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# try-finally ステートメント
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

**Microsoft 固有の仕様 →**  
  
 次の構文は、`try-finally` ステートメントを示しています。  
  
```  
__try {  
   // guarded code  
}  
__finally {  
   // termination code  
}  
```  
  
## 文法  
 *try\-finally\-statement*:  
 `__try` *compound\-statement*  
  
 `__finally` *compound\-statement*  
  
 `try-finally` ステートメントは C および C\+\+ 言語に対する Microsoft の拡張機能であり、コードのブロックの実行が中断されたときに、ターゲット アプリケーションがクリーンアップ コードの実行を保証できるようにします。  クリーンアップは、メモリを解放する、ファイルを閉じる、ファイル ハンドルを解放するなどのタスクで構成されます。  `try-finally` ステートメントは、ルーチンからの不完全な戻りが発生する可能性のあるエラーを複数の場所でチェックするルーチンに特に便利です。  
  
 関連情報とコード例については、「[try\-except ステートメント](../cpp/try-except-statement.md)」を参照してください。  一般的な構造化例外処理の詳細については、「[構造化例外処理](../cpp/structured-exception-handling-c-cpp.md)」を参照してください。  マネージ アプリケーションでの例外処理の詳細については、「[\/clr での例外処理](../windows/exception-handling-cpp-component-extensions.md)」を参照してください。  
  
> [!NOTE]
>  構造化例外処理では、C と C\+\+ のソース ファイルの両方で Win32 を使用します。  ただし、特に C\+\+ 用にデザインされたものではありません。  C\+\+ 例外処理を使用して、コードの移植性を高めることができます。  また、C\+\+ 例外処理は、任意の型の例外を処理できるという点で、より柔軟です。  C\+\+ プログラムでは、C\+\+ 例外処理機構 \([try、catch、および throw ステートメント](../cpp/try-throw-and-catch-statements-cpp.md)\) を使用することをお勧めします。  
  
 `__try` 句の後の複合ステートメントは、保護されたセクションです。  `__finally` 句の後の複合ステートメントは、終了ハンドラーです。  ハンドラーは、保護されたセクションが例外によって終了 \(異常終了\) したか、標準的なフォール スルー \(正常終了\) で終了したかにかかわらず、保護されたセクションが終了したときに実行する一連の操作を指定します。  
  
 制御は、単純な順次実行 \(フォール スルー\) によって `__try` ステートメントに到達します。  制御が `__try` に入ると、その関連するハンドラーがアクティブになります。  制御のフローが try ブロックの終わりに到達すると、次のように実行は処理されます。  
  
1.  終了ハンドラーが呼び出されます。  
  
2.  終了ハンドラーが完了すると、`__finally` ステートメントの後から実行が続けられます。  保護されたセクションがどのように終了したかに関係なく \(たとえば、保護された本体外の `goto` または `return` ステートメント経由\)、終端ハンドラーは、制御フローが保護されたセクションの外部に移動する前に実行されます。  
  
     **\_\_finally** ステートメントは適切な例外ハンドラーの検索をブロックしません。  
  
 例外が `__try` ブロックで発生すると、オペレーティング システムは例外のハンドラーを見つける必要があります。見つからない場合プログラムは失敗します。  ハンドラーが見つかった場合、任意およびすべての `__finally` ブロックが実行され、ハンドラーで実行が再開されます。  
  
 たとえば、次の図に示すように、一連の関数呼び出しで、関数 A を関数 D にリンクするとします。  各関数には、1 つの終了ハンドラーがあります。  関数 D で例外が発生し、A で処理されると、スタックがアンワインドされるときに、終了ハンドラーは D、C、B の順に呼び出されます。  
  
 ![終了ハンドラーの実行の順序](../cpp/media/vc38cx1.png "vc38CX1")  
終了順序 \- ハンドラーの実行  
  
> [!NOTE]
>  try\-finally の動作は、**finally** の使用をサポートする C\# のような言語とは異なります。  1 つの `__try` には、`__finally` と `__except` のいずれか、または両方がある場合があります。  両方を一緒に使用する場合は、外側の try\-except ステートメントで内側の try\-finally ステートメントを囲む必要があります。  各ブロックがいつ実行されるかを指定する規則も異なります。  
  
## \_\_leave キーワード  
 `__leave` キーワードは、`try-finally` ステートメントの保護されたセクション内でのみ有効であり、その効果は保護されたセクションの末尾に移動することです。  実行は、終了ハンドラーの最初のステートメントに移って続行されます。  
  
 `goto` ステートメントは、保護されたセクションの外部にジャンプすることもできますが、スタック アンワインドを呼び出すため、パフォーマンスが低下します。  `__leave` ステートメントは、スタック アンワインドが発生しないため、より効率的です。  
  
## 異常終了  
 `try-finally` ステートメントを [longjmp](../c-runtime-library/reference/longjmp.md) ランタイム関数を使用して終了すると、異常終了と見なされます。  `__try` ステートメントにジャンプして入ることはできませんが、このステートメントからジャンプして出ることはできます。  出発点 \(`__try` ブロックの通常の終端\) と処理先 \(例外を処理する `__except` ブロック\) の間でアクティブなすべての `__finally` ステートメントを実行する必要があります。  これは、ローカル アンワインドと呼ばれます。  
  
 **try** ブロックが、ブロックからのジャンプを含む任意の理由で完了前に終了した場合、スタックをアンワインドするプロセスで関連する **finally** ブロックが実行されます。  このような場合、[AbnormalTermination](http://msdn.microsoft.com/library/windows/desktop/ms679265) 関数の戻り値は、**finally** ブロック内で呼び出されると、TRUE になり、それ以外の場合は FALSE になります。  
  
 終了ハンドラーは、プロセスが `try-finally` ステートメントの実行中に中止された場合は呼び出されません。  
  
 **END Microsoft 固有の仕様**  
  
## 参照  
 [終了ハンドラーの記述](../cpp/writing-a-termination-handler.md)   
 [構造化例外処理](../cpp/structured-exception-handling-c-cpp.md)   
 [C\+\+ キーワード](../cpp/keywords-cpp.md)   
 [Termination\-Handler Syntax](http://msdn.microsoft.com/library/windows/desktop/ms681393)