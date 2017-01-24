---
title: "HSE_VERSION_INFO 構造体 | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "HSE_VERSION_INFO"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "HSE_VERSION_INFO 構造体"
ms.assetid: 4837312d-68c8-4d05-9afa-1934d7d49b20
caps.latest.revision: 11
caps.handback.revision: 7
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# HSE_VERSION_INFO 構造体
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

この構造は `CHttpServer::GetExtensionVersion` のメンバー関数の `pVer` パラメーターによってを参照できます。  これは、ISA のバージョン番号と ISA のテキスト説明を指定します。  
  
## 構文  
  
```  
  
      typedef struct _HSE_VERSION_INFO {  
   DWORD dwExtensionVersion;  
   CHAR lpszExtensionDesc[HSE_MAX_EXT_DLL_NAME_LEN];  
} HSE_VERSION_INFO, *LPHSE_VERSION_INFO;  
```  
  
#### パラメーター  
 *dwExtensionVersion*  
 ISA のバージョン番号。  
  
 *lpszExtensionDesc*  
 ISA の説明。  既定の実装では、プレースホルダー テキストを提供します; 独自の説明を提供するためにオーバーライド `CHttpServer::GetExtensionVersion`。  
  
## 必要条件  
 **ヘッダー:** httpext.h  
  
## 参照  
 [構造体、スタイル、コールバック関数とメッセージ マップ](../../mfc/reference/structures-styles-callbacks-and-message-maps.md)