---
title: "DEFINE_COMMAND | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "DEFINE_COMMAND"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "DEFINE_COMMAND マクロ"
ms.assetid: 9d724968-e242-413c-9a13-e7175fccf9b1
caps.latest.revision: 7
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 7
---
# DEFINE_COMMAND
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

[CCommand](../../data/oledb/ccommand-class.md) クラスを使用すると、行セットを作成するために使用するコマンドを指定します。  指定したアプリケーションの種類に一致する文字列型だけを受け取る \(ANSI 文字または Unicode\)。  
  
> [!NOTE]
>  `DEFINE_COMMAND`の代わりに [DEFINE\_COMMAND\_EX](../../data/oledb/define-command-ex.md) を使用することをお勧めします。  
  
## 構文  
  
```  
  
DEFINE_COMMAND(  
x  
,   
szCommand  
 )  
  
```  
  
#### パラメーター  
 *x*  
 \[\]ユーザー レコード \(コマンド\) クラスの名前。  
  
 `szCommand`  
 \[\]ときに [CCommand](../../data/oledb/ccommand-class.md)を使用して行セットを作成するために使用するコマンド文字列。  
  
## 解説  
 指定したコマンド文字列には、既定として [CCommand::Open](../../data/oledb/ccommand-open.md) のメソッドでコマンド テキストを指定しない場合に使用されます。  
  
 このマクロは、Unicode としてアプリケーションをビルドする場合は、ANSI としてアプリケーションをビルドする場合は、Unicode 文字列を受け取ります。ANSI 文字列。  前の Unicode 文字列を受け取るため、`DEFINE_COMMAND`の代わりに Unicode を ANSI またはアプリケーションの種類に関係なく [DEFINE\_COMMAND\_EX](../../data/oledb/define-command-ex.md) を使用することをお勧めします。  
  
## 使用例  
 [BOOKMARK\_ENTRY](../../data/oledb/bookmark-entry.md)を参照してください。  
  
## 必要条件  
 **ヘッダー:** atldbcli.h  
  
## 参照  
 [OLE DB コンシューマー テンプレート用マクロおよびグローバル関数](../Topic/Macros%20and%20Global%20Functions%20for%20OLE%20DB%20Consumer%20Templates.md)