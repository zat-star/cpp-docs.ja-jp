---
title: _SCL_SECURE_NO_WARNINGS | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- _SCL_SECURE_NO_DEPRECATE
- _SCL_SECURE_NO_WARNINGS
dev_langs:
- C++
helpviewer_keywords:
- _SCL_SECURE_NO_DEPRECATE
- _SCL_SECURE_NO_WARNINGS
ms.assetid: ef0ddea9-7c62-4b53-8b64-5f4fd369776f
caps.latest.revision: 5
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
translationtype: Machine Translation
ms.sourcegitcommit: 3f69f0c3176d2fbe19e11ce08c071691a72d858d
ms.openlocfilehash: e2f39c4f07235c75204a63e634053f887682337e
ms.lasthandoff: 02/24/2017

---
# <a name="sclsecurenowarnings"></a>_SCL_SECURE_NO_WARNINGS
C++ 標準ライブラリで安全でない可能性のあるメソッドのいずれかを呼び出すと、[コンパイラの警告 (レベル 3) C4996](../error-messages/compiler-warnings/compiler-warning-level-3-c4996.md) が表示されます。 この警告を無効にするには、コードでマクロ **_SCL_SECURE_NO_WARNINGS** を定義します。  
  
```  
#define _SCL_SECURE_NO_WARNINGS  
```  
  
## <a name="remarks"></a>コメント  
 警告 C4996 を無効にするその他の方法は、次のとおりです。  
  
-   [/D (プリプロセッサの定義)](../build/reference/d-preprocessor-definitions.md) コンパイラ オプションの使用:  
  
 ```  
    cl /D_SCL_SECURE_NO_WARNINGS [other compiler options] myfile.cpp  
```  
  
-   [/w](../build/reference/compiler-option-warning-level.md) コンパイラ オプションの使用:  
  
 ```  
    cl /wd4996 [other compiler options] myfile.cpp  
```  
  
-   [#pragma 警告](../preprocessor/warning.md) ディレクティブの使用:  
  
 ```  
 #pragma warning(disable:4996)  
```  
  
 また、**/w\<l>\<n>** コンパイラ オプションを使用して、警告 C4996 のレベルを手動で変更できます。 たとえば、警告 C4996 をレベル 4 に設定します。  
  
```  
cl /w44996 [other compiler options] myfile.cpp  
```  
  
 詳細については、「[/w、/W0、/W1、/W2、/W3、/W4, /w1, /w2, /w3、/w4、/Wall、/wd、/we、/wo、/Wv、/WX (警告レベル)](../build/reference/compiler-option-warning-level.md)」を参照してください。  
  
## <a name="see-also"></a>関連項目  
 [安全なライブラリ: C++ 標準ライブラリ](../standard-library/safe-libraries-cpp-standard-library.md)


