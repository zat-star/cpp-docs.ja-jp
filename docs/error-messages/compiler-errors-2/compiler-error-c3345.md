---
title: "コンパイラ エラー C3345 | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-csharp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "C3345"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C3345"
ms.assetid: 1dda4c79-73bb-441b-b939-746154c3afba
caps.latest.revision: 4
caps.handback.revision: 4
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# コンパイラ エラー C3345
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'identifier': モジュール名に対する無効な識別子です  
  
 モジュールの*識別子*に 1 つまたは複数の無効な文字が含まれています。 識別子は、最初の文字がアルファベット、アンダースコア、または高位 ANSI \(0x80\-FF\) 文字で、それ以降の任意の文字が英数字、アンダースコア、または高位 ANSI 文字である場合に有効です。  
  
### このエラーを解決するには  
  
1.  *識別子*に空白またはその他の無効な文字が含まれていないことを確認します。  
  
## 使用例  
 次のコード例では、`module` 属性の `name` パラメーターに空白が含まれているので、エラー メッセージ C3345 が発生します。  
  
```  
// cpp_attr_name_module.cpp // compile with: /LD /link /OPT:NOREF #include <atlbase.h> #include <atlcom.h> #include <atlwin.h> #include <atltypes.h> #include <atlctl.h> #include <atlhost.h> #include <atlplus.h> // C3345 expected [module(dll, name="My Library", version="1.2", helpfile="MyHelpFile")] // Try the following line instead //[module(dll, name="MyLibrary", version="1.2", helpfile="MyHelpFile")] // Module attribute now applies to this class class CMyClass { public: BOOL WINAPI DllMain(DWORD dwReason, LPVOID lpReserved) { // add your own code here return __super::DllMain(dwReason, lpReserved); } };  
```  
  
## 参照  
 [\_\_iscsym](../../c-runtime-library/reference/iscsym-functions.md)   
 [文字分類](../../c-runtime-library/character-classification.md)   
 [モジュール](../../windows/module-cpp.md)