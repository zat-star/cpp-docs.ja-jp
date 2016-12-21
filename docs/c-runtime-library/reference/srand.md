---
title: "srand | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
apiname: 
  - "srand"
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
  - "api-ms-win-crt-utility-l1-1-0.dll"
apitype: "DLLExport"
f1_keywords: 
  - "srand"
dev_langs: 
  - "C++"
  - "C"
helpviewer_keywords: 
  - "数, 擬似乱数"
  - "数, 乱数"
  - "擬似乱数"
  - "乱数, 生成"
  - "乱数の始点"
  - "乱数の始点, 設定"
  - "srand 関数"
  - "始点"
  - "始点, 設定 (乱数の)"
ms.assetid: 7bf56dc5-5692-4182-a3c1-18af98d2dd1a
caps.latest.revision: 12
caps.handback.revision: 12
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# srand
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

擬似乱数ジェネレーターのシード開始値を設定します。  
  
## 構文  
  
```  
void srand(  
   unsigned int seed   
);  
```  
  
#### パラメーター  
 `seed`  
 擬似乱数ジェネレーターのシード  
  
## 解説  
 `srand` 関数は、現在のスレッドに一連の整数の擬似乱数を生成するための開始点を設定します。  ジェネレーターを最初期化して、結果の同じシーケンスを作成するには、`srand` 関数を呼び出し、同じ `seed` 引数を再度使用します。  `seed` のその他の値は、擬似乱数シーケンスのさまざまな開始位置にジェネレーターを設定します。  `rand` は、生成される擬似乱数を取得します。  `srand` に対する呼び出しの前に `rand` を呼び出すと、1 として渡された `seed` を使用して `srand` を呼び出すのと同じシーケンスが生成されます。  
  
## 必要条件  
  
|ルーチン|必須ヘッダー|  
|----------|------------|  
|`srand`|\<stdlib.h\>|  
  
 互換性の詳細については、「C ランタイム ライブラリ」の「[互換性](../../c-runtime-library/compatibility.md)」を参照してください。  
  
## 使用例  
 「[rand](../Topic/rand.md)」の例を参照してください。  
  
## 同等の .NET Framework 関数  
 [System::Random Class](https://msdn.microsoft.com/en-us/library/system.random.aspx)  
  
## 参照  
 [浮動小数点サポート](../../c-runtime-library/floating-point-support.md)   
 [rand](../Topic/rand.md)