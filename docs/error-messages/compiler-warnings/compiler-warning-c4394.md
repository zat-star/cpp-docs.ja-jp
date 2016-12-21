---
title: "コンパイラの警告 C4394 | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C4394"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C4394"
ms.assetid: 5de94de0-17e3-4e7c-92f4-5c3c1b825120
caps.latest.revision: 11
caps.handback.revision: 11
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# コンパイラの警告 C4394
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'関数' : appdomain ごとのシンボルは \_\_declspec\(dllexport\) と共に設定することはできません  
  
 [appdomain](../Topic/appdomain.md) `__declspec` 修飾子でマークされている関数がネイティブにではなく MSIL にコンパイルされました。テーブルのエクスポート \([export](../../windows/export.md) `__declspec` 修飾子\) は、マネージ関数ではサポートされていません。  
  
 public アクセシビリティを持つようにマネージ関数を宣言できます。  詳細については、「[型の可視性](../../dotnet/how-to-define-and-consume-classes-and-structs-cpp-cli.md#BKMK_Type_visibility)」と「[メンバーの可視性](../../dotnet/how-to-define-and-consume-classes-and-structs-cpp-cli.md#BKMK_Member_visibility)」を参照してください。  
  
 C4394 は、常にエラーとして表示されます。この警告は、`#pragma warning` または **\/wd** を使用してオフにできます。詳細については、「[warning](../../preprocessor/warning.md)」または「[\/w、\/Wn、\/WX、\/Wall、\/wln、\/wdn、\/wen、\/won \(警告レベル\)](../../build/reference/compiler-option-warning-level.md)」を参照してください。  
  
## 使用例  
 次の例では C4394 エラーが生成されます。  
  
```  
// C4394.cpp  
// compile with: /clr /c  
__declspec(dllexport) __declspec(appdomain) int g1 = 0;   // C4394  
__declspec(dllexport) int g2 = 0;   // OK  
```