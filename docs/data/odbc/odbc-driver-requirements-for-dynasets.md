---
title: "ダイナセットを使う場合の ODBC ドライバーの必要条件 | Microsoft Docs"
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
  - "ドライバー, ダイナセットの"
  - "ドライバー, ODBC"
  - "ダイナセット"
  - "ODBC ドライバー, ダイナセット"
  - "ODBC レコードセット, ダイナセット"
  - "レコードセット, ダイナセット"
ms.assetid: 585cc67b-4d92-404b-9903-d769cd17badc
caps.latest.revision: 7
caps.handback.revision: 7
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# ダイナセットを使う場合の ODBC ドライバーの必要条件
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

MFC の ODBC データベース クラスにおけるダイナセットは、動的プロパティを持つレコードセットであり、なんらかの方法でデータ ソースと同期しています。  MFC のダイナセット \(前方スクロール専用レコードセット以外\) は、レベル 2 API 準拠の ODBC ドライバーが必要です。  [データ ソース](../../data/odbc/data-source-odbc.md)のドライバーがレベル 1 API 準拠の場合は、更新可能スナップショット、上書き禁止スナップショット、および前方スクロール専用レコードセットは使えますが、ダイナセットは使えません。  ただし、レベル 1 ドライバーでも、拡張フェッチとキーセット ドリブン カーソルをサポートしている場合は、ダイナセットを使えます。  
  
 ODBC の用語では、ダイナセットとスナップショットのことをカーソルと呼びます。  カーソルは、レコードセット内の位置を追跡するためのしくみです。  ダイナセット用のドライバーの条件の詳細については、「[ダイナセット](../../data/odbc/dynaset.md)」を参照してください。  カーソルの詳細については、MSDN ドキュメントの [ODBC \(Open Database Connectivity\)](https://msdn.microsoft.com/en-us/library/ms710252.aspx) SDK を参照してください。  
  
> [!NOTE]
>  更新可能レコードセットの場合は、使用する ODBC ドライバーが、位置指定更新ステートメントまたは **::SQLSetPos** ODBC API 関数をサポートする必要があります。  両方がサポートされている場合、MFC では、効率を考慮して **::SQLSetPos** を使います。  スナップショットの場合は、カーソル ライブラリを使えます。カーソル ライブラリには、更新可能なスナップショットに必要なサポート \(静止カーソルと位置指定付き更新文\) があります。  
  
## 参照  
 [ODBC の基礎](../../data/odbc/odbc-basics.md)