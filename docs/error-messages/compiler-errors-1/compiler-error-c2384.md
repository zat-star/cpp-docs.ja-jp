---
title: "コンパイラ エラー C2384 |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C2384
dev_langs: C++
helpviewer_keywords: C2384
ms.assetid: 8145f7ad-31b1-406d-ac43-0d557feab635
caps.latest.revision: "15"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: a7494c38c787a0e0877496a8f65556d568d77f7d
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-error-c2384"></a>コンパイラ エラー C2384
'member' : __declspec(thread) をマネージ クラスまたは WinRT クラスのメンバーに適用できません  
  
 [スレッド](../../cpp/thread.md)`__declspec`修飾子は、管理対象のメンバーまたは Windows ランタイム クラスでは使用できません。  
  
 マネージ コード内の静的なスレッド ローカル ストレージは、静的に読み込まれた DLL に対してのみ使用できます。DLL は、プロセスの開始時に静的に読み込まれる必要があります。 Windows ランタイムでは、スレッド ローカル ストレージはサポートされません。  
  
 次の例では、C2384 を生成し、C++/CLI コードで修正する方法を示しています。  
  
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