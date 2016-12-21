---
title: "言語固有のハンドラー | Microsoft Docs"
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
ms.assetid: 6503e0cd-2d3a-4330-a925-8bed8c27c2be
caps.latest.revision: 9
caps.handback.revision: 9
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# 言語固有のハンドラー
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

言語固有のハンドラーの相対アドレスは、フラグ UNW\_FLAG\_EHANDLER またはフラグ UNW\_FLAG\_UHANDLER が設定される場合は常に UNWIND\_INFO にあります。  前のセクションで説明したとおり、言語固有のハンドラーは、例外ハンドラーの検索の一部またはアンワインドの一部として呼び出されます。  このハンドラーは、次のプロトタイプを持ちます。  
  
```  
typedef EXCEPTION_DISPOSITION (*PEXCEPTION_ROUTINE) (  
    IN PEXCEPTION_RECORD ExceptionRecord,  
    IN ULONG64 EstablisherFrame,  
    IN OUT PCONTEXT ContextRecord,  
    IN OUT PDISPATCHER_CONTEXT DispatcherContext  
);  
```  
  
 **ExceptionRecord** は、例外レコードへのポインターを提供します。例外レコードは標準 Wind64 定義を持ちます。  
  
 **EstablisherFrame** は、この関数の固定スタック割り当ての基底アドレスです。  
  
 **ContextRecord** は、例外が発生したときの例外コンテキスト \(例外ハンドラーの場合\)、または現在の "アンワインド" コンテキスト \(終了ハンドラーの場合\) をポイントします。  
  
 **DispatcherContext** は、この関数のディスパチャ コンテキストをポイントします。  次の定義を持ちます。  
  
```  
typedef struct _DISPATCHER_CONTEXT {  
    ULONG64 ControlPc;  
    ULONG64 ImageBase;  
    PRUNTIME_FUNCTION FunctionEntry;  
    ULONG64 EstablisherFrame;  
    ULONG64 TargetIp;  
    PCONTEXT ContextRecord;  
    PEXCEPTION_ROUTINE LanguageHandler;  
    PVOID HandlerData;  
} DISPATCHER_CONTEXT, *PDISPATCHER_CONTEXT;  
```  
  
 **ControlPc** は、この関数内の RIP 値です。  これは、例外アドレス、またはコントロールが構築関数をそのまま残したアドレスのいずれかになります。  これは、コントロールが、この関数内の保護された構成要素 \(\_\_try\/\_\_except または \_\_try\/\_\_finally の \_\_try ブロックなど\) の内側にあるかどうかを判断するのに使用する RIP です。  
  
 **ImageBase** は、この関数を含むモジュールのイメージ ベース \(ロード アドレス\) で、相対アドレスを記録するために関数エントリおよびアンワインド情報内で使用される 32 ビット オフセットに追加されます。  
  
 **FunctionEntry** は、RUNTIME\_FUNCTION 関数とそのアンワインド情報のイメージ ベース相対アドレスを保持する、RUNTIME\_FUNCTION 関数エントリへのポインターを提供します。  
  
 **EstablisherFrame** は、この関数の固定スタック割り当ての基底アドレスです。  
  
 **TargetIp** は、アンワインドの連結アドレスを指定するオプションの命令アドレスを提供します。  **EstablisherFrame** が指定されない場合、このアドレスは無視されます。  
  
 **ContextRecord** は、システム例外ディスパッチまたはアンワインド コードで使用するための例外コンテキストをポイントします。  
  
 **LanguageHandler** は、呼び出される言語固有の言語ハンドラー ルーチンをポイントします。  
  
 **HandlerData** は、この関数の言語固有のハンドラー データをポイントします。  
  
## 参照  
 [例外処理 \(x64\)](../build/exception-handling-x64.md)