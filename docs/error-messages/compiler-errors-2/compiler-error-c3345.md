---
title: "コンパイラ エラー C3345 |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: C3345
dev_langs: C++
helpviewer_keywords: C3345
ms.assetid: 1dda4c79-73bb-441b-b939-746154c3afba
caps.latest.revision: "4"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: ca51e90d8c0cbb1806cc0b042d9c3ae2480a9729
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-error-c3345"></a>コンパイラ エラー C3345
'identifier': モジュール名に対する無効な識別子です  
  
 モジュールの *識別子* に 1 つまたは複数の無効な文字が含まれています。 識別子は、最初の文字がアルファベット、アンダースコア、または高位 ANSI (0x80-FF) 文字で、それ以降の任意の文字が英数字、アンダースコア、または高位 ANSI 文字である場合に有効です。  
  
### <a name="to-correct-this-error"></a>このエラーを解決するには  
  
1.  *識別子* に空白またはその他の無効な文字が含まれていないことを確認します。  
  
## <a name="example"></a>例  
 次のコード例では、 `name` 属性の `module` パラメーターに空白が含まれているので、エラー メッセージ C3345 が発生します。  
  
```  
// cpp_attr_name_module.cpp  
// compile with: /LD /link /OPT:NOREF  
#include <atlbase.h>  
#include <atlcom.h>  
#include <atlwin.h>  
#include <atltypes.h>  
#include <atlctl.h>  
#include <atlhost.h>  
#include <atlplus.h>  
  
// C3345 expected  
[module(dll, name="My Library", version="1.2", helpfile="MyHelpFile")]   
// Try the following line instead  
//[module(dll, name="MyLibrary", version="1.2", helpfile="MyHelpFile")]   
// Module attribute now applies to this class  
class CMyClass {  
public:  
BOOL WINAPI DllMain(DWORD dwReason, LPVOID lpReserved) {  
   // add your own code here  
   return __super::DllMain(dwReason, lpReserved);  
   }  
};  
```  
  
## <a name="see-also"></a>参照  
 [__iscsym](../../c-runtime-library/reference/iscsym-functions.md)   
 [文字分類](../../c-runtime-library/character-classification.md)   
 [モジュール](../../windows/module-cpp.md)