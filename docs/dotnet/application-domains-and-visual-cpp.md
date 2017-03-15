---
title: "アプリケーション ドメインと Visual C++ | Microsoft Docs"
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
  - "/clr コンパイラ オプション [C++], アプリケーション ドメイン"
  - "アプリケーション ドメイン [C++], C++"
  - "相互運用 [C++], アプリケーション ドメイン"
  - "相互運用性 [C++], アプリケーション ドメイン"
  - "混在アセンブリ [C++], アプリケーション ドメイン"
ms.assetid: 75a08efc-9b02-40ba-99b7-dcbd71010bbf
caps.latest.revision: 7
caps.handback.revision: 7
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# アプリケーション ドメインと Visual C++
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

`__clrcall` 仮想関数がある場合、vtable はアプリケーション ドメイン \(appdomain\) に準拠します。  1 つの appdomain でオブジェクトを作成する場合、その appdomain 内から仮想関数を呼び出すだけです。  **\/clr:pure** コンパイル単位で定義されるすべての関数で `__clrcall` 呼び出し規約が使用されます。  そのため、**\/clr:pure** コンパイル単位で定義されるすべての vtable が appdomain に準拠します。  混合モード \(**\/clr**\) では、型に `__clrcall` 仮想関数が存在しない場合はプロセス単位で vtable が存在します。  
  
 詳細については、次のトピックを参照してください  
  
-   [appdomain](../Topic/appdomain.md)  
  
-   [\_\_clrcall](../cpp/clrcall.md)  
  
-   [方法: \/clr:pure に移行する](../dotnet/how-to-migrate-to-clr-pure-cpp-cli.md)  
  
-   [プロセス](../cpp/process.md)  
  
## 参照  
 [混在 \(ネイティブおよびマネージ\) アセンブリ](../Topic/Mixed%20\(Native%20and%20Managed\)%20Assemblies.md)