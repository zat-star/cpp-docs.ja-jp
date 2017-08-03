---
title: _except_handler3 | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
apiname:
- _except_handler3
apilocation:
- msvcrt.dll
- msvcr90.dll
- msvcr80.dll
- msvcr110_clr0400.dll
- msvcr120.dll
- msvcr100.dll
- msvcr110.dll
apitype: DLLExport
f1_keywords:
- _except_handler3
- except_handler3
dev_langs:
- C++
helpviewer_keywords:
- _except_handler3 function
- except_handler3 function
ms.assetid: b0c64898-0ae5-48b7-9724-80135a0813e2
caps.latest.revision: 7
author: corob-msft
ms.author: corob
manager: ghogen
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
ms.translationtype: Human Translation
ms.sourcegitcommit: d6eb43b2e77b11f4c85f6cf7e563fe743d2a7093
ms.openlocfilehash: ce3717ea39cec55ab982de3c9d8fddd0b50632ee
ms.contentlocale: ja-jp
ms.lasthandoff: 05/18/2017

---
# <a name="excepthandler3"></a>_except_handler3
内部 CRT 関数。 現在の例外を処理する適切な例外ハンドラーを見つけるためにフレームワークによって使用されます。  
  
## <a name="syntax"></a>構文  
  
```  
int _except_handler3(  
   PEXCEPTION_RECORD exception_record,  
   PEXCEPTION_REGISTRATION registration,  
   PCONTEXT context,  
   PEXCEPTION_REGISTRATION dispatcher  
);  
```  
  
#### <a name="parameters"></a>パラメーター  
 [入力] `exception_record`  
 特定の例外に関する情報。  
  
 [入力] `registration`  
 例外ハンドラーを見つけるために使用する必要があるスコープ テーブルを示すレコード。  
  
 [入力] `context`  
 予約済み。  
  
 [入力] `dispatcher`  
 予約済み。  
  
## <a name="return-value"></a>戻り値  
 例外を破棄する必要がある場合は、`DISPOSITION_DISMISS` を返します。 カプセル化する例外ハンドラーにレベルを上げて例外を渡す必要がある場合は、`DISPOSITION_CONTINUE_SEARCH` を返します。  
  
## <a name="remarks"></a>コメント  
 適切な例外ハンドラーが見つかった場合、このメソッドはそのハンドラーに例外を渡します。 この状況では、このメソッドはそれを呼び出したコードには戻らず、戻り値は無関係です。  
  
## <a name="see-also"></a>関連項目  
 [関数リファレンス (アルファベット順)](../c-runtime-library/reference/crt-alphabetical-function-reference.md)
