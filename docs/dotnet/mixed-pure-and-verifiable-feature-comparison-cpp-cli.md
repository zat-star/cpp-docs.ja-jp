---
title: "混合、純粋、および確認可能の各機能の比較 (C++/CLI) | Microsoft Docs"
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
  - "混在アセンブリ [C++]"
  - "混在アセンブリ [C++], 比較 (純粋との)"
  - "混在アセンブリ [C++], 比較 (安全との)"
  - "純粋なアセンブリ [C++]"
  - "純粋 MSIL [C++]"
  - "純粋 MSIL [C++], 比較 (混合および安全との)"
  - "純粋 MSIL [C++], 比較 (混合との)"
  - "純粋 MSIL [C++], 比較 (安全との)"
  - "安全なアセンブリ [C++]"
  - "安全なアセンブリ [C++], 比較 (混合との)"
  - "安全なアセンブリ [C++], 比較 (純粋との)"
  - "検証可能なアセンブリ [C++]"
  - "検証可能なアセンブリ [C++], 比較 (混合との)"
  - "検証可能なアセンブリ [C++], 比較 (純粋との)"
ms.assetid: 3f7a82ba-0e69-4927-ba0c-fbc3160e4394
caps.latest.revision: 8
caps.handback.revision: 8
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# 混合、純粋、および確認可能の各機能の比較 (C++/CLI)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

このトピックでは、**\/clr** の各コンパイル モードの機能を比較します。  詳細については、「[\/clr \(共通言語ランタイムのコンパイル\)](../build/reference/clr-common-language-runtime-compilation.md)」を参照してください。  
  
## 機能の比較  
  
|機能|混合 \(\/clr\)|純粋 \(\/clr:pure\)|タイプ セーフ \(\/clr:safe\)|関連情報|  
|--------|------------------|-----------------------|----------------------------|----------|  
|CRT ライブラリ|サポートされている|サポートされている||[カテゴリ別ランタイム ルーチン](../c-runtime-library/run-time-routines-by-category.md)|  
|MFC\/ATL|サポートされている|||[MFC デスクトップ アプリケーション](../mfc/mfc-desktop-applications.md) &#124; [クラスの概要](../atl/atl-class-overview.md)|  
|アンマネージ関数|サポートされている|||[混在 \(ネイティブおよびマネージ\) アセンブリ](../Topic/Mixed%20\(Native%20and%20Managed\)%20Assemblies.md)|  
|アンマネージ データ|サポートされている|サポートされている||[純粋なコードと検証可能なコード](../dotnet/pure-and-verifiable-code-cpp-cli.md)|  
|アンマネージ関数から呼び出し可能|サポートされている|||[方法: \/clr:pure に移行する](../dotnet/how-to-migrate-to-clr-pure-cpp-cli.md)|  
|アンマネージ関数の呼び出しのサポート|サポートされている|C スタイルの関数のみ|P\/Invoke のみ|[C\+\+ Interop \(暗黙の PInvoke\) の使用](../dotnet/using-cpp-interop-implicit-pinvoke.md)|  
|リフレクションのサポート|DLL のみ|サポートされている|サポートされている|[リフレクション](../dotnet/reflection-cpp-cli.md)|  
  
## 参照  
 [純粋なコードと検証可能なコード](../dotnet/pure-and-verifiable-code-cpp-cli.md)