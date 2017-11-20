---
title: "_execute_onexit_table、_initialize_onexit_table、_register_onexit_function | Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
apiname:
- _execute_onexit_table
- _initialize_onexit_table
- _register_onexit_function
apilocation: api-ms-win-crt-runtime-l1-1-0.dll
apitype: DLLExport
f1_keywords:
- _execute_onexit_table
- process/_execute_onexit_table
- _initialize_onexit_table
- process/_initialize_onexit_table
- _register_onexit_function
- process/_register_onexit_function
dev_langs: C++
helpviewer_keywords:
- _execute_onexit_table function
- _initialize_onexit_table function
- _register_onexit_function function
ms.assetid: ad9e4149-d4ad-4fdf-aaaf-cf786fcb4473
caps.latest.revision: "3"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 630b8a5160eaa808c12c16ec8dd45a96a621b7bb
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/24/2017
---
# <a name="executeonexittable-initializeonexittable-registeronexitfunction"></a>_execute_onexit_table、_initialize_onexit_table、_register_onexit_function
終了時に呼び出されるルーチンを管理します。  
  
## <a name="syntax"></a>構文  
  
```  
int _initialize_onexit_table(  
    _onexit_table_t* table  
    );  
  
int _register_onexit_function(  
    _onexit_table_t* table,  
    _onexit_t        function  
    );  
  
int _execute_onexit_table(  
    _onexit_table_t* table  
    );  
```  
  
#### <a name="parameters"></a>パラメーター  
 [inout] `table`  
 onexit 関数テーブルを指すポインター。  
  
 [入力] `function`  
 onexit 関数テーブルに追加する関数を指すポインター。  
  
## <a name="return-value"></a>戻り値  
 正常に終了した場合は、0 を返します。 それ以外の場合は、負の値を返します。  
  
## <a name="remarks"></a>コメント  
 これらの関数は、C ランタイムをサポートするために使用されるインフラストラクチャ実装の詳細であり、ご使用のコードから直接呼び出してはなりません。 C ランタイムでは、*onexit 関数テーブル*を使用して、`atexit`、`at_quick_exit`、および `_onexit` の呼び出しによって登録される関数のシーケンスを表現します。 onexit 関数テーブルのデータ構造は、C ランタイムの不透明な実装の詳細であり、データ メンバーの順番と意味は変わる場合があります。 それらを外部コードによって確認してはなりません。  
  
 `_initialize_onexit_table` 関数は、onexit 関数テーブルをその初期値に初期化します。  この関数は、onexit 関数テーブルを `_register_onexit_function` または `_execute_onexit_table` に渡す前に呼び出す必要があります。  
  
 `_register_onexit_function` 関数は、onexit 関数テーブルの末尾に関数を追加します。  
  
 `_execute_onexit_table` 関数は、onexit 関数テーブル内のすべての関数を実行し、テーブルをクリアして、制御を返します。 `_execute_onexit_table` の呼び出しの後、このテーブルは無効な状態になります。再度使用するには `_initialize_onexit_table` を呼び出して事前に再初期化しておく必要があります。  
  
## <a name="requirements"></a>要件  
  
|ルーチン|必須ヘッダー|  
|-------------|---------------------|  
|`_initialize_onexit_table function`、`_register_onexit_function`、`_execute_onexit_table`|C、C++: \<process.h>|  
  
 `_initialize_onexit_table`、`_register_onexit_function`、`_execute_onexit_table` の各関数は、Microsoft 固有の関数です。 互換性の詳細については、「[互換性](../c-runtime-library/compatibility.md)」を参照してください。  
  
## <a name="see-also"></a>関連項目  
 [atexit](../c-runtime-library/reference/atexit.md)   
 [exit、_Exit、_exit](../c-runtime-library/reference/exit-exit-exit.md)   
 [_onexit、_onexit_m](../c-runtime-library/reference/onexit-onexit-m.md)