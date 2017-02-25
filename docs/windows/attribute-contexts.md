---
title: "Attribute Contexts | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "attributes [C++], contexts"
ms.assetid: 3086351f-77a8-4048-99e9-3b6b041b9437
caps.latest.revision: 8
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 8
---
# Attribute Contexts
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

C\+\+ 属性は 4 種類の基本的なフィールドを使用して記述できます : ターゲットは反復可能でない \(\) **複数回の適用**  で他の属性 \(\) **必要な属性**  必須の表示および他の属性 \(\) **無効な属性**  の互換性 \(\) **に適用されます。** 適用できます。  これらのフィールドは属性に関するトピックに添付の表に示します。  これらの各フィールドについて次に説明します。  
  
## 対象  
 このフィールドは指定された属性の使用可能なターゲットであるC\+\+ 言語要素について説明します。  たとえば属性を  **に適用されます。** のフィールドに 「クラス」を指定する場合属性を有効な C\+\+ クラスにのみ適用できないことを示します。  この属性がクラスのメンバー関数に適用する場合構文エラーが発生します。  
  
 詳細については[使用法別の属性](../windows/attributes-by-usage.md) を参照してください。  
  
## 複数回の適用  
 このフィールドは属性が同じターゲットに繰り返し適用できるかどうかを示します。  属性のほとんどは反復できません。  
  
## 必要な属性  
 このフィールド リスト正しく機能するために指定された属性に \(つまり同じターゲットに適用\) する必要がある他の属性。  この属性をフィールドのエントリが一般的です。  
  
## 無効な属性  
 このフィールド リスト\] で指定した属性に対応しない別の属性。  この属性をフィールドのエントリが一般的です。  
  
## 参照  
 [C\+\+ Attributes Reference](../windows/cpp-attributes-reference.md)