---
title: "__hook | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
f1_keywords: 
  - "__hook_cpp"
  - "__hook"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "__hook キーワード [C++]"
  - "イベント ハンドラー, 接続 (イベントを)"
ms.assetid: f4cabb10-d293-4c0e-a1d2-4745ef9cc22c
caps.latest.revision: 10
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 10
---
# __hook
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

ハンドラー メソッドをイベントに関連付けます。  
  
## 構文  
  
```  
  
      long __hook(  
   &SourceClass::EventMethod,  
   source,  
   &ReceiverClass::HandlerMethod  
   [, receiver = this]  
);  
long __hook(  
   interface,  
   source  
);  
```  
  
#### パラメーター  
 **&** *SourceClass* `::` *EventMethod*  
 イベント ハンドラー メソッドをフックする先のイベント メソッドへのポインター。  
  
-   ネイティブ C\+\+ イベント: *SourceClass* はイベント ソース クラスであり、*EventMethod* はイベントです。  
  
-   COM イベント: *SourceClass* はイベント ソース インターフェイスであり、*EventMethod* はメソッドの 1 つです。  
  
-   マネージ イベント: *SourceClass* はイベント ソース クラスであり、*EventMethod* はイベントです。  
  
 `interface`  
 [event\_receiver](../windows/event-receiver.md) 属性の *layout\_dependent* パラメーターが **true** である COM イベント レシーバーのみに対して、`receiver` にフックされているインターフェイス名。  
  
 *source*  
 イベント ソースのインスタンスへのポインター。  **event\_receiver** に指定された `type` コードに応じて、*source* は次のいずれかになります。  
  
-   ネイティブ イベント ソース オブジェクト ポインター。  
  
-   **IUnknown** のベースの COM ポインター \(COM ソース\)。  
  
-   マネージ オブジェクトのポインター \(マネージ イベントの場合\)。  
  
 **&** *ReceiverClass* `::` `HandlerMethod`  
 イベントにフックするイベント ハンドラー メソッドへのポインター。  ハンドラーは、クラスのメソッドまたはそれへの参照として指定されます。ユーザーがクラス名を指定しない場合、`__hook` は、それを呼び出したクラスを使用します。  
  
-   ネイティブ C\+\+ イベント: *ReceiverClass* はイベント レシーバー クラスであり、`HandlerMethod` はハンドラーです。  
  
-   COM イベント: *ReceiverClass* はイベント レシーバー インターフェイスであり、`HandlerMethod` はハンドラーの 1 つです。  
  
-   マネージ イベント: *ReceiverClass* はイベント レシーバー クラスであり、`HandlerMethod` はハンドラーです。  
  
 `receiver` \(省略可能\)  
 イベント レシーバー クラスのインスタンスへのポインター。  レシーバーを指定しない場合、既定値は `__hook` が呼び出されるレシーバー クラスまたは構造体です。  
  
## 使用法  
 イベント レシーバー クラス外の main を含む、任意の関数スコープで使用できます。  
  
## 解説  
 ハンドラー メソッドをイベント メソッドに関連付けるかフックするには、イベント レシーバー内で組み込み関数 `__hook` を使用します。  ソースで指定されたイベントが発生すると、指定されたハンドラーが呼び出されます。  複数のイベント ハンドラーを 1 つのイベントに、または複数のイベントを 1 つのイベント ハンドラーにフックすることができます。  
  
 `__hook` には 2 つの形式があります。  ほとんどの場合、最初 \(引数が 4 つ\) の形式を使用できます。特に、[event\_receiver](../windows/event-receiver.md) 属性の *layout\_dependent* パラメーターが **false** である COM のイベント レシーバーの場合が該当します。  
  
 このような場合、メソッドの 1 つでイベントを発生させる前に、インターフェイスのすべてのメソッドをフックする必要はありません。イベントを処理するメソッドのみフックする必要があります。  `__hook` の 2 番目 \(引数が 2 つ\) の形式は、*layout\_dependent***\=true** となる COM イベント レシーバーにのみ使用できます。  
  
 `__hook` は long 型の値を返します。  ゼロ以外の戻り値は、エラーが発生したことを示します \(マネージ イベントは例外をスローします\)。  
  
 コンパイラは、イベントが存在するかどうかをチェックし、イベント プロシージャがデリゲート シグネチャと一致することを確認します。  
  
 COM イベントを除き、`__hook` と `__unhook` は、イベント レシーバーの外部で呼び出すことができます。  
  
 `__hook` の使用の代替手段は、\+\= 演算子を使用することです。  
  
 新しい構文でのマネージ イベントのコーディングの詳細については、「[event](../windows/event-cpp-component-extensions.md)」を参照してください。  
  
> [!NOTE]
>  テンプレート クラスまたは構造体にイベントを含めることはできません。  
  
## 使用例  
 使用例については、「[ネイティブ C\+\+ でのイベント処理](../Topic/Event%20Handling%20in%20Native%20C++.md)」および「[COM でのイベント処理](../cpp/event-handling-in-com.md)」を参照してください。  
  
## 参照  
 [C\+\+ キーワード](../cpp/keywords-cpp.md)   
 [イベント処理](../cpp/event-handling.md)   
 [event\_source](../windows/event-source.md)   
 [event\_receiver](../windows/event-receiver.md)   
 [\_\_unhook](../cpp/unhook.md)   
 [\_\_raise](../cpp/raise.md)