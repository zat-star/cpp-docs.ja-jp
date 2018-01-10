---
title: longjmp | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
apiname: longjmp
apilocation:
- msvcrt.dll
- msvcr80.dll
- msvcr90.dll
- msvcr100.dll
- msvcr100_clr0400.dll
- msvcr110.dll
- msvcr110_clr0400.dll
- msvcr120.dll
- msvcr120_clr0400.dll
- ucrtbase.dll
apitype: DLLExport
f1_keywords: longjmp
dev_langs: C++
helpviewer_keywords:
- restoring stack environment and execution locale
- longjmp function
ms.assetid: 0e13670a-5130-45c1-ad69-6862505b7a2f
caps.latest.revision: "9"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 864aacbc30d9d50e1d0335d0d74c7ed63119d132
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
---
# <a name="longjmp"></a>longjmp
スタック環境と実行ロケールを復元します。  
  
## <a name="syntax"></a>構文  
  
```  
  
      void longjmp(  
   jmp_buf env,  
   int value   
);  
```  
  
#### <a name="parameters"></a>パラメーター  
 `env`  
 環境が格納されている変数。  
  
 *値*  
 `setjmp` 呼び出しに返される値。  
  
## <a name="remarks"></a>コメント  
 `longjmp` 関数は、以前に `setjmp` によって `env` に保存されたスタック環境と実行ロケールを復元します。 `setjmp` と `longjmp` は非ローカル `goto` を実行する方法を提供します。これらは通常、通常呼び出し規約と復帰規約を使用せずに、前に呼び出されたルーチンのエラー処理または回復コードに実行の制御を渡すために使用されます。  
  
 `setjmp` を呼び出すと、現在のスタック環境は `env` に保存されます。 `longjmp` への後続の呼び出しは、保存されている環境を復元し、対応する `setjmp` 呼び出しの直後のポイントに制御を返します。 実行は、*value* が `setjmp` 呼び出しによって返されたかのように再開されます。 制御を受け取るルーチンからアクセスできるすべての変数 (レジスタ変数を除く) の値には、`longjmp` が呼び出されたときに保持していた値が含まれます。 レジスタ変数の値は予測できません。 `setjmp` によって返される値は、0 以外である必要があります。 *value* が 0 として渡される場合、実際の戻り値では 1 が代入されます。  
  
 `setjmp` を呼び出した関数が戻る前に `longjmp` を呼び出します。それ以外の場合、結果は予測できません。  
  
 `longjmp` を使用する場合は、次の制限事項にご注意ください。  
  
-   レジスタ変数の値は変わらないと見なさないでください。 `setjmp` を呼び出すルーチンのレジスタ変数の値は、`longjmp` の実行後、適切な値に復元されない場合があります。  
  
-   割り込み処理ルーチンから制御を移動するために `longjmp` を使用しないでください。ただし、割り込みが浮動小数点例外によって発生した場合を除きます。 この場合、`_fpreset` を呼び出して浮動小数点演算パッケージが最初に再初期化されるなら、プログラムは `longjmp` を介して割り込みハンドラーから復帰できます。  
  
     **注** C++ プログラムで `setjmp` と `longjmp` を使用する場合は注意が必要です。 これらの関数は C++ オブジェクト セマンティクスをサポートしていないため、C++ 例外処理機構を使用する方が安全です。  
  
 詳細については、「[setjmp/longjmp の使用](../../cpp/using-setjmp-longjmp.md)」を参照してください。  
  
## <a name="requirements"></a>必要条件  
  
|ルーチンによって返される値|必須ヘッダー|  
|-------------|---------------------|  
|`longjmp`|\<setjmp.h >|  
  
 互換性の詳細については、「C ランタイム ライブラリ」の「 [互換性](../../c-runtime-library/compatibility.md) 」を参照してください。  
  
## <a name="libraries"></a>ライブラリ  
 [C ランタイム ライブラリ](../../c-runtime-library/crt-library-features.md)のすべてのバージョン。  
  
## <a name="example"></a>例  
 「[_fpreset](../../c-runtime-library/reference/fpreset.md)」の例を参照してください。  
  
## <a name="see-also"></a>参照  
 [プロセス制御と環境制御](../../c-runtime-library/process-and-environment-control.md)   
 [setjmp](../../c-runtime-library/reference/setjmp.md)