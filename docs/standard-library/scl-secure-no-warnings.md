---
title: _SCL_SECURE_NO_WARNINGS | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-standard-libraries
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
ms.translationtype: MT
ms.sourcegitcommit: 65f4e356ad0d46333b0d443d0fd6ac0b9f2b6f58
ms.openlocfilehash: 92cc02c47d4a423cce70a1289a1ce54587a92c2f
ms.contentlocale: ja-jp
ms.lasthandoff: 10/03/2017

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
  
 C4996 に警告のレベルを手動で変更しても、 **/w\<l >\< n>** コンパイラ オプション。 たとえば、警告 C4996 をレベル 4 に設定します。  
  
```  
cl /w44996 [other compiler options] myfile.cpp  
```  
  
 詳細については、「[/w、/W0、/W1、/W2、/W3、/W4, /w1, /w2, /w3、/w4、/Wall、/wd、/we、/wo、/Wv、/WX (警告レベル)](../build/reference/compiler-option-warning-level.md)」を参照してください。  
  
## <a name="see-also"></a>関連項目  
 [安全なライブラリ: C++ 標準ライブラリ](../standard-library/safe-libraries-cpp-standard-library.md)


