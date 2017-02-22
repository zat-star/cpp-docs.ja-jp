---
title: "OpenMP Libraries | Microsoft Docs"
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
ms.assetid: f89abf97-67e3-4327-bc30-43f85b9533a2
caps.latest.revision: 9
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 9
---
# OpenMP Libraries
[!INCLUDE[vs2017banner](../../../assembler/inline/includes/vs2017banner.md)]

OpenMP の Visual C\+\+ ランタイム ライブラリを構成する .lib ファイルについて説明します。  
  
 次のライブラリはVisual C\+\+ OpenMP のランタイム ライブラリ関数が含まれています。  
  
|OpenMP ランタイム ライブラリ|特性|  
|------------------------|--------|  
|VCOMP.LIB|マルチスレッド動的リンク \(VCOMP.LIB 用インポート ライブラリ\)。|  
|VCOMPD.LIB|マルチスレッド動的リンク \(\) VCOMPD.LID \(デバッグ\) のインポート ライブラリ|  
  
 \_DEBUG がコンパイルで定義されている場合`#include omp.h` がソース・コードにある場合VCOMPD.LIB は既定のライブラリです。  それ以外 VCOMP.LIB が使用されます。  
  
 既定のライブラリを除外し明示的に選択ライブラリとリンクする [\/NODEFAULTLIB \(ライブラリを無視する\)](../../../build/reference/nodefaultlib-ignore-libraries.md) を使用できます。  
  
 OpenMP DLL はVisual C\+\+ 再頒布可能パッケージのディレクトリにありOpenMP を使用するアプリケーションとともに配布する必要があります。  
  
## 参照  
 [Library Reference](../../../parallel/openmp/reference/openmp-library-reference.md)