---
title: "Compiler Error C2384 | Microsoft Docs"
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
  - "C2384"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2384"
ms.assetid: 8145f7ad-31b1-406d-ac43-0d557feab635
caps.latest.revision: 15
caps.handback.revision: 15
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# Compiler Error C2384
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'member' : \_\_declspec\(thread\) をマネージ クラスまたは WinRT クラスのメンバーに適用できません  
  
 [thread](../../cpp/thread.md) `__declspec` 修飾子は、マネージ クラスまたは Windows ランタイム クラスのメンバーでは使用できません。  
  
 マネージ コード内の静的なスレッド ローカル ストレージは、静的に読み込まれた DLL に対してのみ使用できます。DLL は、プロセスの開始時に静的に読み込まれる必要があります。  Windows ランタイムでは、スレッド ローカル ストレージはサポートされません。  
  
 次の例では、C2384 を生成し、C\+\+\/CLI コードで修正する方法を示しています。  
  
```  
// C2384.cpp  
// compile with: /clr /c  
public ref class B {  
public:  
   __declspec( thread ) static int tls_i = 1;   // C2384  
  
   // OK - declare with attribute instead  
   [System::ThreadStaticAttribute]  
   static int tls_j;  
};  
```