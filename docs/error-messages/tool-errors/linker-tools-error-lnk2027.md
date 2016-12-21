---
title: "リンカ ツール エラー LNK2027 | Microsoft Docs"
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
  - "LNK2027"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "LNK2027"
ms.assetid: e2f857a8-8e8a-4697-bbff-12ccb84a35c1
caps.latest.revision: 6
caps.handback.revision: 6
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# リンカ ツール エラー LNK2027
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

未解決のモジュール参照 'モジュール'  
  
 リンカーに渡されたファイルは、モジュールに依存していますが、そのモジュールは、**\/ASSEMBLYMODULE** で指定されておらず、またリンカーに直接渡されてもいません。  
  
 LNK2027 エラーを解決するには、以下のいずれかの操作を実行します。  
  
-   モジュールに依存するファイルをリンカーに渡さないようにします。  
  
-   モジュールを **\/ASSEMBLYMODULE** で指定します。  
  
-   モジュールが安全"、リンカーにモジュールを直接渡します。  
  
 詳細については、「[\/ASSEMBLYMODULE \(MSIL モジュールのアセンブリへの追加\)](../../build/reference/assemblymodule-add-a-msil-module-to-the-assembly.md)」および「[リンカー入力としての .netmodule ファイル](../Topic/.netmodule%20Files%20as%20Linker%20Input.md)」を参照してください。