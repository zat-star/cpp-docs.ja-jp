---
title: setjmp | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: reference
apiname:
- setjmp
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
f1_keywords:
- setjmp
dev_langs:
- C++
helpviewer_keywords:
- programs [C++], saving states
- current state
- setjmp function
ms.assetid: 684a8b27-e8eb-455b-b4a8-733ca1cbd7d2
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: ef5c4b0e026090718fc02dd109a1fccb91152010
ms.sourcegitcommit: 6002df0ac79bde5d5cab7bbeb9d8e0ef9920da4a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/14/2018
---
# <a name="setjmp"></a>setjmp
プログラムの現在の状態を保存します。  
  
## <a name="syntax"></a>構文  
  
```  
int setjmp(  
   jmp_buf env   
);  
```  
  
#### <a name="parameters"></a>パラメーター  
 `env`  
 環境が格納されている変数。  
  
## <a name="return-value"></a>戻り値  
 スタックの環境を保存した後に 0 を返します。 `longjmp` の呼び出しの結果として `setjmp` が値を返す場合は `longjmp` の引数 `value` を返し、`longjmp` の `value` 引数が 0 の場合、`setjmp` は 1 を返します。 エラーの戻り値はありません。  
  
## <a name="remarks"></a>コメント  
 `setjmp` 関数はスタックの環境を保存します。この環境は、`longjmp` を使用して後から復元することができます。 `setjmp` と `longjmp` を一緒に使用すると、非ローカルの `goto` を実行する方法が提供されます。 これらは一般的に、通常の呼び出し規約や復帰規約を使用せず、前に呼び出されたルーチンのエラー処理または回復コードに実行の制御を渡すために使用されます。  
  
 `setjmp` の呼び出しにより、現在のスタックの環境が `env` で保存されます。 `longjmp` への後続の呼び出しは、保存されている環境を復元し、対応する `setjmp` 呼び出しの直後のポイントにコントロールを返します。 コントロールを受け取るルーチンにアクセスできるすべての変数 (レジスタ変数を除く) には、`longjmp` が呼び出されたときに保持していた値が含まれます。  
  
 `setjmp` を使用してにネイティブ コードからマネージ コードに移動することはできません。  
  
 **注** `setjmp` と `longjmp` は C++ オブジェクトのセマンティクスをサポートしていません。 C++ プログラムでは、C++ 例外処理機構を使用します。  
  
 詳細については、「[setjmp/longjmp の使用](../../cpp/using-setjmp-longjmp.md)」を参照してください。  
  
## <a name="requirements"></a>必要条件  
  
|ルーチンによって返される値|必須ヘッダー|  
|-------------|---------------------|  
|`setjmp`|\<setjmp.h >|  
  
 互換性の詳細については、「C ランタイム ライブラリ」の「 [互換性](../../c-runtime-library/compatibility.md) 」を参照してください。  
  
## <a name="example"></a>例  
 「[_fpreset](../../c-runtime-library/reference/fpreset.md)」の例を参照してください。  
  
## <a name="see-also"></a>参照  
 [プロセス制御と環境制御](../../c-runtime-library/process-and-environment-control.md)   
 [longjmp](../../c-runtime-library/reference/longjmp.md)   
 [_setjmp3](../../c-runtime-library/setjmp3.md)