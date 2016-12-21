---
title: "リソース コンパイラ エラー RW2001 | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "RW2001"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "RW2001"
ms.assetid: 963bdc7d-6ebe-4378-8bbc-47dfcf5d330c
caps.latest.revision: 6
caps.handback.revision: 6
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# リソース コンパイラ エラー RW2001
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Invalid directive in preprocessed RC file  
  
 RC ファイル内に **\#pragma** ディレクティブがあります。  
  
 インクルード ファイル内で、定数 **RC\_INVOKED** を指定したプリプロセス ディレクティブ **\#ifndef** を使用します。定数 **RC\_INVOKED** は、リソース コンパイラがインクルード ファイルを処理するときに定義される定数です。  **RC\_INVOKED** 定数が定義されているときには処理されないブロック内に、**\#pragma** ディレクティブを配置します。  このブロック内のコードは C\/C\+\+ のコンパイラで処理され、リソース コンパイラでは処理されません。  この手法を使用したコードの例を次に示します。  
  
```  
#ifndef RC_INVOKED  
#pragma pack(2)  // C/C++ only, ignored by Resource Compiler  
#endif  
```  
  
 プリプロセッサ ディレクティブ **\#pragma** は、.RC ファイルでは意味を持ちません。  プリプロセッサ ディレクティブ **\#include** は、ヘッダー ファイル \(プロジェクトごとのカスタム ヘッダー ファイルや Microsoft が製品と共に提供する標準のヘッダー ファイル\) をインクルードするために .RC ファイル内で頻繁に使用されます。  これらのインクルード ファイルの中には、**\#pragma** ディレクティブを使用しているものもあります。  ヘッダー ファイルは 1 つ以上のほかのヘッダー ファイルをインクルードする可能性があるため、エラーの原因となった **\#pragma** ディレクティブが入っているファイルをすぐに見つけられない場合があります。  
  
 **\#ifndef RC\_INVOKED** を使用する手法では、プロジェクトごとのヘッダー ファイルでのヘッダー ファイルのインクルードを制御することもできます。