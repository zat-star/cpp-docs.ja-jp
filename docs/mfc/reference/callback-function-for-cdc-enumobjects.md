---
title: "CDC::EnumObjects 用コールバック関数 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "Callback Function for CDC::EnumObjects"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "コールバック関数, CDC::EnumObjects の"
ms.assetid: 380088b1-88a5-4fb4-bbb5-dd9e8386572b
caps.latest.revision: 10
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 11
---
# CDC::EnumObjects 用コールバック関数
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

*ObjectFunc の* 名前はアプリケーションに用意された関数名のプレースホルダーです。  
  
## 構文  
  
```  
  
      int CALLBACK EXPORT ObjectFunc(   
   LPSTR lpszLogObject,   
   LPSTR* lpData    
);  
```  
  
#### パラメーター  
 *lpszLogObject*  
 オブジェクトの論理属性に関する情報を含む [LOGPEN](../../mfc/reference/logpen-structure.md) または [LOGBRUSH](../Topic/LOGBRUSH%20Structure.md) のデータ構造体へのポインター。  
  
 `lpData`  
 `EnumObjects` に渡されるアプリケーションが指定したデータをポイントして機能します。  
  
## 戻り値  
 コールバック関数は `int`を返します。  この戻り値は、ユーザーが定義したものです。  コールバック関数が 0 を返す場合、`EnumObjects` は列挙体をすぐに停止します。  
  
## 解説  
 実際の名前は、エクスポートする必要があります。  
  
## 必要条件  
 **ヘッダー:** afxwin.h  
  
## 参照  
 [構造体、スタイル、コールバック関数とメッセージ マップ](../../mfc/reference/structures-styles-callbacks-and-message-maps.md)   
 [CDC::EnumObjects](../Topic/CDC::EnumObjects.md)