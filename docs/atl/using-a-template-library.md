---
title: "テンプレート ライブラリの使用方法 | Microsoft Docs"
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
  - "テンプレート ライブラリ"
ms.assetid: 5e80ec6e-a61c-41ce-b34b-9a6252c46265
caps.latest.revision: 10
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 5
---
# テンプレート ライブラリの使用方法
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

テンプレートは多少マクロと同様です。  マクロと同様にコードに、テンプレートを起動すると、\(適切なパラメーター置換\) わずかに配置します。  ただし、パラメーターとして渡す型に基づいて新しいクラスの作成を可能にするには、テンプレートはこれよりもさらにに移動します。  これらの新しいクラスは、テンプレート コードで表される操作を実行するタイプ セーフな方法を実装します。  
  
 ATL のようなテンプレート ライブラリは、従来の C\+\+ クラス ライブラリとソース・コードとしてのみ \(通常はまたは\) のサポート、ソース・コードの実行時\) として指定され、実際の場所または、本質的に階層的ではないことです。  機能に派生するクラスから派生する代わりに、インスタンスを作成するテンプレートからクラスを望んでします。  
  
## 参照  
 [ATL の概要](../Topic/Introduction%20to%20ATL.md)