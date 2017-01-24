---
title: "progress_reporter クラス | Microsoft Docs"
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
  - "ppltasks/concurrency::progress_reporter"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "progress_reporter クラス"
ms.assetid: b836efab-2d05-4649-b6fa-d15236f1f813
caps.latest.revision: 11
caps.handback.revision: 5
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# progress_reporter クラス
[!INCLUDE[vs2017banner](../../../assembler/inline/includes/vs2017banner.md)]

progress reporter クラスは、特定の型の進行状況の通知をレポートできます。  各 progress\_reporter オブジェクトが、特定の非同期アクションまたは操作にバインドされます。  
  
## 構文  
  
```  
template<  
   typename _ProgressType  
>  
class progress_reporter;  
```  
  
#### パラメーター  
 `_ProgressType`  
 progress\_reporter クラスによって報告される進行状況の各通知のペイロードの種類。  
  
## メンバー  
  
### パブリック コンストラクター  
  
|名前|説明|  
|--------|--------|  
|[progress\_reporter::progress\_reporter コンストラクター](../Topic/progress_reporter::progress_reporter%20Constructor.md)||  
  
### パブリック メソッド  
  
|名前|説明|  
|--------|--------|  
|[progress\_reporter::report メソッド](../Topic/progress_reporter::report%20Method.md)|progress reporter クラスのバインド先となる非同期アクションまたは非同期操作に、進行状況レポートを送信します。|  
  
## 解説  
 このクラスは、Windows ストア アプリでのみ使用できます。  
  
## 継承階層  
 `progress_reporter`  
  
## 必要条件  
 **ヘッダー:** ppltasks.h  
  
 **名前空間:** concurrency  
  
## 参照  
 [concurrency 名前空間](../../../parallel/concrt/reference/concurrency-namespace.md)   
 [create\_async 関数](../Topic/create_async%20Function.md)