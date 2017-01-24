---
title: "CDC::GrayString 用コールバック関数 | Microsoft Docs"
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
  - "Callback Function for CDC::GrayString"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "コールバック関数, CDC::GrayString の"
ms.assetid: 5217e183-df48-426b-931b-6245022ca36f
caps.latest.revision: 11
caps.handback.revision: 7
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# CDC::GrayString 用コールバック関数
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

*OutputFunc は* アプリケーションに用意されたコールバック関数名のプレースホルダーです。  
  
## 構文  
  
```  
  
      BOOL CALLBACK EXPORT OutputFunc(   
   HDC hDC,   
   LPARAM lpData,   
   int nCount    
);  
```  
  
#### パラメーター  
 `hDC`  
 `GrayString`に `nWidth` と `nHeight` で指定された少なくとも幅と高さのビットマップでメモリ デバイス コンテキストを指定します。  
  
 `lpData`  
 描画される文字列へのポインター。  
  
 `nCount`  
 文字数を出力するように指定します。  
  
## 戻り値  
 コールバック関数は、成功を示す **TRUE** ;である必要があります。それ以外の場合は **FALSE**です。  
  
## 解説  
 コールバック関数 \(*OutputFunc*\) は、座標 \(0,0\) に対してではなく、イメージを描画必要があります \(*x*が *y\)* 。  
  
## 必要条件  
 **ヘッダー:** afxwin.h  
  
## 参照  
 [構造体、スタイル、コールバック関数とメッセージ マップ](../../mfc/reference/structures-styles-callbacks-and-message-maps.md)   
 [CDC::GrayString](../Topic/CDC::GrayString.md)