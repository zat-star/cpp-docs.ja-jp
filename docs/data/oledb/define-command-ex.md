---
title: "DEFINE_COMMAND_EX | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "DEFINE_COMMAND_EX"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "DEFINE_COMMAND_EX マクロ"
ms.assetid: d3e2ef20-1455-46d2-8499-8ab84bbb90a4
caps.latest.revision: 7
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 7
---
# DEFINE_COMMAND_EX
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

[CCommand](../../data/oledb/ccommand-class.md) クラスを使用すると、行セットを作成するために使用するコマンドを指定します。  Unicode サポートおよび ANSI アプリケーション。  
  
## 構文  
  
```  
  
DEFINE_COMMAND_EX(  
x  
,   
wszCommand  
 )  
  
```  
  
#### パラメーター  
 *x*  
 \[\]ユーザー レコード \(コマンド\) クラスの名前。  
  
 `wszCommand`  
 \[\]ときに [CCommand](../../data/oledb/ccommand-class.md)を使用して行セットを作成するために使用するコマンド文字列。  
  
## 解説  
 指定したコマンド文字列には、既定として [CCommand::Open](../../data/oledb/ccommand-open.md) のメソッドでコマンド テキストを指定しない場合に使用されます。  
  
 このマクロは、アプリケーションの種類に関係なく、Unicode 文字列を使用できます。  このマクロは [DEFINE\_COMMAND](../../data/oledb/define-command.md) に Unicode または ANSI アプリケーションをサポートするため、お勧めします。  
  
## 使用例  
 [BOOKMARK\_ENTRY](../../data/oledb/bookmark-entry.md)を参照してください。  
  
## 必要条件  
 **ヘッダー:** atldbcli.h  
  
## 参照  
 [OLE DB コンシューマー テンプレート用マクロおよびグローバル関数](../Topic/Macros%20and%20Global%20Functions%20for%20OLE%20DB%20Consumer%20Templates.md)