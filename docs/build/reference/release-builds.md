---
title: "リリース ビルド | Microsoft Docs"
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
  - "デバッグ ビルド, 変換 (リリース ビルドへ)"
  - "デバッグ [C++], リリース ビルド"
  - "リリース ビルド"
ms.assetid: fa9a78fa-f4b5-4722-baf4-aec655c4ff0f
caps.latest.revision: 7
caps.handback.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# リリース ビルド
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

リリース ビルドでは最適化が使用されます。  リリース ビルドの作成時に最適化を使用すると、シンボリック デバッグ情報が生成されません。  シンボリック デバッグ情報がなく、TRACE および ASSERT 呼び出しのコードが生成されないため、実行可能ファイルのサイズが小さくなり、実行速度が向上します。  
  
 ここでは、デバッグ ビルドからリリース ビルドに移行する理由と時期について説明します。  また、デバッグ ビルドからリリース ビルドに移行するときに発生する可能性のある問題についても説明します。  
  
-   [リリース ビルドの作成](../../build/reference/how-to-create-a-release-build.md)  
  
-   [リリース ビルド作成時によくある問題](../../build/reference/common-problems-when-creating-a-release-build.md)  
  
-   [リリース ビルドの問題の解決](../../build/reference/fixing-release-build-problems.md)  
  
    -   [ASSERT ステートメントの確認](../../build/reference/using-verify-instead-of-assert.md)  
  
    -   [デバッグ ビルドを使用したメモリ上書きのチェック](../Topic/Using%20the%20Debug%20Build%20to%20Check%20for%20Memory%20Overwrite.md)  
  
    -   [リリース ビルドのデバッグ](../../build/reference/how-to-debug-a-release-build.md)  
  
    -   [メモリ上書きのチェック](../../build/reference/checking-for-memory-overwrites.md)  
  
## 参照  
 [Visual Studio での C\+\+ プロジェクトのビルド](../../ide/building-cpp-projects-in-visual-studio.md)   
 [C\/C\+\+ ビルドのリファレンス](../Topic/C-C++%20Building%20Reference.md)