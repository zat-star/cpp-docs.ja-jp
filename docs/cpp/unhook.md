---
title: "__unhook | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
f1_keywords: 
  - "__unhook"
  - "__unhook_cpp"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "__unhook キーワード [C++]"
  - "イベント ハンドラー, 関連付けの解除 (イベント)"
ms.assetid: 953a14f3-5199-459d-81e5-fcf015a19878
caps.latest.revision: 9
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 9
---
# __unhook
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

イベントからハンドラー メソッドの関連付けを解除します。  
  
## 構文  
  
```  
  
      long  __unhook(  
   &SourceClass::EventMethod,  
   source,  
   &ReceiverClass::HandlerMethod  
   [, receiver = this]   
);  
long  __unhook(   
   interface,  
   source  
);  
long  __unhook(  
   source   
);  
```  
  
#### パラメーター  
 **&** *SourceClass* `::` *EventMethod*  
 イベント ハンドラー メソッドをアンフックする元のイベント メソッドへのポインター。  
  
-   ネイティブ C\+\+ イベント: *SourceClass* はイベント ソース クラスであり、*EventMethod* はイベントです。  
  
-   COM イベント: *SourceClass* はイベント ソース インターフェイスであり、*EventMethod* はメソッドの 1 つです。  
  
-   マネージ イベント: *SourceClass* はイベント ソース クラスであり、*EventMethod* はイベントです。  
  
 `interface`  
 [event\_receiver](../windows/event-receiver.md) 属性の *layout\_dependent* パラメーターが **true** である COM イベント レシーバーのみに対して、`receiver` からアンフックされるインターフェイス名。  
  
 *source*  
 イベント ソースのインスタンスへのポインター。  **event\_receiver** に指定された `type` コードに応じて、*source* は次のいずれかになります。  
  
-   ネイティブ イベント ソース オブジェクト ポインター。  
  
-   **IUnknown** のベースの COM ポインター \(COM ソース\)。  
  
-   マネージ オブジェクトのポインター \(マネージ イベントの場合\)。  
  
 **&** *ReceiverClass* `::` `HandlerMethod`  
 イベントからアンフックするイベント ハンドラー メソッドへのポインター。  ハンドラーは、クラスのメソッドまたはそれへの参照として指定されます。ユーザーがクラス名を指定しない場合、`__unhook` は、それを呼び出したクラスを使用します。  
  
-   ネイティブ C\+\+ イベント: *ReceiverClass* はイベント レシーバー クラスであり、`HandlerMethod` はハンドラーです。  
  
-   COM イベント: *ReceiverClass* はイベント レシーバー インターフェイスであり、`HandlerMethod` はハンドラーの 1 つです。  
  
-   マネージ イベント: *ReceiverClass* はイベント レシーバー クラスであり、`HandlerMethod` はハンドラーです。  
  
 `receiver` \(省略可能\)  
 イベント レシーバー クラスのインスタンスへのポインター。  レシーバーを指定しない場合、既定値は `__unhook` が呼び出されるレシーバー クラスまたは構造体です。  
  
## 使用法  
 イベント レシーバー クラス外の main を含む、任意の関数スコープで使用できます。  
  
## 解説  
 ハンドラー メソッドとイベント メソッドとの関連付けを解除、つまり "アンフック" するには、イベント レシーバー内で組み込み関数 `__unhook` を使用します。  
  
 `__unhook` には 3 つの形式があります。  ほとんどの場合、最初の形式 \(引数が 4 つ\) を使用できます。  `__unhook` の 2 番目 \(引数が 2 つ\) の形式は、COM イベント レシーバーにのみ使用でき、イベント インターフェイス全体がアンフックされます。  3 番目 \(引数が 1 つ\) の形式は、指定したソースからすべてのデリゲートをアンフックする場合に使用します。  
  
 ゼロ以外の戻り値は、エラーが発生したことを示します \(マネージ イベントは例外をスローします\)。  
  
 フックされていないイベントやイベント ハンドラーに対して `__unhook` を呼び出した場合、効果はありません。  
  
 コンパイル時に、コンパイラはイベントが存在することを確認し、指定されたハンドラーを使用してパラメーターの型チェックを実行します。  
  
 COM イベントを除き、`__hook` と `__unhook` は、イベント レシーバーの外部で呼び出すことができます。  
  
 `__unhook` の使用の代替手段は、\-\= 演算子を使用することです。  
  
 新しい構文でのマネージ イベントのコーディングの詳細については、「[event](../windows/event-cpp-component-extensions.md)」を参照してください。  
  
> [!NOTE]
>  テンプレート クラスまたは構造体にイベントを含めることはできません。  
  
## 使用例  
 使用例については、「[ネイティブ C\+\+ でのイベント処理](../Topic/Event%20Handling%20in%20Native%20C++.md)」および「[COM でのイベント処理](../cpp/event-handling-in-com.md)」を参照してください。  
  
## 参照  
 [C\+\+ キーワード](../cpp/keywords-cpp.md)   
 [event\_source](../windows/event-source.md)   
 [event\_receiver](../windows/event-receiver.md)   
 [\_\_event](../cpp/event.md)   
 [\_\_hook](../cpp/hook.md)   
 [\_\_raise](../cpp/raise.md)