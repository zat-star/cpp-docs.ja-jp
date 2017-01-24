---
title: "_SCL_SECURE_NO_WARNINGS | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "_SCL_SECURE_NO_DEPRECATE"
  - "_SCL_SECURE_NO_WARNINGS"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "_SCL_SECURE_NO_DEPRECATE"
  - "_SCL_SECURE_NO_WARNINGS"
ms.assetid: ef0ddea9-7c62-4b53-8b64-5f4fd369776f
caps.latest.revision: 5
caps.handback.revision: 4
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# _SCL_SECURE_NO_WARNINGS
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

標準 C\+\+ ライブラリを使用すると、安全でないメソッドのいずれかを呼び出すと、[コンパイラの警告 \(レベル 3\) C4996](../error-messages/compiler-warnings/compiler-warning-level-3-c4996.md)になります。  この警告を無効にするには、コードの **\_SCL\_SECURE\_NO\_WARNINGS** マクロを定義する:  
  
```  
#define _SCL_SECURE_NO_WARNINGS  
```  
  
## 解説  
 C4996 警告を無効にするもう一つの方法は、次のとおりです。:  
  
-   [\/D \(プリプロセッサの定義\)](../build/reference/d-preprocessor-definitions.md) のコンパイラ オプションの使用:  
  
    ```  
    cl /D_SCL_SECURE_NO_WARNINGS [other compiler options] myfile.cpp  
    ```  
  
-   [\/w](../build/reference/compiler-option-warning-level.md) のコンパイラ オプションの使用:  
  
    ```  
    cl /wd4996 [other compiler options] myfile.cpp  
    ```  
  
-   [\#pragma warning](../preprocessor/warning.md) のディレクティブの使用:  
  
    ```  
    #pragma warning(disable:4996)  
    ```  
  
 また、手動で **\/w\<l\>\<n\>** コンパイラ オプションを C4996 警告レベルを変更できます。  たとえば、C4996 警告レベルを 4 に設定するには:  
  
```  
cl /w44996 [other compiler options] myfile.cpp  
```  
  
 詳細については、「[\/w、\/Wn、\/WX、\/Wall、\/wln、\/wdn、\/wen、\/won \(警告レベル\)](../build/reference/compiler-option-warning-level.md)」を参照してください。  
  
## 参照  
 [安全なライブラリ: C\+\+ 標準ライブラリ](../standard-library/safe-libraries-cpp-standard-library.md)