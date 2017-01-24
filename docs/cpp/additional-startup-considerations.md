---
title: "起動に関するその他の考慮事項 | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "main より前の初期化"
  - "プログラムの起動 [C++]"
  - "スタートアップ コード"
ms.assetid: 0e942aa6-8342-447c-b068-8980ed7622bd
caps.latest.revision: 6
caps.handback.revision: 6
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# 起動に関するその他の考慮事項
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

C\+\+ では、オブジェクトの構築時と破棄時にユーザー コードを実行することができます。  したがって、どの初期化が **main** に入る前に発生し、どのデストラクターが **main** から出た後に呼び出されるかを把握することが重要です  \(オブジェクトの構築と破棄に関する詳細については、「[コンストラクター](../cpp/constructors-cpp.md)」と「[デストラクター](../cpp/destructors-cpp.md)」を参照してください\)。  
  
 次の初期化は、**main** に入る前に発生します。  
  
-   静的データのゼロへの既定の初期化。  明示的な初期化子のないすべての静的データは、ランタイム初期化も含めて、他のコードを実行する前にゼロに設定されます。  その場合でも、静的データ メンバーは明示的に定義する必要があります。  
  
-   翻訳単位でのグローバルな静的オブジェクトの初期化。  これは、**main** に入る前、またはオブジェクトの翻訳単位でいずれかの関数またはオブジェクトを最初に使用する前に発生することがあります。  
  
 **Microsoft 固有の仕様 →**  
  
 Microsoft C\+\+ では、グローバルな静的オブジェクトは **main** に入る前に初期化されます。  
  
 **END Microsoft 固有の仕様**  
  
 相互依存しているのに翻訳単位が異なるグローバルな静的オブジェクトは、正しくない動作の原因になる可能性があります。  
  
## 参照  
 [起動と終了](../cpp/startup-and-termination-cpp.md)