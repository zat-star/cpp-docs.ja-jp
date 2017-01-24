---
title: "モジュールでの &lt;keyword&gt; キーワードの使い方が正しくありません | Microsoft Docs"
ms.custom: ""
ms.date: "11/17/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "vbc42028"
  - "BC42028"
helpviewer_keywords: 
  - "BC42028"
ms.assetid: a9bc1e9d-ba2c-4a71-b147-0fb66f670316
caps.latest.revision: 12
caps.handback.revision: 12
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# モジュールでの &lt;keyword&gt; キーワードの使い方が正しくありません
モジュールはインスタンスを持たず、継承をサポートしたり、インターフェイスを実装したりしません。 そのため、次のキーワードはモジュールの宣言に適用されません。  
  
-   [MustInherit](../Topic/MustInherit%20\(Visual%20Basic\).md)  
  
-   [NotInheritable](../Topic/NotInheritable%20\(Visual%20Basic\).md)  
  
-   [Overloads](../Topic/Overloads%20\(Visual%20Basic\).md)  
  
-   [Private](../Topic/Private%20\(Visual%20Basic\).md)  
  
-   [Protected](../Topic/Protected%20\(Visual%20Basic\).md)  
  
-   [Shadows](../Topic/Shadows%20\(Visual%20Basic\).md)  
  
-   [Shared](../Topic/Shared%20\(Visual%20Basic\).md)  
  
-   [Static](../Topic/Static%20\(Visual%20Basic\).md)  
  
 [Module Statement](../Topic/Module%20Statement.md) でサポートされるキーワードは、[Public](../Topic/Public%20\(Visual%20Basic\).md) と [Friend](../Topic/Friend%20\(Visual%20Basic\).md) のみです。  
  
 また、[Implements](../Topic/Implements%20Clause%20\(Visual%20Basic\).md) ステートメントまたは [Inherits Statement](../Topic/Inherits%20Statement.md) をモジュールのステートメント ブロックで使用することはできません。  
  
 既定では、このメッセージは警告です。 警告を表示しない方法や、警告をエラーとして扱う方法の詳細については、「[Visual Basic での警告の構成](../Topic/Configuring%20Warnings%20in%20Visual%20Basic.md)」を参照してください。  
  
 **エラー ID:** BC42028  
  
### このエラーを解決するには  
  
-   このプログラミング要素をモジュールにする場合は、その宣言内で `Public` キーワードまたは `Friend` キーワードのみを使用します。 モジュールのアクセス レベルを指定しない場合、既定では `Friend` が使用されます。  
  
-   このプログラミング要素のインスタンスを作成する場合は、クラスとして宣言します。 そうすると、クラス宣言に適用されるキーワードを使用できます。  
  
## 参照  
 [Class Statement](../Topic/Class%20Statement%20\(Visual%20Basic\).md)