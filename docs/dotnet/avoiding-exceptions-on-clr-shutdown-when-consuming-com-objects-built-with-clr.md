---
title: "/clr で構築された COM オブジェクト使用時における CLR シャットダウンの例外の回避 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "/clr コンパイラ オプション [C++], CLR シャットダウンの例外"
  - "/clr コンパイラ オプション [C++], COM オブジェクト"
  - "CLR シャットダウンの例外 [C++]"
  - "相互運用 [C++], CLR シャットダウンの例外"
  - "相互運用性 [C++], CLR シャットダウンの例外"
  - "混在アセンブリ [C++], CLR シャットダウンの例外"
ms.assetid: 41249d83-4b51-4e46-866f-27f475f2498c
caps.latest.revision: 4
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 4
---
# /clr で構築された COM オブジェクト使用時における CLR シャットダウンの例外の回避
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

共通言語ランタイム \(CLR\) がシャットダウン モードになると、ネイティブ関数は CLR サービスへのアクセスが制限されます。  **\/clr** でコンパイルされた COM オブジェクトに対して Release を呼び出そうとすると、CLR はネイティブ コードに遷移し、次に、\(マネージ コードに定義されている\) IUnknown::Release 呼び出しを提供するためにマネージ コードに戻ります。  CLR はシャットダウン モードであるため、マネージ コードへのコールバックが回避されます。  
  
 これを解決するには、Release のメソッドから呼び出されたデストラクターにのみネイティブ コードが含まれていることを確認します。  
  
## 参照  
 [混在 \(ネイティブおよびマネージ\) アセンブリ](../Topic/Mixed%20\(Native%20and%20Managed\)%20Assemblies.md)