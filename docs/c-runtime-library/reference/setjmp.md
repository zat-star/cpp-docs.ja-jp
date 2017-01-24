---
title: "setjmp | Microsoft Docs"
ms.custom: ""
ms.date: "12/15/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
apiname: 
  - "setjmp"
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
  - "setjmp"
dev_langs: 
  - "C++"
  - "C"
helpviewer_keywords: 
  - "プログラム [C++]、状態の保存"
  - "現在の状態"
  - "setjmp 関数"
ms.assetid: 684a8b27-e8eb-455b-b4a8-733ca1cbd7d2
caps.latest.revision: 12
caps.handback.revision: 12
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# setjmp
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

プログラムの現在の状態が保存されます。  
  
## 構文  
  
```  
int setjmp(  
   jmp_buf env   
);  
```  
  
#### パラメーター  
 `env`  
 環境を格納する変数。  
  
## 戻り値  
 スタック環境を保存すると 0 を返します。  `longjmp` の結果として `setjmp` が呼び出すと、`longjmp`の `value` の引数、または `longjmp` の `value` の引数が 0 の場合、`setjmp` は 1.を返します。  エラーの戻り値はありません。  
  
## 解説  
 `setjmp` 関数は `longjmp`を使用して復元実行可能なスタック環境を格納します。  同時に使用した場合、`setjmp` と `longjmp` は非ローカルな `goto`を実行する方法を示します。  呼び出す場合は通常、標準を使用せずに呼び出しルーチンのエラー処理や復元コードに実行制御を渡すためにまたはサービスの規則が使用されます。  
  
 `setjmp` の呼び出しは `env`の現在のスタックに環境を格納します。  `longjmp` への後続の呼び出しで、`setjmp` の対応する呼び出しの直後の位置に格納された環境を処理してコントロールを復元します。  定期的な受信のコントロールにアクセスできるすべての変数 \(レジスタ変数を除く\) `longjmp` がいつが呼び出されたときの値が含まれます。  
  
 ネイティブ コードからマネージ コードにジャンプするために `setjmp` を使用することはできません。  
  
 **メモ** `setjmp` と `longjmp` は C\+\+ オブジェクトのセマンティクスをサポートしません。  C\+\+ プログラムでは、C\+\+ 例外処理機構を使用します。  
  
 詳細については、「[setjmp および longjmp を使用する](../../cpp/using-setjmp-longjmp.md)」を参照してください。  
  
## 必要条件  
  
|ルーチン|必須ヘッダー|  
|----------|------------|  
|`setjmp`|\<setjmp.h\>|  
  
 互換性の詳細については、「C ランタイム ライブラリ」の「[互換性](../../c-runtime-library/compatibility.md)」を参照してください。  
  
## 使用例  
 [\_fpreset](../../c-runtime-library/reference/fpreset.md)"の例を参照してください。  
  
## 同等の .NET Framework 関数  
 使用できません。標準 C 関数を呼び出すには、`PInvoke` を使用します。詳細については、「[プラットフォーム呼び出しの例](../Topic/Platform%20Invoke%20Examples.md)」を参照してください。  
  
## 参照  
 [プロセス制御と環境制御](../../c-runtime-library/process-and-environment-control.md)   
 [longjmp](../../c-runtime-library/reference/longjmp.md)   
 [\_setjmp3](../../c-runtime-library/setjmp3.md)