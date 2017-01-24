---
title: "lock クラス | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "msclr::lock"
  - "msclr.lock"
  - "lock"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "ロック (クラスを)"
ms.assetid: 5123edd9-6aed-497d-9a0b-f4b6d6c0d666
caps.latest.revision: 10
caps.handback.revision: 10
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# lock クラス
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

このクラスは、複数のスレッドからオブジェクトへのアクセスを同期するためのロックの取得を自動化します。作成された場合に、ロックを取得すると破棄されたロックを解除します。  
  
## 構文  
  
```  
ref class lock;  
```  
  
## 解説  
 `lock` は CLR オブジェクトに対してのみ指定でき、CLR コードでのみ使用できます。  
  
 内部的には、ロック クラスは、アクセスを同期するために <xref:System.Threading.Monitor> を使用します。  同期の詳細については、このトピックを参照してください。  
  
## 必要条件  
 **ヘッダー ファイル** \<msclr\\lock.h\>  
  
 **名前空間** の msclr  
  
## 参照  
 [lock](../dotnet/lock.md)   
 [lock のメンバー](../dotnet/lock-members.md)