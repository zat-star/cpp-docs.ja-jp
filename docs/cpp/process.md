---
title: "プロセス | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
f1_keywords: 
  - "Process"
  - "process_cpp"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "__declspec キーワード [C++], プロセス"
  - "process __declspec キーワード"
ms.assetid: 60eecc2f-4eef-4567-b9db-aaed34733023
caps.latest.revision: 16
caps.handback.revision: 16
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# プロセス
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

マネージ アプリケーション プロセスが、プロセス内のすべてのアプリケーション ドメイン間で共有される特定のグローバル変数、静的メンバー変数、または静的ローカル変数のコピーを 1 つ持つことを指定します。  **\/clr:pure** では、グローバル変数と静的変数が既定でアプリケーション ドメインごとになっているため、これは、主に、**\/clr:pure** を指定してコンパイルするときに使用するためのものです。  **\/clr** でコンパイルすると、グローバル変数と静的変数は既定でプロセスごとになります \(そのため、`__declspec(process)` を使用する必要はありません\)。  
  
 `__declspec(process)` でマークできるのは、グローバル変数、静的メンバー変数、またはネイティブ型の静的ローカル変数だけです。  
  
 **\/clr:pure** を指定してコンパイルする場合、プロセスごととしてマークされている変数は、`const` としても宣言する必要があります。  これにより、プロセスごとの変数は 1 つのアプリケーション ドメイン内で変更されなくなり、他のアプリケーション ドメインに予測できない結果を与えることもなくなります。  `__declspec(process)` の主な用途は、**\/clr:pure** でグローバル変数、静的メンバー変数、または静的ローカル変数のコンパイル時初期化を可能にすることです。  
  
 `process` は、[\/clr](../build/reference/clr-common-language-runtime-compilation.md) または **\/clr:pure** を指定してコンパイルする場合にのみ有効であり、**\/clr:safe** を指定してコンパイルする場合は無効になります。  
  
 各アプリケーション ドメインがグローバル変数の独自のコピーを持つようにするには、[appdomain](../Topic/appdomain.md) を使用します。  
  
 詳細については、「[アプリケーション ドメインと Visual C\+\+](../dotnet/application-domains-and-visual-cpp.md)」を参照してください。  
  
## 参照  
 [\_\_declspec](../cpp/declspec.md)   
 [C\+\+ キーワード](../cpp/keywords-cpp.md)