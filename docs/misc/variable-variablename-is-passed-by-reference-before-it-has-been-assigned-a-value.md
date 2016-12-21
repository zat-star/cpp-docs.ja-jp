---
title: "変数 &#39;&lt;variablename&gt;&#39; は、値が割り当てられる前に参照によって渡されています | Microsoft Docs"
ms.custom: ""
ms.date: "11/24/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "vbc42030"
  - "BC42030"
helpviewer_keywords: 
  - "BC42030"
ms.assetid: 8f1aae99-f032-4fdf-b6dc-3360cc5b94de
caps.latest.revision: 11
caps.handback.revision: 11
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# 変数 &#39;&lt;variablename&gt;&#39; は、値が割り当てられる前に参照によって渡されています
変数 '\<variablename\>' は、値が割り当てられる前に参照によって渡されています。 結果として、実行時に null 参照の例外が発生する可能性があります。  
  
 変数に何らかの値が割り当てられる前に、プロシージャ呼び出しが `ByRef` パラメーターへの引数として変数を渡しています。  
  
 変数に値が割り当てられていない場合、変数はそのデータ型の既定値を保持します。 参照データ型の場合、その既定値は [Nothing](../Topic/Nothing%20\(Visual%20Basic\).md) です。 値が `Nothing` である参照変数を読み取ると、状況によって <xref:System.NullReferenceException> が発生する可能性があります。  
  
 プロシージャ `ByRef` に引数を渡すと、引数の基になる変数がプロシージャによって変更される可能があります。  
  
 既定では、このメッセージは警告です。 警告を非表示にする方法や、警告をエラーとして扱う方法について詳しくは、「[Visual Basic での警告の構成](../Topic/Configuring%20Warnings%20in%20Visual%20Basic.md)」をご覧ください。  
  
 **エラー ID:** BC42030  
  
### このエラーを解決するには  
  
-   プロシージャによって `ByRef` 引数で変数に値を割り当てるつもりであり、既に変数に値が保持されているかどうかは問題でない場合、処置は必要ありません。  
  
-   プロシージャのロジックが値を割り当てる前の引数を読み取り、かつ変数が値の型の場合は、変数が既定値を保持するかどうかにプロシージャのロジックが左右されないようにします。  
  
-   プロシージャのロジックが値を割り当てる前の引数を読み取り、かつ変数が参照型である場合は、プロシージャのロジックが値 `Nothing` を処理できるようにします。 たとえば、[Try...Catch...Finally Statement](../Topic/Try...Catch...Finally%20Statement%20\(Visual%20Basic\).md) を使用して <xref:System.NullReferenceException> をキャッチできる場合があります。  
  
## 参照  
 [Dim Statement](../Topic/Dim%20Statement%20\(Visual%20Basic\).md)   
 [Value Types and Reference Types](../Topic/Value%20Types%20and%20Reference%20Types.md)   
 [Passing Arguments by Value and by Reference](../Topic/Passing%20Arguments%20by%20Value%20and%20by%20Reference%20\(Visual%20Basic\).md)   
 [ByRef](../Topic/ByRef%20\(Visual%20Basic\).md)   
 [変数宣言](../Topic/Variable%20Declaration%20in%20Visual%20Basic.md)   
 [変数のトラブルシューティング](../Topic/Troubleshooting%20Variables%20in%20Visual%20Basic.md)