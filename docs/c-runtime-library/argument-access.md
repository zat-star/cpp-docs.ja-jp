---
title: "引数へのアクセス | Microsoft Docs"
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
  - "c.arguments"
dev_langs: 
  - "C++"
  - "C"
helpviewer_keywords: 
  - "引数アクセス マクロ [C++]"
  - "可変長の引数リスト"
ms.assetid: 7046ae34-a0ec-44f0-815d-3209492a3e19
caps.latest.revision: 8
caps.handback.revision: 8
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# 引数へのアクセス
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

引数の数が可変である場合 `va_arg`、`va_end`と `va_start` マクロは、関数引数へのアクセスを提供します。  これらのマクロは、ANSI C の互換性の STDARG.H とシステム UNIX V.との互換性の VARARGS.H で定義されます。  
  
### 引数アクセス マクロ  
  
|マクロ|使用方法|同等の .NET Framework 関数|  
|---------|----------|---------------------------|  
|[va\_arg マクロ](../c-runtime-library/reference/va-arg-va-copy-va-end-va-start.md)|一覧から引数を取得してください。|[\<caps:sentence id\="tgt9" sentenceid\="f260effcc218d99ea9ab361455fd493c" class\="tgtSentence"\>System::ParamArrayAttribute Class\<\/caps:sentence\>](https://msdn.microsoft.com/en-us/library/system.paramarrayattribute.aspx)|  
|[va\_end](../c-runtime-library/reference/va-arg-va-copy-va-end-va-start.md)|ポインターをリセットします。|[\<caps:sentence id\="tgt12" sentenceid\="f260effcc218d99ea9ab361455fd493c" class\="tgtSentence"\>System::ParamArrayAttribute Class\<\/caps:sentence\>](https://msdn.microsoft.com/en-us/library/system.paramarrayattribute.aspx)|  
|[va\_start](../c-runtime-library/reference/va-arg-va-copy-va-end-va-start.md)|引数リストの先頭へのポインターを設定します。|[\<caps:sentence id\="tgt15" sentenceid\="f260effcc218d99ea9ab361455fd493c" class\="tgtSentence"\>System::ParamArrayAttribute Class\<\/caps:sentence\>](https://msdn.microsoft.com/en-us/library/system.paramarrayattribute.aspx)|  
  
## 参照  
 [カテゴリ別ランタイム ルーチン](../c-runtime-library/run-time-routines-by-category.md)