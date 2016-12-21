---
title: "ランタイム ライブラリの動作 | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "_DllMainCRTStartup"
  - "CRT_INIT"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "_CRT_INIT マクロ"
  - "_DllMainCRTStartup メソッド"
  - "DllMain 関数"
  - "DLL [C++], エントリ ポイント関数"
  - "DLL [C++], ランタイム ライブラリの動作"
  - "DLL [C++], 起動処理"
  - "プロセスのアタッチ [C++]"
  - "プロセスのデタッチ [C++]"
  - "実行時 [C++], DLL の起動処理"
ms.assetid: e06f24ab-6ca5-44ef-9857-aed0c6f049f2
caps.latest.revision: 8
caps.handback.revision: 8
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# ランタイム ライブラリの動作
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

C\/C\+\+ ランタイム ライブラリ コードは、DLL の起動処理を実行します。Windows 3.x でのように、別のモジュールとリンクする必要はありません。  C\/C\+\+ ランタイム ライブラリ コードには、**\_DllMainCRTStartup** という DLL エントリ ポイント関数が含まれています。  **\_DllMainCRTStartup** 関数は、**\_CRT\_INIT** の呼び出しなど、いくつかの役割を持っています。\_CRT\_INIT は、C\/C\+\+ ランタイム ライブラリを初期化し、非ローカルな静的変数に対して C\+\+ コンストラクターを起動します。  この関数がないと、ランタイム ライブラリは初期化されません。  **\_CRT\_INIT** は、静的にリンクされた CRT または CRT DLL Msvcr90.dll に対するリンクの両方について、ユーザーの DLL から利用できます。  
  
 \/ENTRY: リンカー オプションを使うとエントリ ポイント関数を指定できますが、そのエントリ ポイント関数では **\_DllMainCRTStartup** が行う全処理を繰り返す必要があるため、この方法は推奨できません。  Visual C\+\+ で DLL をビルドする場合、**\_DllMainCRTStartup** は自動的にリンクされるため、\/ENTRY: リンカー オプションを使ってエントリ ポイント関数を指定する必要はありません。  
  
 **\_DllMainCRTStartup** は、ランタイム ライブラリを初期化した後、`DllMain` という関数を呼び出します。  Visual C\+\+ はビルドする DLL の種類に応じた `DllMain` を必ずリンクするので、**\_DllMainCRTStartup** によるこの呼び出しは常に可能です。  DLL を初期化する必要がない場合、DLL のビルド時に必要な処理は特にありません。  DLL を初期化する必要がある場合、コードを追加する場所は、DLL の種類によって異なります。  詳細については、「[DLL の初期化](../build/initializing-a-dll.md)」を参照してください。  
  
 C\/C\+\+ ランタイム ライブラリ コードは、非ローカルの静的変数に対してコンストラクターとデストラクターを呼び出します。  たとえば、次に示す DLL ソース コードの `Equus` と `Sugar` は、Horses.h に定義されている `CHorse` クラスの 2 つの非ローカルな静的オブジェクトです。  ソース コードには、`CHorse` に対してコンストラクター関数やデストラクター関数を呼び出す関数はありません。これらのオブジェクトは、どの関数からみても外部にあるからです  このため、コンストラクターやデストラクターの呼び出しは、ランタイム コードから行う必要があります。  アプリケーションのランタイム ライブラリ コードもこれと同じ機能を果たします。  
  
```  
#include "horses.h"  
  
CHorse  Equus( ARABIAN, MALE );  
CHorse  Sugar( THOROUGHBRED, FEMALE );  
  
BOOL    WINAPI   DllMain (HANDLE hInst,   
                            ULONG ul_reason_for_call,  
                            LPVOID lpReserved)  
...  
```  
  
 新しいプロセスが DLL を使用しようとするたびに、オペレーティング システムは、DLL のデータを 1 部作成します。これを "プロセスのアタッチ" と呼びます。  DLL のランタイム ライブラリ コードは、必要に応じてグローバル オブジェクトに対してコンストラクターを呼び出し、次に該当するプロセスのアタッチに対して `DllMain` 関数を呼び出します。  この反対がプロセスのデタッチです。この場合、ランタイム ライブラリ コードは該当するプロセスのデタッチに対して `DllMain` を呼び出し、次に、`atexit` 関数やグローバル オブジェクト用のデストラクター、静的オブジェクト用のデストラクターなど、一連の終了関数を呼び出します。  プロセスのアタッチでのイベントの順序は、プロセスのデタッチの逆です。  
  
 ランタイム ライブラリ コードは、スレッドのアタッチからスレッドのデタッチまでの間にも呼び出されますが、この場合は初期化や終了処理は行いません。  
  
## 目的に合ったトピックをクリックしてください  
  
-   [DLL の初期化](../build/initializing-a-dll.md)  
  
## 参照  
 [Visual C\+\+ の DLL](../build/dlls-in-visual-cpp.md)