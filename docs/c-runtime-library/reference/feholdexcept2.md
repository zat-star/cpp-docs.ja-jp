---
title: "feholdexcept2 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "cpp"
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
apiname: 
  - "feholdexcept"
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
  - "api-ms-win-crt-runtime-l1-1-0.dll"
apitype: "DLLExport"
f1_keywords: 
  - "feholdexcept"
  - "fenv/feholdexcept"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "feholdexcept 関数"
ms.assetid: 88e512ae-b5d8-452c-afe9-c824cd3ef1d8
caps.latest.revision: 5
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 5
---
# feholdexcept
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

指定したオブジェクトで現在の浮動小数点環境を保存、浮動小数点ステータス フラグをクリアし、可能であれば、浮動小数点環境を停止モードにします。  
  
## 構文  
  
```  
int feholdexcept(  
   fenv_t *penv  
);  
  
```  
  
#### パラメーター  
 `penv`  
 ポインター、 `fenv_t` 浮動小数点環境のコピーを格納するオブジェクト。  
  
## 戻り値  
 場合にのみ、関数は神業浮動小数点の例外処理が正常に有効にすることは、0 を返します。  
  
## 解説  
 `feholdexcept` である現在のフローティング ポイント環境の状態を格納する関数が使用される、 `fenv_t` によって指されるオブジェクト `penv`, 、浮動小数点例外の実行が中断するための環境を設定するとします。 これは神業モードと呼ばれます。  このモードを使用して、環境が復元されるまでの継続 [fesetenv](../Topic/fesetenv2.md) または [feupdateenv](../Topic/feupdateenv.md)です。  
  
 呼び出し元からの 1 つまたは複数の浮動小数点例外を非表示にする必要があるサブルーチンの先頭には、この関数を使用することができます。 例外を報告するための内容を消去望ましくない例外を使用して [feclearexcept、](../../c-runtime-library/reference/feclearexcept1.md) への呼び出しで停止モードを終了し、 `feupdateenv`します。  
  
 この関数を使用するのには、浮動小数点の最適化を使用してアクセスを妨げる可能性のあるオフにする必要があります、 `#pragma fenv_access(on)` 呼び出しの前にディレクティブです。 詳細については、「[fenv\_access](../../preprocessor/fenv-access.md)」を参照してください。  
  
## 必要条件  
  
|関数|C ヘッダー|C\+\+ ヘッダー|  
|--------|------------|----------------|  
|`feholdexcept`|\<fenv.h\>|\<cfenv\>|  
  
 互換性について詳しくは、「[互換性](../../c-runtime-library/compatibility.md)」をご覧ください。  
  
## 参照  
 [関数リファレンス \(アルファベット順\)](../../c-runtime-library/reference/crt-alphabetical-function-reference.md)   
 [feclearexcept](../../c-runtime-library/reference/feclearexcept1.md)   
 [fesetenv](../Topic/fesetenv2.md)   
 [feupdateenv](../Topic/feupdateenv.md)