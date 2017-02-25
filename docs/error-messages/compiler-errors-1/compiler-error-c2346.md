---
title: "コンパイラ エラー C2346 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C2346"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2346"
ms.assetid: 246145be-5645-4cd6-867c-e3bc39e33dca
caps.latest.revision: 12
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 12
---
# コンパイラ エラー C2346
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'関数' はネイティブとしてコンパイルできません: '理由'  
  
 関数を MSIL にコンパイルできませんでした。  
  
 詳細については、「[マネージ、アンマネージ](../../preprocessor/managed-unmanaged.md)」および「[\/clr \(共通言語ランタイムのコンパイル\)](../../build/reference/clr-common-language-runtime-compilation.md)」を参照してください。  
  
### このエラーを解決するには  
  
1.  MSIL にコンパイルできない関数をコードから削除します。  
  
2.  **\/clr** を使用してモジュールをコンパイルしたり、アンマネージ プラグマを使用して関数にアンマネージのマークを付けたりしないでください。  
  
## 使用例  
 次の例では C2346 エラーが生成されます。  
  
```  
// C2346.cpp  
// processor: x86  
// compile with: /clr   
// C2346 expected  
struct S  
{  
   S()  
   {  
      { __asm { nop } }  
   }  
   virtual __clrcall ~S() { }  
};  
  
void main()  
{  
   S s;  
}  
```