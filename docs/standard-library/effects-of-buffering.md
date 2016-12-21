---
title: "バッファリングの効果 | Microsoft Docs"
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
  - "バッファー、バッファリングの効果"
  - "バッファリング、効果"
ms.assetid: 5d544812-e95e-4f28-b15a-edef3f3414fd
caps.latest.revision: 9
caps.handback.revision: 8
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# バッファリングの効果
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

次に、バッファリングの効果を示す例を示します。`please wait` を出力して 5 秒待ってから先に進むプログラムを想定することができますが、 必ずしもそのとおりに動作するとは限りません。これは、出力がバッファリングされるためです。  
  
```  
// effects_buffering.cpp // compile with: /EHsc #include <iostream> #include <time.h> using namespace std; int main( ) { time_t tm = time( NULL ) + 5; cout << "Please wait..."; while ( time( NULL ) < tm ) ; cout << "\nAll done" << endl; }  
```  
  
 プログラムを論理的に動作させるには、メッセージが表示されたときに `cout` オブジェクトがそれ自体を空にする必要があります。`ostream` オブジェクトをフラッシュするには、それを `flush` マニピュレーターに送信します。  
  
```  
cout << "Please wait..." << flush;  
```  
  
 この手順ではバッファーがフラッシュされるため、必ず待機の前にメッセージが出力されます。 バッファーをフラッシュして復帰と改行を出力する `endl` マニピュレーターを使用することも、`cin` オブジェクトを使用することもできます。 通常、このオブジェクト \(および `cerr` または `clog` オブジェクト\) は `cout` オブジェクトに関連付けられています。 そのため、`cin` \(あるいは `cerr` または `clog` オブジェクト\) を使用すると、`cout` オブジェクトがフラッシュされます。  
  
## 参照  
 [出力ストリーム](../standard-library/output-streams.md)