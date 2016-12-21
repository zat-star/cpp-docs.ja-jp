---
title: "CStringT によるメモリ管理 | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "CStringT"
  - "ATL::CStringT"
  - "ATL.CStringT"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CFixedStringT クラス, 記述"
  - "CString オブジェクト, メモリ管理"
  - "CStringT クラス, メモリ管理"
  - "IAtlStringMgr クラス, 使用"
  - "メモリ [C++], 使い方"
  - "文字列 [C++], カスタム メモリ管理"
  - "文字列 [C++], メモリ管理"
ms.assetid: 88b8342d-19b5-48c4-9cf6-e4c44cece21e
caps.latest.revision: 10
caps.handback.revision: 6
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# CStringT によるメモリ管理
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

クラス [CStringT](../atl-mfc-shared/reference/cstringt-class.md)、可変長文字列操作に使用されるテンプレート クラスです。  これらの文字列を保持するメモリは `CStringT`の各インスタンスに関連付けられた文字列マネージャー オブジェクトを介して割り当てと解放されます。  MFC および ATL `CString`は、`CStringA`と `CStringW`と呼ばれる異なる文字型の文字列を処理する `CStringT`の既定のインスタンス化を提供します。  これらの文字型は型 **TCHAR**、`char`と `wchar_t`、それぞれです。  これらの既定の文字列型はヒープ プロセス \(ATL\) または CRT ヒープからメモリを割り当てる文字列マネージャーを使用します \(MFC\)。  一般的なアプリケーションでは、このメモリ割り当ての設定で十分です。  ただし文字列にローカライズ的に使用する内で、コード \(またはマルチスレッド コード\) の既定のメモリ マネージャーが最上位に実行しない場合があります。  このトピックでは、タスク オブジェクト用に最適化されたアロケーターを作成する `CStringT`の既定のメモリ管理の動作をオーバーライドする方法について説明します。  
  
-   [カスタム文字列マネージャー \(基本メソッド\) の実装](../atl-mfc-shared/implementation-of-a-custom-string-manager-basic-method.md)  
  
-   [ヒープの競合の回避](../atl-mfc-shared/avoidance-of-heap-contention.md)  
  
-   [カスタム文字列マネージャー \(高度なメソッド\) の実装](../Topic/Implementation%20of%20a%20Custom%20String%20Manager%20\(Advanced%20Method\).md)  
  
-   [CFixedStringT: カスタム文字列マネージャーの例](../atl-mfc-shared/cfixedstringt-example-of-a-custom-string-manager.md)  
  
## 参照  
 [CustomString サンプル](../top/visual-cpp-samples.md)