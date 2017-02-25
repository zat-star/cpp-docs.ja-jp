---
title: "longjmp | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
apiname: 
  - "longjmp"
apilocation: 
  - "msvcrt.dll"
  - "msvcr80.dll"
  - "msvcr90.dll"
  - "msvcr100.dll"
  - "msvcr100_clr0400.dll"
  - "msvcr110.dll"
  - "msvcr110_clr0400.dll"
  - "msvcr120.dll"
  - "msvcr120_clr0400.dll"
  - "ucrtbase.dll"
apitype: "DLLExport"
f1_keywords: 
  - "longjmp"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "longjmp 関数"
  - "復元 (スタック環境と実行ロケールを)"
ms.assetid: 0e13670a-5130-45c1-ad69-6862505b7a2f
caps.latest.revision: 9
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 9
---
# longjmp
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

復元スタック実行環境とロケール。  
  
## 構文  
  
```  
  
      void longjmp(  
   jmp_buf env,  
   int value   
);  
```  
  
#### パラメーター  
 `env`  
 環境を格納する変数。  
  
 *value*  
 `setjmp` の呼び出しに返す値を指定します。  
  
## 解説  
 `longjmp` 関数は、以前に `env` に格納されたスタック実行環境とロケールを `setjmp`で復元します。  `setjmp` と `longjmp` は非ローカルな `goto`を実行します; これらは、通常通話を処理して規則を使用せずに呼び出しルーチンのエラー処理や復元コードに実行制御を渡すために使用されます。  
  
 `setjmp` への呼び出しは、現在のスタック `env`に環境を格納します。  `longjmp` への後続の呼び出しで、`setjmp` の対応する呼び出しに続くポイントに格納された環境を処理してコントロールを復元します。  実行は、*値が*`setjmp` の呼び出しによって、返されるように再開されます。  すべての変数の値 \(レジスタ変数を除き、定期的な受信のコントロールにアクセスできる `longjmp` がいつが呼び出されたときの値が含まれます。  レジスタ変数の値は予測不可能です。  `setjmp` によって返される値が 0 以外のである必要があります。  *値が* 0 として渡された場合、値 1 は実際の値で置き換えられます。  
  
 `setjmp` の戻りを呼び出した関数の前に `longjmp` ;を呼び出します。それ以外の場合、結果は予測できません。  
  
 `longjmp`を使用するときは、以下の制限を確認する:  
  
-   レジスタ変数の値が変わらないとは限りません。  定期的に呼び出されて `setjmp` のレジスタ変数の値は適切な値に `longjmp` の実行後に復元されない場合があります。  
  
-   割り込みが浮動小数点例外によって引き起こされなかったら割り込み処理ルーチンから転送する `longjmp` を使用しないでください。  この場合、プログラムは `longjmp` によって割り込みハンドラーから `_fpreset`を呼び出して、最初に使用する浮動小数点演算パッケージの初期設定をやり直せば返される可能性があります。  
  
     **メモ**は  `setjmp` と `longjmp` を C\+\+ プログラムで使用する場合は注意してください。  これらの関数は C\+\+ オブジェクトのセマンティクスをサポートしないため、C\+\+ 例外処理機構を使用しても安全です。  
  
 詳細については、「[setjmp および longjmp を使用する](../../cpp/using-setjmp-longjmp.md)」を参照してください。  
  
## 必要条件  
  
|ルーチン|必須ヘッダー|  
|----------|------------|  
|`longjmp`|\<setjmp.h\>|  
  
 互換性の詳細については、「C ランタイム ライブラリ」の「[互換性](../../c-runtime-library/compatibility.md)」を参照してください。  
  
## ライブラリ  
 [C ランタイム ライブラリ](../../c-runtime-library/crt-library-features.md)のすべてのバージョン。  
  
## 使用例  
 [\_fpreset](../../c-runtime-library/reference/fpreset.md)"の例を参照してください。  
  
## 同等の .NET Framework 関数  
 使用できません。標準 C 関数を呼び出すには、`PInvoke` を使用します。詳細については、「[プラットフォーム呼び出しの例](../Topic/Platform%20Invoke%20Examples.md)」を参照してください。  
  
## 参照  
 [プロセス制御と環境制御](../../c-runtime-library/process-and-environment-control.md)   
 [setjmp](../../c-runtime-library/reference/setjmp.md)