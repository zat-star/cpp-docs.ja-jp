---
title: "C/C++ 分離アプリケーションおよび side-by-side アセンブリのビルド | Microsoft Docs"
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
  - "分離アプリケーション [C++]"
  - "WinSxS [C++]"
  - "ネイティブ アセンブリ キャッシュ [C++]"
  - "ビルド [C++], 分離アプリケーション"
  - "side-by-side 実行アプリケーション [C++]"
  - "ビルド [C++], side-by-side アセンブリ"
ms.assetid: 9465904e-76f7-48bd-bb3f-c55d8f1699b6
caps.latest.revision: 20
caps.handback.revision: 18
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# C/C++ 分離アプリケーションおよび side-by-side アセンブリのビルド
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Visual C\+\+ では、[分離アプリケーション](http://msdn.microsoft.com/library/aa375190)および [side\-by\-side アセンブリ](_win32_side_by_side_assemblies)という概念に基づく、Windows クライアント アプリケーションの配置モデルがサポートされます。 既定では、Visual C\+\+ では、すべてのネイティブ C\/C\+\+ アプリケーションは、[マニフェスト](http://msdn.microsoft.com/library/aa375365)を使用して Visual C\+\+ ライブラリへの依存関係を記述する分離アプリケーションとしてビルドされます。  
  
 C\/C\+\+ プログラムを分離アプリケーションとしてビルドすることには、さまざまな利点があります。 たとえば、分離アプリケーションは、他の C\/C\+\+ アプリケーションによって Visual C\+\+ ライブラリがインストールまたはアンインストールされる場合に影響を受けません。 分離アプリケーションで使用される Visual C\+\+ ライブラリは、アプリケーションのローカル フォルダーに、またはネイティブ アセンブリ キャッシュ \(WinSxS\) へのインストールによって、再配布される場合もあります。ただし、[発行者構成ファイル](http://msdn.microsoft.com/library/aa375680)を使用することによって、既に配置されているアプリケーションの Visual C\+\+ ライブラリのサービス提供を簡略化できます。 分離アプリケーションの配置モデルにより、特定のコンピューターで実行されている C\/C\+\+ アプリケーションで最新バージョンの Visual C\+\+ ライブラリが使用されるようにすることが簡単になります。一方で、アプリケーションが依存する DLL に対する明示的なバージョン バインディングは、引き続きシステム管理者およびアプリケーション作成者が制御できます。  
  
 このセクションでは、C\/C\+\+ アプリケーションを分離アプリケーションとしてビルドし、マニフェストを使用して Visual C\+\+ ライブラリにバインドされるようにする方法について説明します。 このセクションの情報は、主にネイティブ \(アンマネージ\) Visual C\+\+ アプリケーションに適用されます。 Visual C\+\+ でビルドされたネイティブ アプリケーションの配置の詳細については、「[Visual C\+\+ ファイルの再配布](../Topic/Redistributing%20Visual%20C++%20Files.md)」を参照してください。  
  
## このセクションの内容  
 [分離アプリケーションおよび side\-by\-side アセンブリの概念](../build/concepts-of-isolated-applications-and-side-by-side-assemblies.md)  
  
 [C\/C\+\+ 分離アプリケーションのビルド](../build/building-c-cpp-isolated-applications.md)  
  
 [C\/C\+\+ side\-by\-side アセンブリのビルド](../build/building-c-cpp-side-by-side-assemblies.md)  
  
 [方法 : 登録を必要としない COM をビルドする](../build/how-to-build-registration-free-com-components.md)  
  
 [方法 : COM コンポーネントを使用する分離アプリケーションをビルドする](../Topic/How%20to:%20Build%20Isolated%20Applications%20to%20Consume%20COM%20Components.md)  
  
 [C\/C\+\+ プログラムのマニフェスト生成についての理解](../Topic/Understanding%20Manifest%20Generation%20for%20C-C++%20Programs.md)  
  
 [トラブルシューティング](../build/troubleshooting-c-cpp-isolated-applications-and-side-by-side-assemblies.md)  
  
## 関連項目  
 [分離アプリケーションと side\-by\-side アセンブリ](http://msdn.microsoft.com/library/dd408052)  
  
 [デスクトップ アプリケーションの配置](../Topic/Deploying%20Native%20Desktop%20Applications%20\(Visual%20C++\).md)