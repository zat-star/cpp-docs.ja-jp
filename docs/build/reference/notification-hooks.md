---
title: "通知フック | Microsoft Docs"
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
  - "遅延読み込み (DLL を), 通知フック"
ms.assetid: e9c291ed-2f2d-4319-a171-09800625256f
caps.latest.revision: 7
caps.handback.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# 通知フック
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

ヘルパー ルーチンで以下のアクションが行われる直前に、通知フックが呼び出されます。  
  
-   格納されているライブラリ ハンドルが読み込み済みかどうかを確認します。  
  
-   **LoadLibrary** を呼び出して、DLL を読み込みます。  
  
-   **GetProcAddress** を呼び出して、プロシージャのアドレスを取得します。  
  
-   遅延インポート読み込みサンクに制御を返します。  
  
 通知フックは、次のいずれかの方法で有効にします。  
  
-   通知を受け取る独自の関数を指すように初期化した、新しい定義のポインター **\_\_pfnDliNotifyHook2** を指定します。  
  
     または  
  
-   プログラムで遅延読み込みされる DLL が呼び出される前に、フック関数をポインター **\_\_pfnDliNotifyHook2** に設定します。  
  
 通知が **dliStartProcessing** である場合、フック関数では以下の値が返されます。  
  
 NULL  
 既定のヘルパーで DLL の読み込みが処理されます。  これは情報だけが目的の場合に便利です。  
  
 関数ポインター  
 既定の遅延読み込み処理がバイパスされます。  したがって、独自の読み込みハンドラーを使用できます。  
  
 通知が **dliNotePreLoadLibrary** である場合、フック関数では以下の値が返されます。  
  
-   0。情報通知だけが必要な場合に返されます。  
  
-   読み込まれた DLL の HMODULE。DLL 自体が読み込まれた場合に返されます。  
  
 通知が **dliNotePreGetProcAddress** である場合、フック関数では以下の値が返されます。  
  
-   0。情報通知だけが必要な場合に返されます。  
  
-   インポートされた関数のアドレス。フック関数でアドレス自体が取得される場合に返されます。  
  
 通知が **dliNoteEndProcessing** である場合は、フック関数の戻り値は無視されます。  
  
 このポインターを 0 以外に初期化すると、遅延読み込みヘルパーは、実行中に特定の通知ポイントで関数を呼び出します。  関数ポインターの定義は次のとおりです。  
  
```  
// The "notify hook" gets called for every call to the  
// delay load helper.  This allows a user to hook every call and  
// skip the delay load helper entirely.  
//  
// dliNotify == {  
//  dliStartProcessing |  
//  dliNotePreLoadLibrary  |  
//  dliNotePreGetProc |  
//  dliNoteEndProcessing}  
//  on this call.  
//  
ExternC  
PfnDliHook   __pfnDliNotifyHook2;  
  
// This is the failure hook, dliNotify = {dliFailLoadLib|dliFailGetProc}  
ExternC  
PfnDliHook   __pfnDliFailureHook2;  
```  
  
 通知によって、**DelayLoadInfo** 構造体と通知値がフック関数に渡されます。  このデータは、遅延読み込みヘルパー ルーチンが使用するデータと同じです。  通知値は、「[構造体と定数の定義](../../build/reference/structure-and-constant-definitions.md)」で定義されている値の 1 つです。  
  
## 参照  
 [エラー処理と通知](../../build/reference/error-handling-and-notification.md)