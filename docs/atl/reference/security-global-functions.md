---
title: "セキュリティに関するグローバル関数 | Microsoft Docs"
ms.custom: ""
ms.date: "12/16/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "ACL オブジェクトのグローバル関数"
  - "セキュリティ ID [C++]"
  - "SID [C++], 変更 (SID オブジェクトを)"
ms.assetid: 6a584bfe-16b7-47f4-8439-9c789c41567a
caps.latest.revision: 20
caps.handback.revision: 8
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# セキュリティに関するグローバル関数
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

これらの関数は、変更の SID と ACL のオブジェクトをサポートします。  
  
> [!IMPORTANT]
>  次の表に示す関数は [!INCLUDE[wrt](../../atl/reference/includes/wrt_md.md)]で実行されるアプリケーションで使用することはできません。  
  
|||  
|-|-|  
|[AtlGetDacl](../Topic/AtlGetDacl.md)|指定されたオブジェクトの随意アクセス制御リスト \(DACL: Discretionary Access Control List\) の情報を取得します。|  
|[AtlSetDacl](../Topic/AtlSetDacl.md)|指定されたオブジェクトの随意アクセス制御リスト \(DACL: Discretionary Access Control List\) の情報を設定します。|  
|[AtlGetGroupSid](../Topic/AtlGetGroupSid.md)|オブジェクトのグループ セキュリティ識別子 \(SID: Security Identifier\) を取得します。|  
|[AtlSetGroupSid](../Topic/AtlSetGroupSid.md)|オブジェクトのグループ セキュリティ識別子 \(SID: Security Identifier\) を設定します。|  
|[AtlGetOwnerSid](../Topic/AtlGetOwnerSid.md)|オブジェクトの所有者セキュリティ識別子 \(SID: Security Identifier\) を取得します。|  
|[AtlSetOwnerSid](../Topic/AtlSetOwnerSid.md)|オブジェクトの所有者セキュリティ識別子 \(SID: Security Identifier\) を設定します。|  
|[AtlGetSacl](../Topic/AtlGetSacl.md)|指定されたオブジェクトのシステム アクセス制御リスト \(SACL: System Access Control List\) の情報を取得します。|  
|[AtlSetSacl](../Topic/AtlSetSacl.md)|指定されたオブジェクトのシステム アクセス制御リスト \(SACL: System Access Control List\) の情報を設定します。|  
|[AtlGetSecurityDescriptor](../Topic/AtlGetSecurityDescriptor.md)|指定されたオブジェクトのセキュリティ記述子を取得します。|  
  
## 参照  
 [関数](../../atl/reference/atl-functions.md)