---
title: _abnormal_termination | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
apiname:
- _abnormal_termination
apilocation:
- msvcr110.dll
- msvcr110_clr0400.dll
- msvcr90.dll
- msvcr120.dll
- msvcrt.dll
- msvcr80.dll
- msvcr100.dll
apitype: DLLExport
f1_keywords:
- _abnormal_termination
dev_langs:
- C++
helpviewer_keywords:
- _abnormal_termination
ms.assetid: 952970a4-9586-4c3d-807a-db729448c91c
caps.latest.revision: 2
author: corob-msft
ms.author: corob
manager: ghogen
translation.priority.ht:
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- ru-ru
- zh-cn
- zh-tw
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
translationtype: Human Translation
ms.sourcegitcommit: 3168772cbb7e8127523bc2fc2da5cc9b4f59beb8
ms.openlocfilehash: 37b80a5e21d7310269797d0760be3d9f76d3c581

---
# <a name="abnormaltermination"></a>_abnormal_termination
システムが終了ハンドラーの内部リストの実行中に、[try-finally ステートメント](../cpp/try-finally-statement.md)の `__finally` ブロックが入力されているかどうかを示します。  
  
## <a name="syntax"></a>構文  
  
```cpp  
int   _abnormal_termination(  
   );  
```  
  
## <a name="return-value"></a>戻り値  
 システムがスタックを*アンワインド*する場合は `true`、それ以外は `false` です。  
  
## <a name="remarks"></a>コメント  
 これは、アンワインドの例外を管理するために使用される内部関数で、ユーザー コードから呼び出されるものではありません。  
  
## <a name="requirements"></a>要件  
  
|ルーチン|必須ヘッダー|  
|-------------|---------------------|  
|_abnormal_termination|excpt.h|  
  
## <a name="see-also"></a>関連項目  
 [try-finally ステートメント](../cpp/try-finally-statement.md)


<!--HONumber=Feb17_HO4-->


