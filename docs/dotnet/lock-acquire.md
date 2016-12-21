---
title: "lock::acquire | Microsoft Docs"
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
  - "lock::acquire"
  - "acquire"
  - "msclr.lock.acquire"
  - "msclr::lock::acquire"
  - "lock.acquire"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "acquire メソッド"
ms.assetid: c214274e-7519-4739-82aa-91b04a32d3f9
caps.latest.revision: 14
caps.handback.revision: 12
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# lock::acquire
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

ロックを、または、ロックを、指定した時間だけに完全に取得するには、オプションで待機するオブジェクトを取得します。  
  
## 構文  
  
```  
void acquire();  
void acquire(  
   int _timeout  
);  
void acquire(  
   System::TimeSpan _timeout  
);  
```  
  
#### パラメーター  
 `_timeout`  
 ミリ秒のまたは <xref:System.TimeSpan>にタイムアウト値。  
  
## 例外  
 ロックの取得がタイムアウトの前に発生する <xref:System.ApplicationException> をスローします。  
  
## 解説  
 タイムアウト値を指定しない場合は、既定のタイムアウトは、<xref:System.Threading.Timeout.Infinite>です。  
  
 ロックが既に得られたら、この関数は何も行いません。  
  
## 使用例  
 この例は、複数のスレッド間でクラスの単一のインスタンスを使用します。クラスは、データへのアクセスが各スレッドに対して一貫していることを確認するために、独自のロックを使用します。メイン アプリケーション スレッドは、ワーカー スレッドがまだ、すべてのワーカー スレッド終了まで待機が完了したタスクを定期的に確認するために、クラス インスタンスの同じロックを使用します。  
  
```  
// msl_lock_acquire.cpp  
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
 [lock のメンバー](../dotnet/lock-members.md)   
 [lock::try\_acquire](../Topic/lock::try_acquire.md)