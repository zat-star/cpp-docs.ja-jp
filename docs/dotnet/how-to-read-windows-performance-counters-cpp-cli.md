---
title: "方法: Windows パフォーマンス カウンターを読み取る (C++/CLI) | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "カウンター, 読み取り (Windows パフォーマンス カウンターを)"
  - "パフォーマンス"
  - "パフォーマンス カウンター"
  - "パフォーマンス カウンター, 読み取り (Windows パフォーマンス カウンターを)"
  - "パフォーマンス モニター"
  - "パフォーマンス モニター, Windows パフォーマンス カウンター"
  - "パフォーマンス, カウンター"
ms.assetid: 9e1c836c-cb0f-4f37-9a93-3dca6412d6b1
caps.latest.revision: 12
caps.handback.revision: 12
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# 方法: Windows パフォーマンス カウンターを読み取る (C++/CLI)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

一部のアプリケーションおよび Windows サブシステムでは、Windows パフォーマンス システムを使用してパフォーマンス データが公開されます。  これらのカウンターにアクセスするには、<xref:System.Diagnostics.PerformanceCounterCategory> クラスと <xref:System.Diagnostics.PerformanceCounter> クラスを使用します。これらのクラスは、<xref:System.Diagnostics?displayProperty=fullName> 名前空間に存在します。  
  
 これらのクラスを使用して、Windows によって更新されるカウンターを取得して表示し、プロセッサのビジー時間率を示す方法を次のコード例に示します。  
  
> [!NOTE]
>  この例を Windows Vista で実行するには管理特権が必要です。  
  
## 使用例  
  
```  
// processor_timer.cpp  
// compile with: /clr  
#using <system.dll>  
  
using namespace System;  
using namespace System::Threading;  
using namespace System::Diagnostics;  
using namespace System::Timers;  
  
ref struct TimerObject  
{  
public:  
   static String^ m_instanceName;  
   static PerformanceCounter^ m_theCounter;  
  
public:  
   static void OnTimer(Object^ source, ElapsedEventArgs^ e)  
   {  
      try   
      {  
         Console::WriteLine("CPU time used: {0,6} ",  
          m_theCounter->NextValue( ).ToString("f"));  
      }   
      catch(Exception^ e)  
      {  
         if (dynamic_cast<InvalidOperationException^>(e))  
         {  
            Console::WriteLine("Instance '{0}' does not exist",  
                  m_instanceName);  
            return;  
         }  
         else  
         {  
            Console::WriteLine("Unknown exception... ('q' to quit)");  
            return;  
         }  
      }  
   }  
};  
  
int main()  
{  
   String^ objectName = "Processor";  
   String^ counterName = "% Processor Time";  
   String^ instanceName = "_Total";  
  
   try  
   {  
      if ( !PerformanceCounterCategory::Exists(objectName) )  
      {  
         Console::WriteLine("Object {0} does not exist", objectName);  
         return -1;  
      }  
   }  
   catch (UnauthorizedAccessException ^ex)  
   {  
      Console::WriteLine("You are not authorized to access this information.");  
      Console::Write("If you are using Windows Vista, run the application with ");  
      Console::WriteLine("administrative privileges.");  
      Console::WriteLine(ex->Message);  
      return -1;  
   }  
  
   if ( !PerformanceCounterCategory::CounterExists(  
          counterName, objectName) )  
   {  
      Console::WriteLine("Counter {0} does not exist", counterName);  
      return -1;  
   }  
  
   TimerObject::m_instanceName = instanceName;  
   TimerObject::m_theCounter = gcnew PerformanceCounter(  
          objectName, counterName, instanceName);  
  
   System::Timers::Timer^ aTimer = gcnew System::Timers::Timer();  
   aTimer->Elapsed += gcnew ElapsedEventHandler(&TimerObject::OnTimer);  
   aTimer->Interval = 1000;  
   aTimer->Enabled = true;  
   aTimer->AutoReset = true;  
  
   Console::WriteLine("reporting CPU usage for the next 10 seconds");  
   Thread::Sleep(10000);  
   return 0;  
}  
```  
  
## 参照  
 [Introduction to Monitoring Performance](http://msdn.microsoft.com/ja-jp/d40f10b9-e2b7-4ec8-a9b3-706929e5bf35)   
 [Windows の操作](../dotnet/windows-operations-cpp-cli.md)   
 [C\+\+\/CLI による .NET プログラミング](../dotnet/dotnet-programming-with-cpp-cli-visual-cpp.md)