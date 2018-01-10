---
title: _CxxThrowException | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
apiname: _CxxThrowException
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
- CxxThrowException
- _CxxThrowException
dev_langs: C++
helpviewer_keywords:
- _CxxThrowException function
- CxxThrowException function
ms.assetid: 0b90bef5-b7d2-46e0-88e2-59e531e01a4d
caps.latest.revision: "8"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: d1c66f35a61a1b3f8577ac7a1432423906f091ab
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
---
# <a name="cxxthrowexception"></a>_CxxThrowException
例外レコードを作成し、ランタイム環境を呼び出して例画の処理を開始します。  
  
## <a name="syntax"></a>構文  
  
```  
extern "C" void __stdcall _CxxThrowException(  
   void* pExceptionObject  
   _ThrowInfo* pThrowInfo  
);  
```  
  
#### <a name="parameters"></a>パラメーター  
 [入力] `pExceptionObject`  
 例外を生成したオブジェクト。  
  
 [入力] `pThrowInfo`  
 例外の処理に必要な情報。  
  
## <a name="remarks"></a>コメント  
 このメソッドは、コンパイラで例外処理に使用されるコンパイラ専用ファイルに含まれています。 このメソッドはコードから直接呼び出さないでください。  
  
## <a name="requirements"></a>必要条件  
 **ソース:** Throw.cpp  
  
## <a name="see-also"></a>参照  
 [関数リファレンス (アルファベット順)](../../c-runtime-library/reference/crt-alphabetical-function-reference.md)