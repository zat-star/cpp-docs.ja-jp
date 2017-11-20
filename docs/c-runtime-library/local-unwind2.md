---
title: _local_unwind2 | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
apiname: _local_unwind2
apilocation:
- msvcr110_clr0400.dll
- msvcrt.dll
- msvcr100.dll
- msvcr110.dll
- msvcr80.dll
- msvcr90.dll
- msvcr120.dll
apitype: DLLExport
f1_keywords:
- _local_unwind2
- local_unwind2
dev_langs: C++
helpviewer_keywords:
- _local_unwind2 function
- local_unwind2 function
ms.assetid: 44f1fa82-e01e-490f-a6e6-18fc6811c28c
caps.latest.revision: "5"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 8ad37d66e0e73e7ee75e2c44869c59c545025bd6
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/24/2017
---
# <a name="localunwind2"></a>_local_unwind2
内部 CRT 関数。 指定されたスコープ テーブルに示されているすべての終了ハンドラーを実行します。  
  
## <a name="syntax"></a>構文  
  
```  
void _local_unwind2(  
   PEXCEPTION_REGISTRATION xr,  
   int stop  
);  
```  
  
#### <a name="parameters"></a>パラメーター  
 [入力] `xr`  
 1 つのスコープ テーブルに関連付けられている登録レコード。  
  
 [入力] `stop`  
 `_local_unwind2` の停止箇所を示す構文レベル。  
  
## <a name="remarks"></a>コメント  
 このメソッドは、ランタイム環境によってのみ使用されます。 このメソッドをコードで呼び出さないでください。  
  
 このメソッドが終了ハンドラーを実行する場合、現在の構文レベルで開始し、`stop` で示されたレベルに到達するまで構文レベル内を上へ移動します。 `stop` で示されたレベルでは終了ハンドラーを実行しません。  
  
## <a name="see-also"></a>関連項目  
 [関数リファレンス (アルファベット順)](../c-runtime-library/reference/crt-alphabetical-function-reference.md)