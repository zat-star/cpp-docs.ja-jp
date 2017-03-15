---
title: "ODBC とデータベース クラス | Microsoft Docs"
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
  - "データベース クラス [C++], ODBC"
  - "MFC [C++], ODBC および"
  - "ODBC API 関数 [C++]"
  - "ODBC クラス [C++], MFC データベース クラス"
ms.assetid: b166f82d-6f85-4556-aac8-fb851235d22c
caps.latest.revision: 8
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 8
---
# ODBC とデータベース クラス
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

MFC の ODBC データベース クラスには、ODBC API 関数への呼び出しがカプセル化されています。通常、これらの呼び出しは、[CDatabase](../../mfc/reference/cdatabase-class.md) クラスと [CRecordset](../Topic/CRecordset%20Class.md) クラスのメンバー関数で使います。  たとえば、複雑な ODBC 呼び出し、返されたレコードと格納場所の対応付け、エラー処理などがデータベース クラスによって行われます。  この結果、レコードセット オブジェクトを介したレコード操作を簡単なクラス インターフェイスで行うことができます。  
  
> [!NOTE]
>  ODBC データ ソースには、ここで説明するように、MFC ODBC クラス経由でアクセスできます。また、MFC DAO \(Data Access Object\) クラス経由でもアクセスできます。  
  
 データベース クラスには ODBC の機能がカプセル化されていますが、ODBC API 関数に一対一に対応しているわけではありません。  データベース クラスは、Access や Visual Basic などにあるような、より抽象的な機能を提供します。データベース クラスの提供する高度な抽象化は、Access や Visual Basic のデータ アクセス オブジェクトを参考にしています。  詳細については、「[MFC データベースのプログラミング モデル](../../data/what-is-the-mfc-database-programming-model-q.md)」を参照してください。  
  
## 参照  
 [ODBC の基礎](../../data/odbc/odbc-basics.md)