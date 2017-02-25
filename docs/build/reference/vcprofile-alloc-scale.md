---
title: "VCPROFILE_ALLOC_SCALE | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "VCPROFILE_ALLOC_SCALE"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "VCPROFILE_ALLOC_SCALE 環境変数"
ms.assetid: 5cb5ce27-f9b8-489b-b46c-d6e9bcab2d34
caps.latest.revision: 4
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 4
---
# VCPROFILE_ALLOC_SCALE
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

プロファイル データを格納するために割り当てるメモリ容量を変更します。  
  
## 構文  
  
```  
VCPROFILE_ALLOC_SCALE=scale_value  
```  
  
#### パラメーター  
 `scale_value`  
 テスト シナリオを実行するために必要なメモリ容量のスケール値。既定値は 1 です。  
  
## 解説  
 まれに、テスト シナリオの実行中に、プロファイル データを収集するために使用できるメモリが不足する場合があります。このような場合は、`VCPROFILE_ALLOC_SCALE` を使用してメモリ容量を増やすことができます。  
  
 テストの実行中にメモリ不足を示すエラー メッセージが表示された場合は、メモリ不足エラーなしでテストが完了するまで、`VCPROFILE_ALLOC_SCALE` により大きな値を割り当てます。  
  
## 使用例  
  
```  
set VCPROFILE_ALLOC_SCALE=2  
```  
  
## 参照  
 [ガイド付き最適化のプロファイルの環境変数](../../build/reference/environment-variables-for-profile-guided-optimizations.md)