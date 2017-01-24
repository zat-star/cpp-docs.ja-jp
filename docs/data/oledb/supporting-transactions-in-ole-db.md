---
title: "OLE DB でのトランザクションのサポート | Microsoft Docs"
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
  - "データベース [C++], トランザクション"
  - "分散トランザクション [C++]"
  - "入れ子になったトランザクション [C++]"
  - "OLE DB [C++], トランザクション サポート"
  - "OLE DB コンシューマー テンプレート (C++), トランザクション サポート"
  - "トランザクション [C++], OLE DB でのサポート"
ms.assetid: 3d72e583-ad38-42ff-8f11-e2166d60a5a7
caps.latest.revision: 10
caps.handback.revision: 10
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# OLE DB でのトランザクションのサポート
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

[トランザクション](../../data/transactions-mfc-data-access.md)とは、データ ソースに対する複数の更新操作をまとめて "バッチ的に" 連続処理することです。トランザクション内の更新操作は、すべて一度にコミットされるか、\(いずれか 1 つが失敗した場合は\) まったくコミットされずにトランザクション全体がロールバックされるかのどちらかです。  このプロセスにより、データ ソースの結果の整合性が保証されます。  
  
 OLE DB は、次の 3 つのメソッドでトランザクションをサポートします。  
  
-   [\<caps:sentence id\="tgt4" sentenceid\="0699a86bb6d6316bff035b804a56f0aa" class\="tgtSentence"\>ITransactionLocal::StartTransaction\<\/caps:sentence\>](https://msdn.microsoft.com/en-us/library/ms709786.aspx)  
  
-   [\<caps:sentence id\="tgt5" sentenceid\="39299b0fea086b86052550bd165334f7" class\="tgtSentence"\>ITransaction::Commit\<\/caps:sentence\>](https://msdn.microsoft.com/en-us/library/ms713008.aspx)  
  
-   [\<caps:sentence id\="tgt6" sentenceid\="8e992150c28ae247d532408ca7828bfe" class\="tgtSentence"\>ITransaction::Abort\<\/caps:sentence\>](https://msdn.microsoft.com/en-us/library/ms709833.aspx)  
  
## セッションとトランザクションの関係  
 単一のデータ ソース オブジェクトは、1 つ以上のセッション オブジェクトを作成できます。各オブジェクトは、特定の時点でトランザクションのスコープの内部または外部にあります。  
  
 セッションがトランザクションに入れられていない場合、そのセッションでデータ ストアに対して行われたすべての作業は、各メソッドの呼び出し時にすぐにコミットされます。これは、自動コミット モードまたは暗黙モードと呼ばれることもあります。  
  
 セッションがトランザクションに入れられた場合、そのセッションでデータ ストアに対して行われたすべての作業は、そのトランザクションの一部であり、1 つの単位としてコミットまたは中止されます。これは、手動コミット モードと呼ばれることもあります。  
  
 トランザクションのサポートはプロバイダーに固有です。  使用しているプロバイダーがトランザクションをサポートしている場合は、**ITransaction** と **ITransactionLocal** をサポートするセッション オブジェクトを単純な \(入れ子になっていない\) トランザクションに入れることができます。  OLE DB テンプレート クラス [CSession](../../data/oledb/csession-class.md) は、これらのインターフェイスをサポートしています。この方法は、Visual C\+\+ でトランザクション サポートを実装する方法として推奨されます。  
  
## トランザクションの開始と終了  
 コンシューマーの行セット オブジェクトで、`StartTransaction`、**Commit**、**Abort** の各メソッドを呼び出します。  
  
 **ITransactionLocal::StartTransaction** を呼び出すと、新規のローカル トランザクションが開始します。  トランザクションを開始した場合、後続の操作で要求されるすべての変更は、実際には、トランザクションをコミットするまでデータ ストアに適用されません。  
  
 **ITransaction::Commit** または **ITransaction::Abort** を呼び出すと、トランザクションが終了します。  **Commit** を呼び出すと、トランザクションのスコープ内のすべての変更がデータ ストアに適用されます。  **Abort** を呼び出すと、トランザクションのスコープ内のすべての変更がキャンセルされ、データ ストアはトランザクション開始前の状態のままになります。  
  
## 入れ子になったトランザクション  
 [入れ子になったトランザクション](https://msdn.microsoft.com/en-us/library/ms716985.aspx)は、アクティブなトランザクションが既にセッションに存在するときに、新規のローカル トランザクションを開始した場合に発生します。  新規のトランザクションは、現在のトランザクションの下に入れ子になったトランザクションとして開始します。  入れ子になったトランザクションをプロバイダーがサポートしていない場合は、アクティブなトランザクションが既にセッションにあるときに `StartTransaction` を呼び出すと、**XACT\_E\_XTIONEXISTS** が返されます。  
  
## 分散トランザクション  
 分散トランザクションは、分散されたデータ \(複数のネットワーク コンピューター システム上のデータ\) を更新するトランザクションです。  分散システムでのトランザクションをサポートする場合は、OLE DB トランザクション サポートではなく、.NET Framework を使用する必要があります。  
  
## 参照  
 [アクセサーの使用](../../data/oledb/using-accessors.md)