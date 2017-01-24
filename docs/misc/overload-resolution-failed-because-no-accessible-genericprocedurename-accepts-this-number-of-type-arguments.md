---
title: "この型引数の数を受け付けるアクセス可能な &#39;&lt;genericprocedurename&gt;&#39; がないため、オーバーロードの解決に失敗しました | Microsoft Docs"
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
  - "bc32087"
  - "vbc32087"
helpviewer_keywords: 
  - "BC32087"
ms.assetid: a3eaafd3-80f6-4b7d-9b75-47b043fe17b5
caps.latest.revision: 11
caps.handback.revision: 11
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# この型引数の数を受け付けるアクセス可能な &#39;&lt;genericprocedurename&gt;&#39; がないため、オーバーロードの解決に失敗しました
コンパイラが適切な数の型パラメーターを持つオーバーロードされたバージョンにアクセスできないため、オーバーロードされたジェネリック プロシージャへの呼び出しを解決できません。  
  
 ジェネリック プロシージャを呼び出す場合は、型パラメーターごとに 1 つの型引数を指定する必要があります。 または、型引数を指定せずに、コンパイラが*型の推定*を行うようにすることもできます。 詳細については、「[Generic Procedures in Visual Basic](../Topic/Generic%20Procedures%20in%20Visual%20Basic.md)」の「型の推定」を参照してください。  
  
 **エラー ID:** BC32087  
  
### このエラーを解決するには  
  
1.  呼び出すバージョンを呼び出しコードでアクセスできるようにします。 「[Access Levels in Visual Basic](../Topic/Access%20Levels%20in%20Visual%20Basic.md)」を参照してください。  
  
2.  呼び出しコードに対して型引数を追加または削除して、型引数リストが呼び出すバージョンの型パラメーター リストと一致するようにします。  
  
     または  
  
     呼び出しコードからすべての型引数を削除して、コンパイラが型の推定を行うようにします。 競合またはあいまいさがある場合は、型の推定が失敗する可能性があることに注意してください。  
  
## 参照  
 [Overloaded Properties and Methods](../Topic/Overloaded%20Properties%20and%20Methods%20\(Visual%20Basic\).md)   
 [Overload Resolution](../Topic/Overload%20Resolution%20\(Visual%20Basic\).md)   
 [Visual Basic におけるジェネリック型](../Topic/Generic%20Types%20in%20Visual%20Basic%20\(Visual%20Basic\).md)   
 [Type List](../Topic/Type%20List%20\(Visual%20Basic\).md)