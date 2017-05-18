---
title: "ランタイム エラー チェック | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- c.runtime
dev_langs:
- C++
helpviewer_keywords:
- run-time error checking
- run-time errors, checking
ms.assetid: c965dd01-57ad-4a3c-b1d6-5aa04f920501
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
ms.sourcegitcommit: e257f037a05c45f5b98e64ea55bd125af443b0be
ms.openlocfilehash: eb9db9ea42d50faa6e7a693c95795036e650a760
ms.contentlocale: ja-jp
ms.lasthandoff: 03/29/2017

---
# <a name="run-time-error-checking"></a>ランタイム エラー チェック
C のランタイム ライブラリには、ランタイム エラー チェック (RTC) をサポートする関数が含まれています。 ランタイム エラー チェックにより、特定の種類のランタイム エラーが報告されるようにプログラムを作成することができます。 エラーの報告方法と、報告するエラーの種類を指定できます。 詳細については、「[ランタイム エラー チェック](http://msdn.microsoft.com/Library/dc7b2f1e-5ff6-42e0-89b3-dc9dead83ee1)」を参照してください。  
  
 プログラムによるランタイム エラー チェックの方法をカスタマイズするには、次の関数を使用します。  
  
### <a name="run-time-error-checking-functions"></a>ランタイム エラー チェックの関数  
  
|関数|用途|  
|--------------|---------|  
|[_RTC_GetErrDesc](../c-runtime-library/reference/rtc-geterrdesc.md)|ランタイム エラー チェックの種類に関する簡単な説明を返します。|  
|[_RTC_NumErrors](../c-runtime-library/reference/rtc-numerrors.md)|ランタイム エラー チェックで検出できるエラーの合計数を返します。|  
|[_RTC_SetErrorFunc](../c-runtime-library/reference/rtc-seterrorfunc.md)|ランタイム エラー チェックを報告するためのハンドラーとして関数を指定します。|  
|[_RTC_SetErrorType](../c-runtime-library/reference/rtc-seterrortype.md)|ランタイム エラー チェックで検出されたエラーを特定の種類に関連付けます。|  
  
## <a name="see-also"></a>関連項目  
 [カテゴリ別ランタイム ルーチン](../c-runtime-library/run-time-routines-by-category.md)   
 [/RTC (ランタイム エラー チェック)](../build/reference/rtc-run-time-error-checks.md)   
 [runtime_checks](../preprocessor/runtime-checks.md)   
 [RTC サンプル](http://msdn.microsoft.com/en-us/b3415b09-f6fd-43dc-8c02-9a910bc2574e)   
 [デバッグ ルーチン](../c-runtime-library/debug-routines.md)
