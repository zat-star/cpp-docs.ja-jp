---
title: "致命的なエラー C1509 | Microsoft Docs"
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
  - "C1509"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C1509"
ms.assetid: 40dd100d-c6ba-451c-bd26-2c99ec1c36d6
caps.latest.revision: 7
caps.handback.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# 致命的なエラー C1509
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

コンパイラの制限: 関数が多すぎます。例外ハンドラーの状態は「機能"。関数を簡略化します。  
  
 例外ハンドラーの状態の数の内部制限 \(32,768 個\) を超えています。  
  
 このエラーの最も一般的な原因は、ユーザー定義のクラスの変数と算術演算子を使用した複合式が関数に含まれていることです。  
  
### 次のような解決策を使用して問題を解決するには  
  
1.  共通な部分式をテンポラリ変数に代入して式を単純にします。  
  
2.  関数を小さな複数の関数に分割します。