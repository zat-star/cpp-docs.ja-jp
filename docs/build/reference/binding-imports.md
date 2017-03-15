---
title: "インポートのバインド | Microsoft Docs"
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
  - "/DELAY:NOBIND リンカー オプション"
  - "DELAY:NOBIND リンカー オプション"
ms.assetid: bb766038-deb1-41b1-bcbc-29a30e8c1e2a
caps.latest.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 7
---
# インポートのバインド
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

リンカーの既定の動作では、遅延読み込み DLL に対してバインド可能なインポート アドレス テーブル \(IAT: Import Address Table\) が作成されます。  DLL をバインドすると、ヘルパー関数は、参照先の各インポートに対して **GetProcAddress** を呼び出さずに、バインドされた情報を使用します。  タイムスタンプまたは設定アドレスが、読み込まれた DLL と一致しない場合、ヘルパー関数はバインドされた IAT が最新でないと見なし、バインドされた IAT がないものとして処理を続けます。  
  
 DLL の遅延読み込みされたインポートをバインドしない場合は、リンカーのコマンド ラインで [\/delay](../../build/reference/delay-delay-load-import-settings.md):nobind を指定すると、バインドされた IAT が生成されず、イメージ ファイルの容量が消費されることもありません。  
  
## 参照  
 [リンカーによる DLL の遅延読み込み](../../build/reference/linker-support-for-delay-loaded-dlls.md)