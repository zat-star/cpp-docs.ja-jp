---
title: "方法 : 登録を必要としない COM をビルドする | Microsoft Docs"
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
  - "COM コンポーネント, 登録を必要としない"
ms.assetid: 7e585d6a-0314-45b2-8f1b-cae9ac4df037
caps.latest.revision: 11
caps.handback.revision: 11
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# 方法 : 登録を必要としない COM をビルドする
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

登録を必要としない COM コンポーネントは、マニフェストが DLL に組み込まれた COM コンポーネントです。  
  
### マニフェストを COM コンポーネントに組み込むには  
  
1.  COM コンポーネントのプロジェクトのプロパティ ページを開きます。  
  
2.  **\[構成プロパティ\]** ノードを展開し、次に **\[マニフェスト ツール\]** ノードを展開します。  
  
3.  **\[入力と出力\]** プロパティ ページをクリックし、**\[埋め込みマニフェスト\]** プロパティを **\[はい\]** に設定します。  
  
4.  \[OK\] をクリックします。  
  
5.  ソリューションをビルドします。  
  
## 参照  
 [分離アプリケーション](http://msdn.microsoft.com/library/aa375190)   
 [side\-by\-side アセンブリ](_win32_side_by_side_assemblies)   
 [方法 : COM コンポーネントを使用する分離アプリケーションをビルドする](../Topic/How%20to:%20Build%20Isolated%20Applications%20to%20Consume%20COM%20Components.md)