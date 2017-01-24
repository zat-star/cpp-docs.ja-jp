---
title: "lock_when Enum | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "msclr::lock_when"
  - "msclr.lock_when"
  - "lock_when"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "lock_when 列挙型"
ms.assetid: 6b87bbe9-63cd-450d-a02e-bb91ffd0dcea
caps.latest.revision: 9
caps.handback.revision: 7
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# lock_when Enum
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Translate 無制限のロックを延期しました。  
  
## 構文  
  
```  
enum lock_when {  
   lock_later  
};  
```  
  
## 解説  
 [lock::lock](../dotnet/lock-lock.md)に渡されると、`lock_later` はロックで実行される必要があることを指定します。  
  
## 使用例  
 この例は、複数のスレッド間でクラスの単一のインスタンスを使用します。クラスは、データへのアクセスが各スレッドに対して一貫していることを確認するために、独自のロックを使用します。メイン アプリケーション スレッドは、ワーカー スレッドがまだ、すべてのワーカー スレッド終了まで待機が完了したタスクを定期的に確認するために、クラス インスタンスの同じロックを使用します。  
  
```  
// msl_lock_lock_when.cpp  
// compile with: /clr  
#include <msclr/lock.h>  
  
using namespace System;  
using namespace System::Threading;  
using namespace msclr;  
  
ref class CounterClass {  
private:  
   int Counter;     
  
public:  
   property int ThreadCount;  
  
   // function called by multiple threads, use lock to keep Counter consistent  
   // for each thread  
   void UseCounter() {  
      try {  
         lock l(this); // wait infinitely  
  
         Console::WriteLine("In thread {0}, Counter = {1}", Thread::CurrentThread->ManagedThreadId,   
            Counter);  
  
         for (int i = 0; i < 10; i++) {  
            Counter++;  
            Thread::Sleep(10);  
         }  
  
         Console::WriteLine("In thread {0}, Counter = {1}", Thread::CurrentThread->ManagedThreadId,   
            Counter);  
  
         Counter = 0;  
         // lock is automatically released when it goes out of scope and its destructor is called  
      }  
      catch (...) {  
         Console::WriteLine("Couldn't acquire lock!");  
      }  
  
      ThreadCount--;  
   }  
};  
  
int main() {  
   // create a few threads to contend for access to the shared data  
   CounterClass^ cc = gcnew CounterClass;  
   array<Thread^>^ tarr = gcnew array<Thread^>(5);  
   ThreadStart^ startDelegate = gcnew ThreadStart(cc, &CounterClass::UseCounter);  
   for (int i = 0; i < tarr->Length; i++) {  
      tarr[i] = gcnew Thread(startDelegate);  
      cc->ThreadCount++;  
      tarr[i]->Start();  
   }  
  
   // keep our main thread alive until all worker threads have completed  
   lock l(cc, lock_later); // don't lock now, just create the object  
   while (true) {  
      if (l.try_acquire(50)) { // try to acquire lock, don't throw an exception if can't  
         if (0 == cc->ThreadCount) {  
            Console::WriteLine("All threads completed.");  
            break; // all threads are gone, exit while  
         }  
         else {  
            Console::WriteLine("{0} threads exist, continue waiting...", cc->ThreadCount);  
            l.release(); // some threads exist, let them do their work  
         }  
      }  
   }  
}  
```  
  
  **スレッド 3 で、カウンター \= 0**  
**スレッド 3 で、カウンター \= 10**  
**スレッド 5 で、カウンター \= 0**  
**スレッド 5 で、カウンター \= 10**  
**スレッド 7 で、カウンター \= 0**  
**スレッド 7 で、カウンター \= 10**  
**スレッド 4 で、カウンター \= 0**  
**スレッド 4 で、カウンター \= 10**  
**スレッド 6 で、カウンター \= 0**  
**スレッド 6 で、カウンター \= 10**  
**完了しているすべてのスレッド。**   
## 必要条件  
 **ヘッダー ファイル** \<msclr\\lock.h\>  
  
 **名前空間** の msclr  
  
## 参照  
 [lock](../dotnet/lock.md)