---
title: "方法: C# lock キーワードを実装する (C++/CLI) | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "get-started-article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "lock C# キーワード [C++]"
  - "lock ステートメント"
ms.assetid: 436fe544-ffb7-49b9-9798-90794e9974de
caps.latest.revision: 12
caps.handback.revision: 12
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# 方法: C# lock キーワードを実装する (C++/CLI)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

このトピックでは、Visual C\+\+ で C\# `lock` キーワードを実装する方法について説明します。  詳細については、「[lock ステートメント](../Topic/lock%20Statement%20\(C%23%20Reference\).md)」を参照してください。  
  
 C\+\+ サポート ライブラリ内の `lock` クラスも使用できます。  詳細については、「[同期 \(lock クラス\)](../dotnet/synchronization-lock-class.md)」を参照してください。  
  
## 使用例  
  
```  
// CS_lock_in_CPP.cpp  
// compile with: /clr  
using namespace System::Threading;  
ref class Lock {  
   Object^ m_pObject;  
public:  
   Lock( Object ^ pObject ) : m_pObject( pObject ) {  
      Monitor::Enter( m_pObject );  
   }  
   ~Lock() {  
      Monitor::Exit( m_pObject );  
   }  
};  
  
ref struct LockHelper {  
   void DoSomething();  
};  
  
void LockHelper::DoSomething() {  
   // Note: Reference type with stack allocation semantics to provide   
   // deterministic finalization  
  
   Lock lock( this );     
   // LockHelper instance is locked  
}  
  
int main()  
{  
   LockHelper lockHelper;  
   lockHelper.DoSomething();  
   return 0;  
}  
```  
  
## 参照  
 [他の .NET 言語との相互運用性](../dotnet/interoperability-with-other-dotnet-languages-cpp-cli.md)